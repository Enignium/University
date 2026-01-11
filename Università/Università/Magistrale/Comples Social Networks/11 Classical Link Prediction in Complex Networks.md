
La **Link Prediction** è un problema chiave nell'analisi delle reti complesse.
La domanda fondamentale è: *Possiamo predire quali collegamenti (link) è probabile che appaiano, o che siano attualmente mancanti, data la struttura di una rete?*

Capire la link prediction è importante per:
* **Comprendere la dinamica di crescita della rete:** Es. evoluzione dei social network.
* **Scoprire connessioni invisibili:** Es. predire interazioni proteina-proteina in biologia.
* **Raccomandazioni:** Suggerire nuovi amici o prodotti in piattaforme commerciali.

La link prediction è utilizzata in:
* **Social Networks:** Suggerimenti di amicizia su Facebook/LinkedIn ("Persone che potresti conoscere").
* **Reti Biologiche:** Identificazione di interazioni tra geni o proteine non ancora rilevate sperimentalmente.
* **Sistemi di Raccomandazione:** Suggerire film o articoli basandosi sulle interazioni utente-oggetto.
* **Reti di Citazioni:** Prevedere future collaborazioni scientifiche.

## Link Prediction

La link prediction mira a predire l'esistenza di archi mancanti in un grafo noto per esempio per mancanza di dati completi nel dataset, o a prevedere archi che appariranno in futuro.

Dato un grafo $G=(V,E)$ dove $V$ è l'insieme dei nodi ed $E$ l'insieme degli archi osservati l'obbiettivo sarà:
* Trovare coppie di nodi $(u, v)$ tali che $(u, v) \notin E$ (Static/Future Prediction).
* **Classificare** o **ordinare (rank)** tutti i link non osservati in base alla loro probabilità di esistere.

Si differenziano le seguenti task di link prediction:
1.  **Static Link Prediction:** Identificare archi mancanti in un'istantanea fissa della rete (es. dati incompleti).
2.  **Temporal/Future Link Prediction:** Prevedere quali nuovi archi si formeranno nel tempo in una rete dinamica.
3.  **Reti Eterogenee:** Predizione su grafi bipartiti (utenti-prodotti) o con attributi.
###  Metodi di Link Prediction

Esiste una vasta gamma di approcci per la Link Prediction. I metodi classici possono essere categorizzati in base al livello di informazione topologica che utilizzano.

1.  **Metodi Locali (Local Methods):** Utilizzano solo le informazioni dei vicini diretti dei nodi candidati. Sono veloci e scalabili.
2.  **Metodi Globali (Global Methods):** Sfruttano l'intera topologia della rete (es. tutti i cammini possibili). Sono più accurati ma computazionalmente costosi.
3.  **Metodi Quasi-Locali:** Un compromesso che combina caratteristiche locali con una visione leggermente più ampia.
4.  **Machine Learning:** Tecniche che apprendono pattern complessi da feature estratte.
## Metriche di predizione

Per quantificare le performance di un algoritmo di predizione servono metriche rigorose.
La scelta della metrica dipende dall'area di applicazione, dal fatto che si tratti la predizione come un ranking o una classificazione binaria, e soprattutto dal **bilanciamento delle classi** (ci sono molti più "non-link" che "link").
## Metriche di Classificazione binaria

### Matrice di Confusione

Valuta la qualità delle predizioni confrontandole con la realtà (Ground Truth):

| | **Predetto: Link** | **Predetto: No Link** |
| :--- | :---: | :---: |
| **Reale: Link** | **TP** (True Positive) | **FN** (False Negative) |
| **Reale: No Link** | **FP** (False Positive) | **TN** (True Negative) |

* **True Positives (TP):** Link esistenti correttamente predetti.
* **False Positives (FP):** Link predetti che in realtà non esistono.
* **False Negatives (FN):** Link esistenti che l'algoritmo non ha trovato.
* **True Negatives (TN):** Assenza di link correttamente predetta.
 
![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=17&rect=70,49,302,238|11, p.13]]

