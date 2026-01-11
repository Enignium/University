
## Legge di Faraday-Neumann-Lenz

**In una regione di spazio nella quale si manifesta una variazione temporale non nulla del flusso del campo di induzione magnetica questa regione di spazio diventa sede di una differenza di potenziale i cui effetti si oppongono alla causa che l'ha generata.**

$$\frac{\partial\phi(\vec{B})}{\partial t}=-v(t)$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1|150]]

Si può immaginare una regione in cui è presente il campo di induzione magnetica concatenato con una linea chiusa, in questa circostanza in questa linea chiusa si presenterà una differenza di potenziale tale che le sue cause si oppongano alla variazione del campo, per cui:
$$\frac{\partial\phi(\vec{B})}{\partial t}=-v(t)=\oint_{l}\vec{E}\cdot dl$$
Con $\vec{E}(\vec{r},t)$ campo elettrico. 
### Applicazione agli [[Induttori]]

Considerato un induttore con coefficiente di autoinduzione $L=\frac{\phi(\vec{B})}{i}$, sarà possibile esprimere
$$\phi(\vec{B})=Li$$ Applicando la legge di Faraday-Neumann-Lenz:
$$\frac{\partial\phi(\vec{B})}{\partial t}=L \frac{di}{dt}=\pm v_{L}$$
**Per cui qualora un induttore è attraversato da una corrente variabile tempo ha sede una differenza di potenziale ai suoi capi il cui effetto si oppone a sua volta alla variazione della corrente che scorre lungo l'induttore per cui l'induttore è inerziale rispetto alla corrente.**

La potenza dissipata dall'induttore sarà $$P=iV=\frac{d\epsilon}{dt}=iL\frac{di}{dt}$$ per cui moltiplicando entrambi i membri per  $dt$ l'energia sarà:
$$\epsilon=\int_{0}^\epsilon d\epsilon=\int_{i=0}^i Lidi=\frac{1}{2}Li^2$$
### Fase di carica circuito RL corrente continua

Considerato un circuito RL, immaginando di chiudere all'istante $t=0$ un commutatore e fotografar questo singolo istante ,applicando la legge di Kirchoff alla maglia sarà:
$$E=Ri(t)+L \frac{di}{dt}$$
	*Per capire il segno di $V_{L}=L \frac{di}{dt}$ basta portare questo termine al primo membro per avere $E-L \frac{di}{dt}=Ri(t)$ , sii osserva così che al diminuire della corrente la differenza di potenziale tende ad far aumentare $E$ e viceversa all'aumentare, opponendosi così alle variazioni della corrente.*

È possibile risolvere l'equazione differenziale lineare non omogenea risolvibile come somma di una soluzione particolare ed una soluzione omogenea associata
per cui 
$$i(t)=i_{P}(t)+i_{omass}(t)$$
La soluzione particolare è facilmente ottenibile imponendo $i=cost$ facendo andare a 0 $L \frac{di}{dt}$ ottenendo così :
$$i_{P}=\frac{E}{R}$$
Per quanto riguarda l'omogenea associata è sufficiente risolvere l'equazione di partenza annullando il termine noto per cui:
$$-Ri(t)=L \frac{di}{dt}$$
Da cui moltiplicando ambo i membri per $dt$ e moltiplicando e dividendo per L ed i(t) :
$$\frac{di}{i(t)}=-\frac{R}{L}dt$$
Integrando:
$$\int_{i_{0}}^{i(t)}idi=-\frac{R}{L}\int_{0}^tdt$$
Da cui si ottiene:
$$\ln\left( \frac{i(t)}{i_{0}} \right)=-\frac{R}{L}t$$
Da cui:
$${i(t)}={i_{0}}e^{-\frac{R}{L}t}$$
	*Essendo l'esponenziale trascendente l'esponente dovrà essere adimensionale, per cui $\frac{R}{L}$ dovrà essere espresso in $\frac{1}{s}$  dunque $\frac{L}{R}=\tau$ costante di tempo in $s$*

La soluzione generale del circuito RL che parte  da condizioni nulle sarà dunque:
$$i(t)=\frac{E}{R}+{i_{0}}e^{-\frac{R}{L}t}$$
Imponendo la condizione iniziale per cui per $t=0$ sarà  $i(t)=0$  da cui
$i_{0}=-\frac{E}{R}$ per cui:
$$i(t)=\frac{E}{R}-\frac{E}{R}e^{-\frac{R}{L}t}=\frac{E}{R}(1-e^{-\frac{R}{L}t})$$
Sarà un andamento esponenziale crescente che raggiungerà $\frac{2}{3}$ del suo valore massimo all'istante $t=\tau=\frac{L}{R}$ 


