## Generazione Numeri Randomici

Caratteristiche che si desiderano abbiano i numeri randomici sono:

- Uniformità nell'intervallo $[0,1]$, caratteristica per cui dividendo l'intervallo di uniformità in $N$ sottointervalli e generando $x$ valori randomici in ciascun sottointervallo dovranno essere presenti $\frac{x}{N}$ campioni
- Indipendenza , per cui ciascun nuovo campione non deve dipendere dal valore del campione precedente

Nella generazione di numeri casuali si cerca di **approssimare dunque queste caratteristiche.**

Per una approssimazione efficiente si suppone che un algoritmo di generazione di numeri casuali:

- Sia **computazionalmente efficiente**, deve essere particolarmente veloce per algoritmi di generazione  di numeri randomici perchè le chiamate a funzioni che implementano a questi algoritmi sono molto frequenti e se così non fosse molto tempo perso sarebbe speso solo a generare i numeri.
- Abbia **lunghi cicli**, non è effettivamente possibile avere una sequenza infinita di numeri randomici uniformemente in un intervallo, la sequenza di numeri generati dall'algoritmo dopo un certo punto comincerà a rigenerare gli stessi numeri nello stesso ordine.  
  questa lunghezza di numeri entro i quali la sequenza si mantiene randomica si chiama **ciclo**.
- Sia **riproducibile**, La riproducibilità rappresenta la possibilità di riprodurre la stessa sequenza di numeri randomici nel momento in cui si volesse effettuare l'esperimento attraverso la stessa sequenza di numeri casuali.
### Linear congruential method

L'algoritmo principale noto per la generazione di numeri casuali. IL più semplice ed il più diffuso.
Una sequenza di numeri interi $X_{1},X_{2},\dots,$ nell'intervallo $[0,m-1]$ si genera con:
 $$X_{i+1}=(aX_{i}+c)\  mod\ m$$ 
 Con:
 - $X_{0}$ : seed impostato a priori che regola la generazione della sequenza.
 - $a$:  moltiplicatore.
 - $c$ : incremento. 
 - $m$ modulo. 
 Osserviamo che il seed garantisce la riproducibilità

Le caratteristiche dei numeri casuali generati da questo algoritmo si osservano essere:
- Uniformità nell'intervallo $[0,m-1]$ 
- È possibile generare numeri casuali nell'intervallo $[0,1]$ come $R_{i}=\frac{X_{i}}{m}$
	*Si osserva che non potendo mai $X_{i}$ assumere il valore $m$ in questo modo non si otterrà mai $1$, tuttavia si  potrà ottenere un numero che gli sarà sempre più vicino al crescere di $m$. 

### Linear combination

Un algoritmo alternativo che garantisce periodi estramemente lunghi è la Linear Combination, considerati 
$n$ generatori che generano numeri casuali tramite l'algoritmo Linear congruential e facendone la combinazione lineare con coefficenti che si alternano tra $1$ e $-1$ si genera:
$$X_{i}=[\sum_{j=1}^n(-1)^{j-1}X_{i,j}]\ mod\  m_{1}-1$$
Il periodo dei numeri generati da questo metodo dipenderà dal prodotto nel periodi dei generatori:
$$P=\frac{(m_{1}-1)(m_{2}-2)\dots(m_{n}-1)}{2^{n-1}}$$
Si può migliorare il periodo senza aumentare il modulo aumentando il numero di sequenze!

Allo stesso modo è possibile ottenere un numero casuale uniforme nell'intervallo $]0,1[$ a partire da questo metodo tramite:
$$R_{i}=\begin{cases}\frac{X_{i}}{m_{1}},X_{i}>0 \\
\frac{m_{1}-1}{m_{1}},X_{i}=0

\end{cases}$$

## Inverse Transform Sampling

È possibile dimostrare che data la variabile aleatoria **continua** $X$ con funzione densità di probabilità $f_X(x)$, la variabile aleatoria cumulativa:
$$C(X)=\int_{-\infty}^Xf_{X}(u)du$$
È distribuita uniformemente nell'intervallo $[0,1]$.

Essendo $\int_{-\infty}^Xf_{X}(u)du$ un integrale definito sarà possibile esprimerlo in termini delle primitive di $f_{X}(x)$,  essendo la sua primitiva [[3 Variabili Aleatorie e distribuzioni di probabilità#^niqt1s|la funzione CDF]] ed [[3 Variabili Aleatorie e distribuzioni di probabilità#^cewj30|essendo]] $F_{X}(-\infty)=0$  sarà possibile esprimere, osservando in termini di valori specifici di variabili aleatorie:
$$c=F_{X}(x)$$
Se la $F(X)$ è **invertibile** sarà possibile esprimere, osservando in termini di variabili aleatorie: $$X=F^{-1}(C)$$ che sarà una variabile aleatoria che avrà la stessa distribuzione di $X$! 

**Quindi è possibile generare un numero casuale con distribuzione uguale a quella di una variabile aleatoria $X$ proprio conoscendo l'inverso della sua CDF, generando un numero casuale da una distribuzione uniforme tra $[0,1]$**

### Caso Discreto
*da aggiungere*