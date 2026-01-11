Il supervised learning si differenzia per la presenza di un ente supervisore che conosce gli output corretti accoppiati agli ingressi considerati, gli scopi principali di questo tipo di learning è quello di sviluppare sistemi in grado di effettuare **regressione** e **classificazione**.
## Classificazioni approcci al supervised learning
Nel contesto del supervised learning si differenziano i seguenti approcci:
- White Box Vs Black Box
- Model based Vs Instance based
- Online Vs Offline
### White Box Vs Black Box
Nell’approccio white box  il processo decisionale del modello è interpretabile, è possibile comprendere come le variabili in ingresso influenzano l’output.  

Nell’approccio black box la predizione è corretta ma il processo non è trasparente (es. reti neurali profonde).

Esempio algoritmo white box: alberi decisionali.
Esempio algoritmo black box: reti neurali.
## Model based Vs Instance based
![[Slides.pdf#page=2&rect=66,113,532,373|Slides, p.2|550]]
Nell'approccio model based si parte da un dataset dal cui si allena un modello andando così ad ottenere un sistema in grado di effettuare la separazione delle classi degli output, per poi utilizzare questo modello per inferenza. Una volta avuto il modello non sono più necessari dati per poterlo utilizzare. 

Nell'approccio instance based si parte sempre da un dataset attraverso il quale viene effettuata l'inferenza senza effettuare un training. Esempi di algoritmi instance based  è il $KNN$, un algortimo del genere è capace di identificare gli output nei pressi di un input preso in considerazione ed attraverso un sistema di voto effettuare la classificazione.

|                | Training    | Inferenza | Costo in memoria |
| -------------- | ----------- | --------- | ---------------- |
| Model Based    | Lento       | Veloce    | Basso            |
| Instance Based | No Training | Lenta     | Alto             |

### Online Vs Offline

Un sistema online in un approccio di Continous Learning, 

Un sistema offline in un approccio di Static Learning

# Regressione
La regressione è un algoritmo relativamente semplice utilizzato nell'ambito dell'apprendimento data-driven supervisionato.

I dati in un dataset sono composti da da righe (esempi) e colonne (features) in input attraverso i quali si ottengono i label (output)

Immaginato di voler considerare un problema di regressione con un singolo output $y$ ed $n$ features $x_{n}$ in ingresso per cui:
$$\begin{array}
Ax\in R^n \\
y\in R \\
y=f(x)+\epsilon \\
f:R^n\to R
\end{array}$$
**Definendo $\epsilon$ rumore che indica l'imperfezione della relazione tra input ed output, lo scostamento dei punti catturati dal dataset dai valori ottenuti attraverso la funzione reale.**

La funzione $f$ è la funzione "reale", la funzione che connette gli input agli output.

Per semplicità assumiamo che il valore atteso del rumore $E[\epsilon]=0$, per cui statisticamente il rumore è nullo. 

Essendo l'obiettivo dell'apprendimento ottenere una funzione tanto più vicina alla vera $f(x)$ tanto più piccolo sarà $\epsilon$ più facile sarà possibile ottenere informazioni sulla relazione.
	*Esempio: si vuole ottenere la f(x) che date informazioni relative alla umidità ed alla pressione in ingresso consente di ottenere la temperatura*
![[Slides.pdf#page=3&rect=90,132,305,280|Slides, p.3]]
Considerati i punti rossi i punti presenti nel dataset e la retta blu la funzione reale $f(x)$ che lega input ed output, nel caso in cui $\epsilon=0$ allora i punti sarebbero precisamente sulla retta, **i dati catturano perfettamente la funzione reale**.
Nel caso in figura il valore atteso $E[\epsilon]=0$ in quanto mediamente i punti orbitano attorno alla funzione reale.
![[Slides.pdf#page=3&rect=326,130,496,266|Slides, p.3]]Se i punti fossero sempre sotto la retta il dataset starebbe "sovrastimando" la funzione reale e si avrebbe un valore atteso del rumore $E[\epsilon]\neq0$

In questi casi è necessario lavorare sui dati in modo tale da ottenerne di più rappresentativi.

**Il processo di training consiste nello stimare $f(\cdot)$ in modo tale da ottenere una $\hat{f(\cdot)}\simeq f(\cdot)$** 

**Il processo di inferenza consiste, una volta ottenuta la $\hat{f}(\cdot)$  dato un nuovo esempio (coppia di input e output) $(x^*,y^*)$ e noto l'output corretto, nell'ottenere una predizione corretta per cui $\hat{y}^*=\hat{f}(x^*)$**
### Errore riducibile ed irriducibile

L'errore (calcolato al quadrato in quanto non rilevante il segno) sarà definito come $$Error=(y^*-\hat{y}^*)^2$$
Il valore atteso dell'errore sarà:
$$E[(y^*-\hat{y}^*)^2]=E[((f(x^*)+\epsilon)-\hat{f}(x^*))^2]$$
Che sarà uguale a:
$$E[(y^*-\hat{y}^*)^2]=(f(x^*)-\hat{f}(x^*))^2+Var[\epsilon]$$
Con il primo contributo **errore riducibile** ed il secondo **errore irriducibile**. L'unica parte che si può migliorare è quella relativa all'errore riducibile, che può essere ridotta il più prossimamente possibile a $0$, la parte relativa all'errore irriducibile non può essere migliorata e dipende dalla varianza dell'errore $\epsilon$, la dispersione dei dati rispetto al valore della funzione reale.

Generalmente se gli input sono molto correlati agli output la varianza di $\epsilon$ è piuttosto bassa. Nei casi in cui si mantiene il rumore nel processo di apprendimento, verrà appreso il rumore ed il modello andrà in "overfitting", così non riuscendo a generalizzare a casi e

sterni a quelli sui quali è stato allenato, per cui $\hat{f}$ deve essere simile a $f(\cdot)$ non ad $f(\cdot)+\epsilon$

### Univariate Linear Regression

Considerati input con una singola feature ed output con una singola label per cui ed assumiamo con:
$$\begin{array}
x x\in R \\
y\in R \\
y=f(x)+\epsilon \\
E[\epsilon]=0
\end{array}$$
Assumiamo per ipotesi che $x$ ed $y$ siano legati da una funzione $f(x)$ lineare, per cui anche la funzione modellata sarà:
$$\hat{f}=\Theta_{0}+\Theta_{1}x=h(\Theta_{0},\Theta_{1})$$
Con $\theta_{0},\theta_{1}$ parametri dell'ipotesi o parametri del modello.

$\hat{f}(\cdot)=h(\theta_{0},\theta_{1})$ è una famiglia di soluzioni, tutte rette che si differenziano in base ai parametri.

Dato il dataset si vuole risalire ai $\theta_{0}$ e $\theta_{1}$ 

![[Slides.pdf#page=5&rect=81,363,489,610|Slides, p.5]]

La retta verde e  blu sono due possibili soluzioni con parametri diversi, l'obiettivo è ottenere i valori ottimali di $\theta_{0}$ e $\theta_{1}$ tali da minimizzare l'errore per ogni punto del dataset, la distanza tra il punto predetto dalla funzione modellata con quei parametri ed il punto individuato dalla funzione reale.

Dati $\theta_{0}^*$ e $\theta_{1}^*$ valori ottimali rispetto ad una funzione costante.

Resi ottimali rispetto ad una funzione costo.
Considerata la funzione errore quadratico medio come costo.

Considerati $m$ esempi e tutte le coppie $$(x^{(n)},y^{(n)})$$ 
per ciascun esempio sarà possibile esprimere una 
$$\hat{y}^{(n)}=\Theta_0+\Theta_1x^{(n)}$$ E così calcolare gli errori come:
$$Err^{(n)}=[y^{(n)}-(\Theta_0+\Theta_1x^{(n)})]^2$$
Sarà errore quadratico medio dunque la media degli errori:
$$J(\Theta_0,\Theta1)=\frac{1}{m}\sum_{n=1}^m[y^{(n)}-(\Theta_0+\Theta_1x^{(n)})]^2$$
	*Nota bene: nella funzione costo $y^{(n)}$ e $x^{(n)}$ sono delle costanti! sono le label del dataset e le relative features! sono note a priori! le uniche variabili sono i theta.*

Data la funzione $J$ che si vuole rendere minima per ottenere i parametri ottimali il problema diventa un problema di ottimizzazione: 

**Ottenere i $\Theta_0^*$ e $\Theta_1^*$ che minimizzano $J(\Theta_0,\Theta_1)$.**

Noto che l'errore quadratico medio:
Assumendo per ipotesi che $\Theta_0=0$ per poter plottare in due dimensioni:
![[Slides.pdf#page=7&rect=255,374,502,548|Slides, p.7]]

**Si dimostra che per la regressione lineare l'errore quadratico medio è sempre una funzione convessa, questa convessità implica che esiste un unico minimo, ciò la rende ottimale per trovare i $\theta$.**

#### Gradient Descent

L'algoritmo utilizzato per trovare il minimo della funzione errore quadratico medio $J$ nel momento in cui non abbiamo modo di ottenerlo attraverso la sua forma chiusa.

L'idea dietro la Gradient Descent è trovare il minimo della funzione.

Partendo da un punto casuale individuato da  $\overline\theta_{0}$ e $\overline\theta_{1}$ qualunque.

![[Slides.pdf#page=8&rect=84,78,298,373|Slides, p.8|350]]

La pendenza in un certo punto da informazione sulla direzione verso il minimo.
La direzione è data dalle derivate parziali.
Essendo la funzione $MSE$:
$$J(\theta_0,\theta1)=\frac{1}{m}\sum_{n=1}^my^n-(\theta_0+\theta_1x^{(n)})^2$$Sarà:
$$\frac{\partial}{\partial \theta_{0}}J=\frac{2}{m}\sum_{n=1}^m(\theta_0+\theta_1x^{(n)})-y^n$$
E:
$$\frac{\partial}{\partial \theta_{1}}J=\frac{2}{m}\sum_{n=1}^m[(\theta_0+\theta_1x^{(n)})-y^n]\cdot x^{(n)}$$
![[Slides.pdf#page=9&rect=75,348,330,482|Slides, p.9]]
Nel caso bidimensionale si osserva che superato il minimo la derivata rispetto a $\theta_{1}$ di $J$ sarà positiva e viceversa prima del minimo. 

Per cui l'algoritmo consisterà nell'aumentare $\theta$ quando si ha una pendenza positiva e diminuirlo quando invece è negativa. 

Perciò si ripete fino alla convergenza per ciascun $\theta$:
$$\theta_{k}^{new}=\theta_{k}-\partial \frac{J(\theta_{0},\theta_{1})}{\partial \theta_{k}}\cdot \alpha$$

**Per cui si calcolerà la pendenza ed il suo contributo sposterà il valore di $\theta_{k}$ proporzionalmente ad un iperparametro (un parametro manipolabile liberamente, i parametri normali solo quelli del modello che si vuole ottenere) "learning rate" $\alpha$.**

L'aggiornamento del valore $\theta_{k}$ deve assere atomico, per cui per calcolare i nuovi valori si utilizzando i vecchi:

![[Slides.pdf#page=10&rect=62,572,509,695|Slides, p.10]]
	*Manca $\alpha$ nella formulazione di $\theta_{1}$ per colpa sua* 

È possibile calcolare la convergenza con una certa soglia, per cui quando gli aggiornamenti smettono di superare una soglia $\gamma$ (un altro iperparametro):
	`if`$|J(\theta_{1}^{new},\theta_{0}^{new})-J(\theta_{1},\theta_{0})| <\gamma$ `then stop`

La soglia gamma determina un trade-off tra l'accuratezza (una soglia bassa) ed il tempo impiegato nel training (una soglia alta). 

Si osserva che al variare di alpha:
![[Slides.pdf#page=11&rect=70,562,533,702|Slides, p.11]]
- Un $\alpha$ troppo basso porta a degli update molto piccoli ed una convergenza lenta.
- Un $\alpha$ troppo grande porta a una divergenza.

### Multi-variate Linear Regression
Considerati input con più features ed output con una singola label per cui:
$$\begin{array}
x \overline{x}^{(i)}\in R^n \\
y^{(i)}\in R \\
y^{(i)}=f(\overline{x}^{(i)})+\epsilon \\
E[\epsilon]=0
\end{array}$$
Per cui  considerati $m$ esempi (righe) per ciascun esempio $i-$esimo  saranno presenti $n$ features (colonne):
$$\begin{array}
xx_{1}^{(1)} & x_{2}^{(1)} & \dots & x_{n}^{(1)} & y^{(1)}\\
x_{1}^{(2)} & x_{2}^{(2)} & \dots & x_{n}^{(2)} & y^{(2)}\\
\dots & \dots & \dots & \dots & \dots\\
x_{1}^{(m)} & x_{2}^{(m)} & \dots & x_{m}^{(1)} & y^{(m)}
\end{array}$$

Assumiamo per ipotesi che $x$ ed $y$ siano legati da una funzione $f(x_{1},x_{2},\dots,x_{n})$ lineare, per cui anche la funzione modellata sarà:
$$\hat{f}(\overline x)=\theta_{0}+\theta_{1}x_{1}+\theta_{2}x_{2}+\dots+\theta_{n}x_{n}$$
Si osserva che si avranno $n+1$ parametri $\theta_{n}$. **Queste soluzioni rappresentano iperpiani ad $n$ dimensioni.**

Esempio con $n=3$:
![[Slides.pdf#page=11&rect=247,126,436,275|Slides, p.11]]
Potremmo esprimere dunque le feature di ciascun esempio come una matrice colonna, così come i parametri della funzione, per esprimere tutto in forma matriciale, immaginando di aggiungere una feature pari ad $1$ per poi poter esprimere tutto come un prodotto matriciale:
$$\overline x=\begin{bmatrix}
1\\
x_{1} \\
x_{2}  \\
\dots \\
x_{n} 
\end{bmatrix}\  \overline\theta=\begin{bmatrix}
\theta_{0}\\
\theta_{1} \\
\theta_{2}\\
\dots \\
\theta_{n}  
\end{bmatrix}$$
 Con $\overline x \in R^{n+1}$  e  $\overline \theta \in R^{n+1}$, ovvero ($n$,$1$)

Sarà dunque possibile esprimere la funzione  modellata come prodotto matriciale :
$$\hat{y}^{(i)}=\overline{x}^{^T(i)}\cdot  \overline{\theta}$$
	*Che si osserva che svolgendo il prodotto riga per colonna fa effettivamente*  $$\hat{y}^{(i)}=\theta_{0}+\theta_{1}x_{1}^{(i)}+\theta_{2}x_{2}^{(i)}+\dots+\theta_{n}x_{n}^{(i)}$$
#### Matrice di design
Sarà la matrice di design $\overline X$ la matrice con tutte le feature degli esempi per righe:
$$\overline X=\begin{bmatrix}
1 & x_{1}^{(1)} & x_{2}^{(1)} & \dots & x_{n}^{(1)} \\
1 & x_{1}^{(2)} & x_{2}^{(2)} & \dots & x_{n}^{(2)} \\
\dots & \dots & \dots & \dots & \dots \\
1 & x_{1}^{(m)} & \dots & \dots & x_{n}^{(m)}
\end{bmatrix}$$
Con $\overline X\in R^{m\times n+1}$ ovvero ($m$,$n+1$)
#### Vettore delle label
Sarà invece vettore delle label $Y$ il vettore con in ogni riga la label relativa a ciascun esempio calcolata attraverso **la funzione reale**:  (si ha dal dataset) 
$$Y=\begin{bmatrix}
y^{(1)} \\
y^{(2)} \\
y^{(3)} \\
\dots\\
y^{(m)}
\end{bmatrix}$$
#### Vettore di predizione
Si definisce il vettore di predizione $\overline{\hat{Y}}$ il vettore con in ogni riga la label relativa a ciascun esempio calcolata attraverso **la funzione di predizione**:
$$\overline{\hat{Y}}=\begin{bmatrix}
\hat{y}^{(1)} \\
\hat{y}^{(2)} \\
\hat{y}^{(3)} \\
\dots\\
\hat{y}^{(m)}
\end{bmatrix}$$
Sarà dunque tenendo tutto in considerazione ricordando la definizione di [[Prodotto matriciale|prodotto matriciale]] sarà:$$\overline{\hat{Y}}=\overline X\cdot \overline \theta=\begin{bmatrix}
1 & x_{1}^{(1)} & x_{2}^{(1)} & \dots & x_{n}^{(1)} \\
1 & x_{1}^{(2)} & x_{2}^{(2)} & \dots & x_{n}^{(2)} \\
\dots & \dots & \dots & \dots & \dots \\
1 & x_{1}^{(m)} & \dots & \dots & x_{n}^{(m)}
\end{bmatrix}\cdot\begin{bmatrix}
\theta_{0}\\
\theta_{1} \\
\theta_{2}\\
\dots \\
\theta_{n}  
\end{bmatrix}=\begin{bmatrix}
\hat{y}^{(1)} \\
\hat{y}^{(2)} \\
\hat{y}^{(3)} \\
\dots\\
\hat{y}^{(m)}
\end{bmatrix}$$Essendo chiaramente ciascun: $$\hat{y}^{(i)}=\theta_{0}+\theta_{1}x_{1}^{(i)}+\theta_{2}x_{2}^{(i)}+\dots+\theta_{n}x_{n}^{(i)}$$
#### Funzione di costo nel caso multi-variate
La funzione di costo:
$$J(\theta_{0},\theta_{1},\dots,\theta_{n})=\frac{1}{m}\sum_{i}^m(\hat{y}^{(i)}-y^{(i)})^2=\frac{1}{m}\sum_{i}^m(\theta_{0}+\theta_{1}x_{1}^{(i)}+\theta_{2}x_{2}^{(i)}+\dots+\theta_{n}x_{n}^{(i)}-y^{(i)})^2$$ Si osserva che esprimendo la differenza tra il prodotto fra la matrice di design $\overline X$ed il vettore dei parametri $\overline\theta$ ed il vettore delle label $\overline Y$ *(Ovvero $\overline{\hat{Y}}-\overline Y$)* si ottiene la matrice colonna:
$$\overline X\cdot\overline \theta -\overline Y=\begin{bmatrix}
\theta_{0}+\theta_{1}x_{1}^{(1)}+\theta_{2}x_{2}^{(1)}+\dots+\theta_{n}x_{n}^{(1)} - y^{(1)}\\
\theta_{0}+\theta_{1}x_{1}^{(2)}+\theta_{2}x_{2}^{(2)}+\dots+\theta_{n}x_{n}^{(2)} - y^{(2)}\\
\dots \\
\theta_{0}+\theta_{1}x_{1}^{(m)}+\theta_{2}x_{2}^{(m)}+\dots+\theta_{n}x_{n}^{(m)} - y^{(m)}\\
\end{bmatrix}$$
Sarà così possibile esprimere la funzione costo come:
$$J(\theta_{0},\theta_{1},\dots,\theta_{n})=\frac{1}{m}(\overline X\cdot\overline\theta-\overline Y)^T(\overline X\cdot\overline \theta-\overline Y)$$
	*Nota: Quello che succede moltiplicando la trasposta per se stessa è ottenere ciascuna riga al quadrato e poi sommarle tra di loro (basta farlo per rendersene conto), questo equivale alla parte relativa alla sommatoria, perciò basta poi dividere tutto per m e si ha un espressione della $J$. Osserva che $J$ è uno scalare!*

L'obbiettivo è trovare il $\overline{\theta^*}$ tale da minimizzare la funzione di costo.

Per farlo analiticamente sarà necessario derivare la forma chiusa:
	*Per forma chiusa intende trovare un espressione diretta che consenta di trovare il vettore $\overline \theta^*$ direttamente.*

Considerato [[Operatori differenziali#Gradiente di un campo scalare|gradiente]] di $J$ la matrice colonna con in ciascuna riga le derivate della funzione costo rispetto a ciascun parametro:
$$\nabla J(\theta)=\begin{bmatrix}
\frac{\partial J(\theta)}{\partial \theta_{0}} \\
\frac{\partial J(\theta)}{\partial \theta_{1}} \\
\frac{\partial J(\theta)}{\partial \theta_{2}}\\
\dots\\
\frac{\partial J(\theta)}{\partial \theta_{n}}
\end{bmatrix} \in R^{n+1}$$
SI vuole trovare il valore $\overline \theta^*$ che annulla le derivate parziali per trovare il minimo, quello che renda $0$ dunque tutte le righe di questa matrice.
	*Nota: I punti di massimo e minimo di una funzione hanno derivata nulla ed essendo la funzione costo con ipotesi di funzione reale lineare una funzione convessa questa avrà soltanto un minimo, per cui il punto in cui si annulla la derivata dovrà corrispondere proprio a questo.*
Dall'espressione della funzione di costo svolgendo i prodotti si ottiene:
$$J(\overline\theta)=\frac{1}{m}(\overline X\cdot \overline \theta-Y)^T(\overline X\cdot \overline \theta-\overline Y)=\frac{1}{m}[(\overline X\cdot\overline\theta)^T\cdot(\overline X\cdot \overline\theta)-(\overline X\cdot\overline\theta)^T\cdot\overline Y -\overline Y^T\cdot(\overline X\cdot\overline\theta)+\overline Y^T\overline Y]$$
Si osserva che essendo $(\overline X\cdot\overline\theta)^T \cdot \overline Y$ il prodotto tra una matrice riga ed una matrice colonna il risultato sarà uno scalare:
	*Nota: $(\overline X\cdot\overline\theta)$ Sarebbe il vettore $\overline{\hat{Y}}$ che è un vettore colonna, trasposto dunque diventa un vettore riga che moltiplicato per $\overline Y$ che è un vettore colonna fa uno scalare.*
Per lo stesso motivo sarà uno scalare $\overline Y^T(\overline X\cdot\overline\theta)$ 
	*Nota: Questo perchè in questo caso $\overline Y^T$ sarà un vettore riga e $(\overline X\cdot\overline\theta)$ un vettore colonna*.
Si osserva così che queste due quantità sono uguali, per cui riscrivendo:
$$J(\overline\theta)=\frac{1}{m}[(\overline X\cdot\overline\theta)^T\cdot(\overline X\cdot \overline\theta)-2(\overline X\cdot\overline\theta)^T\cdot\overline Y+\overline Y^T\overline Y]$$
Da questa notazione matriciale possiamo calcolare il gradiente di $J$ semplicemente applicando le regole di derivazione derivando rispetto a $\overline \theta$, nonostante questo sia un vettore. 

Osservando che $\overline Y^T\cdot \overline Y$ non dipende da $\overline \theta$ sarà:
$$ \frac{\partial J(\overline\theta)}{\partial \overline \theta}=\frac{\partial\frac{1}{m}[(\overline X\cdot\overline\theta)^T\cdot(\overline X\cdot \overline\theta)-2(\overline X\cdot\overline\theta)^T\cdot \overline Y]}{\partial \overline \theta}$$
Continuando ad applicare le regole di derivazione:
$$\frac{\partial J(\overline\theta)}{\partial \overline \theta}=\frac{1}{m}[2\overline X^T\cdot\overline X\cdot\overline\theta-2\overline X^{T}\cdot\overline Y]$$
Per trovare il $\overline\theta^*$ che minimizza la funzione di costo bisogna trovare il valore che annulla il gradiente, per cui:
$$\frac{1}{m}[2\overline X^T\cdot\overline X\cdot\overline\theta^*-2\overline X^{T}\cdot\overline Y]=0$$
Da cui:
$$2\overline X^T\cdot \overline X\cdot\overline\theta^*=2\overline X^T\cdot\overline Y$$
Infine:
$$\overline\theta^*=(\overline X^T\overline X)^{-1}X^TY$$
Questa espressione ci permette di calcolare analiticamente il vettore dei parametri che minimizzano la funzione di costo.

In alternativa è sempre possibile applicare l'algoritmo Gradient Descent aggiornando iterativamente ciascun $\theta_{i}$
## Polynomial Regression
![[Slides.pdf#page=15&rect=47,112,509,241|Slides, p.15]]
(Caso uni variato)

Assumendo che la funzione reale $f(x)$ non sia una funzione lineare, sarà necessario stimare una funzione anch'essa non lineare, per cui:
$$\hat{y}=\underset{\text{ipotesi lineare}}{\theta_{0}+\theta_{1}x}+\theta_{2}x^2$$
Si osserva che per avere un ipotesi non lineare sarà necessario aggiungere un parametro $\theta_{2}$ ed una feature extra non presente nel nostro dataset che ipotizziamo sia:
![[Slides.pdf#page=16&rect=61,433,447,587|Slides, p.16]]
Quello che dobbiamo fare è creare una colonna extra $x^2$!(Stiamo aggiungendo una nuova feature falsa per aggiungere una dimensione al problema per poterlo considerare lineare)
![[Slides.pdf#page=16&rect=65,236,206,384|Slides, p.16|250]]
Abbiamo così trasformato un problema non lineare in uno lineare, passando da $y=f(x)$ ,non lineare a $y=f(x,x^2)$ un problema lineare rispetto alle due dimensioni(sono tutti punti che stanno sullo stesso piano!).

Assumendo di avere $y=x+x^2$, sostituendo ad $x_{1}=x$ ed a $x_2=x^2$ allora:
$$\hat{y}=\theta_{0}+\theta_{1}x_{1}+\theta_{2}x_{2}$$
Sarà lineare!

Quindi questa nuova ipotesi sarà polinomiale rispetto al problema originale ma **lineare** rispetto al nuovo problema, nel quale abbiamo aggiunto una feature non presente nel dataset originale. 
![[Slides.pdf#page=17&rect=81,445,565,602|Slides, p.17]]
Si osserva che introducendo poche feature polinomiali l'ipotesi sarà in underfitting, il modello non avrà la capacità di approssimare la funzione reale.

Il trucco sta proprio nel fare un ipotesi lineare per un problema non lineare! Per poter usare la regressione lineare.

### Caso multi variato
Immaginando di avere un numero di feature $n>2$
Ad esempio con :
$$y=f(x_{1},x_{2},x_{3})+\epsilon$$
La nostra ipotesi lineare sarà:
$$\underset{\text{ipotesi lineare}}{\hat{y}=\theta_{0}+\theta_{1}x_{1}+\theta_{2}x_{2}+\theta_{3}x_{3}}+\theta_{4}x_{1}^2+\theta_{5}x_{2}^2+\theta_{6}x_{3}^2+\dots$$
Il numero di combinazioni di features è molto grande.

Se si aggiungono troppe feature extra polinomiali:
- Aumenterebbe la complessità computazionale, matrici più grandi portano ad algoritmi più lenti.
- Sono presenti range numerici diversi tra le feature (ci sarebbero feature non bilanciate tra i range in quanto le feature elevate al grado più alto avrebbero più impatto), questo potrebbe portare a problemi nelle soluzioni numeriche (come il gradient descent) Osservando il contour plot della funzione di costo ![[Slides.pdf#page=17&rect=84,90,536,198|Slides, p.17]]Con range simili si raggiunge la convergenza molto più facilmente, bisogna utilizzare l'alpha corretto, rischiando di ottenere una convergenza molto lenta.
- Overfitting, si rischia di allenarsi troppo sul rumore.

### Feature Scaling
Si cerca di trasformare le feature per ottenere lo stesso range per ciascuna feature con le seguenti tecniche di  feature scaling, per cui si trasformano le feature mantenendo però le relazioni tra di loro:

**Minmax Scaling** per cui data una $x$ nel dataset si crea una nuova feature data come:
$$x'=\frac{x-min(x)}{max(x)-min(x)}$$
Così sarà $x'\in[0,1]$

**Mean Normalization** per cui data una $x$ nel dataset si crea una nuova feature come:
$$x'=\frac{x-mean(x)}{max(x)-min(x)}$$
Così sarà $x'\in[-1,1]$ e valore medio $mean(x')=0$ 

**Standardization** per cui data una $x$ nel dataset:
$$x'=\frac{x-mean(x)}{var(x)}$$ Con $x'$ senza restrizioni ma con le seguenti proprietà statistiche:
$mean(x')=0$ e $var(x')=1$

**Il feature scaling è utile anche fuori dal contesto della regressione polinomiale.**
## Performance della gradient descent
Le performance dell'algoritmo variano in base alla sua implementazione:

Nel caso della **batch gradient descent**, calcolata in forma matriciale:
![[Slides.pdf#page=18&rect=94,292,513,352|Slides, p.18]]
L'update sarà effettuato computando la derivata della funzione costo rispetto l'intero dataset (necessario a causa della sommatoria nella formula della derivata).

Nel caso della **stochastic gradient descent**:

L'update è effettuato computando la derivata della funzione costo relativamente ad un singolo esempio scelto casualmente, usando quindi escludendo la sommatoria. 

Per cui a seconda del punto scelto la correzione potrebbe essere più o meno effettiva.
Sarà dunque una variante computazionalmente meno complessa ma meno precisa, portando ad una convergenza più lenta.

Nel caso della **mini batch gradient descent**:

L'update viene effettuato scegliendo un sottoinsieme di esempi e calcolando su questi il costo, questa soluzione generalmente è la preferita.

## Debugging del modello

Si vuole sapere se  il modello è capace di generalizzare e performare bene quando riceve in input dei nuovi dati non presenti in fase di training, un modello potrebbe aver azzerato la funzione di costo ma comunque non essere accurata con input mai visti.

Per quantificare la capacità di generalizzazione si dovrà dividere il dataset in due parti con percentuali diverse, cercando di dividere i dati nei vari sottoinsieme casualmente quando possibile (questo per cercare di evitare il caso di prendere solo certe selezioni da dati ordinati che potrebbe non fornire una rappresentazione realistica del fenomeno, questo potrebbe non essere possibile ad esempio quando i dati dipendono dal tempo cercando di inferire qualcosa relativa alla loro consequenzialità, in quanto mischiandoli si perderebbe la correlazione temporale.): 
- Training
-  Test

Possiamo dunque da questi dataset calcolare due funzioni costo diverse:
- $J^{train}$
- $J^{test}$

Data la capacità del modello, un valore proporzionale al numero di parametri, diminuendo la capacità eccessivamente si andrà in underfitting per cui $J^{train}$ sarà alto così come $J^{test}$. 

aumentando la capacità eccessivamente si andrà in overfitting, per cui $J^{train}$ sarà basso ma $J^{test}$ sarà alto!

Si vuole ottenere la capacità ottimale per cui la $J^{train}$ sarà bassa così come la $J^{test}$.

Un euristica per ottenere questo risultato è l'applicazione del **rasoio di Occam**, per cui tra tutte le soluzioni possibili è necessario scegliere le più semplicità


Introducendo parametri diversi nella funzione costo, come ad esempio il numero di parametri utilizzati, cercherà di utilizzare meno capacità possibile in modo tale da cercare di bilanciare la riduzione dell'errore quadratico medio e l'aggiunta di muovi parametri, evitando di andare in overfitting

### Curve di apprendimento 
Le curve di apprendimento sono plot di $J_{Train}$ e $J_{Test}$ rispetto a qualcosa di specifico.

- Una possibilità è quella di plottarle rispetto al numero di iterazioni della gradient descent.

- Un altra possibilità è effettuare il plot rispetto alla capacità del modello.
![[Slides.pdf#page=39&rect=150,350,521,531|Slides, p.39]]


- Un'altra possibilità è quella di effettuare il plot rispetto alle dimensioni del dataset (il numero di esempi $m$).
![[Slides.pdf#page=39&rect=70,119,546,297|Slides, p.39]]
Osserviamo che all'aumentare della dimensione del dataset il costo di allenamento continua a crescere.
![[Slides.pdf#page=40&rect=71,542,401,711|Slides, p.40]]
Il costo di test invece diminuisce all'aumentare di $m$.

Plottandole insieme ci rendiamo conto di $3$ scenari possibili:
![[Slides.pdf#page=40&rect=67,345,554,507|Slides, p.40]] 

- Un'altra possibilità relative alle reti neurali è quella di effettuare il plot rispetto alle epoche della rete neurale.

### Regolarizzazione

L'obiettivo è indicare all'algoritmo di tenere la più bassa capacità possibile per evitare di andare in overfitting, questo è possibile indicando la capacità del modello come parametro nella funzione di costo, così l'algoritmo tenderà a ridurlo, cercando di mantenere comunque il più basso possibile l'errore quadratico medio.

Vogliamo quindi introdurre una funzione della capacità $\phi(c)$ nella $J(\theta)$, considerando questo termine come termine di regolarizzazione, come:
$$J(\theta)=\frac{1}{m}\sum_{i=1}^m[\hat{y}^{(i)}-y^{(i)}]+\lambda\phi(c)$$
Con $\lambda$ iperparametro che regola quanto peso dare alla parte relativa alla riduzione della capacità.

La capacità del modello $c$ è correlata al numero di parametri per cui è possibile esprimere la stessa $J(\theta)$ indicando $\phi$ come una funzione dei parametri:
$$J(\theta)=\frac{1}{m}\sum_{i=1}^m[\hat{y}^{(i)}-y^{(i)}]+\lambda\phi(\theta)$$
Esistono due possibili approcci per esprimere $\phi(\theta)$:
- Ridge Regression
- Lasso Regression
#### Ridge regression

Nella Ridge regression la funzione di costo si esprime come:
$$J(\theta)=\frac{1}{m}\sum_{i=1}^m[\hat{y}^{(i)}-y^{(i)}]+\lambda \sum_{j=1}^q\theta_{j}^2$$
	*Non consideriamo $\theta_0$ in quanto non viene regolarizzato, in quanto non è associato ad una specifica feature e non è strettamente correlato alla capacità del modello ma comporta solo una traslazione.*

Si osserva che ciascun parametro indica la rilevanza della feature relativa, per cui scartane uno implica scartare un parametro. Per cui il valore stesso del parametro è correlato alla capacità del modello 
	*Esempio: in un modello polinomiale se la feature quadratica viene associata ad un valore tendente a $0$ il modello si comporterà da modello lineare) *

La regolarizzazione dunque agisce sul valore numerico dei parametri oltre che sul loro numero.

#### Lasso Regression

Nella lasso regression la funzione di costo con il termine di regolarizzazione viene espressa come:
$$J(\theta)=\frac{1}{m}\sum_{i=1}^m[\hat{y}^{(i)}-y^{(i)}]+\lambda \sum_{j=1}^q|\theta_{j}|$$Considerando solo  il valore assoluto di ciascun $\theta_{j}$ 

#### Differenze tra lasso e ridge regression

Consideriamo un esempio con solo due feature e consideriamo la $J$ con solo il termine di regolarizzazione:
$$J(\theta)\begin{cases}\lambda \sum_{j=1}^q\theta_{j}^2=\theta_{1}+\theta_{2} \ Ridge\\ \\

\lambda \sum_{j=1}^q|\theta_{j}|=|\theta_{1}|+|\theta_{2}| \ \ Lasso

\end{cases}$$
Osservando i contour plot(che indica i punti in cui il valore della funzione di costo è lo stesso):
![[Slides.pdf#page=42&rect=62,62,561,322|Slides, p.42]]

La ridge regression cercherà di ridurre la capacità cercando di ridurre l'effetto di ciascuna feature.

La lasso regression invece porterà a $0$ le feature meno importanti, per cui questo metodo può essere utilizzato come un selezionatore di feature. 

# Classificazione
Lo scopo della classificazione è predirre una classe (non un valore numerico come nella regressione). Si differenziano:

- Classificazione binaria (con solo due classi)
- Classificazione multi-classe ( più di due classi mutualmente esclusive)
- Classificazione multi-classe multi-label (più di due classi non mutualmente esclusive)

La classificazione consiste nel calcolo della probabilità che l'input appartenga a ciascuna classe e dall'utilizzo di questa allo scopo di effettuare la predizione.
## Classificazione binaria

Lo scopo finale è predire la classe corretta **tra due singole classi**, avendo inizialmente un dataset nel quale la label corrisponde ad una classe.
![[Slides.pdf#page=20&rect=58,468,262,604|Slides, p.20]]
Si avrà, codificando le due classi rispettivamente con $0$ ed $1$: 
$$\begin{array}
ay=f(x)+\epsilon \\
x \in R^n  \\
y \in \{ 0,1 \} \\
E[\epsilon]=0
\end{array}$$Date le features in input si vuole per prima cosa predire **la probabilità che l'input appartenga ad una classe e da questa**, la classe.

Essendo la probabilità un valore numerico si può applicare su questa una regressione.
### Regressione Logistica
Dato un esempio si vuole ottenere la probabilità di essere nella classe $1$ dato $x*$ come input:
$$P(y=1|x*)=1-P(y=0|x^*)$$
Per trovare questo valore effettuiamo un ipotesi **lineare**, immaginando di essere nel caso con una sola feature:
$$P(y=1|x*)={h}(x*)=\theta_{0}+\theta_{1}x*$$
**Si suppone dunque che la probabilità di appartenere ad una certa classe $1$ aumenti linearmente con $x$.**

Essendo una probabilità quella che si vuole ottenere, deve essere compresa tra $[0,1]$

Per far ciò si applica il valore ottenuto dall'ipotesi ad una **funzione logistica**, una funzione che limita i valori di uscita di  tra $0$ ed $1$ definita come:
$$z=\frac{1}{1+e^{-x}}=\sigma(x)$$

![[Slides.pdf#page=21&rect=350,238,522,416|Slides, p.21|350]]
Per cui sarà:
$$\hat{y}(x)=\sigma(\theta_{0}+\theta_{1}x)=\frac{1}{1+e^{-\theta_{0}+\theta_{1}x}}$$
Nel caso multi variato, in cui $x \in R^n$ sarà:
$$\hat{y}(x)=\sigma(\theta_{0}+\theta_{1}x_{1}+\theta_{2}x_{2}+\dots+\theta _{n}x_{n})$$
Per cui sarà possibile esprimere tutto in forma matriciale: 
$$\hat{y}(x)=\sigma(\overline{X}\cdot\overline{\theta)}=\frac{1}{1+e^{-\overline{x}\cdot\overline\theta }}$$ A questo punto ottenuta la probabilità si potrà computare una funzione costo per ottimizzare i parametri dell'ipotesi.

Nella regressione logistica l'errore quadratico medio non è convesso a causa dell'esponenziale, una funzione di costo non convessa conterrà minimi locali e plateau che porteranno l'algoritmo gradient descent ad interrompersi prima di aver trovato il valore ottimale.
![[Slides.pdf#page=23&rect=85,71,381,184|Slides, p.23]]
Per cui sarà necessario trovare un altra funzione di costo che sia una funzione convessa che indichi un costo elevato quando l'output della regressione logistica non è coerente con la classe indicata dall'esempio.
![[Slides.pdf#page=24&rect=66,469,545,646|Slides, p.24]]
Data la funzione esponenziale che rende la funzione di costo non convessa sarà possibile applicare una funzione di costo logaritmica per rimuovere l'esponenziale.
![[Slides.pdf#page=24&rect=60,250,298,448|Slides, p.24|250]]
![[Slides.pdf#page=24&rect=306,252,549,466|Slides, p.24|250]]
Si osserva che le funzioni $-\log[h_{\theta}(x)]$ e $-\log[1-h_{\theta}(x)]$ sono convesse, inoltre:
- $-\log[h_{\theta}(x)]$ ritorna costi alti per valori bassi e viceversa, dunque è una funzione di costo coerente per i casi in cui $y=1$
- $-\log[h_{\theta}(x)]$ ritorna costi bassi per valori bassi e viceversa, dunque è una funzione di costo coerente per i casi in cui $y=0$

È possibile dunque combinare le due funzioni come:
$$\log[h_{\theta}(x^{(i)})]y^{(i)}-\log[1-h_{\theta}(x^{(i)})](1-y^{(i)})$$
Così da esprimere la funzione di costo come:
$$J(\theta)=\frac{1}{m}\sum_{i=1}^m\log[h_{\theta}(x^{(i)})]y^{(i)}-\log[1-h_{\theta}(x^{(i)})](1-y^{(i)})$$
 Essendo questa una funzione di costo convessa, sarà possibile effettuare il gradient descent, così da trovare i parametri $\theta$ necessari.

**Una volta ottenuta una stima della probabilità sarà possibile predire la classe finale utilizzando una soglia.**
## Decision Boundaries
![[Slides.pdf#page=26&rect=62,195,560,293|Slides, p.26]]
![[Slides.pdf#page=26&rect=82,54,515,197|Slides, p.26]]
![[Slides.pdf#page=27&rect=70,549,534,721|Slides, p.27]]
Si osserva che $\hat{y}^{(i)}=1$ solo quando $x^{(i)^T}\theta>0$ e viceversa.

Per cui per $x^{(i)^T}=0$ si avrà un iperpiano in $n$ dimensioni definito come **decision boundary** che rappresenta la soglia dalla quale ci si considera in una o l'altra classe.

## Classificazione multi-classe
Si effettua la classificazione multi-classe quando il numero di classi è $>2$ e queste sono mutualmente esclusive.

Si differenziano le seguenti classificazione multi-classe:
- One vs All in cui si allenano $k$ diversi classificatori binari, dopodichè si decide la classe finale tramite un sistema di voti.
- One vs One per cui vengono allenati $\frac{k(k-1)}{2}$ ed alla fine si predice la classe che ottiene il numero massimo di vittorie.
- Regressione softmax per cui si predicono $k$ probabilità con $k$ classificatori.

### Regressione softmax

tutto quello che dice molto ez
*sistema*

### Multi label multi class classification

Considerato un numero di classi $>2$ non mutualmente esclusive, si converte il problema in una classificazione multiclasse, ad esempio utilizzando il one-hot encoding, ipotizzando di avere una sola istanza per ciascuna classe alla volta per esempio.

*sistema*
## Metriche di classificazione

*matrice di confusione*

Si definiscono le seguenti metriche per valutare un algoritmo di classificazione:
- Si definisce **accuratezza** il rapporto tra il numero di predizioni corrette sul numero di predizioni totali effettuate. Questa metrica però è significativa solo per dataset bilanciati, in cui le classi appaiono con frequenze simili, non dovesse essere così anche un algoritmo poco efficace potrebbe ottenere accuratezze molto alte.
- Si definisce **precisione** il rapporto tra predizioni positive corrette e la somma tra predizioni positive totali, per cui questa metrica si abbassa quando aumenta il numero di falsi positivi.
- Si definisce **recall** il rapporto tra predizioni positive corrette e la somma tra le predizioni positive vere ed i falsi negativi. Questa metrica si abbassa quando aumentano i falsi negativi.


**Se si ha un modello di regressione logistica allenato è possibile alterare i valori di precisione e recall senza rifare l'allenamento cambiando la soglia.**

