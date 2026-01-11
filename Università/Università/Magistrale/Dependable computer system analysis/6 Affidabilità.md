
## Reliability

Si definisce l'affidabilità come **la probabilità che un sistema lavori in modo continuo in un determinato intervallo di tempo**. L'istante di tempo nel quale il sistema smette di funzionare, **failure time**,  è una variabile aleatoria. 

Formalmente l'affidabilità è definita ad un tempo particolare $t$  per cui questa è l'abilità di un componente di effettuare il lavoro assegnato nell'intervallo di tempo da $(0,t)$ dato il suo comportamento e gli stress a cui è soggetto. Il tempo $t$ è detto **mission time**. 

Data $X$ la variabile aleatoria che rappresenta il tempo di vita del sistema (o il tempo impiegato a fallire) e supponendo di conoscerne la [[3 Variabili Aleatorie e distribuzioni di probabilità#Funzione distribuzione cumulativa|CDF]]:
$$F_{X}(t)=P(X\leq t)$$

Sarà la **funzione affidabilità** $R(t)$  la probabilità che il sistema superi il tempo di vita stimato:
$$R(t)=P(X>t)=1-P(X\leq t)=1-F_{X}(t)$$

> [!caution] Osservazione
> Questa definizione assume che il sistema abbia continuato a funzionare dall'istante $0$ all'istante $t$ senza interruzioni.
  

> [!danger] Importante
> L'affidabilità è sempre valuta rispetto ad un tempo $t$, mission time.
### Proprietà 
La  funzione affidabilità mostra le seguenti proprietà:

- La funzione $R(t)$ non è una CDF nonostante sia definita come $1-F_{X}(t)$ in quanto **non è una funzione monotona non decrescente**.
- Il $\lim_{ t \to \infty }R(t)=0$ e non $1$. (La probabilità di trovare un sistema funzionante al tempo $\infty$ è uguale a $0$). 
- La funzione $R(t)$ è una funzione **monotona non crescente**.
- La funzione è $0\leq R(t)\leq1$ nell'intervallo tra $[0,\infty]$ essendo una probabilità.
- Data $f_{x}(t)$ la [[3 Variabili Aleatorie e distribuzioni di probabilità#Funzione densità di probabilità|PDF]] di $X$ è possibile derivare:
$$R(t)=\int_{t}^{\infty}f_{x}(\tau)d\tau$$

> [!dimostrazione]- 
> Dato:
> 
> $R(t)=1-F_{X}(t)=1-\int_{-\infty}^{t}f_{x}(\tau)d\tau$
> 
> Essendo l'integrale della PDF su tutto il domino uguale ad $1$ , seguirà che: 
> $$R(t)+\int_{-\infty}^{t}f_{x}(\tau)d\tau=1$$
> Per cui $R(t)$ dov rà essere quell'integrale sulla parte rimanente del dominio:
> $$R(t)=\int_{t}^{\infty}f_{x}(\tau)d\tau$$

$$f_{X}(t)=\frac{dF_{X}(t)}{dt}=-\frac{dR(t)}{dt}$$

> [!dimostrazione]-
> Questa si ottiene semplicemente sostituendo $F_{X}$  con $1-R(t)$
> ottenuta dalla definizione di affidabilità e poi derivando, per cui derivando si ottiene proprio: 
> $$f_{X}(t)=\frac{d(1-R(t))}{dt}=-\frac{dR(t)}{dt}$$

- Si ottiene attraverso un integrazione per parti che il  [[3 Variabili Aleatorie e distribuzioni di probabilità#Valore atteso|valore atteso]] del tempo di vita (detto tempo medio di fallimento **MTTF**) si può esprimere come: 
$$MTTF=E[t]=\int_{0}^\infty tf_{x}(t)dt=\int_{0}^\infty R(t)dt$$
## Failure rate

Considerando l'intervallo di tempo $(t,t+\Delta t)$ la probabilità che il sistema fallirà in questo intervallo senza assunzioni su ciò che è successo fuori da questo intervallo,[[3 Variabili Aleatorie e distribuzioni di probabilità#^zd3cv5| approssimando l'integrale della pdf in quell'intervallo sarà]]:
$$\int_{t}^{t+\Delta t}f_{X}(t)\simeq f_{X}(t)\cdot\Delta t$$
**Questa probabilità sarà non condizionata** in quanto non si sta assumendo nulla su cosa sia successo prima di $t$.

Se assumessimo invece **che il sistema ha funzionato fino all'istante $t$,** volendo sapere la probabilità che fallirà in un $\Delta t$ questa sarà una probabilità condizionata.

La probabilità sarà, sfruttando la definizione di [[1 Introduzione alla teoria delle Probabilità#Probabilità condizionata|probabilità condizionata]]:
$$P(t<X<(t+\Delta t)|X>t)=\frac{P(t<X<t+\Delta t)}{P(X>t)}=\frac{F_{X}(t+\Delta t)-F_{X}(t)}{R(t)}$$
È possibile ottenere un **informazione sul tasso con cui il sistema fallisce per  unità di tempo** portando $\Delta t \to 0$ e dividendo per $\Delta t$:
$$h(t)=\lim_{ \Delta t \to 0 }\frac{F_{X}(t+\Delta t)-F_{X}(t)}{R(t)} \frac{1}{\Delta t}$$
**Questa quantità è il tempo di fallimento istantaneo ,hazard rate o failure rate, un informazione che quantifica quanto sia probabile che il sistema fallisca in ciascun istante di tempo noto che il sistema abbia funzionato correttamente fino ad allora.**
### Proprietà

Si osservano le seguenti proprietà riguardanti il failure rate:

- È possibile calcolare l'affidabilità a partire dal failure rate come:
$$R(t)=e^{-{\int_{0}^th(x)dx}}$$

> [!dimostrazione]- Dimostrazione
> Dato il failure rate:$$h(t)=\lim_{ \Delta t \to 0 }\frac{F(t+\Delta t)-F(t)}{R(t)} \frac{1}{\Delta t}$$ si osserva che è possibile esprimere $\lim_{ \Delta t \to 0 }\frac{F(t+\Delta t)-F(t)}{\Delta t}$ come derivata della funzione $F_{X}$, che essendo una CDF avrà come derivata la PDF. Per cui sarà: 
> $$h(t)=\frac{f_{X}(t)}{R(t)}=-\frac{1}{R(t)}\cdot\frac{dR(t)}{dt}$$
> Risolvendo questa equazione differenziale viene proprio:
> $$R(t)=e^{-{\int_{0}^th(x)dx}}$$

- L'andamento di $h(t)$ nel tempo assume questa forma:
![[6.pdf#page=12&rect=139,233,608,437|06-affidab, p.12]]


- Si differenziano diverse fasi dell'andamento del failure rate nel tempo:
    - Una fase di diminuzione iniziale: **Deacreasing Failure Rate**
     - Una fase costante : **Costant Failure Rate**
     - Una fase di incremento: **Increasing Failure Rate**


- **Se la variabile aleatora $X$ tempo di vita è distribuita esponenzialmente allora $h(t)$ sarà costante.**

> [!dimostrazione]- Dimostrazione
> Quando la variabile $X$ è distribuita esponenzialmente avrà: 
> - CDF $F_{X}(t)=1-e^{-\lambda t}$
> - PDF $f(t)=\lambda e^{-\lambda t}$
>Per cui sarà:
>$$R(t)=1-F(t)=1-(1-e^{-\lambda t})=e^{-\lambda t}$$
>Dunque il failure rate sarà:
>$$h(t)=\frac{f_{X}(t)}{R(t)}=\frac{\lambda e^{-\lambda t}}{e^{-\lambda t}}=\lambda$$
>Per cui il failure rate quando $X$ è distribuita esponenzialmente è costante e pari proprio al parametro $\lambda$ della distribuzione esponenziale.

Quando il failure rate è costante la variabile aleatoria life time ha una distribuzione esponenziale con parametro $\lambda$, per cui sarà:
$$MTTF=E[t]=\frac{1}{\lambda}$$

> [!caution] Osservazione
> $\lambda$ è dimensionalmente uguale a $t^{-1}$, per cui costituisce una frequenza. Spesso si tende ad indicare l'affidabilità $R(t)$ in termini di $-\lambda t$ , un valore adimensionale.

_Distribuzione di weibull_

## Valutazione sperimentale 

Dati $N$ componenti uguali, il cui corso della vita è indipendente, supponendo che tutti inizino ad operare all'istante $t=0$, si osserva per ciascuno di questi un istante di fallimento $t_{i}$ nel quale ciascuno smette di funzionare. 

È possibile scegliere un istante $t$ ed utilizzarlo come soglia, esprimendo così come:
-  $N_{v}(t)$  numero di componenti ancora operativi all'istante $t$
- $N_{r}(t)$ numero di componenti guasti all'istante $t$. 

Sarà possibile così approssimare:
$$\hat{F_{X}}(t)=\frac{N_{r}(t)}{N}$$
$$\hat{R}(t)=\frac{N_{v}(t)}{N}=1-\hat{F}(t)$$
Sarà dunque:
$$\hat{f}(t)=\frac{d\hat{F}}{dt}=-\frac{d\hat{R}(t)}{dt}$$
Ed il failure rate:
$$\hat{h}(t)=\frac{\hat{f}(t)}{\hat{R}(t)}=\frac{1}{N_{v}(t)}\frac{dN_{r}(t)}{dt}$$
*da sistemare*