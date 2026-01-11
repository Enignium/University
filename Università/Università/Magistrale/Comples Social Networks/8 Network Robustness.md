 I network costituiscono la base di quasi tutti i sistemi reali: biologici, tecnologici, sociali e ingegneristici.

La robustezza è definita come la capacità di una rete di mantenere le proprie funzioni nonostante il guasto di nodi o link (errori casuali) o la loro rimozione intenzionale.

La struttura del network è ciò che ne determina la sopravvivenza. Elementi chiave includono:
* **Hub:** Nodi altamente connessi che mantengono la coesione.
* **Ridondanza:** Offre percorsi alternativi in caso di interruzioni.
* **Clustering:** Connessioni locali dense che limitano la frammentazione.

> [!caution] Osservazione
> Gli errori e i guasti sono inevitabili. Tuttavia, molti sistemi mostrano una sorprendente capacità di mantenere le funzioni anche quando alcuni componenti falliscono.
> 
> **Non è il singolo nodo a determinare la sopravvivenza di una rete, ma l’organizzazione complessiva dei collegamenti.**

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=5&rect=79,30,271,226|8, p.4]]

La figura mostra l'effetto della rimozione progressiva di nodi sulla connettività. La rimozione di un nodo qualsiasi (come quello evidenziato in verde) comporta l'eliminazione automatica di tutti gli archi ad esso collegati.
Questo processo può determinare una riduzione significativa della connettività fino a provocare la frammentazione del grafo in sotto componenti isolate.

## Teoria della Percolazione

La teoria della percolazione fornisce un modello matematico per studiare **la comparsa e la scomparsa della connettività su larga scala**  in seguito alla rimozione casuale di elementi.

La [[3 Random Network#Evoluzione della connettività di un random network|connettività di un sistema emerge gradualmente all'aumentare della probabilità]] $p$ che due nodi siano connessi.

Esiste una **Soglia di Percolazione** (*Percolation Threshold*) indicata con $p_c$, che rappresenta il punto critico per la connettività globale.

* **Per $p < p_c$:** La rete è costituita da molti piccoli cluster isolati. Non c'è connettività globale
![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=8&rect=85,40,275,229|8, p.6]]
* **Per $p \ge p_c$:** I piccoli cluster si fondono dando origine a una **componente gigante** che attraversa l'intera rete.
![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=9&rect=79,28,291,226|8, p.7]]
> [!caution] Nota: Transizione di Fase
> In corrispondenza di $p_c$ si osserva una **transizione di fase**: il sistema passa bruscamente da una condizione disconnessa a una condizione globalmente connessa.Questo fenomeno è universale e analogo alle transizioni di fase in fisica (es. passaggio acqua-ghiaccio).

### Quantità Fondamentali ed Esponenti Critici

Per descrivere questa transizione di fase sono necessarie tre quantità fondamentali, descritte da esponenti critici universali (che dipendono dalla classe dimensionale del sistema).

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=13&rect=41,17,317,234|8, p.11]]

##### Dimensione Media dei Cluster finiti $\langle s \rangle$
Rappresenta la dimensione media di tutti i cluster *finiti* (**escludendo la componente gigante**).
La relazione è data da:
$$\langle s \rangle \propto |p - p_c|^{-\gamma_p}$$
Dove $\gamma_p$ è l'esponente critico.

> [!caution] Andamento di $\langle s \rangle$ (Vedi Figura C)
> * **$p$ basso:** I cluster sono piccoli, $\langle s \rangle$ è basso.
> * **$p \to p_c$:** I cluster si fondono creando strutture sempre più grandi. La dimensione media **diverge** (raggiunge il massimo) in prossimità del punto critico.
> * **$p > p_c$:** La maggior parte dei nodi entra nella componente gigante (che viene esclusa dal calcolo). I cluster residui sono piccoli, quindi $\langle s \rangle$ diminuisce nuovamente.

##### Parametro d'Ordine ($P_{\infty}$)
Rappresenta la probabilità che un nodo scelto a caso appartenga al cluster più grande (Componente Gigante) e va valutata solo per valori di $p>p_{c}$.
$$\ P_{\infty} \propto (p - p_c)^{\beta_p}$$

