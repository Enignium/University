Le catene di Markov consentono la modellazione di processi stocastici in cui è presente dipendenza tra gli stati per lo studio di valutazione di indicatori di performance, tuttavia la loro natura rende la rappresentazione complessa e poco intuitiva, **soprattutto per sistemi con un vasto spazio di stati**.

## Definizione Reti di Petri

Le reti di Petri sono uno strumento per rappresentare l'evoluzione temporale di un sistema capace di modellare interazioni come:

- Sincronizzazione
- Sequenze
- Concorrenze
- Conflitti

Una rete di Petri è definita come una [[Liste#Liste|n-upla]]:
$$PN=\{ P,T,I,O,M_{0} \}$$
Con:
- $P$: insieme di $n_{P}$ posti.
- $T$: insieme di $n_{T}$ transizioni.
- $I$: insieme di funzioni di input.
- $O$: insieme di funzioni di output. 
- $M_{0}=\{ m_{1},m_{2},\dots,m_{n_{P}} \}$  marcatura iniziale. 


> [!check] Nota Pratica
>  Ciascun posto viene rappresentato graficamente da un cerchio ed una transizione da una linea.


### Funzioni di Input e di Output 

Le funzioni di Input ed Output associano ad una transizione una borsa di elementi di $P$.    

Si definisce una funzione di input come:
$$I:T \to Bag(P)$$

Si definisce una funzione di output come:
$$O:T \to Bag(P)$$
> [!info] Chiarimento
> Una borsa  $Bag(A)$ è una collezione di elementi dell'insime $A$ che a differenza degli insiemi propriamente definiti ammette elementi ripetuti.
> Esempio:$$Bag(A)=\{ p_{1},p_{1},p_{4}\}=\{ p_{1}^{(2)},p_{4} \}=\{2,0,0,1\}$$

> [!intuito] Intuito
> Per una transizione le funzioni di Input definiscono quali sono i posti di ingresso.
> Per una transizione le funzioni di Output definiscono quali sono i posti di uscita.
> L'identificazione avviene attraverso l'indice del posto.

Si indicano:
- $I(t)$ la $bag$ di posti in input associati alla transizione $t$.
- O(t) la $bag$ di posti in output associati alla transizione $t$.
- Con $I(t,p)$ la molteplicità del posto $p$ nella $bag$ $I(t)$
- Con $O(t,p)$ la molteplicità del posto $p$ nella $bag$ $O(t)$
### Token 

Ciascun posto può contenere un certo numero di token. 

**La distribuzione di token rispetto ai posti identifica lo stato della rete di Petri**, rappresentato dalle marcature.

> [!check] Nota Pratica
>  Ciascun token viene rappresentato graficamente da un cerchio nero interno ad un posto.
### Marcature 

Le marcature sono $n-uple$ che associano a ciascun indice il numero di token presenti nel posto corrispondente:
$$M_{i}=\{ m_{1},m_{2},\dots,m_{n_{P}} \}$$
Con $m_{i}\in N$ numero di token nel posto $p_{i}$.

> [!example]- Esempio
> Esempio 1:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=11&rect=9,53,646,474|11, p.11]]
> Esempio 2:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=12&rect=142,96,526,431|11, p.12]]

### Regola di abilitazione

Si definisce una regola di abilitazione per la quale una transizione può essere attivabile o meno in un determinato stato.

Una transizione $t_{k}$ è abilitata in una marcatura $M_{i}$ se:

$$\forall p \in P_{I}(t_{k})\Rightarrow M_{i}(p)\geq I(t_{k},p)$$
Con $P_{I}(t_{k})$ insieme di posti in input della transizione $t_{k}$.

**Per cui una transizione $t_{k}$ è detta abilitata se nella marcatura $M_{i}$ se il numero di token nei suoi posti in input è maggiore o uguale al numero di archi in input.**
### Regola di attivazione (Firing rule)

Una transizione abilitata  in una marcatura $M_{i}$ può attivarsi producendo un cambio di marcatura verso una marcatura $M_{j}$ secondo la regola:
$$M_{j}=M_{i}-I(t_{k})+O(t_{k})$$

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=15&rect=8,27,692,480|11, p.15]]

Due transizioni si dicono:

- **In conflitto** se l'attivazione di una porta alla disabilitazione dell'altra.
- **Concorrenti** se l'attivazione di una non porta alla disabilitazione dell'altra.

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=17&rect=36,83,660,424|11, p.17]]

Il comportamento così definito rende le reti di Petri efficaci nella descrizione di interazioni durante l'evoluzione temporale della rete.

> [!example]- Esempio
> Rete di Petri per modellare la sincronizzazione:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=19&rect=195,73,528,403|11, p.19]]
> Rete di Petri per modellare la condivisione di risorse finite:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=20&rect=172,62,535,402|11, p.20]]
> Rete di Petri per modellare il processo produttore/consumatore:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=21&rect=83,81,660,415|11, p.21]]
> Rete di Petri per modellare la mutua esclusione:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=22&rect=53,45,679,431|11, p.22]]

