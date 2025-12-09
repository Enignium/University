Un **random walk** è un processo stocastico che, partendo da un nodo iniziale, si muove verso un nodo adiacente **scelto in modo casuale** a ogni passo.
# Grafo e vicinato

Dato un grafo, per un nodo:

$$ 
\tau(v) = {u_1, u_2, u_3, \dots}  
$$

dove **τ(v)** è l’insieme dei suoi vicini.
### Probabilità di transizione

Se il random walk si trova nel nodo corrente **v**, il prossimo nodo viene scelto **uniformemente** tra i vicini:

$$  
P(\text{next} = u_i \mid \text{current} = v) = \frac{1}{|\tau(v)|}  
$$

### Walk di lunghezza L

Un random walk di lunghezza **L** è una sequenza:

$$ 
(v_0, v_1, v_2, \dots, v_L)  
$$

dove ogni transizione $( v_{t} \rightarrow v_{t+1} )$ è determinata dal processo casuale precedente.

>[!caution] Intuizione
>
>- Il percorso esplora localmente il grafo.
>- Nodi con **alto grado** tendono a essere visitati più spesso.
>- È alla base di algoritmi come **PageRank**, **Node2Vec**, **DeepWalk** e molte misure di >centralità stocastica.
# Proprietà Avanzate

## Stationary Distribution

Per un grafo **connesso** e **non orientato**, un random walk semplice converge a una **distribuzione stazionaria**:
$$  
\pi(v) = \frac{\deg(v)}{\sum_{u \in V} \deg(u)}  
$$
  >[!caution] Osservazione
>Nel lungo periodo, la probabilità di trovarsi nel nodo ( v ) è **proporzionale al suo grado**. Quindi, i nodi con **alto grado** vengono visitati più spesso.
## Mixing Time

Il **mixing time** è il numero di passi necessari affinché il random walk si avvicini alla distribuzione stazionaria.

- **Fast mixing** → il grafo viene esplorato rapidamente.
- **Slow mixing** → la struttura del grafo rallenta la diffusione (es. grafi con colli di bottiglia o cluster molto separati).
## Commute Time

Il **commute time** è il tempo atteso per:

1. partire da un nodo ( u )
2. raggiungere un nodo ( v )
3. **tornare** a ( u )
$$  
\text{Commute}(u,v) = \mathbb{E}[\text{tempo}(u \rightarrow v \rightarrow u)]  
$$
- Tempi di commute **brevi** indicano che ( u ) e ( v ) appartengono alla **stessa comunità** o sono ben collegati nel grafo.
Ecco la versione corretta, completa e formattata **per Obsidian**, mantenendo lo stesso stile degli appunti precedenti.
## Sampling del Vicinato

### Un singolo random walk

Un **singolo** random walk partendo da un nodo fornisce **solo un campione** del suo vicinato.

- Esplora _un solo percorso_.
- Raccoglie informazione limitata sulla struttura locale.
- Può mancare intere parti del vicinato.
### Molti random walk

Eseguire **molti random walk** da ogni nodo permette di:

- campionare **vicini diversi**,
- catturare **variazioni strutturali** del grafo,
- osservare nodi a diversa distanza dal punto di partenza.
## Perché sono utili più walk

Ogni walk segue un percorso diverso e quindi:

>[!caution] Osservazione
>Ogni walk scopre vicini a distanze diverse e lungo configurazioni differenti del grafo.

Questo permette di catturare:

- struttura **locale** (nodi molto vicini),
- struttura **mesoscopica** (cluster, community),
- struttura **globale** per cammini più lunghi.

Questo è esattamente il meccanismo alla base di **DeepWalk** e **Node2Vec**, dove i random walk generano “contesti” simili alle frasi del linguaggio naturale.

Ecco tutto **pulito, corretto e formattato per Obsidian**, in continuità perfetta con gli appunti precedenti.
## Perché usiamo i Random Walk negli Embedding

## Co-occurrence → Similarità

