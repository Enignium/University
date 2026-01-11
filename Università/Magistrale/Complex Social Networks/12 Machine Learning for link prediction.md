Le euristiche classiche predicono i link utilizzando formule esplicite basate *solo* sulla topologia del grafo.
* **Esempi:** Common Neighbors, Jaccard Coefficient, Adamic-Adar, Preferential Attachment, Katz Index, SimRank.
* **Caratteristiche:** Sono trasparenti, facili da calcolare e non richiedono dati di addestramento (unsupervised).

Tuttavia le euristiche classiche presentano le seguenti limitazioni:
* **Solo pattern strutturali:** Non possono combinare informazioni topologiche con attributi dei nodi o degli archi.
* **Modello fisso:** Non possono apprendere pattern complessi automaticamente; la formula è la stessa indipendentemente dal tipo di dato.
* **Dipendenza dalla topologia:** Le performance crollano su grafi che non presentano le caratteristiche specifiche assunte dall'euristica (es. basso clustering o assenza di hub).
### Vantaggi dell'Approccio ML

Gli approcci di **Machine Learning (ML)** sfruttano molteplici feature e imparano dai dati la combinazione predittiva ottimale.

> [!success] Punti di Forza del ML
> * **Flessibilità:** I modelli ML possono incorporare le euristiche classiche come *feature*, insieme ad attributi dei nodi ed embedding.
> * **Adattabilità:** Il modello impara dalla struttura reale dei dati, adattandosi allo specifico dominio.
> * **Performance:** Spesso ottengono risultati migliori dei metodi classici, specialmente su reti complesse.
## Approccio ML 

Gli approcci ML formulano la Link Prediction come una **task di classificazione supervisionata**.
Ogni possibile coppia di nodi $(x, y)$ viene rappresentata da un **vettore di feature** che riassume le informazioni disponibili.

Le feature su cui si basa il modello comprendono:
1.  **Euristiche Topologiche:** Common Neighbors, Adamic-Adar, Jaccard, Katz, ecc. (calcolate come numeri).
2.  **Attributi dei Nodi:** Similarità dei profili, appartenenza a gruppi, dati demografici.
3.  **Attributi degli Archi:** Pesi, timestamp, tipi di relazione.
4.  **Node Embeddings:** Rappresentazioni vettoriali dense (da algoritmi come node2vec o DeepWalk).

## Costruzione del Dataset

Per addestrare il modello, dobbiamo costruire una matrice di feature $X$ e un vettore di label $Y$.

Per una coppia $(x, y)$, il vettore di feature può apparire così:
$$X_{(x,y)} = [s_{CN}(x,y), s_{AA}(x,y), s_{J}(x,y), \text{attributi}, \text{embeddings}, \dots]$$