> [!caution] Andamento di $P_{\infty}$ (Vedi Figura D)
> * **$p < p_c$:** Non esiste componente gigante quindi si definisce $P_{\infty} = 0$.
> * **$p > p_c$:** Compare la componente gigante. $P_{\infty}$ diventa positivo e cresce rapidamente verso 1.

#### 3. Lunghezza di Correlazione ($\xi$)
Rappresenta la distanza media tra tutte le coppie di nodi appartenenti allo stesso cluster.
$$\xi \propto |p - p_c|^{-\nu}$$
Al punto critico, la lunghezza di correlazione diverge, indicando che l'intera rete diventa interconnessa.

> [!intuito] Intuito
> Questa grandezza intuitivamente rappresenta quanti cammini è possibile attraversare in media restando nello stesso cluster. 
> Questa aumenta all'aumentare della connettività della rete, diventando infinita nel momento in cui tutti i nodi appartengono alla componente gigante, per cui è possibile camminare all'infinito restandoci all'interno.

## Percolazione Inversa

Mentre la teoria classica della percolazione studia l'emergere della connettività aggiungendo nodi, la **Percolazione Inversa** analizza il processo opposto: la perdita di connettività globale in seguito alla rimozione di nodi o link.

Questo approccio è fondamentale per modellare la **Robustezza** delle reti, simulando scenari di guasto (errori casuali) o attacchi mirati.

Nella percolazione inversa, il parametro di controllo non è più la probabilità di occupazione $p$, ma la frazione di nodi rimossi $f$.
La relazione tra i due è semplice:

$$f = 1 - p$$

* $f$: rappresenta il grado di danno o fallimento del sistema.
* $f_c$: è la soglia critica di rimozione. Corrisponde a $1 - p_c$.

> [!caution] Il Collasso della Connettività
> Quando la frazione di nodi rimossi raggiunge la soglia critica ($f = f_c$), la componente gigante collassa e la rete perde la sua connettività globale, frammentandosi in piccoli cluster isolati.
> Questa inversione collega direttamente la fisica statistica ai problemi reali di robustezza delle reti.

## Transizione di Fase nella Percolazione Inversa

Il processo segue una dinamica precisa descritta dai seguenti passaggi:

1.  **Stato Iniziale ($f=0$):** Si parte da un sistema completamente occupato o connesso. Esiste un cluster gigante che copre l'intero reticolo.
2.  **Processo di Rimozione ($f > 0$):** Man mano che $f$ aumenta (vengono rimossi nodi), le dimensioni dei cluster si riducono e la rete inizia a frammentarsi.
3.  **Punto Critico ($f = f_c$):** Il parametro d'ordine $P_{\infty}$ (la probabilità che un nodo appartenga al cluster più grande) svanisce. La rete si spezza definitivamente.

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=18&rect=59,16,302,232|8, p.15]]

Osservando il grafico di $P_{\infty}$ in funzione di $f$:

* Per valori bassi di $f$ (es. $f=0.1$), $P_{\infty}$ rimane alto: la rete è ancora ben connessa (zona viola nel grafico).
* Avvicinandosi a $f_c$, la curva inizia a scendere drasticamente.
* Superato $f_c$ (es. $f=0.8$), $P_{\infty}$ va a zero: rimangono solo "detriti" o polvere di nodi isolati (zona grigia nel grafico).
## Applicazioni e Rilevanza

La percolazione inversa non è solo un esercizio teorico, ma fornisce strumenti predittivi fondamentali per diversi ambiti:

* **Infrastrutture:** Prevedere quando una rete elettrica o di trasporti smetterà di funzionare a causa di guasti locali.
* **Biologia:** Capire quanti geni o proteine possono essere soppressi prima che una cellula muoia.
* **Sistemi Sociali:** Analizzare come si disgrega una comunità o un'organizzazione se i membri chiave vengono rimossi.

## Percolazione nelle Reti Complesse

Lo studio della percolazione inversa sulle reti si focalizza su come la connettività viene persa a seguito della rimozione di nodi o link. La domanda chiave non è più *se* esiste una componente gigante, ma **quando essa svanisce**.

A differenza dei reticoli regolari, nelle reti complesse la transizione dipende dalla **topologia** e dalla **distribuzione dei gradi** $P(k)$.

### Il Criterio di Molloy-Reed

Per determinare se una rete possiede una componente gigante, si utilizza il **Criterio di Molloy-Reed**.
Una rete possiede una componente gigante se il rapporto tra il secondo e il primo momento della distribuzione dei gradi soddisfa la condizione:

