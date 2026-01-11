Le variabili aleatorie sono necessarie per dare un associazione numerica all'esito di un esperimento randomico. Le computazioni di natura probabilistica vengono eseguite in termini di variabili aleatorie.
## Definizione
Una variabile aleatoria $X$ su uno spazio campione $S$  è una funzione che associa ad un elemento dello spazio campione un numero reale:
$$X:S\to R$$
Per cui $X(s)$ per ogni punto dello spazio campione assume un valore reale.

> [!example]- Esempio
> Considerato l'esperimento del lancio della moneta lo spazio campione $S=\{Testa,Croce\}$ sarà $s_{1}=Testa$ ed $s_{2}=Croce$, sarà possibile dunque assegnare una variabile aleatoria $X$ all'esperimento tale  che $X(s_{1})=0$ e $X(s_{2})=1$. L'assegnazione dei punti dello spazio campione a rispettivi valori reali è del tutto arbitraria.

Deve essere vera la seguente condizione:  $$\forall x\in R\Rightarrow X(s)\leq x\\ \text{ È un evento}$$
> [!example]- Esempio
> - Considerato $x=0$ sarà un evento $X(s)\leq0$ sarà l'evento $E_{0}=\{Testa\}$
> - Considerato $x=1$ sarà un evento $X(s)\leq 1$ sarà l'evento $E_{1}=\{Testa,Croce\}$
> - Considerato x=-1 sarà un evento $X(s) \leq -1$ sarà l'evento $E_{2}=\{\}$ , l'evento nullo 

A seconda dei valori assunti da $X$ la variabile aleatoria può essere: 
- Continua
- Discreta
- Mista (Può assumerne in un intervallo continuo separato da un intervallo di valori discreti)

La somma delle probabilità che la variabile aleatoria assuma ciascun valore possibile deve essere $1$:
$$\sum_{i}P(X=x_{i})=1$$
## Funzione massa di probabilità 
È possibile definire un evento in funzione del valore assunto dalla variabile aleatoria quando si avvera formalmente come:$$A_{x}=\{s\in S|X(s)=x\}$$
	*L'evento $A_{x}$ così definito rappresenta l'evento in cui la variabile aleatoria $X$ assume un valore specifico $x$*
La probabilità che la variabile aleatoria assuma un valore specifico $x$ si valuta come la somma delle probabilità degli eventi per i quali la variabile aleatoria $X$ assume il valore $x$:
$$P(A_{x})=P([X=x])=\sum_{X(s)=x}P(s)$$
	*La probabilità $P(A_{x})$ rappresenta la probabilità che la variabile aleatoria assuma un determinato valore x* ^7xwj9i

Si definisce funziona massa (pmf) di probabilità di $X$ la funzione che associa ad ogni possibile valore assunto dalla variabile aleatoria $X$ la sua probabilità:
$$p_{X}(x)=P(X=x)=\sum_{X(s)=x}P(s)$$

> [!example]- Esempio
> Nel caso del lancio della moneta con $S=\{1,2,3,4,5,6 \}$ avendo $\forall s \in S\Rightarrow P(s)=\frac{1}{6}$ codificando  $\forall s\in S|s\text{\ è\ pari}\Rightarrow X(s)=1$ e $\forall s\in S|s\text{\ è\ dispari}\Rightarrow X(s)=2$ per ogni s dispari sarà $p_{X}(1)=\frac{1}{6}+\frac{1}{6}+\frac{1}{6}$ e $p_{X}(2)=\frac{1}{6}+\frac{1}{6}+\frac{1}{6}$

Valgono per la funzione probabilità di massa le seguenti proprietà:

- $0\leq p_{X}(x)\leq 1$ per cui per ogni valore di $x$ la probabilità dovrà sempre essere compresa tra $0$ ed $1$

- $\sum_{i}p_{X}(x_{i})=1$ per cui la somma di tutti i valori assunti da $p_{X}(x)$ deve fare $1$ 
## Funzione distribuzione cumulativa
La funzione distribuzione $F_{X}(t)$ cumulativa per una variabile aleatoria $X$ associa la probabilità che la variabile $X$ assuma un valore minore uguale a $t$:
$$F_{X}(t)=P(X\leq t)=\sum_{x\leq t}p_{X}(x)$$
Valgono le seguenti proprietà:

- $\lim_{ t \to -\infty} F_{X}(t)=0$ in quanto la probabilità che la variabile aleatoria assuma un valore minore di $-\infty$ è uguale a $0$  ^cewj30

- $\lim_{ t \to \infty}F_{X}(t)=1$ in quanto la probabilità che la variabile aleatoria assuma un valore minore di $+\infty$ è uguale ad 1 (il 100%)

- $0<=F_{X}(t)<=1$ con $-\infty<=t<=+\infty$ Essendo la probabilità sempre compresa tra $0$ ed $1$.

- $P(a<X\leq b)=P(X\leq b)-P(X\leq A)=F(b)-F(a)$ 

> [!info] Chiarimento
> Questa proprietà anche se chiara intuitivamente viene dal fatto che $P(a < X \le b) = P\big(\{X \le b\} \setminus \{X \le a\}\big)$ (tutto ciò che è minore di b tranne ciò che è minore di a è ciò che è compreso tra i due) e dalla proprietà [[1 Introduzione alla teoria delle Probabilità#^o0zmt1|della probabilità dell'unione degli eventi]] viene facilmente che la probabilità della differenza è la differenza delle probabilità. ^jb9gc3

## Funzione densità di probabilità

Nel caso dello spazio campione continuo la probabilità $P(X=x)=0$ con un qualsiasi $x$ specifico per cui la funzione probabilità di massa $p_{X}(x)$ non può essere definita.

Si definisce invece funzione densità di probabilità (pdf) per variabili aleatorie continue come la derivata della funzione distribuzione cumulativa:
$$f_{x}=\frac{dF_{x}(x)}{dx}$$
Da cui viene che:
$$F(x)=\int_{-\infty}^xf(x)dx$$
Si osserva che per una variabile discreta, la CDF è la [[3 Variabili Aleatorie e distribuzioni di probabilità#^7xwj9i|somma della pmf]]:  ^niqt1s
$$
F_X(x) = \sum_{x_i \le x} p_X(x_i)$$
Per una variabile continua, l’integrale della pdf gioca lo stesso ruolo:
$$
F_X(x) = \int_{-\infty}^{x} f_X(t) \, dt$$
Segue quindi che essendo la probabilità che la variabile  assuma un valore minore di $\infty$:$$\int_{-\infty}^\infty f_{X}(x)dx=1$$Inoltre dal [[Teorema di Torricelli]]:
$$\int_{a}^b f_{X}(x)dx=F_{X}(a)-F_{X}(b)=P(a\leq x\leq b)=1$$ ^zd3cv5

## Valore atteso
Se definisce valore atteso:
$$E[X]=\int_{-\infty}^\infty xf(x)dx$$
Noto il fatto che $x$ sia il valore assunto dalla variabile aleatoria $X$ e che $f(x)dx$ sia la probabilità che $X$ cada nell'intervallo infinitesimo$[x,x+dx]$ 

Il valore atteso è **una media ponderata** dei valori di X, pesata dalle probabilità infinitesime $f_X(x)dx$ .

> [!intuito] Intuito
> È il “centro di massa” della distribuzione: valori con alta probabilità contribuiscono di più alla media. 

## Quantile

Data una funzione densità di probabilità su una variabile aleatoria generica $X$ definisce $x_{p}$ **quantile di ordine $p$** il valore $x$ della variabile aleatoria per cui $F_{X}(x_{p})=P(X\leq x_{p})=p$   

**Il quantile indica per quale valore della variabile aleatoria $X$ si accumula una certa probabilità $p$.**

> [!example]- Esempio
> Se $x=12$ è il quantile di ordine $0.5$, significherà che metà dei valori assunti dalla variabile aleatoria saranno sotto il $12$ e l'altra metà sopra.

## Operazioni tra variabili aleatorie

*da aggiungere*