Dalla matrice di confusione è possibile ricavare le seguenti metriche standard:

### Precision
La frazione di link predetti che sono effettivamente veri. Risponde alla domanda: *"Quanto posso fidarmi quando l'algoritmo dice che c'è un link?"*

$$Precision = \frac{TP}{TP + FP}$$

### Recall
La frazione di link veri che sono stati effettivamente predetti. Risponde alla domanda: *"Quanti dei link nascosti sono riuscito a trovare?"*

$$Recall = \frac{TP}{TP + FN}$$

### F1-Score
La media armonica tra Precision e Recall. È utile per bilanciare i due aspetti con un singolo numero.

$$F1 = 2 \cdot \frac{Precision \cdot Recall}{Precision + Recall}$$

> [!warning] Il Problema dell'Accuratezza (Accuracy)
> L'accuratezza è definita come la frazione totale di predizioni corrette:
> $$Accuracy = \frac{TP + TN}{TP + TN + FP + FN}$$
>
> Tuttavia, nella Link Prediction **non va usata**.
> * **Motivo:** La maggior parte delle coppie di nodi possibili **non sono collegate**. Questo rende il numero di **TN (True Negatives)** enormemente più grande degli altri valori.
> * **Conseguenza:** Un modello pigro che predice sempre "Nessun Link" avrebbe un'accuratezza altissima (es. 99.9%), pur essendo completamente inutile.
>
> **Conclusione:** Preferire sempre Precision e Recall.

### ROC Curve e AUC

La curva **ROC** (Receiver Operating Characteristic) è uno standard per valutare classificatori binari al variare della soglia di decisione.

* **Plot:** Mette in relazione il **True Positive Rate (TPR)** (che coincide con la Recall) sull'asse Y contro il **False Positive Rate (FPR)** sull'asse X.
    $$TPR = \frac{TP}{TP + FN} \quad  \quad FPR = \frac{FP}{FP + TN}$$
* **AUC (Area Under Curve):** È l'area sottesa alla curva ROC.
    * Un valore di **1.0** indica un classificatore perfetto.
    * Un valore di **0.5** indica un classificatore casuale (la linea diagonale tratteggiata).

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=20&rect=55,15,312,238|11, p.16]]
### Precision-Recall Curve

Quando i dati sono fortemente sbilanciati (come nella Link Prediction), la curva ROC può essere troppo ottimistica. La **Curva Precision-Recall** è spesso più informativa.

* Mostra il trade-off tra Precision (asse Y) e Recall (asse X).
* **Interpretazione:**
    * Una curva alta verso l'angolo in alto a destra indica un ottimo modello.
    * All'aumentare della Recall (tentativo di trovare tutti i link), la Precision tende inevitabilmente a scendere (si includono più falsi positivi).
* **AUC-PR:** L'area sotto questa curva è un ottimo indicatore di performance complessiva, un area migliore indica una performance migliore.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=31&rect=27,36,337,238|11, p.27]]
## Metriche di Ranking

Spesso, nella Link Prediction, non vogliamo classificare ogni singola coppia come "Link" o "No Link". Vogliamo invece ottenere una lista ordinata dei **Top-k** link più probabili (es. raccomandazioni di amici).

### Precision@k
Questa metrica valuta la qualità delle prime $k$ predizioni fornite dall'algoritmo.

$$Precision@k = \frac{\text{Numero di link veri nei top k}}{k}$$

> [!example]- Esempio
> Se l'algoritmo suggerisce 10 nuovi amici ($k=10$) e 3 di questi sono suggerimenti corretti:
> $$Precision@10 = \frac{3}{10} = 0.3$$

### Query e Ground Truth 

Considerato un nodo Q  di una rete si definiscono:
* **Query:** Il nodo $Q$ per il quale vogliamo predire i link mancanti.
* **Ground Truth:** L'insieme dei link rilevanti (che dovrebbero esistere) associati alla query $Q$.

Molti algoritmi associano per ogni query una lista ranked di nodi predetti.
### MAP (Mean Average Precision)

