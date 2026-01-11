## Permutazioni semplice

Dato un insieme $I_{n}$ e $P_{n}$ il numero di tutte le possibili *permutazioni semplici* di elementi di $I_{n}$ sarà
$$P_{n}=n!$$
#### Esempio:

Tre palline di colori diversi, si vuole sapere il numero di tutte le possibili sequenze diverse nelle quali si possono disporre,
- $I_{n}=\{rossa,nera,grigia\}$ 
- $n$=3
Per cui sarà:
$$P(n)=3! =6$$
Sarà possibile disporre le palline in 6 sequenze diverse.

## K permutazione
Dati $n$ elementi distinti di un insieme $I_{n}$, tutti i possibili sottoinsiemi di $k$ elementi distinti e totalmente ordinati che formano l'insieme, sono detti $k$ permutazioni di n $D_{n,k}$ con $k<n$
Con:
$$D_{n,k}=\frac{n!}{(n-k)!}$$
L'ordine è rilevante
### Esempio
Tre palline di colori diversi, si vuole sapere il numero di tutte le possibili sequenze di elementi presi a due a due  diverse nelle quali si possono disporre,
- $I_{n}=\{rossa,nera,grigia\}$ 
- $n$=3
- k=2
Per cui sarà:
$$P(n)=\frac{3!}{1!}=6$$
Sarà possibile disporre le palline  in 6 coppie diverse.

## Combinazioni
Dati n elementi distinti, tutti i possibili sottoinsiemi di k elementi distinti di n è detta k combinazione $C_{n,k}$ di n con:
$$C_{n,k}=\frac{D_{n,k}}{k!}=\frac{n!}{(n-k)!k!}=\binom{n}{k}$$


*Da sistemare*

## B

Dati n elementi distinti, tutti i possibili sottoinsiemi di k elementi  degli n sono dette k combinazioni di n con ripetizioni $D'_{n,k}$
Con:
$$D'_{n,k}=n^k$$
### Esempio
Esempio palle di prima ma vengono considerate tutte le possibilità in cui sono presenti gli stessi elementi ma in ordini diversi, prendendo in considerazione anche elementi non distinti


