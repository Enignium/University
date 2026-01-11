## Grado

Si definisce grado il numero di collegamenti che un determinato nodo di una rete  verso gli altri nodi.

Il nodo $k_{i}$ sarà il grado dell'$i-esimo$ nodo della rete.

![[Università/Magistrale/Complex Social Networks/Slides/2.pdf#page=2&rect=102,99,267,164|pdf2, p.2|550]]

In questo caso sarà $k_{1}=2,k_{2}=3,k_{3}=2,k_{4}=1$ 

Nelle reti dirette si differenzia:

- Grado in ingresso $k_{i}^{in}$ rappresentante il numero di collegamenti in entrata al nodo $i$. 
- Grado in uscita $k_{i}^{out}$ rappresentante il numero di collegamenti in uscita dal nodo $i$.

Il grado totale del nodo $i$ sarà dato da:
$$k_{i}=k_{i}^{in}+k_{i}^{out}$$

### Numero totale di collegamenti in una rete non diretta
In una rete non diretta, il numero totale di collegamenti $L$ può essere espresso come un mezzo per la somma dei gradi di ciascun nodo :
$$L=\frac{1}{2}\sum_{i=1}^Nk_{i}$$

> [!intuito] Intuito
> Il fattore $\frac{1}{2}$ corregge il fatto che in un grafo indiretto nella somma dei gradi di ciascun nodo ogni collegamento è contato due volte (una volta per ciascun nodo che collega). 

### Grado medio 

Per le reti non dirette si definisce il grado medio come la media aritmetica dei gradi , esprimibile come:
$$\langle k \rangle = \frac{1}{N}\sum_{i=1}^Nk_{i}=\frac{2L}{N}$$

> [!dimostrazione]- Dimostrazione
> [[#Numero totale di collegamenti in una rete non diretta|Data]] $L=\frac{1}{2}\sum_{i=1}^Nk_{i}$ sostituendo in $\langle k \rangle = \frac{1}{N}\sum_{i=1}^Nk_{i}$, essendo $\sum_{i=1}^Nk_{i}=2L$ sarà:$$\langle k \rangle = \frac{2L}{N}$$

### Distribuzione dei gradi 

La funzione **distribuzione dei gradi** $p_{k}$ fornisce la probabilità che un nodo selezionato nella rete abbia grado $k$. 

Essendo un valore di probabilità sarà normalizzata.

**Per una rete con $N$ nodi la distribuzione dei gradi è un istogramma normalizzato dato da:**
$$p_k=\frac{N_{k}}{N}$$
Con $N_{k}$ numero di nodi di grado $k$ ed $N$ numero di nodi totali. 

![[Università/Magistrale/Complex Social Networks/Slides/2.pdf#page=8&rect=53,11,321,210|pdf2, p.8|450]]

## Massimo numero di collegamenti 

In una rete indiretta di $N$ nodi il numero di collegamenti può variare da un minimo di $L_{min}=0$ ad un massimo di:
$$L_{max}=\frac{N(N-1)}{2}$$

> [!dimostrazione]- Dimostrazione
>
> Immaginiamo di dover costruire un **Grafo Completo** (tutti collegati con tutti).
>
> **Passaggio 1: I collegamenti per ogni nodo**
> Prendiamo un singolo nodo. Se ci sono $N$ nodi in totale, questo nodo può collegarsi ad altri $(N - 1)$ nodi (non può collegarsi a se stesso).
>
> **Passaggio 2: La somma provvisoria**
> Se ripetiamo questo ragionamento per tutti gli $N$ nodi, sembrerebbe che il totale dei collegamenti sia:
> $$\text{Collegamenti Totali?} = N \times (N - 1)$$
>
> **Passaggio 3: Il problema del doppio conteggio**
> C'è un problema: in una rete non orientata (senza frecce), il collegamento tra il nodo $A$ e il nodo $B$ è lo stesso del collegamento tra $B$ e $A$.
>
> Nel calcolo al passaggio 2, abbiamo contato ogni filo due volte:
> 1. Una volta partendo da $A$ verso $B$.
> 2. Una volta partendo da $B$ verso $A$.
>
> **Passaggio 4: La correzione finale**
> Per ottenere il numero reale di link unici, dobbiamo dividere il totale per 2:
>
> $$L_{max} = \frac{N(N - 1)}{2}$$
>
> **Nota Matematica (Calcolo Combinatorio)**
> Formalmente, questo corrisponde al coefficiente binomiale "N su 2" ($\binom{N}{2}$), ovvero il numero di modi possibili per scegliere una coppia di nodi distinti in un gruppo di $N$.

**Si definisce una rete sparsa quando il numero di collegamenti è estremamente ridotto rispetto al numero massimo di collegamenti possibili tra i nodi.**

## Reti pesate

Una rete pesata è una rete in cui a ciascun collegamento $(i,j)$ si associa un peso unico $w_{i,j}$ 

## Reti bipartite

Una rete bipartita è una rete i quali nodi possono essere divisi in due insiemi disgiunti $U$ e $V$ in modo tale che ciascun collegamento associ ad un nodo del gruppo $U$ un nodo del gruppo $V$. 

È possibile generare per ciascuna rete bipartita due proiezioni:

- La prima collega insieme i nodi dell'insieme $U$ che sono collegati allo stesso nodo dell'insieme $V$.
- La seconda collega insieme i nodi dell'insieme $V$ che sono collegati allo stesso nodo dell'insieme $U$.

![[Università/Magistrale/Complex Social Networks/Slides/2.pdf#page=22&rect=36,27,314,210|pdf2, p.22|550]]

## Percorsi e Distanze

Nelle reti la distanza è rappresentata dalla lunghezza del percorso che collega due nodi attraversando i collegamenti della rete. 

**La lunghezza di un percorso è definita dal numero di collegamenti che il percorso contiene.**

Valgono per i percorsi: 
- Il percorso più corto tra due nodi $i$ e $j$ è il percorso con il numero minore di collegamenti. Questo viene indicato come **distanza tra i due nodi** $i$ e $j$ espresso come $d_{i,j}$
- È possibile avere multipli percorsi più corti della stessa lunghezza tra un paio di nodi.
- In una rete indiretta $d_{i,j}=d_{j,i}$.
- In una rete diretta l'esistenza di un percorso dal nodo $i$ al nodo $j$ non garantisce l'esistenza di un percorso dal nodo $j$ al nodo $i$. 

**Si definisce diametro di una rete $d_{max}$ il massimo percorso più corto presente, ovvero la distanza registrata più grande tra ogni coppia di nodi.**

Si definisce lunghezza media del percorso $\langle d \rangle$ come la distanza media tra tutte le coppie di nodi nella rete. 

![[Università/Magistrale/Complex Social Networks/Slides/2.pdf#page=27&rect=59,47,304,175|pdf2, p.27]]

### Connettività (Connectedness)

**Due nodi $i$ e $j$ si definiscono connessi se esiste un percorso tra di loro**. La distanza tra due nodi disconnessi è definita essere $d_{i,j}=\infty$. 

**Una rete è connessa se tutte le coppie di nodi della rete sono connesse.**

Una rete è disconnessa se esiste almeno una coppia di nodi $i,j$ per cui $d_{i,j}=\infty$. 

Se una rete è disconnessa le sue sottoreti si definiscono *componenti* o *cluster*. 

Data una rete composta da due componenti, **si definisce ponte il collegamento che consente di rendere la rete connessa collegando le due componenti**.  

![[Università/Magistrale/Complex Social Networks/Slides/2.pdf#page=30&rect=35,59,241,167|pdf2, p.30]]

## Coefficiente di clustering

Il coefficiente di clustering indica quanto i vicini di un nodo $i$ siano collegati tra loro. 

Per un nodo $i$ di grado $k_{i}$ definiamo coefficiente di clustering locale:
$$C_{i}=\frac{2L_{i}}{k_{i}(k_{i}-1)}$$
Dove $L_{i}$ rappresenta il numero di collegamenti tra i $k_{i}$ vicini del nodo $i$.

> [!dimostrazione]- Dimostrazione
> Il coefficiente $C_i$ misura la "coesione" dei vicini del nodo $i$. È definito come il rapporto tra i collegamenti esistenti e quelli massimi possibili tra i vicini.  
> **Passaggio 1: Definire i Vicini** > Il nodo $i$ ha un grado $k_i$, il che significa che ha **$k_i$ vicini**. 
> **Passaggio 2: Contare i collegamenti reali ($L_i$)** > $L_i$ è il numero di collegamenti che esistono *effettivamente* tra questi $k_i$ vicini (esclusi i collegamenti con $i$ stesso).
> **Passaggio 3: Calcolare i collegamenti massimi possibili** > Se tutti i $k_i$ vicini fossero collegati tra loro (formando una "clique" o grafo completo), quanti collegamenti avremmo? > Usiamo la formula vista prima per $L_{max}$, applicata però al numero di vicini $k_i$: > $$L_{max\_vicini} = \frac{k_i(k_i - 1)}{2}$$
> **Passaggio 4: Costruire il Rapporto** > Il coefficiente è la frazione tra realtà e possibilità: > $$C_i = \frac{\text{Collegamenti Reali}}{\text{Collegamenti Possibili}} = \frac{L_i}{\frac{k_i(k_i - 1)}{2}}$$
> **Passaggio 5: Semplificazione Algebrica** > Per togliere la frazione al denominatore, moltiplichiamo numeratore e denominatore per 2: > > $$C_i = \frac{2 \cdot L_i}{k_i(k_i - 1)}$$ 

> [!intuito] intuito 
> **$C_i = 1$**: Tutti i vicini sono collegati tra loro (massima coesione). $C_i = 0$**: Nessun vicino è collegato con un altro vicino (struttura a stella).
> 
> Questo valore rappresenta la probabilità che due vicini di un nodo siano collegati tra di loro.
> **È una misura della densità locale della rete**

Si definisce coefficiente di clustering medio $\langle C \rangle$ la media aritmetica dei coefficienti di clustering di ciascun nodo della rete:
$$\langle C \rangle = \frac{1}{N}\sum_{i=1}^N  C_{i}$$
Questa grandezza cattura il grado di clustering dell'intera rete.

![[Università/Magistrale/Complex Social Networks/Slides/2.pdf#page=33&rect=76,21,278,114|pdf2, p.33]]