La **Mean Average Precision** è una metrica robusta che premia gli algoritmi che posizionano i link corretti in cima alla lista.
### Average Precision (AP)
Per una singola query $q$, l'AP è la media della precisione calcolata in corrispondenza di ogni $k$ in cui appare un link rilevante.

$$AP(q) = \frac{1}{N_{rel}(q)} \sum_{k=1}^{n} Precision@k(q) \cdot rel_k(q)$$

Dove:
* $N_{rel}(q)$: Numero totale di link rilevanti per la query, derivante dalla Ground Truth.
* $rel_k(q)$: Vale 1 se il link al rango $k$ è rilevante, 0 altrimenti.

> [!example]- Esempio
> **Situazione:**
> * **Query:** Nodo $Q$.
> * **Link Reali (Ground Truth):** $\{(Q, A), (Q, C)\}$ (Totale = 2).
> * **Lista Predetta (ordinata):** $[(Q, B), (Q, A), (Q, C), (Q, E)]$.
>
> **Calcolo Passo-Passo:**
> 1.  **Rank 1:** $(Q, B)$ $\to$ Errato. (Non conta per l'AP).
> 2.  **Rank 2:** $(Q, A)$ $\to$ **Corretto**.
>     * Link trovati finora: 1. Posizioni scorse: 2.
>     * $Precision@2 = 1/2 = 0.5$.
> 3.  **Rank 3:** $(Q, C)$ $\to$ **Corretto**.
>     * Link trovati finora: 2. Posizioni scorse: 3.
>     * $Precision@3 = 2/3 \approx 0.667$.
> 4.  **Rank 4:** $(Q, E)$ $\to$ Errato.
>
> **Risultato Finale:**
> $$AP(Q) = \frac{0.5 + 0.667}{2} \approx 0.583$$

### Mean Average Precision (MAP)
È semplicemente la media delle AP calcolata su tutte le query $Q$ nel dataset.

$$MAP = \frac{1}{Q} \sum_{q=1}^{Q} AP(q)$$

## Euristiche Locali (Local Heuristics)

Le euristiche locali si basano sull'idea che due nodi hanno maggiori probabilità di collegarsi se sono vicini nella rete, ovvero se condividono molti amici o vicini.
### Common Neighbors (CN)

È il metodo più semplice e intuitivo. Fornisce un punteggio basato sul numero di vicini in comune tra due nodi $x$ e $y$.

$$s_{CN}(x,y) = |\Gamma(x) \cap \Gamma(y)|$$
Dove $\Gamma(x)$ è l'insieme dei vicini del nodo $x$.

> [!intuito] Intuito
> "Se abbiamo molti amici in comune, è probabile che ci conosciamo o ci conosceremo presto."

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=42&rect=90,93,282,230|11, p.36]]
### Jaccard Coefficient

Il coefficiente di Jaccard normalizza il numero di vicini comuni rispetto al numero totale di vicini dei due nodi. Questo evita che i nodi con grado molto alto (hub) abbiano score elevati solo perché hanno tanti vicini.

$$s_{Jaccard}(x,y) = \frac{|\Gamma(x) \cap \Gamma(y)|}{|\Gamma(x) \cup \Gamma(y)|}$$

* **Range:** Valori da 0 (nessun vicino in comune) a 1 (vicinato identico).
* **Utilità:** Molto utile in contesti eterogenei dove i gradi dei nodi variano notevolmente.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=44&rect=86,94,279,233|11, p.38]]

### Adamic-Adar Index (AA)

L'indice Adamic-Adar raffina il concetto di Common Neighbors. L'idea è che i vicini comuni non sono tutti uguali: un vicino comune che è collegato a *tutti* (un hub) è meno informativo di un vicino comune che ha *pochi* collegamenti.
Pertanto, pesa i vicini comuni inversamente al loro grado.

$$s_{AA}(x,y) = \sum_{z \in \Gamma(x) \cap \Gamma(y)} \frac{1}{\log|\Gamma(z)|}$$

