
## Tipi di simulazione

Si differenziano:

-  **Simulazioni terminanti**: simulazioni che continuano per un tempo $T_{E}$ con $E$ evento specifico terminante. Sono anche dette **simulazioni transitorie**, perchè si studia  il comportamento transitorio del sistema che si sta simulando, cioè come si evolve a partire dalle condizioni iniziali fino al termine dell'esperimento.

- **Simulazioni a stato fisso**: simulazioni nelle quali il sistema continua indeterminatamente per un lungo periodo di tempo senza che il suo stato sia influenzato dalle condizioni iniziali. Lo scopo è analizzare le **proprietà di regime** del sistema ignorando al fase transitoria.


## Misure di interesse

Dalla simulazione spesso si ottiene una collezione di valori raccolti in corrispondenza ad instanti di tempo discreti che sono collezionati per ottenere una stima di una misura $\theta$, tuttavia è possibile anche ottenere valori derivati da tempi continui:

- **Nel caso discreto**, i risultati della simulazione sono costituiti da una sequenza di osservazioni effettuate in istanti di tempo discreti, del tipo:: $$\{ Y_{1},Y_{2},\dots,Y_{n}\}$$

> [!example]- Esempio
> *Ad esempio registrando in istante discreto $t_{i}$ si può registrare il numero di clienti presenti ottenendo una sequenza di valori del tipo:*
> *$$\{ 3,4,5,2,1,3 \}$$ Che rappresenta  i clienti nel sistema ai tempi $t_{1},t_{2},t_{3},t_{4},t_{5}$*
> 

- **Nel caso continuo**, i risultati sono rappresentati da funzioni del tempo, definite su un intervallo continuo: $$\{ Y(t),0\leq t\leq T_{E} \}$$

> [!example]- Esempio
> *Nel caso continuo la grandezza di interesse sono il numero di clienti nel sistema all'istante continuo $t$ con $0\leq t\leq T_{E}$ . Anche se gli eventi accadono in istanti discreti questa quantità è definita su tutto l'intervallo temporale, assumendo valori costanti tra un evento e l'altro!* 


Sarà possibile effettuare una stima di una misura $\theta$  attraverso uno stimatore che consentirà di ottenere una approssimazione $\hat{\theta}$.

- **Nel caso discreto** lo stimatore sarà semplice la **media aritmetica**:
$$\hat{\theta}=\frac{1}{n}\sum_{i=1}^nY_{i}$$
- **Nel caso continuo** lo stimatore sarà la **media temporale** calcolata sull'intervallo di tempo continuo:
$$\hat{\theta}=\frac{1}{T_{E}}\int_{0}^{T_{E}}Y(t)dt$$
Si osserva che essendo le misure risultati di esperimenti randomici, la stima $\hat{\theta}$ sarà [[3 Variabili Aleatorie e distribuzioni di probabilità|variabile aleatoria]].

> [!caution] Osservazione
> Il vero valore $\theta$ si definisce come il valore atteso della variabili aleatorie $Y$ , ottenuta dunque come una media teorica calcolata su un numero infinito di valori assunti da $Y$. Il valore di $\hat{\theta}$ invece è aleatorio perchè viene calcolato campionando solo un numero finito  di valori di $Y$.

In entrambi i casi lo stimatore è detto **privo di errore** (senza bias) se il valore atteso della stima è proprio la vera misura $\theta$: 
$$E[\hat{\theta}]=\theta$$
## Distribuzione t di Student

Quando lo stimatore è non distorto, è possibile introdurre una variabile aleatoria **statistica $t$ di Student** con distribuzione nota come:
$$t=\frac{\hat{\theta}-\theta}{\sigma(\hat{\theta})}$$
Con $\sigma(\hat{\theta})$ **deviazione standard** calcolata come $\sigma=\frac{s}{\sqrt{n}}$ ed $s$ **varianza campionaria** calcolata come radice di: $s^2=\frac{1}{n-1}\sum_{i=1}^n(Y_{i}-\hat{\theta})^2$

La variabile $t$ è **distribuita con la distribuzione $t$ di Student** con $n$ , corrispondente al numero di campioni collezionati, **gradi libertà**.

**Questa variabile $t$ rappresenta una misura di quanto la media campionaria  si discosta dal valore vero della media della popolazione.**