$$\frac{\langle k^2 \rangle}{\langle k \rangle} > 2$$

> [!intuito] Intuito
> Questo rapporto $\frac{\langle k^2 \rangle}{\langle k \rangle}$ (spesso indicato con $\kappa$) rappresenta il numero medio di collegamenti che un nodo ha verso altri nodi, escludendo il collegamento da cui siamo arrivati (branching factor).
> Se questo valore è sufficientemente alto (> 2), la rete riesce a ramificarsi e sostenere una struttura connessa globale.

Si dimostra che è possibile calcolare analiticamente la soglia critica $f_c$ (percentuale di nodi rimossi necessaria per frammentare la rete) come:
$$f_c = 1 - \frac{1}{\frac{\langle k^2 \rangle}{\langle k \rangle} - 1}$$

Questa formula rivela una differenza fondamentale tra le diverse tipologie di reti:

 - Reti Casuali (Random Networks)
Hanno un valore di $f_c$ **finito**.
Significa che esiste una specifica percentuale di nodi che, se rimossa, distrugge sicuramente la rete.

-  Reti Scale-Free
Per reti Scale-Free con esponente $2 < \gamma < 3$ (come Internet o molte reti sociali), accade qualcosa di straordinario.
Poiché il secondo momento $\langle k^2 \rangle$ [[4 The Scale-Free Property#Il significato di Scale-Free|diverge]] (tende a infinito) al crescere della dimensione della rete:

$$f_c \rightarrow 1$$

> [!caution] Osservazione
> Il fatto che $f_c$ tenda a 1 significa che per disconnettere una rete Scale-Free bisogna rimuovere **quasi il 100% dei nodi**.
> Finché rimane anche solo una piccola frazione di nodi attivi, la rete tende a rimanere connessa grazie alla presenza degli Hub. Questo conferisce alle reti Scale-Free una robustezza intrinseca eccezionale contro i guasti casuali.

## Guasti Casuali (Random Failures)

L'analisi dei guasti casuali mette in luce una differenza drammatica tra le reti casuali (come il modello Erdős-Rényi) e le reti Scale-Free.
### Impatto sulla Robustezza

* **Reti Casuali:** La rimozione di una frazione finita di nodi porta rapidamente alla distruzione della componente gigante. La transizione è brusca al raggiungimento di $f_c$.
* **Reti Scale-Free:** La componente gigante persiste quasi fino alla rimozione totale di tutti i nodi. La robustezza scala con il secondo momento della distribuzione $\langle k^2 \rangle$.

> [!caution] Meccanismo di Robustezza
> Perché le reti Scale-Free sono così robuste ai guasti casuali?
>
> 1.  **Statistica dei Nodi:** In una rete Scale-Free, la stragrande maggioranza dei nodi ha un grado molto basso ($k$ piccolo).
> 2.  **Probabilità di Rimozione:** Se scelgo un nodo a caso per rimuoverlo (guasto casuale), è statisticamente molto probabile che io colpisca un nodo "piccolo" e periferico.
> 3.  **Sopravvivenza degli Hub:** La probabilità di colpire casualmente un Hub (che sono rari) è bassissima. Di conseguenza, gli Hub rimangono intatti e continuano a tenere unita la rete.
### Dati Empirici e Soglie Critiche

I dati reali confermano questa eccezionale robustezza:

* **Internet:** Si stima un $f_c \approx 97\%$. Bisogna rimuovere quasi l'intera rete per disconnetterla casualmente.
* **Reti Biologiche:** Le reti metaboliche e di interazione proteica mostrano valori di $f_c$ molto alti, indicando una forte tolleranza agli errori cellulari.
* **Reti Sociali:** Anche queste si dimostrano robuste alla rimozione casuale di individui.
### Visualizzazione del Collasso e Influenza di $\gamma$

Il modo in cui la componente gigante si riduce dipende dall'esponente $\gamma$ della distribuzione dei gradi (Power Law $P(k) \sim k^{-\gamma}$).

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=32&rect=60,34,307,219|8, p.27]]

