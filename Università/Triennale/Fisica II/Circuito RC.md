## Corrente attraverso il condensatore

Considerata una rete che comprende un [[Condensatori|condensatore]] essendo presente tra le armature un isolante non non potrà scorrere una corrente continua attraverso il condensatore.

Sapendo che $C=\frac{Q}{V_{c}}$ e che la corrente $i=\frac{dq}{dt}$ nel caso di un condensatore si avrà con $q=CV_{c}$:
$$i_{c}=\frac{dq}{dt}=C\frac{dV_{c}}{dt}$$
Che sarà non nulla solo nel caso in cui $V_{c}$ non è costante. 

Per cui i condensatori saranno attraversati da una [[Corrente#Corrente di spostamento|corrente di spostamento]] $i(t)$   non costante ed ai suoi capi sarà presente una $V_{c}(t)$ e sarà presente un campo $E(\vec{r},t)$ che dipendendo anche dal tempo non sarà elettrostatico. 

~~È possibile considerare  la variazione di questo campo abbastanza lenta da poter  fissando $t$ considerare questo campo un campo elettrostatico~~

~~Sapendo che per un bipolo la potenza dissipata è $P_=V\cdot i$ per il condensatore sarà:~~
~~$$p=V_{c}i_{c}=V_{C}C\frac{dV_{c}}{dt}$$~~
~~Sapendo che la potenza è la derivata dell'energia e moltiplicando ambo i membri per dt:~~
~~$$dt\frac{d\epsilon}{dt}=CV_{c}\frac{dV_{c}}{dt}dt$$~~
~~Da cui integrando entrambi i membri:~~
~~$$\int_{0}^\epsilon d\epsilon=\int_{0}^{V_{c}}CV_{c}dV_{c}$$~~
~~Da cui:~~
~~$$\epsilon=\frac{1}{2}CV^2_{c}$$~~
~~Che è mantiene coerenza con l'energia calcolata nel condensatore anche con l'ipotesi del passaggio di corrente.~~

## Circuito di carica di un condensatore

Considerato un circuito composto da una Fem $E$ ,una resistenza $R$ ed un condensatore $C$ immaginando che in questo circuito sia presente un commutatore e che il circuito sia stato aperto fino all'istante 0 in cui viene chiuso per cui le condizioni all'istante $0$ sono considerata $q(t)$ la carica presente sull'armatura positiva del condensatore:
- $V_{c}(0)=0$
- $q(0)=0$
Allo scorrere del tempo le cariche per effetto della Fem si disporranno sull'armatura positiva e per induzione completa l'altra armatura acquisirà una carica uguale ed opposta. Applicando la legge di Kirchoff alla maglia:
$$E=V_{r}(t)+V_{c}(t)=Ri+\frac{q(t)}{C}=R\frac{dq}{dt}+\frac{q(t)}{C}$$
Essendo $R$ e $C$ in serie attraverso questi bipoli scorrerà la stessa corrente per cui è possibile esprimere:
$$E=RC \frac{dV_{c}}{dt}+V_{c}(t)$$
Potendo così esprimere questa equazione differenziale in termini di $q$ o di $V_{C}$
All'aumentare di $V_{c}$ diminuirà $V_{r}$ 

L'energia immagazzinata dal condensatore sarà dipendente dal tempo:
$$\epsilon(t)=\frac{1}{2}CV^2_{c}(t)$$
**Si nota che quando essendo la tensione generata da $E$ ripartita su $R$ e $C$ quando $C$ sarà carico** 
**$V_{c}=E$ , $q=CE$ e $V_{r}=0$ per cui essendo $V_{r}=Ri$ ed $R$ costante $i$ dovrà essere $0$, per cui il condensatore quando carico si comporta come un circuito aperto
Quando il condensatore sarà scarico invece la corrente sarà uguale a $i=\frac{E}{R}$ perché $V_{c}$ sarà uguale a $0$**

Per capire in che modo in funzione del tempo variano $V_{c}(t)$ e $q(t)$ si risolvono le equazioni differenziali lineari non omogenee del primo ordine a coefficienti costanti descritte sopra.

Considerato di voler sapere come evolve la tensione  $V_{C}(t)$ ai capi del condensatore essendo l'equazione $E=RC \frac{dV_{c}}{dt}+V_{c}(t)$ lineare non omogenea sarà soluzione la somma di due soluzioni , una particolare, ed una alla omogenea associata che si ottiene imponendo a $0$ il termine noto.
Per cui:
$$V_{c}=V_{part}(t)+V_{omass}(t)$$
È possibile ottenere come soluzione particolare il caso in cui $\frac{dV_{c}}{dt}=0$ per cui $V_{c}(t)=E$, questa soluzione da informazioni relative al comportamento a regime. Per conoscere l'andamento lungo il transitorio è necessario ottenere la soluzione alla omogenea associata:
$$RC \frac{dV_{c}}{dt}=-V_{c}(t)$$Dividendo ambo i membri per $RC$ e moltiplicando ambo i membri per $dt$:
$$dt\frac{dV_{c}}{dt}=-\frac{V_{c}(t)}{RC}dt$$
Dividendo ambo i membri per $V_{c}(t)$ ipotizzando che non sia nulla e poi integrando:
$$\int_{V_0}^V\frac{dV_{c}}{V_{c}(t)}=-\int_{0}^t\frac{dt}{RC}$$
Da cui si ottiene:
$$\ln V_{c}(t)\big|_{V_0}^V=-\frac{t}{RC}$$
Da cui:
$$\ln V_{C}(t)-\ln V_{0}=\ln \frac{V_{c}(t)}{V_{0}}=-\frac{t}{RC}$$
Dunque la soluzione omogenea associata è:
$$V_{c}(t)=V_{0}e^{\frac{-t}{RC}}$$
	*Essendo l'esponenziale una funzione trascendente il suo argomento deve essere adimensionale per cui $RC$ , detta costante di tempo del circuito, avrà come unità di misura secondi infatti:*
	*$R=\frac{V}{I}$ e $C=\frac{q}{V}$ per cui $RC$ ha come unità di misura $\frac{q}{i}$ ed essendo $i=\frac{dq}{dt}$ quindi $\frac{C}{S}$ $\frac{q}{i}$ avrà come unità di misura $\frac{C}{\frac{C}{S}}$ dunque $s$.*
La soluzione dell'equazione differenziale è dunque:
$$V_{c}(t)=E+V_{0}e^{\frac{-t}{RC}}$$

Per ottenere la costante $V_{0}$ sfrutto le condizioni iniziali $V_{C}(0)=0$ e valuto l'equazione per $t=0$ per cui:
$$V_{0}=-E$$
L'andamento dunque sarà:
$$V_{c}(t)=E(1-e^{\frac{-t}{RC}})$$
con $t=RC$ la tensione ai capi del condensatore avrà raggiunto circa $\frac{2}{3}$ del suo valore massimo.


disegnino dell'


## Scarica del condensatore

Considerato in un circuito RC di avere una tensione ai capi del condensatore $V_{c}(0) = V_{0}$ e di sostituire la Fem con un cortocircuito per cui $E=0$, applicando il principio di Kirchoff alla maglia in queste condizioni si ottiene:
 $$RC \frac{dV_{c}}{dt}+V_{c}(t)=0$$
 Un equazione differenziale lineare del primo ordine a coefficienti costanti omogenea.
Risolvibile come:
$$RC \frac{dV_{c}}{dt}=-V_{c}(t)$$Dividendo ambo i membri per $RC$ e moltiplicando ambo i membri per $dt$:
$$dt\frac{dV_{c}}{dt}=-\frac{V_{c}(t)}{RC}dt$$
Dividendo ambo i membri per $V_{c}(t)$ ipotizzando che non sia nulla e poi integrando:
$$\int_{V_0}^V\frac{dV_{c}}{V_{c}(t)}=-\int_{0}^t\frac{dt}{RC}$$
Da cui si ottiene:
$$\ln V_{c}(t)\big|_{V_0}^V=-\frac{t}{RC}$$
Da cui:
$$\ln V_{C}(t)-\ln V_{0}=\ln \frac{V_{c}(t)}{V_{0}}=-\frac{t}{RC}$$
Dunque la soluzione  è:
**$$V_{c}(t)=V_{0}e^{\frac{-t}{RC}}$$Per cui l'andamento nella fase di scarica è un esponenziale decrescente**

All'istante $t=RC$ la differenza di potenziale ai capi del condensatore si sarà ridotta a circa un terzo del valore iniziale.

## Carica del condensatore che parte da condizioni iniziali non nulle

Considerato in un circuito RC un condensatore con ai capi una tensione $V_{C}=V_{0}$ 
Essendo $R$ e $C$ in serie attraverso questi bipoli scorrerà la stessa corrente per cui è possibile esprimere applicando il principio di Kirchoff alla maglia:
$$E=RC \frac{dV_{c}}{dt}+V_{c}(t)$$
Per cui portando $V_{c}$ al primo membro e moltiplicando per $dt$ da entrambe le parti:
$$dt(E-V_{c}(t))=RC \frac{dV_{c}}{dt}dt$$
Dividendo ambo i membri per $E-V_{c}(t)$ e dividendo tutto per $RC$:
$$\frac{dt}{RC}=\frac{dV_{c}}{E-V_{c}(t)}$$
Integrando:
$$\int_0^t \frac{dt}{RC}=\int_{V_{c}(0)}^{V_{c}(t)} \frac{dV_{c}}{E-V_{c}(t)}$$
Per cui:
$$\ln[E-V_{c}(t)] \big|_{Vc(0)}^{V_{c}(t)}=-\frac{t}{RC}$$
Sviluppando:
$$\frac{E-V_{c}(t)}{E-V_{c}(0)}=e^{-\frac{t}{RC}}$$
Quindi:
$$E-V_{c}(t)={E-V_{c}(0)}e^{-\frac{t}{RC}}$$
Da cui:
$$V_{c}(t)=E\left( 1-e^{-\frac{t}{RC}} \right)+V_{c}(0)e^{-\frac{t}{RC}}$$
**In questa soluzione si contraddistingue una parte relativa alla soluzione di regime ed una parte relativa all'evoluzione delle condizioni iniziali, il cui contributo tende ad azzerarsi.**

## Circuito RC alternata
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 1|450]]

