 I network costituiscono la base di quasi tutti i sistemi reali: biologici, tecnologici e sociali. L'analisi delle comunità (_Community Detection_) serve a svelare l'organizzazione interna di queste reti, identificando gruppi di nodi densamente connessi tra loro.
## Esempi Reali di Struttura a Comunità

### Il Caso del Belgio: Segregazione Linguistica
Il Belgio è spesso citato come una società biculturale modello (59% Fiamminghi, 40% Valloni). Tuttavia, l'analisi delle reti rivela una forte segregazione.
Uno studio sulle chiamate telefoniche mobili ha mostrato che la società è divisa in due cluster giganti che comunicano quasi esclusivamente al proprio interno, basati sulla lingua.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=3&rect=69,3,291,221|9, p.3|center|350]]

> [!info] Analisi del Grafo
> * **Cluster:** Due grandi gruppi (Rosso = Francofoni, Verde = Fiamminghi).
> * **Connessioni:** Forti all'interno dei gruppi, deboli tra i due gruppi.
> * **Bruxelles:** L'area centrale mista funge da "ponte" culturale, mostrando una maggiore integrazione.

### Zachary's Karate Club
Questo è il dataset di riferimento per la scienza delle reti. Rappresenta le relazioni di 34 membri di un club di karate che, a seguito di un conflitto interno, si è diviso in due fazioni.
Gli algoritmi di community detection riescono a prevedere la divisione basandosi solo sulla topologia delle amicizie, senza conoscere i dettagli del conflitto.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=6&rect=81,106,272,222|9, p.6|center|350]]
## Basi e Definizioni di Comunità

Non esiste una definizione unica di comunità, ma diverse interpretazioni che variano per rigidità.
### Clique (Sottografo Completo)
È la definizione più rigida. Una comunità è vista come un gruppo dove **tutti conoscono tutti**.
In termini di grafi, è un **sottografo completo**.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=10&rect=85,32,241,191|9, p.10|center|350]]
> [!warning] Limiti
> Richiedere che una comunità sia una clique è troppo restrittivo. Nelle reti reali i triangoli sono frequenti, ma le clique grandi sono rare.
### Strong Community (Comunità Forte)
Definizione basata sui singoli nodi. Un sottografo connesso è una comunità forte se **ogni singolo nodo** ha più connessioni interne che esterne.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=11&rect=109,23,251,178|9, p.11|center|350]]
$$k_{in}(i) > k_{out}(i) \quad \forall i \in C$$

Dove:
* $k_{in}$: grado interno (verso nodi dello stesso gruppo).
* $k_{out}$: grado esterno (verso nodi di altri gruppi).
### Weak Community (Comunità Debole)
Definizione basata sul gruppo. Un sottografo è una comunità debole se la **somma totale** dei gradi interni supera la somma dei gradi esterni.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=12&rect=109,33,242,199|9, p.12|center|350]]

$$\sum_{i \in C} k_{in}(i) > \sum_{i \in C} k_{out}(i)$$

Non serve che ogni nodo soddisfi la condizione individualmente, basta che il gruppo nel complesso sia più coeso internamente.

# Numero di Comunità

Una delle domande fondamentali nell'analisi delle reti è: **in quanti modi i nodi di una rete possono essere raggruppati in comunità?**

Una risposta approssimativa viene fornita dal problema più semplice di individuazione delle comunità: la **Bisezione del Grafo** (*Graph Bisection*).

## Il Problema della Bisezione del Grafo

L'idea consiste nel dividere la rete in **due sottografi non sovrapposti**.
L'obiettivo è minimizzare la **Cut Size**, ovvero il numero di collegamenti che uniscono i nodi appartenenti ai due gruppi diversi.

Per risolvere esattamente questo problema, bisognerebbe teoricamente ispezionare **tutte le possibili divisioni** in due gruppi e scegliere quella con la *cut size* minore.

### Costo Computazionale

Il costo computazionale di questo approccio è dato dal numero di modi distinti in cui possiamo partizionare una rete di $N$ nodi in due gruppi di dimensione $N_1$ e $N_2$.
La formula combinatoria è:

$$\frac{N!}{N_{1}!N_{2}!}$$