Se due nodi **u** e **v** compaiono spesso **vicini** all’interno degli stessi random walk:
$$
u \approx v \quad \Rightarrow \quad \text{emb}(u) \sim \text{emb}(v)  
$$
**Idea chiave:**  
Nodi che condividono molti contesti di cammino devono avere embedding simili perché svolgono ruoli simili nella struttura della rete.
## Fondamento dei metodi di embedding (DeepWalk / Node2Vec)

## 1️) Generare random walk per raccogliere contesti

- Ogni walk è una sequenza di nodi:  
$$  
(v_0, v_1, v_2, \dots)  
$$
- Le sequenze catturano **vicinati locali** e **strutture più ampie** (cluster, ponti, community).
## 2) Applicare un modello linguistico (Skip-Gram)

- Si trattano i random walk come **frasi**.
- Skip-gram impara a rappresentare come simili i nodi che co-occorrono nella stessa finestra di contesto.
$$
\text{massimizzare } P(\text{vicini}(v) \mid \text{emb}(v))  
$$
Il modello impara vettori che preservano relazioni strutturali del grafo.
### Approccio in 2 step
$$ 
\text{(1) Random Walks} + \text{(2) Skip-Gram} = \text{Node Embedding}  
$$
Ed è **esattamente** ciò che fanno:

- **DeepWalk** → random walks uniformi + skip-gram
- **Node2Vec** → random walks _biased_ (controllati da p e q) + skip-gram

Ecco la versione pulita, corretta e pronta per Obsidian, in continuità con il resto degli appunti.
# Word2Vec — Embedding del Linguaggio

## Cos'è Word2Vec

Word2Vec è un metodo basato su **reti neurali** per apprendere **rappresentazioni vettoriali (embeddings)** delle parole a partire da grandi corpora testuali.
## Idea centrale
Le parole che compaiono in **contesti simili** devono avere **vettori simili**.
$$
\text{similar context} ;\Rightarrow; \text{similar embedding}  
$$
Esempio intuitivo:

Parole come:

- **king**
- **queen**
- **prince**
- **princess**
compaiono in contesti correlati  
→ quindi i loro vettori embedding occupano **regioni vicine** nello spazio.
## Perché è importante

Word2Vec è la **base concettuale** degli attuali metodi di embedding, non solo nel linguaggio naturale ma anche nei grafi.

Metodi come **DeepWalk** e **Node2Vec** funzionano proprio perché trattano i **random walk** come frasi e applicano lo stesso modello **Skip-Gram** introdotto in Word2Vec.
## Contesto e Finestra di Contesto

Il **contesto** di una parola è definito da una **finestra di ampiezza fissa** che include le parole vicine.

- Data una finestra di ampiezza ( k )
- Per ogni parola, consideriamo le ( k ) parole precedenti e le ( k ) successive.

Per esempio:

**"the quick brown fox jumps over the lazy dog"**

Finestra di contesto: ( k = 2 )
### Contesti

- **"quick"** → contesto: { "the", "brown" }
- **"brown"** → contesto: { "quick", "fox" }
- **"fox"** → contesto: { "brown", "jumps" }

(Generalizzabile a tutte le parole della frase.)
## Come Word2Vec apprende la similarità

Osservando quali parole compaiono **frequentemente nello stesso contesto** su un grande corpus, il modello:

- assegna vettori simili alle parole con contesti simili,
- raggruppa semanticamente termini correlati,
- cattura relazioni come king–queen, dog–cat, Paris–France.

$$
\text{similar contexts} \Rightarrow \text{similar vector representations}  
$$
## Architetture e Obiettivo di Ottimizzazione

## 🔹 Due architetture principali

Word2Vec utilizza due modelli:

- **CBOW (Continuous Bag of Words)**: Predice la parola centrale dato il contesto. 
- **Skip-Gram**: Predice le parole del contesto data la parola centrale (target) → **È il modello più usato** anche in DeepWalk e Node2Vec.
### Idea centrale