### Archi inibitori

Introducendo il concetto di archi inibitori, aggiungendo l'insieme di funzioni di input inibitorie $H$ alla definizione di rete di Petri si ottiene:

$$PN=\{ P,T,I,O,H,M_{0} \}$$

Dove si definiscono le funzioni di input inibitorie come:
$$H:T\to Bag(P)$$

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=23&rect=26,88,538,409&color=red|11, p.23]]

**La presenza di archi inibitori porta all'aggiunta di un'altra regola di attivazione, per cui la transizione sarà attiva solo se entrambe saranno soddisfatte.**

Si aggiunge quindi la seguente regola di attivazione: 
$$\forall p \in P_{H}(t_{k})\Rightarrow M_{i}(p)<H (t_{k},p)$$
Con $P_{H}$ insieme dei posti in input tramite archi inibitori alla transizione $t_{k}$.

**Per cui ciascun posto in input tramite arco inibitorio dovrà avere meno token della molteplicità di archi corrispondenti.**

> [!danger] Attenzione
> La transizione sarà attiva solo se entrambe le regole di attivazione saranno soddisfatte! 
> Dunque dovrà valere:
> $$\forall p \in P_{I}(t_{k})\Rightarrow M_{i}(p)\geq I(t_{k},p)$$
> $$\forall p \in P_{H}(t_{k})\Rightarrow M_{i}(p)<H (t_{k},p)$$

> [!example]- Esempio
> Esempio di transizione disabilitata dalla regola di abilitazione per gli archi inibitori.
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=25&rect=121,119,613,418&color=red|11, p.25]]
> Esempio utilizzo rete di petri con archi inibitori per modellazione di comportamento di mutua esclusione con priorità:
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=26&rect=53,45,676,440&color=red|11, p.26]]

## Grafo di Raggiungibilità

**Da uno stato $M_{i}$ se è possibile raggiungere un nuovo stato $M_{j}$ tramite l'attivazione di una transizione $t_{k}\in T$ abilitata nello stato $M_{i}$ è detto che lo stato $M_{j}$ è raggiungibile da $M_{i}$**

È possibile  tracciare dall'attivazione ripetuta di transizioni un grafo di raggiungibilità rappresentante la dinamica della rete di Petri. 

**Uno stato $M_{i}$ è detto raggiungibile se dato uno stato iniziale $M_{0}$ esiste una sequenza di attivazione di transizioni che porta da $M_{0}$ a $M_{i}$.**

Si esprime una sequenza di attivazione come:
$$\epsilon=\{ (M_{0},t_{1});(M_{2},t_{2});\dots;(M_{i},t_{i}) \}$$
L'insieme di tutti gli stati raggiungibili da uno stato iniziale $M_{0}$ è detto insieme di raggiungibilità $RS(M_{0})$ 

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=30&rect=3,127,709,448&color=red|11, p.30]]

## Reti di Petri temporizzate

È possibile estendere la definizione delle reti di Petri aggiungendo alla definizione l'insieme di funzioni di temporizzazione $\Theta$:
$$TPN=\{ P,T,I,O,H,M_{0},\Theta \}$$
Con: $$\Theta:T \to R^+$$
Ciascuna di queste funzioni associa ad una transizione un ritardo temporale di attivazione.

Cambia così la definizione di una sequenza di attivazione che dovrà tenere conto della temporizzazione, considerando una transizione da $M_{i}$ a $M_{n}$ dunque sarà:
$$\epsilon=\{ (M_{i},t_{i},\tau_{i}),\dots,(M_{n},t_{n},\tau_{n}) \}$$

## Reti di Petri stocastiche

Le reti di Petri stocastiche sono reti di Petri temporizzate con ritardi di attivazione delle transizioni [[3 Variabili Aleatorie e distribuzioni di probabilità|variabili aleatorie]] con distribuzione esponenziale. 

Si definiscono così le reti di Petri stocastiche:
$$SPN=\{P,T,I,O,H,M_{0},L \}$$
Con $L:T\to R$  funzione che associa a ciascuna transizione $t_{i}$ il parametro $\lambda_{i}$ della distribuzione esponenziale della variabile aleatoria temporizzazione specifica per quella transizione.

> [!check] Nota pratica
> Le transizioni sono rappresentate graficamente come barre vuote.

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=33&rect=115,93,602,434&color=red|11, p.33]]

**Una volta campionato per ciascuna transizione dalla distribuzione esponenziale con il relativo parametro $\lambda_{i}$ il ritardo, si attiverà la transizione con il ritardo campionato più corto.**

> [!danger] Attenzione
> Dopo l'attivazione di una transizione bisogna ricampionare il ritardo per tutte le transizioni in quanto vale la proprietà di **mancanza di memoria**.
> 

