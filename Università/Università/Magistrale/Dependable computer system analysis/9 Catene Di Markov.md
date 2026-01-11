
## Processi stocastici 

Un processo stocastico $X(t)$ è considerabile una **famiglia** di variabili aleatorie caratterizzate da un parametro $t$,  al variare del quale varierà la distribuzione della variabile aleatoria.

Si intende una realizzazione legata ad un esito $\omega$ del processo $X(t,\omega)$  una sequenza concreta di stati che si ottiene eseguendo il processo.

> [!caution] Osservazione
> Per un dato $t$, la distribuzione di $X(t)$ sarà la stessa per tutte le realizzazioni.

Ciascun valore concreto della variabile aleatoria per una realizzazione specifica $\omega$ di $X(t)$ è detto stato e quando il valore di $X(t,\omega)$ cambia avviene una **transizione di stato**. 

> [!info] Proprietà
> Valgono per i processi stocastici le seguenti affermazioni:
> - Gli stati possono essere continui o discreti essendo dipendenti dalla caratterizzazione dello spazio campione.
> - Quando lo spazio campione è discreto il processo stocastico è chiamato **catena**.
> - Il parametro $t$ può assumere valori continui o discreti.

> [!example]- Esempio
> 
> Consideriamo un sacchetto in cui:
> - A valori di $t$ dispari aggiungiamo una pallina verde, a $t$ pari una rossa.
> - Estraiamo una pallina a caso al tempo $t$e la osserviamo.
> 
> Definiamo il processo stocastico $X(t)$ estratto al tempo $t$.
> 
> - **Stato**: valore concreto estratto in un esperimento specifico, es. X(2, ω₁) = rossa.
> - **Realizzazione**: sequenza completa di stati in un esperimento, es. ω₁ = (verde, rossa, verde,...), ω₂ = (verde, verde, rossa,...).
> - La **distribuzione** di X(t) è la stessa per tutti gli esperimenti, ma gli stati concreti possono differire.

## Catene di Markov

Considerati:
- $X(t)$ un processo stocastico a stati discreti
- $P[X(t_{n})=j]$ la probabilità che il processo sia nello stato $j$ all'istante $t_{n}$

Il processo $X(t)$ è detto una catena di Markov quando:
$$P[X(t_{n})=j|X(t_{n-1})=i_{n-1},X(t_{n-2})=i_{n-2},\dots,X(t_{0})=i_{0}]=P[X(t_{n})=j|X(t_{n-1})=i_{n-1}]$$

Per cui la probabilità di trovarsi nello stato $j$ al tempo $t_n$​ dipende **solo dallo stato immediatamente precedente** $i_{n-1}$ e gli stati assunti negli istanti ancora precedenti non influenzano la probabilità di raggiungere il prossimo stato. 

> [!intuito] Intuito
>  Lo stato presente contiene tutta l’informazione necessaria per predire il futuro immediato del processo: questa è la proprietà fondamentale di Markov, o **memorylessness**.

La catena di Markov è detta omogenea quando:
$$
P[X(t+\tau)=j \mid X(t)=i] = P[X(\tau)=j \mid X(0)=i]
$$
Per cui la probabilità dipende solo dall’intervallo $\tau$ non dal tempo assoluto $t$.

> [!intuito] Intuito
> La probabilità di passare ad un certo stato dipende solo dall'intervallo $\tau$ e non da quando si inzia l'osservazione.

> [!example]- Esempio
> 
> Consideriamo un processo stocastico a stati discreti {A, B} che evolve a passi di $\tau=1$ secondo:
> - Se il processo è nello stato A, passa a B con probabilità 0.3 o resta in A con probabilità 0.7.
> - Se il processo è nello stato B, passa a A con probabilità 0.4 o resta in B con probabilità 0.6.
> 
> Questa catena è **omogenea** perché le probabilità di transizione **non cambiano nel tempo**.  
> Ad esempio, la probabilità di passare da A a B tra t=0 e t=1 è 0.3, così come tra t=5 e t=6 o tra t=100 e t=101.  
> 
> - **Stati:** A, B  
> - **Transizioni:** dipendono solo dallo stato attuale, non dal tempo assoluto  
> - **Proprietà di Markov:** memoria corta → lo stato futuro dipende solo dallo stato attuale.

Nelle **catene di Markov continue nel tempo**, il tempo trascorso in uno stato prima di fare una transizione spesso segue una **distribuzione esponenziale decrescente**.

Se il tempo di soggiorno in ogni stato non segue una distribuzione esponenziale, non è possibile utilizzare una catena di Markov per modella il sistema, se non introducendo un approssimazione utilizzando il tempo medio, se noto, di soggiorno in ciascuno stato, come parametro della distribuzione esponenziale che lo rappresenterebbe nella catena di Markov.
### Computazione

