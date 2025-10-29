I network costituiscono la base di quasi tutti i sistemi reali biologici, tecnologici, sociali e ingegneristici.
# Robustezza

Si definisce *Robustezza* la capacità della rete di continuare a funzionare anche in presenza di guasti o rimozioni di nodi.

La struttura del network è ciò che ne determina la sua sopravvivenza:

- Hub: (nodi altamente connessi) mantengono la coesione;

- Ridondanza: offre percorsi alternativi;

- Clustering: (connessioni locali dense) limita la frammentazione;


> [!caution] Nota
> Gli errori e i guasti sono inevitabili in qualsiasi sistema, nonostante ciò, **molti sistemi naturali e sociali mostrano una sorprendente capacità di mantenere le proprie funzioni anche quando alcuni componenti falliscono**. **Non è il singolo nodo** a determinare la sopravvivenza di una rete, ma **l’organizzazione complessiva dei collegamenti**
> 
## Percolation Theory

![[Pasted image 20251029153143.png|400]]

I grafi rappresentano dei **Random Networks**, caratterizzate dall’assenza di veri e propri hub.  
La figura mostra l’effetto della **rimozione progressiva di nodi** sulla connettività della rete.
La **rimozione di un nodo qualsiasi** (come quello evidenziato in verde) comporta l’eliminazione automatica di tutti gli archi ad esso collegati.  
Questo processo, anche se applicato a un numero limitato di nodi, può determinare una **riduzione significativa della connettività complessiva**, fino a provocare la **frammentazione** del grafo in **più sottocomponenti isolate**.

> [!caution] Nota
> In molte reti reali, la perdita di un singolo nodo ha effetti limitati; ma la perdita di **nodi altamente connessi (hub)** può provocare un **collasso improvviso**.

## Percolazione

La **teoria della percolazione** descrive il modo in cui la **connettività di un sistema** emerge gradualmente man mano che aumenta la **probabilità p** che due nodi siano connessi.

![[Pasted image 20251029160441.png|700]]

- Per **valori bassi di p (es. p = 0.1)**, la rete contiene solo **piccoli cluster isolati** (figura a)
- Quando **p supera un valore critico pₙ**, questi piccoli cluster iniziano a **fondersi**, dando origine a una **componente gigante** che attraversa l’intera rete (figura b)

In corrispondenza di $p_c$ si osserva quindi una **transizione di fase**: il sistema passa da una condizione disconnessa a una condizione globalmente connessa.

>[!caution] Nota
> Come esattamente per i modelli Random Networks, esperimenti diversi, danno risultati diversi. Quindi con la stessa probabilità ogni volta si otterranno componenti diverse.

### Emergence and Disappearance of Large-Scale Connectivity

La **transizione di percolazione** è il fenomeno di **comparsa e scomparsa della connettività globale** in una rete soggetta a **rimozione casuale di nodi o link**.

Definiamo come *Percolation Threshold* $p_c$ la soglia critica oltre la quale la rete passa da uno stato frammentato ad uno stato connesso.

- Per $p < p_c$ : i nodi sono riuniti in piccoli cluster isolati $\rightarrow$ **assenza di connettività globale**.

- Per $p > p_c$ : compare una **componente gigante** che connette la maggior parte dei nodi $\rightarrow$ **rete "percolante"**.
 
Definiamo come *Critical Exponents*:
$$\langle s \rangle \sim |p - p_c|^{-\gamma}$$

Con $p$ probabilità attuale, $p_c$ probabilità critica e $\gamma$ parametro discriminante, la dimensione media dei cluster finiti.
Cresce rapidamente all’avvicinarsi di $p_c$ $\rightarrow$ diverge al punto critico ([[Andamento all'aumentare di p_c|figura c]])

$$P_{\infty} \sim (p - p_c)^{\beta}$$

Con $\beta$ come parametro discriminante, la probabilità che un nodo scelto casualmente appartenga alla componente gigante.  
Per $p < p_c$ vale 0, mentre per $p > p_c$ aumenta rapidamente ([[Andamento all'aumentare di p_c|figura d]])

$$\xi \sim |p - p_c|^{-\nu}$$

Con $\nu$ come parametro discriminante, la distanza media fra nodi appartenenti allo stesso cluster.
Al punto $p_c$ , ξ diverge: l’intera rete diventa interconnessa

>[!caution] Nota
 >La **transizione di percolazione** rappresenta la **soglia di robustezza strutturale** di una rete: sotto $p_c$ il sistema è frammentato e vulnerabile, sopra $p_c$ diventa robusto e capace di mantenere la propria funzionalità globale.  
È un fenomeno **universale**, analogo alle transizioni di fase in fisica (come il passaggio acqua–ghiaccio), che descrive come la **struttura di un network determina la sua resilienza** a errori o attacchi.

>[!danger] Importante
>La soglia critica $p_c$ **dipende dalla dimensionalità del sistema**: al crescere della dimensione, diminuisce la frazione di nodi necessari per ottenere la connettività globale. 
>- In **2D (reticolo quadrato)**: $p_c$ ≈ 0.593
>- In **3D (reticolo cubico)**: $p_c$ ≈ 0.3116
Questo accade perché, in dimensioni maggiori, **ogni nodo può connettersi a un numero più elevato di vicini**, aumentando le probabilità di formare un cluster percolante

## Inverse Percolation Transition and Robustness


