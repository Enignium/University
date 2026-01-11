Ai fini di utilizzare algoritmi di machine learning per la link prediction è utile ottenere una rappresentazione vettoriale (*embedding*) di un collegamento.

## Random Walk

Un **Random Walk** è un processo stocastico che inizia in un nodo e, ad ogni passo, si sposta verso un vicino scelto casualmente.

Dato un nodo corrente $v$ con vicini $\Gamma(v)=\{u_{1}, u_{2}, ..., u_{k}\}$:
* Il prossimo nodo viene scelto uniformemente a caso:
  $$P(next=u_{i} | current=v) = \frac{1}{|\Gamma(v)|}$$
* Una passeggiata di lunghezza $L$ è una sequenza di nodi $(v_{0}, v_{1}, v_{2}, ..., v_{L})$ generata da questo processo.
![[12.pdf#page=48&rect=47,6,318,230|12, p.44]]

I random walk non sono solo movimenti casuali; essi campionano la struttura del grafo in modo intelligente.

* **Regioni Dense:** Il walker tende a trascorrere più tempo nelle regioni densamente connesse (comunità) perché ci sono molti percorsi interni da attraversare.
* **Regioni Sparse:** Le aree con pochi collegamenti vengono visitate meno frequentemente.
* **Co-occorrenza:** Se due nodi sono nella stessa comunità, è molto probabile che appaiano insieme nello stesso random walk.

> [!caution] Osservazione
> I random walk forniscono un modo per **campionare i vicinati** che riflette la struttura della rete senza dover calcolare esplicitamente metriche complesse o distanze globali.

Esistono proprietà teoriche che rendono i random walk ideali per l'apprendimento degli embedding.

1.  **Distribuzione Stazionaria:** In un grafo connesso non orientato, il random walk converge a una distribuzione stazionaria $\pi(v) \propto deg(v)$.
    * *Significato:* A lungo termine, la probabilità di trovarsi in un nodo è proporzionale al suo grado (i nodi importanti vengono visitati più spesso).
2.  **Mixing Time:** Il numero di passi necessari per avvicinarsi alla distribuzione stazionaria.
    * Un mixing time veloce significa che il grafo viene esplorato rapidamente.
3.  **Commute Time:** Il tempo atteso per andare da $u$ a $v$ e tornare indietro.
    * Tempi brevi indicano che $u$ e $v$ sono nella stessa comunità strutturale.

### Random Walk Multipli: Campionamento su Scala

Un singolo random walk è solo un campione. Per catturare veramente la struttura, ne servono molti.

* **Campionamento Robusto:** Generare molti walk da ogni nodo permette di raccogliere un insieme ricco e variegato di "vicini".
* **Visione Multi-scala:**
    * I **walk brevi** rimangono locali, focalizzandosi sui vicini immediati.
    * I **walk lunghi** esplorano più lontano, catturando la struttura globale.
* Una collezione di walk di varie lunghezze fornisce una visione completa del vicinato di un nodo a diversi livelli di granularità.

L'immagine seguente mostra la heatmap dei nodi visitati partendo dal nodo 0 dopo 100 random walk.

![[12.pdf#page=54&rect=42,11,308,228|12, p.50]]

> [!example] Analisi (Slide 50)
> * I nodi rossi scuri (0, 1, 3, 4) sono quelli visitati più frequentemente: costituiscono la **comunità locale** del nodo di partenza.
> * I nodi più chiari (nel cluster in basso) sono raggiunti raramente.
> * Questo dimostra visivamente come i random walk identifichino implicitamente le comunità.

### Dai Walk agli Embedding

Come passiamo dai walk agli embedding?

1.  **Ipotesi:** Se il nodo $u$ e il nodo $v$ appaiono spesso insieme nei random walk, dovrebbero avere embedding simili.
2.  **Analogia col Linguaggio:**
    * Random Walk $\approx$ Frase.
    * Nodo $\approx$ Parola.
3.  **Metodo:**
    * Generiamo un corpus di random walk.
    * Applichiamo un modello linguistico (come **Skip-Gram**) per imparare vettori che predicono il contesto.

> [!success] DeepWalk e node2vec
> Questo approccio a due fasi (**Generazione Walk + Skip-Gram**) è esattamente la base di algoritmi come DeepWalk e node2vec.

## Word2Vec

**Word2Vec** impara un embedding vettoriale a valori reali per ogni parola in un vocabolario.

Le parole che appaiono in contesti simili dovrebbero avere vettori simili.

Il segnale proviene dal testo stesso (self-supervised):
* Si osserva una parola e i suoi vicini in una finestra mobile (sliding window).
* Si definisce un task di predizione (contesto $\to$ parola, o parola $\to$ contesto).
* Si imparano gli embedding che massimizzano la performance in questo task.
* **Risultato:** I vettori catturano relazioni semantiche e sintattiche.

### Le Due Varianti: CBOW vs Skip-Gram

**CBOW (Continuous Bag of Words)** e **Skip-Gram** sono reti neurali "shallow" (poco profonde) con la stessa architettura ma obiettivi opposti.

| Modello | Input | Output (Target) | Direzione |
| :--- | :--- | :--- | :--- |
| **CBOW** | Parole del Contesto | Parola Target | Contesto $\to$ Target |
| **Skip-Gram** | Parola Target | Parole del Contesto | Target $\to$ Contesto |

Nonostante l'inversione, gli embedding appresi catturano lo stesso tipo di similarità.

#### CBOW

* **Obiettivo:** Predire una parola target basandosi sulle parole del contesto circostante.
* **Esempio:** Nella frase *"the quick brown fox jumps over"*, con finestra di dimensione 2:
    * **Contesto:** `{quick, brown, jumps, over}`
    * **Target:** `fox`.

* **Perché "Continuous"?**
    * Usa vettori densi a valori reali (embedding) in uno spazio continuo, non simboli one-hot sparsi.
* **Perché "Bag" (Sacco)?**
    * L'ordine delle parole nel contesto non conta; vengono sommate o mediate.
    * Conta solo il *multiset* (il sacco) di parole nella finestra.

Nello schema del CBOW, le parole del contesto ("She", "is", "a", "dancer") vengono aggregate per predire la parola centrale mancante ("great").

![[12.pdf#page=61&rect=42,53,322,232|12, p.56]]

> [!info] Meccanismo
> `Contesto` $\to$ `Aggregazione` $\to$ `Predizione Target`.

Sia $v_{w} \in \mathbb{R}^{d}$ l'embedding della parola $w$.
Consideriamo le parole del contesto $\{w_{-m}, ..., w_{-1}, w_{1}, ..., w_{m}\}$ in una finestra di dimensione $m$.

**Step 1:** Calcolare la media degli embedding del contesto:
$$h = \frac{1}{2m} \sum_{i \in context} v_{i}$$

**Step 2:** Predire la parola target $w_t$ tramite softmax:
$$p(w_{t}|context) = \frac{\exp(v'_{w_{t}} \cdot h)}{\sum_{w \in V} \exp(v'_{w} \cdot h)}$$

Dove:
* $v'_{w}$ è l'embedding di "output" della parola $w$.
* **Loss:** Funzione di costo da minimizzare.
* **Veloce da addestrare:** Richiede meno esempi di training per aggiornamento (media molti contesti in uno).
* **Frequenza:** Funziona bene per le parole frequenti.
* **Semplicità:** Architettura più semplice.
* **Parole Rare:** Meno efficace per parole rare (ogni parola rara è il target meno spesso).
* **Perdita di Info:** Facendo la media, si perde l'informazione sulla posizione/ordine delle parole nel contesto.
* **Qualità:** Spesso produce embedding di qualità leggermente inferiore rispetto a Skip-Gram.

#### Skip-Gram

* **Obiettivo:** Predire le parole del contesto data una parola target.
* **Esempio:** Nella frase *"the quick brown fox jumps over"*, con target `fox`:
    * Si creano le coppie: `(fox, quick)`, `(fox, brown)`, `(fox, jumps)`, `(fox, over)`.
* **Training:** Per ogni coppia, si addestra la rete a predire il contesto dal target.
* **Intuizione:** Imparare embedding in cui il vettore della parola target è bravo a "puntare verso" i suoi vicini di contesto.

Sia $v_{w}$ l'embedding della parola e $v'_{w}$ il suo embedding di output.
Siano $w_t$ la parola target e $w_c$ una parola del contesto.

1.  **Embed Target:** $h = v_{w_{t}}$
2.  **Predizione:** Per ogni parola del contesto $w_c$, predire la probabilità tramite softmax:
    $$p(w_{c}|w_{t}) = \frac{\exp(v'_{w_{c}} \cdot h)}{\sum_{w \in V} \exp(v'_{w} \cdot h)}$$

* **Parole Rare:** Funziona molto bene per le parole rare (ogni occorrenza genera molteplici coppie di training).
* **Qualità:** Spesso produce embedding di qualità superiore.
* **Dettagli:** Cattura meglio le relazioni fini (fine-grained).

* **Lentezza:** Più lento da addestrare (molte più coppie di training per frase).
* **Regolarizzazione:** Richiede una regolarizzazione attenta.
* **Efficienza:** Richiede il trucco del *Negative Sampling* per essere veloce nella pratica.

### Confronto: CBOW vs Skip-Gram

Ecco una sintesi delle differenze principali tra i due approcci.

| Aspetto | CBOW | Skip-Gram |
| :--- | :--- | :--- |
| **Direzione** | Contesto $\to$ Parola | Parola $\to$ Contesto |
| **Velocità Training** | Veloce | Lento |
| **Migliore per** | Parole frequenti | Parole rare |
| **Qualità** | Buona | Spesso migliore |
| **Uso Tipico** | Quando la velocità è critica | Quando la qualità è critica |

### Negative Sampling Trick

Il calcolo della **Full Softmax** su tutto il vocabolario è computazionalmente costoso (dobbiamo calcolare probabilità per tutti i $|V| \approx 10^6$ nodi/parole).
Il **Negative Sampling** risolve questo problema sostituendo la softmax con un problema di classificazione binaria.

Invece di predire la probabilità esatta su tutti i nodi, trasformiamo il problema per ogni coppia di training (target, context):
* **Esempio Positivo:** La coppia reale `(target, context word)`.
* **Esempi Negativi:** Campioniamo $k$ parole casuali dal vocabolario e le trattiamo come "rumore".

Si addestra un classificatore binario per rispondere alla domanda: *"Questa parola è un vero vicino di contesto o è solo rumore?"*.

> [!success] Vantaggi
> * **Velocità:** La complessità scende a $O(k)$ invece di $O(|V|)$ per aggiornamento, dove $k \ll |V|$ (tipicamente $k=5$).
> * **Efficacia:** Empiricamente produce embedding molto simili a quelli ottenuti con la full softmax, ma in una frazione del tempo.

### Connessione con Node2Vec e DeepWalk

L'idea alla base di algoritmi come DeepWalk e Node2Vec è applicare l'architettura **Skip-Gram** (nata per il testo) direttamente ai grafi.

| Concetto in Word2Vec (Testo) | Concetto in DeepWalk/Node2Vec (Grafo) |
| :--- | :--- |
| **"Frasi"** | Random Walks (sequenze di nodi) |
| **"Parole"** | Nodi (o entità del grafo) |
| **"Contesto"** | Nodi vicini lungo il cammino casuale |

> [!info] Nota
> La tecnica di embedding è **agnostica rispetto al dominio**. Funziona ovunque sia possibile definire una nozione di "contesto". Se i nodi hanno intorni simili nei random walk, otterranno vettori simili.

### Word Analogies: Aritmetica Vettoriale

Una delle proprietà più importanti di Word2Vec è che le relazioni semantiche vengono mappate in operazioni aritmetiche nello spazio vettoriale.

**L'Esempio Classico:**
*"King sta a Man come Queen sta a Woman"*

Per risolvere l'analogia, calcoliamo:
$$v_{king} - v_{man} + v_{woman}$$

Cercando il vettore più vicino al risultato (tramite cosen-similarity), idealmente otteniamo: **$v_{queen}$**.

In librerie come `Gensim`, questa operazione si esegue specificando termini positivi e negativi:
* **Positive Words:** Vettori che vengono sommati (es. `["king", "woman"]`). Catturano le proprietà desiderate.
* **Negative Words:** Vettori che vengono sottratti (es. `["man"]`). Rimuovono le proprietà indesiderate.

> [!intuito] Direzioni Semantiche
> Il modello non viene istruito a creare assi espliciti, ma il vettore differenza $(v_{woman} - v_{man})$ codifica naturalmente uno **"shift di genere"**. 

## DeepWalk

Passando a **DeepWalk**, introdotto nel 2014, troviamo l'algoritmo che ha gettato le basi per gli embedding basati su random walk. La sua intuizione fondamentale è trattare i nodi di una rete come se fossero parole in un documento. Proprio come nel Natural Language Processing (NLP) si usano le frasi per imparare il contesto delle parole, DeepWalk usa le passeggiate casuali come "frasi" per imparare la struttura della rete.

L'analogia è diretta:
* **Parole** $\rightarrow$ Nodi
* **Frasi** $\rightarrow$ Random Walks
* **Contesto** $\rightarrow$ Nodi vicini nella passeggiata
### Passeggiate Imparziali (Unbiased)

A differenza di node2vec, DeepWalk utilizza passeggiate casuali **imparziali**. Ad ogni passo, trovandosi in un nodo $v$, la probabilità di spostarsi verso un vicino $x$ è uniforme:
$$P(x | v) = \frac{1}{|\Gamma(v)|}$$
Non esistono parametri di controllo per biasare l'esplorazione; l'algoritmo si affida puramente alla topologia esistente per guidare il campionamento.
### L'Algoritmo in Azione

Il funzionamento operativo segue un flusso preciso. In input si prendono il grafo e gli iperparametri (dimensione dell'embedding $d$, lunghezza della passeggiata $L$, numero di passeggiate per nodo $r$, dimensione della finestra $k$).
1.  **Generazione:** Per ogni nodo del grafo, si simulano $r$ passeggiate casuali di lunghezza $L$.
2.  **Corpus:** L'insieme di tutte le passeggiate viene raccolto in un corpus.
3.  **Training:** Si addestra un modello **Skip-Gram** su questo corpus per imparare la matrice di embedding $Z \in \mathbb{R}^{|V| \times d}$.

Il cuore dell'apprendimento è il modello Skip-Gram.
### Perché DeepWalk Funziona? Il Fondamento Teorico

Il successo di DeepWalk non è accidentale, ma si basa su una profonda connessione teorica tra le probabilità di random walk e la struttura intrinseca del grafo. La probabilità che un nodo $v$ appaia in una passeggiata casuale che parte da $u$ è strettamente legata al concetto di **commute time** e alle partizioni del grafo.

Imparando embedding che preservano la co-occorrenza nelle passeggiate casuali, DeepWalk preserva implicitamente la prossimità e la struttura delle comunità. Poiché i random walk tendono naturalmente a concentrarsi e "intrappolarsi" nelle regioni densamente connesse, i nodi appartenenti alla stessa comunità hanno una probabilità molto più alta di apparire nella stessa sequenza.

**Questo spiega perché, anche senza un obiettivo esplicito di clustering, gli embedding risultanti siano eccezionalmente efficaci per compiti di classificazione dei nodi e link prediction.**
### Gli Iperparametri di DeepWalk

Sebbene l'algoritmo sia semplice, il successo dipende dalla corretta sintonizzazione di diversi iperparametri chiave. Ognuno controlla un aspetto diverso del processo di apprendimento:

* **Embedding dimension ($d$):** Definisce la ricchezza della rappresentazione. Valori più alti catturano più sfumature ma aumentano memoria e tempo di training. (Tipico: $64-128$).
* **Walk length ($L$):** Quanto lontano esplora ogni passeggiata. Passeggiate più lunghe catturano meglio la struttura globale ma sono più lente. (Tipico: $40-80$).
* **Walks per node ($r$):** Quante volte campioniamo il vicinato di ogni nodo. Più passeggiate forniscono un segnale più stabile e ricco. (Tipico: $10-80$).
* **Context window ($k$):** L'ampiezza del vicinato nel modello Skip-Gram. Un $k$ più grande include nodi più distanti nella relazione di similarità. (Tipico: $5-10$).
* **Negative samples ($m$):** Quanti esempi negativi (rumore) contrastare per ogni esempio positivo. (Tipico: $5-15$).

> [!info] Nota Operativa
> Questi valori non sono universali: devono essere adattati all'applicazione specifica. Tuttavia, i range indicati offrono un ottimo punto di partenza per la maggior parte delle reti sociali e biologiche.

### Vantaggi di DeepWalk

DeepWalk brilla per una serie di caratteristiche che lo rendono una scelta solida e affidabile:
* **Semplicità:** Facile da implementare e comprendere, senza complessi parametri di bias da gestire.
* **Velocità:** L'uso di passeggiate imparziali ("unbiased") è computazionalmente leggero perché non richiede il pre-calcolo delle probabilità di transizione.
* **Scalabilità:** La generazione delle passeggiate è facilmente parallelizzabile, rendendolo adatto a reti molto grandi.
* **Efficacia Empirica:** Dimostra performance robuste su classificazione, clustering e link prediction.
* **Flessibilità:** Funziona su grafi pesati, diretti e non diretti.

### Limitazioni di DeepWalk

Tuttavia, la semplicità comporta dei compromessi strutturali:
* **Nessun Controllo del Bias:** A differenza di node2vec, le passeggiate imparziali non permettono di "pilotare" l'algoritmo verso strutture specifiche (come ruoli strutturali vs comunità).
* **Bias di Località:** I random walk tendono a restare nelle comunità locali; potrebbero non catturare la struttura globale bene quanto altri metodi se le passeggiate non sono sufficientemente lunghe.
* **Stocasticità:** I risultati dipendono dal campionamento casuale; esecuzioni diverse possono produrre embedding leggermente diversi.
* **Costo Computazionale:** Generare molte passeggiate lunghe può diventare lento su grafi estremamente massivi.
## Node2Vec

L'obiettivo dei metodi di embedding è trasformare i nodi in vettori $z_{i} \in \mathbb{R}^{d}$ in modo che la similarità strutturale nella rete si rifletta nella vicinanza nello spazio vettoriale. Una volta ottenuti questi vettori, operazioni come la link prediction diventano semplici calcoli geometrici.

Algoritmi come **DeepWalk** hanno aperto la strada trattando le random walks come frasi e i nodi come parole. Tuttavia, DeepWalk utilizza passeggiate imparziali, trattando tutti i vicini allo stesso modo. 

Questo approccio cattura la struttura generale, ma spesso abbiamo bisogno di controllare *quale* tipo di relazione preservare:
* **Omofilia:** Nodi nella stessa comunità dovrebbero essere vicini (es. amici).
* **Equivalenza Strutturale:** Nodi con lo stesso ruolo (es. hub) dovrebbero essere vicini, anche se distanti tra loro.

Per risolvere questo, **node2vec** introduce passeggiate "biased" (orientate) controllate dai parametri **$p$** e **$q$**, permettendo di interpolare tra l'esplorazione locale e quella globale.


> [!example] Esempio: Il Grafo Giocattolo
> Immaginiamo un semplice grafo lineare: **$0-1-2-3-4$**.
> Se generiamo una passeggiata che passa per il nodo 2, come $(2, 1, 0, 1, 2, 3, 4)$, e usiamo una finestra $k=2$:
> * Quando siamo sul nodo 2, il contesto include $\{1, 0\}$ e $\{3, 4\}$.
>
> **Insight:** Il vicinato algoritmico di 2 include il nodo 0 e il nodo 4. Anche se non sono collegati direttamente, la passeggiata li rende "semanticamente vicini", permettendo all'embedding di catturare relazioni a lungo raggio.

### Random Walk di Secondo Ordine

Mentre DeepWalk utilizza passeggiate casuali uniformi, **node2vec** introduce una sofisticata strategia di esplorazione definita di **secondo ordine**. L'innovazione chiave sta nel fatto che la scelta del prossimo nodo non dipende solo dalla posizione attuale, ma anche dalla provenienza.

In un random walk standard, la probabilità di transizione dipende solo dal nodo corrente $v$. In node2vec, invece, la transizione verso il nodo $x$ dipende anche dal nodo precedente $t$ da cui siamo appena arrivati. Questa dipendenza è regolata da un fattore di bias $\alpha_{pq}(t,x)$.

Considerato $d_{tx}$ il percorso più corto tra $t$ ed $x$ nel grafo si definisce il **fattore di bias**:
$$
\alpha_{pq}(t,x) =
\begin{cases}
\frac{1}{p} & \text{se } d_{tx} = 0 \quad (\text{ritorna a } t) \\
1 & \text{se } d_{tx} = 1 \quad (\text{resta vicino a } t) \\
\frac{1}{q} & \text{se } d_{tx} = 2 \quad (\text{allontanati da } t)
\end{cases}
$$

> [!info] Interpretazione
> Stiamo sostanzialmente decidendo tra tre opzioni: tornare indietro ($1/p$), restare nel vicinato immediato ($1$), o esplorare nuove aree ($1/q$).

I parametri $p$ e $q$ definiscono la "personalità" della passeggiata, permettendo di interpolare tra diverse strategie di esplorazione.

**Il Parametro di Ritorno ($p$):** Regola la probabilità di rivisitare immediatamente un nodo.
* **$p$ Alto:** Disincentiva il ritorno. La passeggiata tende a non tornare sui propri passi, favorendo un'esplorazione progressiva.
* **$p$ Basso:** Incoraggia il *backtracking*. La passeggiata tende a rimanere molto locale.

**Il Parametro In-Out ($q$):** Gestisce l'equilibrio tra esplorazione locale e globale.
* **$q > 1$ (BFS-like):** Penalizza l'allontanamento ($1/q$ piccolo). La passeggiata rimane intrappolata localmente.
* **$q < 1$ (DFS-like):** Incentiva l'allontanamento ($1/q$ grande). La passeggiata si spinge in profondità nella rete.

> [!intuito] BFS vs DFS: Cosa Catturano?
> * **BFS-like ($q > 1$):** Esplora la rete "a strati" o "a cipolla" attorno al nodo di partenza. È ideale per catturare l'**Omofilia** (comunità locali).
> * **DFS-like ($q < 1$):** Si muove velocemente lontano dalla sorgente. È ideale per catturare l'**Equivalenza Strutturale** (identifica nodi con ruoli simili, come hub o ponti, anche se distanti tra loro).

### L'Algoritmo Node2Vec Completo

Il funzionamento di node2vec può essere suddiviso in tre fasi operative principali che trasformano il grafo in vettori:

1.  **Precalcolo:** Vengono calcolate le probabilità di transizione $\alpha_{pq}$ per gestire il campionamento in modo efficiente (alias method).
2.  **Simulazione Walk:** Si simulano $r$ passeggiate biased di lunghezza $L$ partendo da ogni nodo, utilizzando le probabilità calcolate.
3.  **Ottimizzazione SGD:** Le passeggiate vengono trattate come frasi per addestrare un modello **Skip-Gram**, massimizzando la probabilità del vicinato osservato.

### Effetto Visivo degli Embedding

L'impatto dei parametri è visibile quando si proiettano i nodi nello spazio vettoriale.
Consideriamo un grafo con due clique collegate da un ponte.

* **Con parametri BFS ($p=1, q=2$):** Gli embedding formano cluster basati sull'appartenenza alle clique. I nodi ponte rimangono vicini alle rispettive comunità.
 ![[12.pdf#page=101&rect=77,52,287,229|12, p.95]]
* **Con parametri DFS ($p=1, q=0.5$):** I nodi che fungono da ponte o che hanno ruoli simili tendono a raggrupparsi insieme, sfumando i confini delle comunità per evidenziare la funzione topologica.
![[12.pdf#page=102&rect=83,56,291,232|12, p.96]]
> [!success] Vantaggi Chiave
> * **Flessibilità:** I parametri $p$ e $q$ permettono di adattare il modello a compiti diversi.
> * **Scalabilità:** Il campionamento è parallelizzabile e l'addestramento è lineare nel numero di nodi.
> * **Performance:** Empiricamente supera metodi più semplici in compiti di classificazione e link prediction.

## Dagli embedding alla Link Prediction

Una volta ottenuti gli embedding $z_u$ e $z_v$, come prediciamo se esiste un link tra $u$ e $v$? Il processo integra l'apprendimento non supervisionato con un classificatore supervisionato.

1.  **Feature Engineering:** Per ogni coppia di nodi candidata, costruiamo un vettore di feature combinando i loro embedding (es. prodotto di Hadamard $z_u \circ z_v$, o distanza $|z_u - z_v|$).
2.  **Training:** Addestriamo un classificatore binario (es. Regressione Logistica, Random Forest) usando i link esistenti come esempi positivi e coppie non collegate come esempi negativi.
3.  **Scoring:** Usiamo il classificatore per assegnare un punteggio alle coppie sconosciute.

Questo approccio combina la potenza espressiva degli embedding (che catturano la struttura latente) con la robustezza dei classificatori classici.
## Confronto Finale: DeepWalk vs Node2Vec

Ecco la sintesi definitiva delle differenze operative e strutturali tra i due algoritmi, basata sulle slide 110 e 111.

| Caratteristica | DeepWalk | Node2Vec |
| :--- | :--- | :--- |
| **Tipo di Random Walk** | **Unbiased (Imparziale):** Tutti i vicini hanno la stessa probabilità di essere scelti. | **Biased (Secondo Ordine):** La scelta dipende dal nodo precedente, guidata dai parametri $p$ e $q$. |
| **Meccanismo di Controllo** | **Nessuno:** L'esplorazione è puramente stocastica. | **Parametri $p, q$:** Permettono di interpolare tra BFS (comunità) e DFS (ruoli strutturali). |
| **Efficienza** | **Più Veloce:** Nessun bisogno di pre-calcolare le probabilità di transizione. | **Più Lento:** Richiede il pre-calcolo delle probabilità di transizione $\alpha_{pq}$. |
| **Obiettivo Principale** | Catturare la **prossimità comunitaria** (omofilia). | Flessibile: può catturare sia comunità che **ruoli strutturali** (hub, ponti). |
| **Performance Empirica** | Ottima baseline, spesso molto simile a node2vec su task standard. | Spesso leggermente superiore grazie alla capacità di tuning, ma la differenza è talvolta marginale. |

> [!success] Sintesi
> **DeepWalk** è lo strumento ideale per la sua semplicità e velocità quando l'obiettivo è generale. **Node2vec** è l'evoluzione necessaria quando il task richiede specificamente di distinguere tra ruoli strutturali e comunità, offrendo un controllo fine al costo di una maggiore complessità.