Considerata  una catena di Markov **omogenea** con: 
- $p_{i}(t)=P[X(t)=i]$ la probabilità che la catena di Markov sia nello stato $i$ all'istante $t$ n.

Si memorizza nel vettore $p(t)$ la probabilità che il sistema sia in ciascuno stato in un istante generico $t$: $$p(t)=[p_{0}(t),p_{1}(t),\dots,]$$
Si vuole valutare la probabilità che la catena **sia nello stato $j$ all’istante $t$**, sapendo che fosse nello stato $i$ all’istante $u$:
$$P_{i,j}(t-u)=P[X(t )=j|X(u)=i]$$
> [!caution] Osservazione
> L’intervallo $t-u$ indica solo la durata tra le due osservazioni, non l’istante preciso in cui la transizione è avvenuta.

È possibile inserire queste probabilità in una matrice di transizione delle probabilità in cui ciascun elemento in posizione $i,j$ è nella forma:
$$P(\tau)=[P_{i,j}(\tau
)]$$
Questa matrice contiene tutte le probabilità che la catena sia in uno stato $j$ dopo un certo intervallo di tempo $\tau$ partendo dallo stato $i$.
> [!example]- Esempio
> 
> Consideriamo una catena di Markov omogenea a tre stati: $S = \{A, B, C\}$.  
> Ogni $\tau = 2$ secondi viene osservato lo stato.  
> Se siamo nello stato $A$ → probabilità di restare in $A$ = 0.5, passare a $B$ = 0.3, passare a $C$ = 0.2.  
> Se siamo in $B$ → probabilità di restare in $B$ = 0.6, andare in $A$ = 0.1, andare in $C$ = 0.3.  
> Se siamo in $C$ → probabilità di restare in $C$ = 0.7, andare in $A$ = 0.2, andare in $B$ = 0.1.  
> 
> Matrice di transizione $P(\tau)$ (riga = stato attuale, colonna = stato futuro dopo $\tau$):  
> $$
> P(2) = 
> \begin{pmatrix}
> P_{A,A}(2) & P_{A,B}(2) & P_{A,C}(2) \\
> P_{B,A}(2) & P_{B,B}(2) & P_{B,C}(2) \\
> P_{C,A}(2) & P_{C,B}(2) & P_{C,C}(2)
> \end{pmatrix}
> =
> \begin{pmatrix}
> 0.5 & 0.3 & 0.2 \\
> 0.1 & 0.6 & 0.3 \\
> 0.2 & 0.1 & 0.7
> \end{pmatrix}
> $$
> 