> [!dimostrazione]- Dimostrazione
> Tutte  i possibili partizionamenti di $N$ nodi in $N_{1}$ elementi sono:
> $$\binom{N}{N_{1}}=\frac{N!}{(N-N_{1})!N_{1}!}$$
> Ma $(N-N_{1})!$ è proprio $N_{2}$ per cui sostituendo sopra sarà: 
> $$\frac{N!}{N_{1}!N_{2}!}$$ 

Questo approccio diventa rapidamente impraticabile al crescere del numero di nodi, come mostrato nell'esempio seguente.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=15&rect=98,7,266,230|9, p.15|center|250]]

> [!example] Esempio: L'Esplosione Combinatoria
> Confrontiamo due casi per capire quanto velocemente cresce la complessità:
>
> * **Caso Semplice ($N=10$):**
>     Bisecare una rete di 10 nodi in due gruppi da 5 ($N_1=N_2=5$).
>     Dobbiamo controllare **252** possibili bisezioni. *Fattibile.*
>
> * **Caso Medio ($N=100$):**
>     Bisecare una rete di 100 nodi in due gruppi da 50 ($N_1=N_2=50$).
>     Dobbiamo controllare **$10^{29}$** possibili bisezioni.
>     *Questo numero è astronomico e rende impossibile la risoluzione con forza bruta.*

# Clustering Gerarchico

Il clustering gerarchico è una tecnica utilizzata per svelare la struttura delle comunità in grandi reti in tempo polinomiale.

Il punto di partenza è una **matrice di similarità**, i cui elementi $X_{ij}$ esprimono la distanza tra il nodo $i$ e il nodo $j$.

Esistono due approcci principali per costruire la gerarchia:
1.  **Algoritmi Agglomerativi (Bottom-up):** Uniscono i nodi con alta similarità nella stessa comunità.
2.  **Algoritmi Divisivi (Top-down):** Isolano le comunità rimuovendo i collegamenti a bassa similarità che tendono a connettere comunità diverse.

Entrambe le procedure producono un **Dendrogramma**, un albero gerarchico che rappresenta la struttura dei raggruppamenti a vari livelli.
## Procedure Agglomerative: L'algoritmo di Ravasz

L'algoritmo di Ravasz si basa sul principio che i nodi appartenenti alla stessa comunità dovrebbero avere un'alta similarità, mentre nodi di comunità diverse dovrebbero averne una bassa.

La similarità viene definita quantitativamente tramite la **Topological Overlap Matrix (TOM)**.
L'intuizione è che nodi collegati tra loro e che condividono gli stessi vicini appartengono probabilmente alla stessa comunità.

La formula per calcolare l'elemento $x_{ij}^0$ della matrice è:

$$x_{ij}^{0}=\frac{J(i,j)}{\min(k_{i},k_{j})+1-\Theta(A_{ij})}$$

Dove:
* $J(i,j)$: numero di vicini comuni tra i nodi $i$ e $j$.
* $\min(k_i, k_j)$: il minore tra i gradi dei due nodi.
* $\Theta(x)$: Funzione gradino di Heaviside (vale 0 se $x \le 0$, 1 se $x > 0$).

> [!info] Interpretazione
> * **$x_{ij}^0 = 1$:** Se i nodi $i$ e $j$ sono collegati e condividono *tutti* i vicini (massima sovrapposizione).
> * **$x_{ij}^0 = 0$:** Se i nodi non hanno vicini in comune.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=19&rect=128,4,240,105|9, p.19|center|350]]

### Procedura dell'algoritmo

1.  **Inizializzazione:** Assegna ogni nodo a una comunità propria e si calcola $x_{ij}$ per tutte le coppie.
2.  **Unione:** Trova la coppia di comunità (o nodi) con la **similarità più alta** e uniscile in una singola comunità.
3.  **Ricalcolo:** Calcola la similarità tra la nuova comunità e tutte le altre. L'algoritmo di Ravasz usa la *average cluster similarity* (media delle $x_{ij}$ tra tutte le coppie di nodi dei due gruppi).
4.  **Iterazione:** Ripeti i passi 2 e 3 finché tutti i nodi non formano un'unica comunità globale.

Il risultato finale è visualizzabile tramite la matrice di similarità gerarchica e il relativo dendrogramma.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=22&rect=13,28,353,217|9, p.22]]

