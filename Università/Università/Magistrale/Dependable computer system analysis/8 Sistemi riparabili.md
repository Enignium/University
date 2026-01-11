## Mantainability
![[9.pdf#page=3&rect=135,200,628,438|09-disp, p.3]]

Un sistema riparabile si alterna tra due stati principali:
- stato operativo $a$.
- stato guasto $b$.

Si identificano:
- $\tau_{i}$gli intervalli di tempo in cui il sistema è operativo.
- $\theta_{i}$ gli intervalli di tempo in cui il sistema è guasto.

Le lunghezze di questi intervalli $\theta_{i}$ e $\tau_{i}$ sono variabili aleatorie con [[3 Variabili Aleatorie e distribuzioni di probabilità#Funzione distribuzione cumulativa|CDF]] rispettivamente $F_{i}(t)$ e $G_{i}(t)$.

Si accettano per semplicità le seguenti ipotesi per cui:
- **Ogni riparazione è rigenerativa**, dunque $F_{1}(t)=F_{2}(t)=\dots=F_{i}(t)=\dots=F(t)$.
- **I tempi di riparazione hanno la stessa distribuzione** per cui $G_{1}(t)=G_{2}(t)=\dots=G_{i}(t)=\dots=G(t)$.

> [!info] Proprietà
> 
> La CDF di $\tau$ sarà [[6 Affidabilità#Reliability|l'inaffidabilità]]:
> $$F(t)=P(\tau \leq t)=1-R(t)$$
> La funzione $G(t)$ sarà:
> $$G(t)=P(\theta \leq t)$$
> **Per cui rappresenta la probabilità di avere una riparazione nell'intervallo da $[0,t]$. Questa grandezza è definita manutenibilità**.
> 
> > [!caution] Osservazione
> > L'intervallo di tempo $[0,t]$ va considerato relativo all'istante di tempo nel quale è avvenuto il guasto, non assoluto. Si tratta di quanto tempo viene impiegato per effettuare la riparazione.
> 
> Si definisce tempo medio di riparazione (**MTTR**) il valore atteso della variabile $\theta$:
> $$MTTR=E[\theta]=\int_{0}^\infty t\cdot g(t)dt=\int_{0}^\infty tdG(t)$$

## Repair rate 

La [[3 Variabili Aleatorie e distribuzioni di probabilità#Funzione densità di probabilità|PDF]] della manutenibilità $G(t)$ sarà:
$$g(t)=\frac{dG(t)}{dt}$$
Dalla quale è possibile ottenere un informazione relativa alla frequenza con la quale in ciascuna unità di tempo avviene una riparazione, il **repair rate**:
$$h_{g}(t)=\frac{g(t)}{1-G(t)}$$

> [!dimostrazione]- Dimostrazione
>  Il repair rate è l'analogo per la riparazione del failure rate, questa definizione viene ottenuta effettuando dei passaggi analoghi alla derivazione del failure rate, calcolando la probabilità che la riparazione avvenga nell'intervallo $[t,t+\Delta t]$ con condizione per cui la riparazione non è ancora avvenuta al tempo $t$:
>  
> Considerando l'intervallo di tempo $(t,t+\Delta t)$ la probabilità che la riparazione del sistema avvenga in questo intervallo senza assunzioni su ciò che è successo prima sarà, approssimando l'integrale della pdf in quell'intervallo:
> $$\int_{t}^{t+\Delta t} g(\theta) \, d\theta \simeq g(t)\cdot \Delta t$$
> **Questa probabilità è non condizionata** in quanto non si assume nulla su cosa sia successo prima di $t$.
> $$P(t < \theta < t+\Delta t \mid \theta > t) = \frac{P(t < \theta < t+\Delta t)}{P(\theta > t)} = \frac{G(t+\Delta t)-G(t)}{1-G(t)}$$
> Portando $\Delta t \to 0$ e dividendo per  $\Delta t$ otteniamo il **repair rate** o **tasso istantaneo di riparazione**:
> $$h_g(t) = \lim_{\Delta t \to 0} \frac{G(t+\Delta t)-G(t)}{\Delta t (1-G(t))} = \frac{g(t)}{1-G(t)}$$

Questo indica quanto è probabile che la riparazione avvenga in ciascun istante di tempo.

> [!info] Proprietà
> - **Se la variabile aleatoria $\theta$ tempo di riparazione è distribuita esponenzialmente allora $h_g(t)$ sarà costante.**
> 
> > [!dimostrazione]- Dimostrazione
> > Quando la variabile $\theta$ è distribuita esponenzialmente avrà: 
> > - CDF $G(t)=1-e^{-\mu t}$
> > - PDF $g(t)=\mu e^{-\mu t}$
> >Per cui sarà:
> >$$1-G(t)=1-(1-e^{-\mu t})=e^{-\mu t}$$
> >Dunque il repair rate sarà:
> >$$h_g(t)=\frac{g(t)}{1-G(t)}=\frac{\mu e^{-\mu t}}{e^{-\mu t}}=\mu$$
> >Per cui il repair rate quando $\theta$ è distribuita esponenzialmente è costante e pari proprio al parametro $\mu$ della distribuzione esponenziale.
> 
> Quando il repair rate è costante la variabile aleatoria tempo di riparazione ha una distribuzione esponenziale con parametro $\mu$, per cui sarà:
> $$MTTR=E[\theta]=\frac{1}{\mu}$$
> 
> > [!caution] Osservazione
> > $\mu$ è dimensionalmente uguale a $t^{-1}$, per cui costituisce una frequenza. Spesso si tende ad indicare la manutenibilità $G(t)$ in termini di $-\mu t$, un valore adimensionale.
> 

## Availability

**Si definisce disponibilità la probabilità che il sistema si trovi nello stato operativo dato un tempo $t$.**
Questa quantità nei [[7 Sistemi non riparabili|sistemi non riparabili]] coincide con l'affidabilità

> [!intuito] Intuito
>Un sistema non riparabile è sempre nello stato operativo finché non avviene un guasto, portandolo al termine della sua vita, perciò il sistema sarà sempre disponibile finchè non sarà rotto.

**Si definisce non disponibilità la probabilità che il sistema sia nello stato non operativo al tempo $t$** per cui:
$$U(t)=1-A(t)$$
La disponibilità è un informazione significativa per l'utente finale,un alta disponibilità indica un sistema con guasti poco frequenti riparati velocemente.

## Sistemi a tassi costanti
Considerato un sistema con failure rate e repair rate costanti per cui:
- $h(t)=\lambda$
- $h_{g}(t)=\mu$
![[9.pdf#page=13&rect=175,251,554,435|09-disp, p.13]]

È possibile dimostrare che:
$$\begin{cases} \frac{dA(t)}{dt}=-\lambda A(t)+\mu U(t) \\
\frac{dU(t)}{dt}=\lambda A(t) - \mu U(t)
\end{cases}$$

> [!intuito] Intuito
> Ogni equazione differenziale descrive come cambia nel tempo la probabilità di trovarsi in ciascuno stato.  
> 
> La variazione di probabilità dipende dal fatto che il sistema sia in ciascuno stato:  
> - la probabilità dello stato operativo $A(t)$ diminuisce a causa della possibile transizione verso lo stato guasto (contributo negativo $\lambda A(t)$),  
> - mentre aumenta grazie alle riparazioni provenienti dallo stato guasto $U(t)$ (contributo positivo $\mu U(t)$).  
> Simmetricamente, la probabilità dello stato guasto $U(t)$ aumenta a causa dei guasti dal sistema operativo (contributo positivo $\lambda A(t)$) e diminuisce per effetto delle riparazioni (contributo negativo $\mu U(t)$).  
> 
> Le condizioni iniziali devono essere specificate a priori per risolvere il sistema, per cui si suppone il sistema funzionante all'avvio: $A(0)=1$ e $U(0)=0$

Si ottiene risolvendo questa equazione differenziale: 
$$\begin{array}
aA(t)=\frac{\mu}{\lambda+\mu}+\frac{\lambda}{\lambda+\mu}e^{-(\lambda+\mu)t} \\
U(t)=\frac{\lambda}{\lambda+\mu}-\frac{\lambda}{\lambda+\mu}e^{-(\lambda+\mu)t}
\end{array}$$
Da cui si ottiene un informazione sulla **disponibilità a stato stazionario**:
$$A_{\infty}=\lim_{ t \to \infty } A(t)=\frac{\mu}{\lambda+\mu}=\frac{\frac{1}{\lambda}}{\frac{1}{\lambda}+\frac{1}{\mu}}=\frac{MTTF}{MTTF+MTTR}$$

> [!caution] Osservazione
> Gli effetti transitori diventano trascurabili con $t\simeq 4.5\cdot \frac{1}{\lambda+\mu}$, per cui per $t$ distanti dall'istante iniziale la disponibilità coincide con $A_{\infty}$.

È possibile considerare:
- Il tempo medio di fallimento tempo medio di up-time (**MUT**)
- Il tempo medio di riparazione tempo medio di down-time (**MDT**)

Per cui:$$\begin{array}AA_{\infty}=\frac{MUT}{MUT+MDT} \\
U_{\infty}=\frac{MDT}{MUT+MDT}
\end{array}$$
Nei sistemi reali $MUT\gg MDT$ per cui approssimando sarà:$$\begin{array}
AU_{\infty}=\frac{MDT}{MUT} \\
A_{\infty}=1-\frac{MDT}{MUT}
\end{array}$$Che con tempi di guasto e di riparazione distribuiti esponenzialmente, quindi con tassi costanti sarà:
$$\begin{array}AA_{\infty}=\frac{\lambda}{\mu} \\
U_{\infty}=1-\frac{\lambda}{\mu}
\end{array}$$
## Sistemi complessi 

Valgono tutte le considerazioni relative a serie e parallelo di sistemi complessi in termini di valutazione della disponibilità fatte per la [[7 Sistemi non riparabili#Strutture complesse#affidabilità nei sistemi complessi]]. 