* **$\gamma = 4.0$ (Simile a Random):** La curva scende velocemente. La rete è poco robusta.
* **$\gamma = 3.0$:** Robustezza intermedia.
* **$\gamma = 2.0$ (Scale-Free puro):** La curva è estremamente "piatta" all'inizio e scende solo verso la fine ($f \to 1$). Questo conferma che minore è $\gamma$ (più eterogenea è la rete), maggiore è la robustezza contro i guasti casuali.
## Attacchi Mirati (Targeted Attacks)

Mentre i guasti casuali colpiscono prevalentemente i nodi di basso grado, gli **attacchi mirati** hanno come obiettivo specifico la rimozione dei nodi con il grado più alto (Hub).

L'impatto sulla rete è devastante:
* La rete si frammenta rapidamente, anche rimuovendo una frazione molto piccola di nodi.
* La soglia critica di attacco $f_c$ è drasticamente inferiore rispetto a quella per i guasti casuali.

> [!caution] Perché gli Hub sono critici?
> Gli Hub mantengono connessi grandi porzioni del network. La loro rimozione priva molti nodi del loro percorso principale verso il resto della rete, innescando una frammentazione a cascata.
> Il grafico mostra chiaramente la differenza: la curva di connettività sotto attacco (viola) crolla quasi istantaneamente rispetto a quella dei guasti casuali (verde).

## Il "Tallone d'Achille" delle Reti Reali

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=38&rect=77,16,280,231|8, p.32]]

I dati empirici confermano questa dualità comportamentale, nota come effetto "Tallone d'Achille": **Robustezza contro gli errori, Fragilità contro gli attacchi**.

Analizzando le curve $P_{\infty}(f)$ per diverse reti reali (Internet, Power Grid, Reti Sociali, Biologiche):
1.  **Curva Verde (Random):** Scende lentamente (alta robustezza).
2.  **Curva Viola (Attacco):** Crolla bruscamente a zero per valori di $f$ molto bassi.

> [!check] Esempio: Internet e Reti Sociali
> * **Internet:** Basta rimuovere una frazione minuscola di hub cruciali per disconnettere la rete, mentre resiste benissimo a guasti casuali dei router periferici.
> * **Eccezione (Power Grid):** Essendo una rete meno eterogenea (non puramente Scale-Free), la differenza tra la curva di attacco e quella di guasto è meno marcata rispetto a Internet.

Questa vulnerabilità strutturale ha implicazioni dirette sulla progettazione e difesa dei sistemi:
* **Difesa:** Le infrastrutture critiche (come Internet) necessitano di protezione mirata per gli Hub (cybersecurity, ridondanza fisica).
* **Medicina:** In ambito medico, questa proprietà è un vantaggio. Per combattere patogeni o malattie complesse, si mira a colpire le "proteine hub" o i nodi vitali della rete metabolica del virus/batterio.

Già agli albori di Internet, Paul Baran teorizzò che la topologia determina la sopravvivenza.
* **Centralizzata (Hub-and-Spoke):** Efficiente ma vulnerabile. Se il centro cade, tutto si ferma.
* **Decentralizzata/Distribuita (Mesh):** Meno efficiente in quanto più collegamenti implicano maggiore complessità e maggiore uso di risorse ma resiliente. La ridondanza dei percorsi permette alla rete di sopravvivere alla perdita di nodi importanti.

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=43&rect=70,87,293,232|8, p.37]]

## Fallimenti a Cascata (Cascading Failures)

La rimozione di un nodo non causa solo un danno locale (isolamento dei vicini), ma può innescare una reazione a catena globale.
Quando un nodo fallisce (es. sovraccarico), il suo carico viene ridistribuito sui nodi vicini. Se questi non riescono a sostenerlo, **falliscono a loro volta, propagando il guasto**.

La dimensione di questi guasti a cascata  segue spesso una distribuzione a legge di potenza (*Power Law*):
* Molti eventi sono piccoli e locali.
* Pochi eventi sono catastrofici e globali (Blackout continentali).

> [!caution] Esempi Reali
> I grafici nelle slide mostrano che la distribuzione delle dimensioni ($s$) segue una retta in scala log-log per:
> * **Blackout Elettrici:** Energia non servita.
> * **Cascate Sociali:** Numero di Retweet su Twitter.
> * **Terremoti:** Magnitudo degli eventi sismici.
>
> Questo conferma che il meccanismo di propagazione è universale nei sistemi complessi interconnessi.

![[Università/Magistrale/Comples Social Networks/Slides/8.pdf#page=46&rect=92,66,274,230|8, p.39]]