La label relativa sarà:
$$Y_{(x,y)} = \begin{cases} 1 & \text{se l'arco esiste (o è stato nascosto per il test)} \\ 0 & \text{altrimenti} \end{cases}$$

Il modello viene addestrato per classificare $X_{(x,y)}$ come "linkato" ($Y=1$) o "non linkato" ($Y=0$).
### Train/Test Splitting

Poiché il nostro obiettivo è predire link *mancanti* o *futuri*, non possiamo usare tutti gli archi visibili per l'addestramento. Dobbiamo simulare lo scenario di predizione.

> [!warning] Procedura Standard
> 1.  **Nascondere Link Reali:** Rimuoviamo casualmente una frazione di archi esistenti dal grafo. Questi diventano il nostro **Positive Test Set**.
> 2.  **Campionare Non-Link:** Selezioniamo coppie di nodi che *non* sono connesse nel grafo originale. Questi diventano il nostro **Negative Test Set**.

* **Training Set:**
    * Tutti gli archi *non* nascosti (Esempi Positivi).
    * Un numero uguale (o maggiore) di non-archi casuali (Esempi Negativi).
* **Test Set:**
    * Gli archi nascosti (Esempi Positivi da ritrovare).
    * Nuovi non-archi campionati (Esempi Negativi).


> [!example]- Esempio
> Per valutare correttamente un modello, è essenziale garantire che i set di training e di test non si sovrappongano e riflettano lo scenario di predizione reale.
> 
> Definiamo formalmente i set:
> * **$E_{train}$**: Insieme degli archi osservati (usati per il training).
> * **$E_{test}$**: Insieme degli archi nascosti (da predire).
> * **$N_{train}$** e **$N_{test}$**: Insiemi di non-archi (coppie non connesse) campionati rispettivamente per il training e il test.
> 
> Il dataset si divide quindi in:
> 1.  **Training Data ($X_{train}, Y_{train}$):**
>     * Esempi Positivi: $E_{train}$ (Label = 1)
>     * Esempi Negativi: $N_{train}$ (Label = 0)
> 2.  **Test Data ($X_{test}, Y_{test}$):**
>     * Esempi Positivi: $E_{test}$ (Label = 1)
>     * Esempi Negativi: $N_{test}$ (Label = 0)
> 

## Dimensionality Reduction: PCA e t-SNE

Spesso i dati delle reti (come gli embedding dei nodi) sono ad **alta dimensionalità**. Per visualizzarli e interpretarli, è necessario proiettarli in uno spazio a bassa dimensionalità (2D o 3D).

1.  **Visualizzazione:** Dati ad alta dimensione (es. vettori a 128 dimensioni) sono impossibili da vedere direttamente.
2.  **Analisi:** Strumenti come PCA e t-SNE aiutano a trovare cluster, outlier e strutture nascoste nei dati.
3.  **Interpretazione:** Permettono di "guardare dentro" il modello per capire cosa ha imparato.

### Principal Component Analysis (PCA)

La **PCA**  è una tecnica **lineare** fondamentale per la riduzione della dimensionalità.

* Identifica le direzioni (chiamate **Componenti Principali**) lungo le quali i dati presentano la maggiore varianza (cioè dove i dati sono più "sparpagliati").
* Proietta i dati su queste prime $k$ componenti (solitamente $k=2$ o $3$) per ottenere un riassunto che conserva la maggior quantità possibile di informazione originale.
* È molto utile per proiettare embedding ad alta dimensionalità in 2D per la visualizzazione.

Dato una matrice di dati $X$ (dove le righe sono i campioni/nodi e le colonne le feature):

1.  **Centratura e Covarianza:** Si calcola la matrice di covarianza $S$:
$$S = \frac{1}{n-1} X^T X$$
2.  **Autovettori:** Si trovano gli autovettori $w_1, w_2, \dots$ di $S$. Questi rappresentano le direzioni di massima varianza.
3.  **Proiezione:** Si proiettano i dati originali usando i primi $k$ autovettori (contenuti nella matrice $W_k$):
$$Z = X \cdot W_k$$

Il risultato $Z$ è una rappresentazione compressa in cui ogni campione è ora un vettore di dimensione $k$ (con $k \ll D$).

Ecco come appare una proiezione PCA su un dataset semplice.

![[12.pdf#page=22&rect=84,63,284,226|12, p.19]]

> [!info] Osservazione
> La PCA ruota e proietta i dati lungo gli assi principali (PC1 e PC2).
> In questo esempio, i cluster (gruppi di punti colorati) rimangono ben separati anche dopo la proiezione in 2D, dimostrando che la struttura globale dei dati è stata preservata.

#### PCA per la Visualizzazione degli Embedding

La PCA può essere applicata direttamente agli embedding dei nodi appresi da algoritmi come **node2vec** o **DeepWalk**.

* **Struttura Globale:** Tende a preservare le distanze relative globali e la dispersione generale dei dati.
* **Cluster:** È efficace nel rivelare raggruppamenti (cluster) macroscopici e relazioni geometriche generali nello spazio ad alta dimensionalità.
* **Limite:** Essendo una trasformazione lineare, potrebbe non riuscire a srotolare o separare strutture complesse e non lineari (come vedremo con t-SNE).

![[12.pdf#page=26&rect=28,99,341,228|12, p.23]]

> [!caution] Osservazione
> Si osserva come la PCA fallisca nel mantenere le separazione in strutture non lineari. 
> La t-SNE riesce correttamente a mantenerla anche in questi casi.

## t-SNE

**t-SNE** sta per *t-Distributed Stochastic Neighbor Embedding*. È una tecnica progettata specificamente per visualizzare dati ad alta dimensionalità.

* **Modellazione della similarità:** L'algoritmo calcola la similarità tra i punti nello spazio ad alta dimensione e cerca di trovare una configurazione in bassa dimensione (2D o 3D) che preservi queste similarità.
* **Preservazione del Vicinato:** Il principio fondamentale è che i punti che sono "vicini" (neighbors) nell'alta dimensione devono rimanere vicini nella rappresentazione a bassa dimensione.
* **Non-Linearità:** A differenza dalla PCA, t-SNE è non-lineare. Non cerca di preservare le distanze globali, ma si concentra quasi esclusivamente sulla struttura locale.

Qui vediamo l'applicazione di t-SNE sugli embedding generati per il grafo *Zachary's Karate Club*. I nodi sono colorati in base alla loro reale appartenenza al club.
![[12.pdf#page=36&rect=86,54,283,230|12, p.33]]
> [!caution] Osservazione
> * I nodi appaiono raggruppati in cluster ben definiti che corrispondono alle fazioni del club (colori rosso e blu).
> * La separazione è molto più netta rispetto a quella ottenuta con la PCA, facilitando l'identificazione visiva delle comunità.

#### Vantaggi di t-SNE

t-SNE è diventato lo standard de facto per la visualizzazione di embedding grazie ai suoi punti di forza unici:

1.  **Rivela strutture non lineari:** Riesce a visualizzare chiaramente cluster  complessi che metodi lineari schiaccerebbero.
2.  **Preservazione del vicinato locale:** Garantisce che i punti molto simili nell'alta dimensione rimangano vicini nel grafico 2D.
3.  **Gestione di geometrie complesse:** Riesce a districare forme difficili come spirali intrecciate o "Swiss rolls".
4.  **Interpretazione intuitiva:** L'interpretazione è diretta: punti vicini nel grafico sono strutturalmente simili; punti lontani sono localmente diversi.
#### Limitazioni di t-SNE

Nonostante la sua potenza, t-SNE non è privo di difetti e va usato con consapevolezza:

* **Perdita della Struttura Globale:** Le distanze tra cluster molto distanti nel grafico non sono significative. Non si può dire che il Cluster A è "più diverso" da B che da C solo basandosi sulla distanza visiva macroscopica.
* **Costo Computazionale:** Ha una complessità di $O(n^2)$, il che lo rende lento e pesante per dataset con molti punti (richiede approssimazioni per grandi moli di dati).
* **Sensibilità agli Iperparametri:** Il risultato cambia drasticamente in base alla **Perplessità** scelta. Non esiste un valore unico corretto per tutti i dati.
* **Non Deterministico:** A causa dell'inizializzazione casuale e dell'ottimizzazione stocastica, esecuzioni diverse possono produrre layout visivamente differenti (sebbene la topologia locale debba restare simile).