> [!info] Interpretazione
> * I vicini comuni "rari" (basso grado) danno un contributo **alto** allo score.
> * I vicini comuni "popolari" (alto grado) danno un contributo **basso**.
> * Privilegia i "ponti" informativi rispetto agli hub generici.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=46&rect=80,89,280,232|11, p.40]]

### Preferential Attachment (PA)

Si basa sul modello "Rich get richer". Assume che i nuovi collegamenti tendano a formarsi verso nodi che hanno già un grado elevato, indipendentemente dai vicini condivisi.

**Formula:**
$$s_{PA}(x,y) = |\Gamma(x)| \cdot |\Gamma(y)|$$

* Si calcola moltiplicando i gradi dei due nodi.
* È particolarmente rilevante nelle reti scale-free in crescita.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=48&rect=67,89,276,240|11, p.42]]

### Resource Allocation Index (RA)

Simile all'Adamic-Adar, ma penalizza i vicini comuni di alto grado in modo ancora più aggressivo (senza il logaritmo). È ispirato ai processi di diffusione delle risorse nella rete.

**Formula:**
$$s_{RA}(x,y) = \sum_{z \in \Gamma(x) \cap \Gamma(y)} \frac{1}{|\Gamma(z)|}$$

* **Differenza con AA:** Senza il logaritmo, il peso dei nodi a basso grado è molto più marcato.
* Efficace in reti dove i nodi a basso grado giocano un ruolo cruciale.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=50&rect=87,82,287,234|11, p.44]]
### Confronto tra Euristiche Locali

Queste misure differiscono principalmente per come pesano i vicini comuni e per la sensibilità al grado dei nodi:

| Metodo                      | Caratteristica Principale                                                                                    |
| :-------------------------- | :----------------------------------------------------------------------------------------------------------- |
| **Common Neighbors**        | Conteggio semplice; ignora il grado dei nodi. Favorisce chi ha tanti amici.                                  |
| **Jaccard**                 | Normalizza per l'unione dei vicini. Penalizza gli hub.                                                       |
| **Adamic-Adar / RA**        | Pesano i vicini comuni inversamente al loro grado. Favoriscono connessioni tramite intermediari "esclusivi". |
| **Preferential Attachment** | Guarda solo al grado dei nodi target, ignorando i vicini in comune.                                          |

## Euristiche Globali 

Le euristiche globali considerano la struttura intera della rete.
### Katz Index

Il **Katz Index** è una misura di **similarità globale**, superando la visione puramente locale di euristiche come CN o Jaccard. Considera l'insieme di tutti i cammini possibili tra due nodi.

$$Katz(u, v) = \sum_{l=1}^{\infty} \beta^l \cdot |\text{walks}_{u,v}^{(l)}|$$

Dove:
* $l$: Lunghezza del cammino.
* $|\text{walks}_{u,v}^{(l)}|$: Numero di cammini di lunghezza $l$ tra $u$ e $v$.
* $\beta$: Fattore di attenuazione ($0 < \beta < 1$) che riduce l'importanza dei cammini lunghi.

> [!info] Logica del Punteggio
> * **Percorsi corti:** Molto importanti (contributo alto).
> * **Percorsi lunghi:** Contano, ma meno (contributo attenuato da $\beta^l$).
> * Se due nodi sono immersi nello stesso "intorno strutturale", avranno un punteggio altissimo.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=62&rect=57,52,299,230|11, p.55]]
### Rooted PageRank

Il **Rooted PageRank** modifica il comportamento classico del random walker per misurare la vicinanza strutturale a uno specifico nodo radice.

Utilizza come punteggio di predizione la probabilità che attraverso la camminata si arrivi su un determinato nodo.

Cattura la raggiungibilità di  un nodo tramite random walk ottenendo informazioni relative sia alla struttura locale che alla struttura globale. 