Considerato un circuito RC in cui è presente un generatore di tensione sinusoidale per cui applicando l'equazione alla maglia , applicabile in questo caso anche se in presenza di fenomeni dipendenti dal tempo in quanto il circuito è fisso, indeformabile e schermato da campi di induzione magnetica variabili nel tempo, per cui non siamo in presenza di campi di induzione magnetica il cui flusso è soggetto a variazioni, sarà:
$$V_{0}sen(wt)=Ri(t)+v_{c}(t)$$
Ovvero:
$$V_{0}sen(wt)=RC\frac{dv_{c}}{dt}+v_{c}(t)$$
Questa equazione differenziale ha un termine noto non costante.

La soluzione di questa equazione differenziale lineare non omogenea sarà la somma di una soluzione particolare più la somma dell'omogenea associata, relativa all'evoluzione delle condizioni iniziali, che si considera trascurabile con l'ipotesi di condizioni iniziali nulle $v_{c}(0)=0$, per cui non evolverebbero. Anche se non fossero state nulle si sarebbero esaurite dopo un tempo pari a $3-4$ costanti di tempo del circuito.

La soluzione particolare sarà una soluzione sinusoidale alla stessa frequenza $w$ della tensione in ingresso al circuito, per cui sarà:
$$v_{c}(t)=V_{c}sen(wt+\phi)$$
**Essendo il condensatore inerziale rispetto alla tensione, ci si aspetta che la tensione ai capi del condensatore sia in ritardo di fase rispetto alla tensione d'ingresso, per cui la fase per cui sarà $\phi<0$** 