## Scarica dell'induttore
Considerato in un circuito RL di avere una corrente attraverso l'induttore $i(0) = i_{0}$ e di sostituire la Fem con un cortocircuito per cui $E=0$, applicando il principio di Kirchoff alla maglia in queste condizioni si ottiene:
 $$0=Ri(t)+L \frac{di}{dt}$$
Per cui:
$$-Ri(t)=L \frac{di}{dt}$$
Da cui moltiplicando ambo i membri per $dt$ e moltiplicando e dividendo per L ed i(t) :
$$\frac{di}{i(t)}=-\frac{R}{L}dt$$
Integrando:
$$\int_{i_{0}}^{i(t)}idi=-\frac{R}{L}\int_{0}^tdt$$
Da cui si ottiene:
$$\ln\left( \frac{i(t)}{i_{0}} \right)=-\frac{R}{L}t$$
Da cui:
$${i(t)}={i_{0}}e^{-\frac{R}{L}t}$$
**Per cui l'andamento della corrente nella fase di scarica è un esponenziale decrescente**
## Carica dell'induttore che parte da condizioni iniziali non nulle

Considerato in un circuito RL un induttore attraverso cui scorre una corrente $i(0)=i_{0}$ 
Essendo $R$ e $L$ in serie attraverso questi bipoli scorrerà la stessa corrente per cui è possibile esprimere applicando il principio di Kirchoff alla maglia:
$$E=Ri(t)+L \frac{di}{dt}$$
Per cui portando $Ri(t)$ al primo membro, mettendo in evidenza R e moltiplicando per $dt$ da entrambe le parti:
$$R\left( \frac{E}{R}-i(t) \right)dt=L\frac{di}{dt}dt$$
Dividendo ambo i membri per L e per $\frac{E}{R}-i(t)$:
$$\frac{R}{L}dt=\frac{di}{\frac{E}{R}-i(t)}$$
Integrando:
$$\int_{0}^t\frac{R}{L}dt=\int_{i_{0}}^{i(t)}\frac{di}{\frac{E}{R}-i(t)}$$
Per cui:
$$\ln\left[ \frac{E}{R}-i(t) \right] \big|_{i(0)}^{i(t)}=-\frac{R}{L}{t}$$
Sviluppando:
$$\frac{\frac{E}{R}-i(t)}{\frac{E}{R}-i(0)}=e^{-\frac{R}{L}t}$$
Quindi:
$$\frac{E}{R}-i(t)=e^{-\frac{R}{L}t}\left( \frac{E}{R}-i(0) \right)$$
Da cui:
$$i(t)=\frac{E}{R}\left( 1-e^{-\frac{R}{L}t} \right)+i(0)e^{-\frac{R}{L}t}$$
**In questa soluzione si contraddistingue una parte relativa alla soluzione di regime ed una parte relativa all'evoluzione delle condizioni iniziali, il cui contributo tende ad azzerarsi.**

Nel passaggio dalla fase di regime alla fase di scarica è presente una singolarità nella differenza di potenziale ai capi dell'induttore che raggiunge un valore negativo per poi tendere a $0$.

**Raggiunta la fase di regime sarà nulla la differenza di potenziale ai capi dell'induttore in quanto sarà costante la corrente per cui in queste circostanze l'induttore si comporterà come un cortocircuito**

## Circuito RL alternata

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 1 2]]
Considerato un circuito RC in cui è presente un generatore di tensione sinusoidale per cui applicando l'equazione alla maglia , applicabile in questo caso anche se in presenza di fenomeni dipendenti dal tempo in quanto il circuito è fisso, indeformabile e schermato da campi di induzione magnetica variabili nel tempo, per cui non siamo in presenza di campi di induzione magnetica il cui flusso è soggetto a variazioni, il ferromagnetico interno all'induttore non è in saturazione e vale l'approssimazione a parametri concentrati sarà applicando la legge alla maglia:

$$v_{0}sen(wt)=Ri(t)+L\frac{di}{dt}$$
Questa equazione differenziale ha un termine noto non costante.

La soluzione di questa equazione differenziale lineare non omogenea sarà la somma di una soluzione particolare più la somma dell'omogenea associata, relativa all'evoluzione delle condizioni iniziali, che si considera trascurabile con l'ipotesi di condizioni iniziali nulle $i(0)=0$, per cui non evolverebbero. Anche se non fossero state nulle si sarebbero esaurite dopo un tempo pari a $3-4$ costanti di tempo del circuito.