> [!caution] Interpretazione Visuale
> Il grafico combina due viste per identificare le comunità:
>
> **1. Il Dendrogramma (in alto)**
> Rappresenta la storia delle fusioni tra gruppi.
> * **Asse Y (Altezza):** Rappresenta la distanza (inversa della similarità). Più in basso avviene l'unione, più i nodi sono simili.
> * **Taglio:** La linea tratteggiata arancione indica la soglia scelta per definire le comunità finali. Tutto ciò che sta "sotto" un ramo tagliato forma un cluster separato.
>
> **2. La Matrice di Similarità (in basso)**
> È una *heatmap* della matrice $X_{ij}$ in cui i nodi (righe/colonne) sono stati riordinati seguendo l'ordine delle foglie del dendrogramma.
> * **Colori Caldi (Rosso/Marrone):** Indicano alta sovrapposizione topologica ($X_{ij} \approx 1$).
> - **Colori Freddi (Verde):** Indicano bassa sovrapposizione ($X_{ij} \approx 0$).
>
> **La Corrispondenza**
> L'algoritmo rivela la struttura a blocchi:
> * I **blocchi rossi quadrati** lungo la diagonale principale corrispondono ai rami più bassi e fitti del dendrogramma.
> * Questi blocchi rappresentano le **comunità** (gruppi densamente connessi al loro interno).
> * I blocchi verdi fuori dalla diagonale indicano la scarsa connessione tra comunità diverse.

## Procedure Divisive: L'algoritmo di Girvan-Newman

A differenza dell'approccio agglomerativo, le procedure **divisive** rimuovono sistematicamente i collegamenti che uniscono nodi appartenenti a comunità diverse, fino a spezzare la rete in isole separate.
### Centralità (Link Betweenness)
Per decidere quale arco tagliare, bisogna definire una misura di "centralità". I collegamenti tra comunità diverse ("ponti") hanno una centralità alta.

La misura utilizzata è la **Link Betweenness**: definita come il **numero di cammini minimi (shortest paths) che passano attraverso quell'arco**.

Ci si aspetta che i collegamenti tra comunità diverse abbiano larga centralità, mentre collegamenti interni ad una community abbiano valori più bassi. 

> [!intuito] Intuito
> Gli archi che collegano due comunità agiscono come "colli di bottiglia": per andare da una parte all'altra della rete, quasi tutti i cammini minimi devono passare di lì, facendone aumentare drasticamente la betweenness.
### Procedura dell'algoritmo

1.  Calcola la centralità (betweenness) per ogni arco della rete.
2.  **Rimuovi l'arco** con la centralità più alta.
3.  **Ricalcola la centralità** di tutti gli archi rimanenti nella rete modificata.
4.  Ripeti i passi 2 e 3 finché non sono stati rimossi tutti gli archi.

Il processo genera un dendrogramma che mostra le scissioni progressive della rete.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=26&rect=31,47,322,229|9, p.26]]

> [!caution] Interpretazione Visuale (Slide 26)
> L'immagine mostra passo dopo passo come l'algoritmo "smonta" la rete rimuovendo i ponti.
>
> **1. La Sequenza di Taglio (a - d)**
> * **(a):** Rete intatta.
> * **(b):** Il primo taglio (croce rossa) colpisce l'arco **C-D**.
>     * *Perché?* È l'unico ponte che collega il triangolo superiore al resto della rete. Ha la **Betweenness più alta** perché tutti i cammini dal gruppo A-B-C verso gli altri nodi devono passare di lì.
> * **(c):** Il taglio successivo colpisce l'arco **G-H**. Questo separa il gruppo di sinistra (E-F-G) da quello di destra.
> * **(d):** Procedendo, la rete si frammenta in componenti isolate.
>
> **2. Il Dendrogramma (e)**
> * Riflette l'ordine dei tagli, ma letto dall'alto verso il basso.
> * La prima biforcazione in alto corrisponde al primo taglio critico (C-D) che ha diviso la rete in due grandi blocchi.
> * I rami successivi mostrano le suddivisioni interne ai sottogruppi.
>
> **3. Il Grafico della Modularità (f)**
> * Mostra il valore di $M$ in funzione del numero di comunità ($n$).
> * Si nota un **picco massimo** a $n=3$.
> * **Significato:** L'algoritmo ci suggerisce che la divisione "naturale" della rete è in **3 comunità** (i tre triangoli/gruppi evidenti nel grafo), poiché lì la qualità della partizione è massima.
## Modularità