Il grafo di raggiungibilità di una rete di Petri stocastica etichettando le transizioni con i relativi parametri $\lambda_{i}$ è una [[9 Catene Di Markov#Catene di Markov tempo continue|catena di Markov tempo continua]] e l'analisi della rete di petri può essere effettuata analogamente.

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=35&rect=33,109,685,426&color=red|11, p.35]]

## Reti di Petri stocastiche generalizzate

È possibile generalizzare le reti di Petri in modo tale da consentire sia la presenza di transizioni immediate che temporizzate. 

La definizione diventa: 
$$GSPN=\{ P,T,I,O,H,M_{0},L,c\}$$
Con $c:T\to N$ funzione che associa a ciascuna transizione una priorità rappresentata da un numero naturale.

Con questa definizione bisogna aggiungere un ulteriore regola di abilitazione:
$$\forall t\in T_{e}^{(i)}\Rightarrow c(t)\leq c(t_{k})\ con\ {t\neq t_k}$$
Con $T_{e}^{(i)}$ insieme di transizioni abilitate nella marcatura $M_{i}$.

> [!danger] Attenzione
> La transizione sarà attiva solo se tutte le regole di attivazione saranno soddisfatte! 
> Dunque dovrà valere:
> $$\forall p \in P_{I}(t_{k})\Rightarrow M_{i}(p)\geq I(t_{k},p)$$
> $$\forall p \in P_{H}(t_{k})\Rightarrow M_{i}(p)<H (t_{k},p)$$
> $$\forall t\in T_{e}^{(i)}\Rightarrow c(t)\leq c(t_{k})\ con\ {t\neq t_k}$$

**Per cui sarà abilitata solo la transizione con $c(t)$ minore, a cui sarà data la priorità**

Si assegna alle transizioni temporizzate un $c(t)=0$


> [!intuito] Intuito
> In uno stato in cui sarebbero abilitate sia transizioni temporizzate che transizioni immediate, le transizioni immediate risulteranno sempre disabilitate in quanto **sempre** meno prioritarie.

Si definisce:
- Una marcatura in cui sono abilitate transizioni immediate **effimera** (*vanishing*).
- Una marcatura in cui sono presenti solo transizioni temporizzate **tangibile**. 

Si associa a ciascuna transizione immediata un peso per far sì che dovessero esserne presenti molteplici abilitate nella stessa marcatura si attiverebbe quella selezionata tramite una scelta probabilistica effettuata sulla base dei pesi: 
$$s_{k}^{(i)}=P\{t_{k}\ si\ attivi|M(t)=M_{i}\}=\frac{w_{k}}{\sum_{t\in T_{e}^{(i)}}w_{t}}$$

> [!intuito] Intuito
> La probabilità che ciascuna transizione immediata venga attivata è ottenuta come il rapporto tra il peso associato alla transizione e la somma dei pesi di tutte le transizioni immediate abilitate in quella marcatura.
> 

### Grafo di raggiungibilità ridotto

Nella rappresentazione del grafo di raggiungibilità di una rete di GSPN vengono rimosse le marcature effimere, ottenendo un grafo di raggiungibilità ridotto.

Questo perchè la presenza di transizioni immediate farebbe sì che il grafo non rappresentasse più una $CTMC$. 

**Queste vengono rimpiazzate da un arco che collega direttamente l'ultimo stato tangibile al prossimo moltiplicando il rate della prossima temporizzata con la probabilità di attivazione della transizione immediata.**

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=45&rect=14,106,713,399|11, p.45]]

### Transizioni dipendenti

È possibile inoltre che i rate di transizione siano funzioni dello stato, per cui:
$$L(t_{k})=\lambda_{k}(M_{i})$$

> [!example]- Esempio
>Il numero di token $k$ nel posto $p_{1}$ rappresenta le componenti ridondanti soggette al fallimento.
>Il tasso di fallimento dunque dipenderà dal numero di componenti presenti, ciascuna che fallisce con rate $\lambda_{t}$, per cui il tasso con cui si attiverà la transizione sarà $\lambda_{t}\cdot(\#p_{1})$.
>Con $(\# p_{1})$ numero di token presenti nel posto $1$
>
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=47&rect=411,40,707,245|11, p.47]]

### Attivazione multipla 

È possibile assumere per una transizione $t_{i}$ con in input un posto contente più token diverse semantiche:

- **Singolo server**: per cui ciascun token consente una singola attivazione seriale per la transizione.
- **Server infiniti**: per cui vengono assegnati per ciascun token alla transizione temporizzazioni diverse consentendo l'evoluzione parallela, rendendo il parametro della transizione $L(t_{i})=n\cdot \lambda$ con $n$ numero di token presenti nel posto in input alla transizione.
- **Server multipli**: per cui i token vengono processati con grado di parallelismo pari a  $k$, per cui il parametro della transizione sarà $L(t_{i})=k\cdot \lambda$

> [!example]- Esempio
> ![[Università/Magistrale/Dependable computer system analysis/Slides/11.pdf#page=49&rect=38,43,695,464|11, p.49]]