#### Dal Random Walk al Rooted PageRank
1.  **Random Walk Standard:** Un walker si muove casualmente. Nel lungo periodo, la probabilità di trovarsi in un nodo è **proporzionale al suo grado** (gli hub dominano).
2.  **Rooted PageRank:** Introduce una preferenza esplicita.
    * Il walker si muove casualmente verso i vicini.
    * A intervalli regolari (con probabilità $1-\alpha$), il walker **ritorna immediatamente al nodo radice (r)**.

> [!intuito] Il Cambio di Prospettiva
> La domanda cambia da *"Quali nodi sono visitati più spesso in assoluto?"* a:
> **"Quali nodi vengono visitati più spesso da un walker che parte sempre da $r$ e continua a tornare su $r$?"**

Questo sconta automaticamente i cammini lunghi o poco probabili e privilegia quelli brevi che partono dalla radice.
![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=64&rect=70,71,293,227|11, p.57]]
### SimRank

Il **SimRank (SR)** introduce un concetto di similarità **ricorsiva** fondamentale: *"Due nodi sono simili se sono collegati a nodi simili"*.

A differenza delle euristiche locali (come Common Neighbors o Adamic-Adar) che guardano solo ai vicini diretti, SimRank ragiona come un'eco che si propaga attraverso l'intera rete.

La similarità tra due nodi $u$ e $v$ dipende dalla similarità dei loro vicini, la quale a sua volta dipende dalla similarità dei vicini dei vicini, e così via.

$$s_{SR}(u, v) = \begin{cases} 1 & \text{se } u = v \\ \frac{C}{|\Gamma(u)||\Gamma(v)|} \sum_{x \in \Gamma(u)} \sum_{y \in \Gamma(v)} s_{SR}(x, y) & \text{se } u \neq v \end{cases}$$

Dove:
* $\Gamma(u)$ e $\Gamma(v)$ sono gli insiemi dei vicini di $u$ e $v$.
* $C$ è un **fattore di decadimento** ($0 < C < 1$) che attenua l'influenza dei vicini man mano che ci si allontana.
* Si impone $s_{SR}(u,u) = 1$ (ogni nodo è massimamente simile a se stesso).

> [!intuito] Intuito
> La domanda fondamentale è:
> **"Se parto dai vicini di $u$ e dai vicini di $v$ e cammino all'indietro nella rete, quanto è probabile che io arrivi in nodi simili?"**
> Non conta quanti vicini condividono *ora*, ma quanto sono simili i loro intorni strutturali completi.

![[Università/Magistrale/Comples Social Networks/Slides/11.pdf#page=66&rect=28,56,297,235|11, p.59]]

SimRank è una **Global Similarity Measure** e si distingue nettamente dagli altri approcci:

* **Non è locale:** A differenza di CN, Jaccard o RA, non si ferma all'intorno immediato ma propaga la similarità iterativamente.
* **Non usa il grado direttamente:** A differenza del Preferential Attachment (PA), non assume che "più connesso = meglio".
* **Non usa cammini espliciti:** A differenza del **Katz Index**, non somma percorsi di lunghezza fissa.
* **Non simula un walker:** A differenza del **Rooted PageRank**, si basa puramente sulla struttura di vicinanza reciproca.
## Differenze tra euristiche locali e globali

Le due famiglie di euristiche operano su livelli di informazione completamente diversi.
### Heuristics Locali (CN, Jaccard, AA, RA, PA)
* **Visione:** "Miope". Guardano solo l'intorno immediato (vicini e vicini dei vicini).
* **Limiti:** Non vedono comunità distanti, non conoscono percorsi lunghi, non percepiscono la forma globale della rete.
* **Vantaggi:** Rapidissime ed economiche. Funzionano bene su reti clusterizzate e semplici.

### Heuristics Globali (Katz, SimRank, RPR)
* **Visione:** "Panoramica". Non si fermano ai vicini immediati.
* **Fattori considerati:**
    * Quanti percorsi totali collegano due nodi e la loro lunghezza.
    * Come si distribuisce un random walker (RPR).
    * Come si propaga la similarità attraverso livelli multipli (SimRank).
* **Costo:** Computazionalmente molto più onerose.