Le equazioni di Chapman-Kolmogorov mostrano la probabilità di passare ad un generico stato stato $j$ in un istante $t$  **senza imporre che parta da un singolo stato specifico** come:
$$p_{j}(t)=p_{0}P_{0,j}(t-u)+p_{1}(u)P_{1,j}(t-u)+\dots+p_{n}(u)P_{n,j}(t-u)$$
> [!caution] Osservazione
> È un applicazione del [[1 Introduzione alla teoria delle Probabilità#Teorema della probabilità totale|teorema della probabilità totale]].

È possibile esprimerla in forma matriciale come:
$$p(t)=p(u)\cdot P(t-u)$$
**Ottenendo così un vettore con ciascun elemento corrispondente alla probabilità di raggiungere lo stato corrispondente in un istante $t$. **

> [!example]- Esempio
> 
> Consideriamo una catena di Markov con due stati $S = \{A, B\}$ e matrice di transizione dopo un intervallo di tempo $t-u = 1$:
> $$
> P(1) =
> \begin{pmatrix}
> 0.8 & 0.2 \\
> 0.3 & 0.7
> \end{pmatrix}
> $$
> 
> Supponiamo che all’istante $u = 0$ la distribuzione delle probabilità sugli stati sia:
> $$
> p(0) = [0.6,\ 0.4]
> $$
> cioè il sistema si trova nello stato $A$ con probabilità 0.6 e nello stato $B$ con probabilità 0.4.
> 
> Applicando la relazione:
> $$
> p(1) = p(0) \cdot P(1)
> $$
> otteniamo:
> $$
> p(1) = [0.6,\ 0.4]
> \begin{pmatrix}
> 0.8 & 0.2 \\
> 0.3 & 0.7
> \end{pmatrix}
> =
> [0.6\times0.8 + 0.4\times0.3,\ 0.6\times0.2 + 0.4\times0.7]
> =
> [0.6,\ 0.4]
> $$
> 
> In questo caso la distribuzione rimane invariata dopo un passo: il sistema ha raggiunto una **distribuzione stazionaria**.

### Catene di Markov tempo discrete

Nel caso **a tempo discreto**, il processo evolve solo in **istanti distinti** $t_0, t_1, t_2, \dots$.  

Per definire la **matrice di transizione costante** e applicare comodamente l’equazione di Chapman-Kolmogorov, ci concentriamo sul **singolo passo** del processo, cioè sulla probabilità di transizione da uno stato all’altro tra $t_n$ e $t_{n+1}$.  

Poiché in una catena **omogenea** tali probabilità non cambiano nel tempo, la matrice di transizione risulta costante:
$$
P = P(1) \quad 
$$

Sarà dunque possibile esprimere l’equazione di **Chapman-Kolmogorov** per un passo come:
$$
p(n+1) = p(n) \cdot P
$$
Iterando nel tempo discreto sarà possibile ottenere il vettore delle probabilità ad un istante generico $n$ come:
$$
p(n) = p(0) \cdot P^n
$$
Con $P^n$ che rappresenterà la matrice di transizione ad $n$ step dall'osservazione: $P(n)$
> [!dimostrazione]- Dimostrazione
> 
> Consideriamo una catena di Markov a tempo discreto con distribuzione iniziale $p(0)$ e matrice di transizione $P$.
> 
> Per un **passo singolo**:
> $$
> p(n+1) = p(n) \cdot P
> $$
> 
> Iterando questa relazione, otteniamo la distribuzione dopo più passi:
> 
> 1. Dal passo 0 al passo 1:
> $$
> p(1) = p(0) \cdot P
> $$
> 2. Dal passo 1 al passo 2:
> $$
> p(2) = p(1) \cdot P = p(0) \cdot P^2
> $$
> 3. Dal passo 2 al passo 3:
> $$
> p(3) = p(2) \cdot P = p(0) \cdot P^3
> $$
> 
> In generale, dopo $n$ passi:
> $$
> p(n) = p(0) \cdot P^n
> $$

> [!example]- Esempio
> 
> Se al tempo iniziale $p(0) = [1,\,0]$ e
> $$
> P = 
> \begin{pmatrix}
> 0.7 & 0.3 \\
> 0.4 & 0.6
> \end{pmatrix},
> $$
> allora dopo un passo:
> $$
> p(1) = p(0) \cdot P = [0.7,\,0.3],
> $$
> e dopo due passi:
> $$
> p(2) = p(0) \cdot P^2 = [0.61,\,0.39].
> $$

#### Stato stazionario

Quando la catena raggiunge lo **stato stazionario**, per $n\to \infty$ il vettore che contiene le probabilità di passare a ciascuno stato a prescindere dallo stato di partenza $p(n)$ non varia più nel tempo e sarà con $p=\lim_{ n \to \infty }p(n)$:
$$
p(n+1) = p(n) \Rightarrow p = p \cdot P
$$
Quest’equazione rappresenta un **sistema lineare** di equazioni **linearmente dipendenti**, poiché le incognite sono probabilità.  

Per ottenere una soluzione unica si aggiunge l’**equazione di normalizzazione**, dove $e$ è un vettore colonna di soli $1$:
$$
p \cdot e = 1
$$

> [!intuito] Intuito
> Questa equazione impone che la somma di tutte le probabilità di passaggio ai singoli stati una volta raggiunto il regime stazionario sia uguale ad $1$.

La soluzione di questo sistema ci consente di ottenere il vettore $p$ in condizioni stazionarie.
### Catene di Markov tempo continue

Dalle equazioni di Chapman-Kolmogorov:
$$p(t)=p(u)\cdot P(t-u)$$
Sarà possibile trovare il vettore delle probabilità ad un istante generico $t$ come:  $$\frac{dp(t)}{dt}=p(t)Q$$
> [!dimostrazione]- Dimostrazione
> Considerato $u=t-\Delta t$ e sottraendo entrambi i termini per $p(t-\Delta t)$ sarà:
> $$p(t)-p(t-\Delta t)=p(t-\Delta t)\cdot P(\Delta t)-p(t-\Delta t)$$
> Sarà con $I$ matrice identità e fattorizzando il secondo termine allora:$$p(t)-p(t-\Delta t)=p(t-\Delta t)(P(\Delta t)-I)$$
> Dividendo tutto per $\Delta t$:
> $$\frac{p(t)-p(t-\Delta t)}{\Delta t}=\frac{p(t-\Delta t)\cdot [P(\Delta t)- I]}{\Delta t}$$
> Facendo il limite per $\Delta t\to 0$ 
> 
>  Il primo termine sarà la derivata di $p$ rispetto a $t$ per cui:
>  $$\frac{dp(t)}{dt}=p(t)Q$$

 Questo è un sistema di equazioni differenziali lineari.
#### Stato stazionario 

Quando la catena raggiunge lo **stato stazionario**, per $t\to \infty$ il vettore che contiene le probabilità di passare a ciascuno stato a prescindere dallo stato di partenza $p(t)$ non varia più nel tempo e sarà con  $p=\lim_{ t \to \infty}p(t)$:
$$\lim_{ t \to \infty } \frac{dp(t)}{dt}=\lim_{ t \to \infty }p(t)\cdot Q$$
All'infinito la derivata sarà $0$ non variando più il vettore $p(t)$, per cui si ottiene un sistema di equazioni differenziali linearmente dipendenti, alla quale si aggiunge un equazione indipendente, la funzione di normalizzazione, per cui sarà: 
$$\begin{cases}0=p\cdot Q\\
p\cdot e=1
\end{cases}$$
> [!caution] Osservazione
> Si esclude la soluzione del sistema per cui $p=0$ in quanto non avrebbe significato fisico.

### La matrice Q

### Matrice dei tassi di transizione

Ciascun elemento della **matrice generatrice infinitesimale** $Q$ si definisce come limite del rapporto incrementale della matrice di transizione $P(\Delta t)$:
$$
q_{ij}=\lim_{ \Delta t \to 0 } \frac{P_{ij}(\Delta t)-\delta_{ij}}{\Delta t}
$$
dove $\delta_{ij}$ è la **delta di Kronecker** tale che:
$$
\delta_{ij} =
\begin{cases}
1 & \text{se } i=j \\
0 & \text{se } i\ne j
\end{cases}
$$

Per intervalli di tempo piccoli $\Delta t$, si ha l’approssimazione:
$$
q_{ij}\cdot \Delta t\simeq P_{ij}(\Delta t)-\delta_{ij}
$$

Quando $i=j$:
$$
q_{ii}\cdot \Delta t \simeq P_{ii}(\Delta t)-1
$$
$$
-\,q_{ii}\cdot \Delta t \simeq 1-P_{ii}(\Delta t)
$$

> [!intuito]
> Il termine $-q_{ii}$ rappresenta il **tasso con cui il processo lascia lo stato $i$**, detto anche **tasso di uscita** (*exit rate*) dallo stato $i$.

Quando $i\neq j$:
$$
q_{ij}\cdot\Delta t\simeq P_{ij}(\Delta t)
$$

> [!intuito]
> In questo caso, $q_{ij}$ rappresenta il **tasso con cui il processo passa dallo stato $i$ allo stato $j$** per unità di tempo.

> [!info] Proprietà
> Valgono per i processi stocastici le seguenti affermazioni:
> - Gli **elementi fuori diagonale** sono **non negativi**:
>   $$
>   q_{ij} \ge 0 \quad \text{per } i \ne j
>   $$
>   poiché $q_{ij}\,\Delta t$ rappresenta una probabilità di transizione.  
> - Gli **elementi diagonali** sono **non positivi**:
>   $$
>   q_{ii} \le 0
>   $$
>   e ciascuna riga della matrice soddisfa la condizione:
>   $$
>   \sum_j q_{ij} = 0
>   $$
>   cioè la somma dei tassi di uscita e ingresso associati a ciascuno stato è nulla.

> [!intuito]
> La matrice $Q$ descrive la **dinamica istantanea** del processo continuo:  
> gli elementi positivi $q_{ij}$ (fuori diagonale) rappresentano i tassi di transizione tra stati distinti,  
> mentre i valori negativi $q_{ii}$ sulla diagonale garantiscono la **conservazione della probabilità totale** nel tempo.

## Classificazione degli stati

Si definisce stato transitorio uno stato nel quale ci saranno un numero di visite limitate su un intervallo di tempo infinito.

SI definisce stato ricorrente uno stato non transitorio.
A partire dallo stato $i$ il processo ritorna ad $i$ con probabilità $1$.
Lo stato è visitato all'infinito su un intervallo di tempo finito.
Sarà:
- Ricorrente non nullo quando il primo tempo di ritorno è feniti
- Ricorrente nullo quando il tempo tra due visite non è finito.


Si definisce stato assorbente uno stato che non può essere lasciato una volta raggiunto.

## Caratterizzazione catene di Markov
*sistemare*
Una catena di Markov  è detta irriducibile se ogni stato è raggiungibile dagli altri.
Una catena di Markov ha è irriducibile se tutti i suoi stati sono ricorrenti.

Una catena di markov è detta aciclica cse è possibile trovare degli stati nel processo che dopo essere stati visitati non possono essere più raggiunti.
Una catena è detta ergodica se è irriducibile e ricorrente non nulla.