Attraverso il metodo delle funzioni di prova utilizzando questa soluzione sarà:
$$V_{0}sen(wt)=RCV_{c}w\cos(wt+\phi)+V_{c}sen(wt+\phi)$$
Trasferendo l'analisi dal dominio del tempo al dominio della frequenza, sostituendo il generatore di tensione con un generatore fittizio che genera una tensione complessa $\dot{V}=V_{0}e^{jwt}$, e sostituendo alla resistenza un'impedenza di valore $Z_{R}=R$ ed alla capacità un impedenza di tipo puramente reattivo $Z_{c}=-\frac{j}{wc}$ , questo circuito sarà attraversato da una corrente $\dot{I}$.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 1 1]]

**L'inserimento di questo generatore complesso fa sì che ci si trovi in un caso equiparabile all'inserimento della serie di due generatori, uno con tensione $V_{0}\cos (wt)$ ed uno con tensione $V_{0}sen(wt)$, per sovrapposizione degli effetti la soluzione sarà la sovrapposizione delle soluzioni al circuito con ingresso ciascuno dei due generatori.**

### Metodo 2

A questo punto sarà possibile calcolare la serie di queste impedenze per cui $Z_{eq}=R-\frac{j}{wc}$.

A questo punto conoscendo $\dot{I}$ si trova $\dot{V}$ attraverso la legge di ohm generalizzata essendo $\dot{V}=Z\dot{I}$ per cui:
$$\dot{V}=Z\dot{I}=\left( R- \frac{j}{wC} \right)\dot{I}$$
Per cui:
$$\dot{I}=\frac{\dot{V}}{R-\frac{j}{wC}}$$
Per quanto riguarda la tensione ai capi del condensatore sarà:
$$\dot{V}_{c}=Z_{c}\dot{I}$$
Per cui:
$$\dot{V_{c}}=\frac{-\frac{j}{wC}\dot{V}}{R-\frac{j}{wC}}$$Dividendo numeratore e denominatore per $-\frac{j}{wc}$:
$$\dot{V_{c}}=\frac{\dot{V}}{1+jwRC}=\frac{{V}_{0}e^{jwt}}{1+jwRC}$$
 Per ottenere un informazione relativa al favore $\tilde{V}_{c}$ bisognerà esprimere il numero complesso $\frac{{V}_{0}}{1+jwRC}$ in termini di modulo e fase, il modulo sarà:
 $$|\frac{{V}_{0}}{1+jwRC}|=\frac{V_{0}}{\sqrt{1+(wRC)^2}}$$
 La fase sarà:
 $$\angle|\frac{{V}_{0}}{1+jwRC}|=tg^{-1}(wRC)$$
 Per cui la nostra $v_{C}(t)$ ottenuta attraverso $\mathrm{Im}(\dot{V}_{C})$ sarà:
 $$v_{C}(t)=\frac{V_{0}}{\sqrt{1+(wRC)^2}}sen[wt-tg^{-1}(wRC)]$$
 **Si osserva che la tensione ai capi del condensatore è in ritardo di fase rispetto alla tensione di ingresso**

**Inoltre all'aumentare della frequenza della tensione in ingresso diminuirà la tensione in uscita tendendo a $0$ , alla frequenza di taglio $w_{T}=\frac{1}{RC}$ l'ampiezza della tensione in uscita varrà esattamente $\frac{V_{0}}{\sqrt{2}}$ , a questa frequenza la fase della tensione in uscita sarà pari a $-\frac{\pi}{4}$,**
**La fase all'aumentare della frequenza diventa sempre più negativa tendendo a $-\frac{\pi}{2}$**
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 1 1 1]]