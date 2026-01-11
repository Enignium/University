I modelli di rete casuali assumono che i collegamenti avvengano in modo arbitrario, indipendentemente dal grado dei nodi. Tuttavia, l'osservazione delle reti reali rivela pattern strutturali ben precisi che smentiscono questa ipotesi.

Il fatto che tali unioni siano invece frequenti evidenzia una proprietà strutturale delle reti sociali: **gli Hub tendono a connettersi ad altri Hub**.

Al contrario, in altri sistemi come la rete di interazione proteica del lievito, si osserva il fenomeno opposto: gli Hub (proteine altamente connesse) evitano di collegarsi tra loro, preferendo connessioni con nodi di basso grado.

## La Matrice di Correlazione di Grado

Un modo visuale per comprendere le correlazioni è osservare la **Matrice di Correlazione di Grado** $e_{ij}$.
Questa matrice rappresenta la probabilità di trovare un nodo di grado $i$ e un nodo di grado $j$ alle due estremità di un collegamento scelto a caso.
Essendo una probabilità, la matrice è normalizzata:
$$\sum_{i,j} e_{ij} = 1$$

Sebbene $e_{ij}$ contenga l'informazione completa sulle correlazioni, la grande quantità di elementi la rende difficile da analizzare numericamente, ma l'ispezione visiva (heatmap) rivela chiaramente i pattern strutturali.
### 1. Reti Assortative