La soluzione particolare sarà una soluzione sinusoidale alla stessa frequenza $w$ della tensione in ingresso al circuito, per cui sarà:
$$i(t)=I_{0}sen(wt+\phi)$$
**Essendo l'induttore inerziale rispetto alla corrente, ci si aspetta che la corrente attraverso l'induttore sia in ritardo di fase rispetto alla tensione d'ingresso, per cui la fase per cui sarà $\phi<0$** 

Trasferendo l'analisi dal dominio del tempo al dominio della frequenza, sostituendo il generatore di tensione con un generatore fittizio che genera una tensione complessa $\dot{V}=V_{0}e^{jwt}$, e sostituendo alla resistenza un'impedenza di valore $Z_{R}=R$ ed alla capacità un impedenza di tipo puramente reattivo $Z_{L}=jwL$ , questo circuito sarà attraversato da una corrente $\dot{I}$.

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 1 1]]
### Metodo 1 
Sostituendo nell'equazione alla maglia:
$$\dot{V}=R\dot{I}+\frac{Ld\dot{I}}{dt}$$
Esplicitando i fasori:
$$V_{0}e^{jwt}=R\tilde{I}e^{jwt}+L \frac{d{\tilde{I}e^{jwt}}}{dt}=V_{0}e^{jwt}=R\tilde{I}e^{jwt}+jwL\tilde{I}e^{jwt}$$
Dividendo tutto per $e^{jwt}$ 
$$V_{0}=R\tilde{I}+jwL\tilde{I}$$
Da cui:
$$\tilde{I}=\frac{V_{0}}{R+JwL}$$
Moltiplicando per $e^{jwt}$ ottengo che il vettore rotante $\dot{I}=\frac{V_{0}}{R+JwL}e^{jwt}$

Per esprimere questo vettore rotante il forma polare mi serve conoscere l'ampiezza e la fase del fasore $\tilde{I}$:
$$|\frac{V_{0}}{R+JwL}|=\frac{V_{0}}{\sqrt{R^2+(wL)^2}}$$
$$\angle\frac{V_{0}}{R+JwL}=-tg^{-1}\left( \frac{wL}{R} \right)$$
Per cui $$\dot{I}=\frac{V_{0}}{\sqrt{R^2+(wL)^2}}e^{-jtg^{-1}(\frac{wL}{R})}e^{jwt}$$
È possibile trovare $i(t)$ attraverso $\mathrm{Im}(\dot{I})$ per cui:
$$i(t)=\frac{V_{0}}{\sqrt{ R^2}+(wL)^2}sen\left( wt-tg^{-1}\left( \frac{wL}{R} \right) \right)$$
### Metodo 2

È possibile calcolare l'impedenza serie equivalente come $Z_{eq}=R+jwL$ ed applicare la legge di Ohm generalizzata per cui $\dot{V}=Z\dot{I}$ da cui:
$$\dot{I}=\frac{\dot{V}}{\dot{Z}}=\frac{V_{0}e^{jwt}}{R+jwL}$$
A questo punto posso trovare $\dot{V}_{L}=\dot{I}Z_{L}$ sapendo che $Z_{L}=jwL$per cui:
$$\dot{V}_{L}=\frac{jwLV_{0}e^{jwt}}{R+jwL}$$
Per esprimere $\frac{jwL}{R+jwL}$ in forma polare si osserva che:
$$|\frac{jwL}{R+jwL}|=\frac{1}{\sqrt{ 1+\left( \frac{R}{wL} \right)^2 }}$$
$$\angle\frac{jwL}{R+jwL}=tg^{-1}\left( \frac{R}{wL} \right)$$
Per cui $$\dot{V}_{L}=\frac{V_{0}}{\sqrt{ 1+\left( \frac{R}{wL} \right)^2 }}e^{tg^{-1}(\frac{R}{wL})}e^{jwt}$$
Per cui ottenendo $v_{l}(t)$ come $\mathrm{Im}(\dot{V}_{L})$ sarà:
$$v_{l}(t)=\frac{V_{0}}{\sqrt{ 1+\left( \frac{R}{wL} \right)^2 }}sen(wt+tg^{-1}(\frac{R}{wL}))$$
**Da cui si osserva che la differenza di potenziale ai capi dell'induttore è in anticipo rispetto alla tensione imposta in ingresso**

Alla frequenza di taglio $w_{T}=\frac{R}{L}$ la tensione sarà $V_{L}=\frac{V_{0}}{\sqrt{ 2 }}$ e la fase uguale a $\frac{\pi}{4}$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 1 1 1 1]]Si osserva che il circuito RL si comporta come un filtro passa alto attenuando segnali con basse frequenze.