La [[3 Variabili Aleatorie e distribuzioni di probabilità#Funzione densità di probabilità|Funzione densità di probabilità]]  della variabile $t$ sarà:
![[Università/Magistrale/Dependable computer system analysis/Slides/5.pdf#page=9&rect=283,35,686,319|05-result_analysis, p.9|500]]

Si osserva che la distribuzione $t$ di Student tende ad una Gaussiana con l'aumentare di $n$.

A parità di ordine, il quantile della distribuzione t di Student risulta maggiore di quello della distribuzione normale.  Questo comporta intervalli di confidenza più ampi, che riflettono la maggiore incertezza dovuta alla stima della varianza.  In tal senso, la distribuzione t può essere vista come una **versione più cauta** della normale, che fornisce limiti superiori più ampi per la stessa probabilità cumulativa.

> [!caution] Osservazione
> Nonostante le code della $t$ di Student siano più pesanti, quindi accumulano area più velocemente rispetto alle code della Gaussiana, questo vantaggio viene compensato dalla diminuzione della densità nelle zone centrali della distribuzione (che si abbassano nella distribuzione $t$), che dato il loro maggior peso fanno sì che complessivamente l'area si accumuli più lentamente rispetto alla Gaussiana.

## Intervalli di confidenza

Considerata la probabilità che la variabile aleatoria $\theta$ ricada in un intervallo $I$:
$$P[\theta \in I]=\alpha$$
Si definiscono:
- $I$ **intervallo di confidenza**
-  $\alpha$ **livello di confidenza**

È possibile valutare l'intervallo $I$ corrispondente ad un certo livello di confidenza $\alpha$ considerando  l'intervallo delimitato da $-t_\alpha$ e $t_{\alpha}$ nel quale si trova con probabilità $\alpha$ la variabile aleatoria $t$: 

$$\ \ \ P[-\overline{t}_{\alpha}\leq t\leq \overline{t}_{\alpha}]=\alpha$$
Sarà:
$$\ \ \ P[-\overline{t}_{\alpha}\leq t\leq \overline{t}_{\alpha}]=P\left[ -\overline{t}_{\alpha}\leq \frac{\hat{\theta}-\theta}{\sigma}\leq \overline{t}_{\alpha} \right]=P[-\overline{t}_{\alpha}\sigma\leq \hat{\theta}-\theta \leq\overline{t}_{\alpha}\sigma]=P[\hat{\theta}-\overline{t}_{\alpha}\sigma\leq \theta\leq \hat{\theta}+\overline{t}_{\alpha}\sigma]$$
Per cui la probabilità $\alpha$ rappresenta la probabilità per cui $\theta$  si trova **nell'intervallo di confidenza**:
$$I=\{x \in R\ |\ \hat{\theta}-\overline{t}_{\alpha}\sigma\leq \theta\leq \hat{\theta}+\overline{t}_{\alpha}\sigma  \}$$

> [!info] Chiarimento
> La probabilità $P[-\overline{t}_{\alpha}\leq t\leq \overline{t}_{\alpha}]=\alpha$ [[3 Variabili Aleatorie e distribuzioni di probabilità#^jb9gc3|sarà uguale a]] $\alpha=F_{T}(t_{\alpha})-F_{T}(-t_{\alpha})$ ed essendo la distribuzione simmetrica rispetto a $0$ e  l'area totale sottesa uguale ad $1$ sarà $F_{T}(-t_{\alpha})=1-F_{T}(t_{\alpha})$ per cui sarà: $\alpha=F_{T(t_{\alpha})}-(1-F_T(T_\alpha))=2F_T(t_\alpha)-1$ da cui $F_{T}(t_{\alpha})=\frac{1+\alpha}{2}$
> Per cui $t_{\alpha}$ sarà il quantile di ordine $\frac{1+\alpha}{2}$ e $-t_{\alpha}$ il suo simmetrico negativo.

### Notazione alternativa

Generalmente si tende a considerare il **livello di confidenza** come $1-\alpha$, considerando $\alpha$ probabilità che $t$ sia **all'esterno dell'intervallo di confidenza**

> [!info] Chiarimento
>  Essendo l'intervallo di confidenza simmetrico rispetto allo $0$ allora essere all'esterno dell'intervallo di confidenza significa essere nelle code della distribuzione. 

In questa circostanza dunque sarà:
$$\ \ \ P[-{t}_{\alpha}\leq t\leq {t}_{\alpha}]=1-\alpha$$

> [!info] Chiarimento
> L'area sotto la curva compresa tra $-t_{\alpha}$ e $t_{\alpha}$ dovrà essere uguale ad $1-\alpha$ per cui la parte rimanente di area (quella nelle code) sarà uguale ad $\alpha$, per cui l'area presente in ciascuna coda fuori dall'intervallo sarà $\frac{\alpha}{2}$, per cui sarà: $P(t\leq -t_{\alpha})=\frac{\alpha}{2}$, per cui $-t_{\alpha}$ sarà il quantile di ordine $\frac{\alpha}{2}$ e $P(t\leq t_{\alpha})=1 -\frac{\alpha}{2}$, per cui $t_{\alpha}$ sarà il quantile di ordine $1-\frac{\alpha}{2}$

Considerata la notazione per cui $-t_{\frac{\alpha}{2},n}$ è il valore di $t$ per cui la distribuzione $t$ di Student con $n$ gradi di libertà ha **area nella coda sinistra** $\frac{\alpha}{2}$ e $t_{\frac{\alpha}{2},n}$ valore di $t$ per cui l'area **nella coda destra** sia $\frac{\alpha}{2}$ sarà:
$$I=\left\{ x \in R\ |\ \hat{\theta}-\overline{t}_{\frac{\alpha}{2},n}\sigma\leq \theta\leq \hat{\theta}+\overline{t}_{\frac{\alpha}{2},n}\sigma   \right\}$$

> [!check] Nota pratica
> I quantili di ordine $p$ di una distribuzione $t$ di Student con $n$ gradi di libertà possono essere ottenuti da una tabella. Dato il quantile, la stima e la varianza, è possibile ottenere gli estremi dell'intervallo di confidenza con livello di confidenza $1-\alpha$.  