![[7.pdf#page=7&rect=36,37,330,212|7, p.7]]

Nelle reti assortative, i nodi tendono a connettersi con nodi di grado simile.
Visivamente, la matrice mostra una concentrazione di probabilità lungo la **diagonale principale**. Questo indica che nodi con grado basso si connettono a nodi con grado basso, e nodi con grado alto si connettono a nodi con grado alto.

### 2. Reti Neutre

![[7.pdf#page=8&rect=36,68,326,209|7, p.8]]
Nelle reti neutre, non c'è preferenza basata sul grado. La mappa di calore appare più diffusa e concentrata attorno ai valori medi della distribuzione dei gradi, senza un asse preferenziale marcato come nel caso assortativo.
### 3. Reti Disassortative

![[7.pdf#page=9&rect=36,43,320,213|7, p.9]]

Nelle reti disassortative, i collegamenti avvengono tra nodi di grado molto diverso.
Visivamente, la matrice mostra alte probabilità lontano dalla diagonale principale indicando connessioni frequenti tra nodi ad alto grado ($k$ grande) e nodi a basso grado ($k$ piccolo).
## Misurare le correlazioni dei gradi 

Poiché la matrice $e_{ij}$ è scomoda da gestire per grandi reti, si utilizza una misura più sintetica per quantificare le correlazioni.

Per ogni nodo $i$, si calcola il **grado medio dei suoi vicini** (*average degree of nearest neighbors*), indicato come $k_{nn}(k_i)$:
$$k_{nn}(k_{i}) = \frac{1}{k_{i}} \sum_{j=1}^{N} A_{ij} k_{j}$$

> [!hint] Chiarimento
> Dove $A_{ij}$ è la matrice di adiacenza ($1$ se connessi, $0$ altrimenti) e $k_i$ è il grado del nodo $i$. In pratica, stiamo sommando i gradi di tutti i vicini di $i$ e dividendo per il numero di vicini.

![[7.pdf#page=11&rect=101,2,266,110|7, p.11]]

### Funzione di correlazione

Per ottenere una misura globale che dipenda dal grado $k$, calcoliamo la media di $k_{nn}$ per tutti i nodi che hanno lo stesso grado $k$.

Definiamo la funzione di correlazione di grado $k_{nn}(k)$ come il valore atteso del grado dei vicini di un nodo generico $k$:

$$k_{nn}(k) = \sum_{k'} k' P(k'|k)$$

Dove $P(k'|k)$ è la **probabilità condizionata** che, seguendo un link che parte da un nodo di grado $k$ si arrivi a un nodo di grado $k'$.

> [!caution] Osservazione
> La funzione $k_{nn}(k)$ ci dice qual è il grado medio dei vicini di un generico nodo di grado $k$.
> Analizzando come questa funzione varia al variare di $k$ (crescente, decrescente o costante), possiamo determinare se la rete è assortativa, disassortativa o neutra.

## Analisi dei Regimi di Correlazione

Utilizzando la funzione $k_{nn}(k)$, possiamo analizzare nel dettaglio i tre regimi di correlazione osservati nelle reti reali.

### 1. Reti Neutre (Neutral Networks)

In una rete neutra, il grado medio dei vicini di un nodo è indipendente dal grado $k$ del nodo stesso. Dipende esclusivamente dalle caratteristiche globali della rete (momenti primo e secondo della distribuzione dei gradi).
Matematicamente si esprime come:

$$k_{nn}(k) = \frac{\langle k^2 \rangle}{\langle k \rangle}$$

Poiché il valore è costante, il grafico di $k_{nn}(k)$ in funzione di $k$ risulta essere una **linea orizzontale** posizionata al valore $\frac{\langle k^2 \rangle}{\langle k \rangle}$.

![[7.pdf#page=14&rect=78,30,285,216|7, p.14]]

> [!caution] Esempio: Power Grid
> La rete elettrica (*Power Grid*) è un esempio classico di rete neutra.
> Come mostrato nel grafico, i dati sperimentali (punti viola) oscillano attorno alla previsione random (linea nera o verde tratteggiata) con un esponente $\mu \approx -0.04$ (praticamente zero).

### 2. Reti Assortative

Nelle reti assortative, gli Hub tendono a connettersi ad altri Hub. Di conseguenza, più alto è il grado $k$ di un nodo, più alto sarà il grado medio dei suoi vicini.
La funzione $k_{nn}(k)$ è **crescente** rispetto a $k$.

![[7.pdf#page=16&rect=89,30,285,213|7, p.16]]

> [!caution] Esempio: Collaborazioni Scientifiche
> Le reti di co-authorship scientifico mostrano una chiara tendenza assortativa.
> Nel grafico si osserva che $k_{nn}(k)$ cresce seguendo una legge di potenza con esponente positivo ($\mu \approx 0.37$). La curva si discosta significativamente dalla previsione random (linea orizzontale), indicando che gli scienziati molto citati tendono a collaborare con altri scienziati molto citati.

### 3. Reti Disassortative

Nelle reti disassortative, gli Hub tendono a connettersi a nodi con basso grado. Pertanto, all'aumentare del grado $k$ di un nodo, diminuisce il grado medio dei suoi vicini.
La funzione $k_{nn}(k)$ è **decrescente** rispetto a $k$.

![[7.pdf#page=18&rect=90,53,273,212|7, p.18]]

> [!caution] Esempio: Rete Metabolica
> Le reti biologiche, come quella metabolica, sono fortemente disassortative.
> Il grafico mostra una pendenza negativa marcata ($\mu \approx -0.76$). I nodi ad altissimo grado (Hub metabolici) sono connessi prevalentemente a nodi di basso grado, risultando in una funzione $k_{nn}$ che crolla ben al di sotto della previsione random per valori alti di $k$.

## L'Esponente di Correlazione $\mu$

Analiticamente, la funzione di correlazione di grado può essere approssimata da una legge di potenza della forma:

$$k_{nn}(k) = a k^{\mu}$$

Il segno dell'esponente di correlazione $\mu$ determina univocamente la natura delle correlazioni nella rete.

> [!caution] Classificazione basata su $\mu$
>
> **1. Reti Assortative ($\mu > 0$)**
> Il grado medio dei vicini cresce con il grado del nodo.
> * *Esempio:* Rete di collaborazione scientifica ($\mu = 0.37 \pm 0.11$).
>
> **2. Reti Neutre ($\mu \approx 0$)**
> Il grado dei vicini è indipendente dal grado del nodo.
> * *Esempio:* Rete elettrica / Power Grid ($\mu = 0.04 \pm 0.05$, statisticamente compatibile con zero).
>
> **3. Reti Disassortative ($\mu < 0$)**
> Il grado medio dei vicini decresce all'aumentare del grado del nodo.
> * *Esempio:* Rete metabolica ($\mu = -0.76 \pm 0.04$).