La **Modularità** ($M$) è la misura standard per quantificare la qualità di una partizione.

L'idea fondamentale è confrontare la densità di collegamenti esistenti all'interno di una comunità con la densità di collegamenti che ci aspetteremmo di trovare se la rete fosse casuale (random network), mantenendo invariati i gradi dei nodi.

* Se i link interni sono **molti di più** di quelli attesi dal caso $\to$ **Vera Comunità**.
* Se i link interni sono uguali o inferiori a quelli attesi $\to$ **Nessuna struttura significativa**.

Consideriamo una rete con $N$ nodi e $L$ link totali, partizionata in $n_c$ comunità.
La modularità totale $M$ è la somma dei contributi delle singole comunità:

$$M = \sum_{c=1}^{n_{c}} \left[ \frac{L_{c}}{L} - \left( \frac{k_{c}}{2L} \right)^{2} \right]$$

Dove per ogni comunità $c$:
* $\frac{L_{c}}{L}$: È la frazione dei link totali della rete che si trovano *internamente* alla comunità $c$.
* $\frac{k_{c}}{2L}$: Rappresenta la somma normalizzata dei gradi dei nodi nella comunità.
* $\left( \frac{k_{c}}{2L} \right)^{2}$: Rappresenta la **frazione attesa** di link interni se la rete fosse casuale.

> [!intuito] Interpretazione della Formula
> La formula misura la **distanza dalla casualità**:
> $$M = (\text{Frazione Reale di Link Interni}) - (\text{Frazione Attesa di Link Interni})$$

### Interpretazione dei Valori di M

La modularità fornisce un indicatore scalare immediato per confrontare diverse partizioni.

![[Università/Magistrale/Complex Social Networks/Slides/9.pdf#page=32&rect=38,77,330,235|9, p.32]]

> [!example] Esempi Visivi (vedi immagine sopra)
> * **Singola Comunità ($M=0$):** Se raggruppiamo tutti i nodi in un unico gruppo, la frazione reale e quella attesa coincidono. Non c'è struttura.
> * **Partizione Ottimale ($M=0.41$):** La divisione rispetta i gruppi densi naturali. Il valore è alto e positivo.
> * **Partizione Subottimale ($M=0.22$):** La divisione cattura qualcosa, ma unisce due gruppi che dovrebbero essere separati. $M$ è positivo ma più basso.
> * **Modularità Negativa ($M=-0.12$):** La partizione taglia nel mezzo i gruppi densi, mettendo nodi connessi in comunità diverse e raggruppando nodi che non c'entrano nulla. È peggio del caso casuale.

## L'Algoritmo Greedy (Ottimizzazione della Modularità)

Poiché non possiamo calcolare $M$ per tutte le possibili partizioni, dobbiamo usare metodi approssimati per trovare il valore massimo.

L'approccio più diffuso è l'**Algoritmo Greedy** (proposto da Newman).

L'assunto è che la partizione con la **Modularità massima** corrisponda alla struttura di comunità ottimale.

L'algoritmo procede per tentativi "avidi" (greedy), facendo ad ogni passo la scelta locale migliore sperando che porti all'ottimo globale.

### Procedura

1.  **Inizializzazione:** Si parte assegnando **ogni nodo a una comunità propria** (se abbiamo $N$ nodi, abbiamo $N$ comunità di dimensione 1).
2.  **Calcolo del Delta:** Per ogni coppia di comunità collegate da almeno un link, si calcola $\Delta M$, ovvero quanto cambierebbe la modularità se unissimo quelle due comunità.
3.  **Unione (Merge):** Si sceglie la coppia che garantisce il **massimo aumento** di $\Delta M$ e la si unisce in una sola comunità.
    * *Nota:* Si unisce anche se $\Delta M$ è negativo, purché sia il "meno peggio", per permettere all'algoritmo di uscire da massimi locali, ma si tiene traccia della storia.
4.  **Iterazione:** Si ripetono i passi 2 e 3 finché tutti i nodi della rete non sono fusi in un'unica gigantesca comunità.
5.  **Selezione:** L'algoritmo ha generato una storia di partizioni. Si scorre lo storico e si **seleziona la partizione che ha registrato il valore di $M$ più alto** in assoluto.