L'evoluzione del World Wide Web ha mostrato fenomeni non spiegabili dai modelli di rete classici. Esempi come Google (nato dopo altri motori di ricerca ma diventato l'hub principale) o Facebook dimostrano che l'età di un nodo non è l'unico fattore determinante per il suo successo.

Nei modelli studiati finora:
* **Modello Erdös-Rényi:** L'identità del nodo più grande è totalmente casuale.
* **Modello Barabási-Albert:** Prevede che ogni nodo aumenti il suo grado secondo la legge $k(t) \sim t^{1/2}$.

> [!caution] Osservazione: First Mover Advantage
> Il modello BA implica che il nodo più vecchio abbia sempre il maggior numero di collegamenti (**First Mover Advantage**).
> Tuttavia, nella realtà il tasso di crescita di un nodo non dipende solo dalla sua età, ma anche dalle sue caratteristiche intrinseche. Un "latecomer" (nodo arrivato dopo) può superare nodi più vecchi se possiede qualità superiori.
## Il Modello Bianconi-Barabasi (Fitness Model)

Per superare i limiti del modello BA, viene introdotto il concetto di **Fitness** ($\eta$). La fitness rappresenta una proprietà intrinseca del nodo (es. la qualità di un servizio, l'attrattiva di un sito web) che lo spinge avanti rispetto agli altri indipendentemente dall'età.

Il Modello Bianconi-Barabasi (BB) modifica il meccanismo di attaccamento preferenziale introducendo questo fattore:

1.  **Growth:** Ad ogni timestep viene aggiunto un nuovo nodo $j$ con $m$ link. Al nodo viene assegnata una fitness $\eta_j$ scelta casualmente da una distribuzione di fitness $\rho(\eta)$. Una volta assegnata, la fitness non cambia nel tempo.
2.  **Preferential Attachment:** La probabilità che un link del nuovo nodo si connetta al nodo $i$ dipende dal prodotto del suo grado e della sua fitness:

$$\Pi_{i}=\frac{\eta_{i}k_{i}}{\sum_{j}\eta_{j}k_{j}}$$

![[Università/Magistrale/Comples Social Networks/Slides/6.pdf#page=7&rect=58,18,325,210|6, p.7]]

> [!caution] Osservazione
> La probabilità $\Pi_i$ cattura due aspetti fondamentali:
> * La dipendenza da $k_i$ riflette la **visibilità** del nodo (i nodi più connessi sono più visibili).
> * La dipendenza da $\eta_i$ riflette l'**attrattiva** intrinseca.
>
> Questo meccanismo permette a nodi giovani (basso $k$ iniziale) ma con alta fitness ($\eta$) di acquisire link molto più rapidamente dei nodi vecchi con bassa fitness.

## Dinamica dei Gradi nel Modello BB

Utilizzando la teoria del continuo, possiamo descrivere l'evoluzione temporale del grado di un nodo $i$ nel modello Bianconi-Barabasi. Il tasso di variazione del grado è dato da:

$$\frac{\partial k_{i}}{\partial t} = m \Pi_{i} = m \frac{\eta_{i}k_{i}}{\sum_{j}\eta_{j}k_{j}}$$

Assumendo che l'evoluzione temporale segua una legge di potenza dipendente dalla fitness, si ottiene:

$$k_{}(t, t_{i}, \eta_{i}) = m \left( \frac{t}{t_{i}} \right)^{\beta(\eta_{i})}$$
Con $t_{i}$ istante di tempo in cui il nodo è stato inserito nella rete.

In quest'espressione l'**esponente dinamico** $\beta(\eta)$ non è più costante (come $1/2$ nel modello BA), ma dipende dalla fitness del nodo specifico:

$$\beta(\eta) = \frac{\eta}{C} \quad \text{con } C = \int \rho(\eta) \frac{\eta}{1-\beta(\eta)} d\eta$$

> [!caution] Osservazione
> **Confronto BA vs BB:**
> * Nel modello BA, $\beta = 1/2$ per tutti i nodi.
> * Nel modello BB, $\beta(\eta) \propto \eta$.
>
> Ciò significa che un nodo con fitness $\eta$ maggiore avrà un esponente $\beta$ più alto e quindi aumenterà il suo grado più velocemente. Col tempo, i nodi con fitness più elevata "lasceranno indietro" i nodi con fitness minore, anche se questi ultimi sono più vecchi. Questo spiega matematicamente come aziende come Facebook (latecomer con alta fitness) possano diventare hub dominanti.