Dato un **target word** $( w_t )$, il modello cerca di **predire le parole nel suo contesto**.
$$
w_t ;\rightarrow; \text{context words}  
$$
## Obiettivo di ottimizzazione

Per una sequenza di parole $( w_1, w_2, \dots, w_T )$:

$$  
\max \sum_{t=1}^{T} ; \sum_{\substack{-k \le j \le k \ j \ne 0}} \log P(w_{t+j} \mid w_t)  
$$
dove:
- $(w_t)$ = parola target in posizione $(t)$
- $(w_{t+j})$ = parola nel contesto (entro distanza $(j)$)
- $(k)$ = dimensione della finestra di contesto

Il modello impara vettori tali per cui la parola target ha **alta probabilità** di predire correttamente le sue parole vicine.
## Perché è importante

Lo stesso obiettivo viene applicato in DeepWalk/Node2Vec:

- **target word** ↦ **nodo nel random walk**
- **context words** ↦ **vicini nel cammino**

→ Ed è così che si imparano gli **embedding dei nodi**.

Ecco la versione **pulita, corretta e formattata per Obsidian**, coerente con tutto il blocco Word2Vec/Skip-Gram che stiamo costruendo.
## Negative Sampling in Word2Vec

## Positive examples

- Coppie di parole che **co-occorrono realmente** nel testo.  
Esempio: _(quick, brown)_, _(king, queen)_, _(dog, barks)_.

Il modello vuole assegnare a queste coppie **alta similarità**:
- **dot product ≈ +1**
- **sigmoid ≈ 1**
## Negative examples

- Coppie di parole **scelte a caso** dal vocabolario, quindi **molto improbabili** da vedere insieme.  
Esempio: _(table, running)_, _(blue, democracy)_.

Il modello deve assegnare a queste coppie **bassa similarità**:
- **dot product ≈ –1**
- **sigmoid ≈ 0**
## Obiettivo del negative sampling

Il modello impara a:

- **distinguere contesti veri** da **rumore casuale**,
- aumentare la probabilità delle coppie _positive_,
- ridurre quella delle coppie _negative_.

Questo crea embedding che catturano la struttura semantica del linguaggio.

## Efficienza del training

Invece di usare la **softmax completa** su tutto il vocabolario ( |V| ), che sarebbe costosissima, il negative sampling:

- genera solo **m negative samples** per ogni coppia positiva,
- tipicamente ( m \approx 5 \text{–} 20 ),
- riduce il costo computazionale da ( O(|V|) ) a **O(m)**.

Ecco la versione **pulita, sistemata e pronta per Obsidian**, perfettamente coerente con gli appunti precedenti.
## Random Walks ↔ Word2Vec — Analogia Centrale

## 🧩 Ruolo dei Random Walk

Nei metodi di embedding per grafi (DeepWalk, Node2Vec):

- i **random walk** svolgono il ruolo delle **frasi (sentences)**
- i **nodi** svolgono il ruolo delle **parole (words)**
$$
\text{walk} ;\leftrightarrow; \text{sentence},  
\qquad  
\text{node} ;\leftrightarrow; \text{word}  
$$
## Corpus di Walk

Generando **molti random walk** da ogni nodo:

- otteniamo un **corpus di sequenze** che cattura la struttura del grafo
- ogni sequenza rappresenta un possibile percorso locale/globale
- i nodi che co-occorrono spesso nello stesso walk diventano **contesti reciproci**
## Addestramento Skip-Gram identico a Word2Vec

Una volta ottenuto il corpus dei walk:

- applichiamo **esattamente lo stesso algoritmo Skip-Gram** di Word2Vec
- stesso obiettivo (massimizzare $( P(\text{contesto} \mid \text{target})$
- stessa procedura di **negative sampling**
- stesso addestramento tramite **SGD**

Il modello apprende embedding tali che:

- nodi che compaiono in contesti simili → embedding simili
- la struttura del grafo (community, ruoli, vicinati) viene catturata nei vettori


