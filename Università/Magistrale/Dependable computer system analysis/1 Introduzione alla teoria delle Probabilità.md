## Spazio campione

Si definisce spazio campione  $S $l'insieme di tutti i possibili esiti di un esperimento casuale. L'insieme $S$ potrà essere un insieme finito o infinito, discreto o continuo.

Considerato il lancio di dadi lo spazio campione è:
$$S=\{1,2,3,4,5,6\}$$
## Evento

Si definisce evento un qualsiasi sottoinsieme di $S$.
Essendo sottoinsiemi di $S$ sono eventi:

- Lo spazio campione $S$ , l'evento universale
- L'insieme vuoto, l'evento impossibile
- Ogni evento semplice $\{s\},s\in S$ è detto evento elementare

Considerato il lancio dei dadi sono eventi:
$$\begin{array}a \\
E_{1}=\{1\} \\
E_{2}=\{1,3,5\} \\
E_{3}=\{1,2,3,4,5\}
\end{array}$$

### Algebra degli eventi

Dati $E_{1},E_{2},E_{3}$ eventi di $S$:

Si definisce $\overline{E}_{1}$ complemento di $E_{1}$ come:
$$\overline{E}=S-E_{1}=\{s\in S|s\not\in E_{1}\}$$

> [!example]- Esempio
> Il complemento di un evento è composto da tutti gli elementi di $S$ che non sono presenti in quell'evento. Se nel lancio di dadi con $S=\{1,2,3,4,5,6\}$ considerato l'evento $E_{1}=\{1,2,3\}$ allora $\overline{E}=\{4,5,6\}$


Si definisce $E_{3}$ intersezione di due eventi $E_{1},E_{2}$:
$$E_{3}=E_{1}\cap E_{2}=\{s\in S|s\in E_{1} \cap E_{2}\}$$

> [!example]- Esempio
> L'intersezione di due eventi è composto da tutti gli elementi di $S$ che sono presenti in entrambi gli eventi. Se nel lancio di dadi con $S=\{1,2,3,4,5,6\}$ considerato l'evento $E_{1}=\{1,2,3\}$ e l'evento $E_{3}=\{1,2\}$ allora $E_{3}=\{1,2\}$


Si definisce $E_{3}$ unione di due eventi $E_{1},E_{2}$:
$$E_{3}=E_{1}\cup E_{2}=\{s\in S|s\in E_{1} \cup E_{2}\}$$

> [!example]- Esempio
> L'intersezione di due eventi è composto da tutti gli elementi di $S$ che sono presenti in entrambi gli eventi. Se nel lancio di dadi con $S=\{1,2,3,4,5,6\}$ considerato l'evento $E_{1}=\{1,2,3\}$ e l'evento $E_{3}=\{4,5\}$ allora $E_{3}=\{1,2,3,4,5\}$

Due eventi si definisco **mutualmente esclusivi** o **disgiunti** quando $E_{1}\cap E_{2}=\{\}$
Due eventi disgiunti non possono avvenire contemporaneamente come esito dello stesso esperimento.
## Probabilità

La probabilità $P(E)$ rappresenta la tendenza dell'evento $E$ di essere l'esito di un esperimento. Si tratta di una misura della frequenza con la quale l'esito dell'esperimento è l'evento $E$.
### Assiomi di Kolmogorov's

Gli assiomi di Kolmogorov's definisco la probabilità in modo tale da far sì che questa rispetti questi assiomi.
- $\forall E\in S,P(E)\geq0$ **per cui la probabilità di un qualunque evento è sempre un numero maggiore di $0$**

- $P(S)=1$ **Per cui la probabilità che l'esito sia presente nello spazio campione è $1$** (il 100%)

- $\forall A,B\in S:A\cap B=0\Rightarrow P(A\cup B)=P(A)+P(B)$ **per cui la probabilità dell'unione di due eventi se i due eventi sono disgiunti è pari alla somma delle probabilità dei singoli eventi. Questo assioma si può generalizzare alla probabilità dell'unione di un qualsiasi numero di eventi.** ^o0zmt1
### Altre proprietà

Sono valide le seguenti proprietà per le probabilità:
- $\forall A \in S,P(\overline{A})=1-P(A)$ **per cui la probabilità di un evento è uguale ad $1$ meno il suo complementare** (questa differenza rappresenta la probabilità che non esca il suo complementare)

- $P(\emptyset)=0$ per cui la probabilità dell'insieme vuoto è nulla

- $P(A\cup B)=P(A)+P(B)-P(A\cap B)$ per cui **la probabilità dell'unione di due eventi congiunti è pari alla somma delle loro probabilità meno la probabilità dell'intersezione dei due eventi**.
> [!info]- Chiarimento
Questo perchè la parte in comune in ciascun evento sarebbe considerata due volte sommandoli, quindi rimuovendola una volta si ottiene la giusta probabilità

### Definizione di Laplace

La definizione di Laplace definisce la probabilità come il rapporto tra il numero di eventi favorevoli ed il numero di eventi possibili:
$$\begin{array}a 
S=\{ E_{1},E_{2},\dots,E_{N}\} \\
P(E_{1})=P(E_{2})=\dots=P(E_{N}) \\
A=E_{1}\cup E_{2}\cup \dots\cup E_{N_{A}} \\
\end{array}$$
Sarà:
$$P(A)=\frac{N_{A}}{N}$$
> [!example]- Esempio
> Considerato il lancio di dadi con $S=\{ 1,2,3,4,5,6 \}$ e con $A=\{ 1,2,3 \}$ saranno $N=6$ e $N_{A}=3$ sarà perciò $P(A)=\frac{3}{6}$

### Frequenza relativa

La definizione di probabilità come frequenza relativa definisce $P(A)$ con $N$ numero di volte che l'esperimento è stato ripetuto ed $N_{A}$ numero di volte in cui l'esito è stato $A$:
$$P(A)=\lim_{ n \to \infty } \frac{N_{A}}{N}$$
### Probabilità condizionata
Si vuole sapere come varia la probabilità che avvenga un determinato evento dato per vero che l'esito dell'esperimento sia contenuto nell'evento $B\in S$ e che  $P(B)\neq {0}$:

Sarà allora probabilità condizionata $P(s|B)$ la probabilità che l'esito dell'esperimento sia l'evento $s$ noto che si avveri l'evento $B$:
$$P(s|B)=\begin{cases}
\frac{P(s)}{P(B)}\ se\in B \\
0\ se\not\in B
\end{cases}$$
Intuitivamente si restringe lo spazio campione a $B$.

> [!example]- Esempio
> Considerato il lancio di dadi con $S=\{1,2,3,4,5,6\}$ e $B=\{1,2,3\}$  con $P(B)=\frac{1}{2}$ volendo sapere la probabilità che l'esito sia $s=\{2\}$ con $P(s)=\frac{1}{6}$ sapendo che si avveri $B$ sarà: $P(s|B)=\frac{1/6}{1/2}=\frac{1}{3}$
> A questo risultato si arriva anche intuitivamente considerati i casi favorevoli in cui l'esito è $s$ restringendosi ai casi in cui l'esito è in $B$: 
> 
> | 1          | 2     | 3     | 4   | 5   | 6   |     |
> | ---------- | ----- | ----- | --- | --- | --- | --- |
> | **B**  *s* | **B** | **B** |     |     |     |     |
> Attenendosi alla definizione di Laplace la probabilità calcolata come casi favorevoli su casi possibili totali restringendosi ai casi in cui si avvera $B$ è $P(B)=\frac{1}{3}$

#### Generalizzazione ad eventi complessi 
Considerati due eventi non elementari $A$ e $B$ di probabilità non nulla allora la probabilità che avvenga l'evento $A$ noto che avviene B è considerando $A$ come la somma dei suoi eventi elementari:
$$P(A|B)=\sum _{s\in A}P(s|B)$$
Scomponendo questo risultato nella somma di tutti gli eventi di $A$ appartenenti anche a $B$ e quelli che non ricadono in $B$:
$$P(A|B)=\sum_{s\in A\cap \overline{B}}P(s|B)+\sum_{s\in A\cap B}P(s|B)$$
Sapendo dalla definizione di probabilità condizionata che se $s\not\in B$  allora $P(s|B)$ sarà $0$ allora andrà a $0$ tutta la prima sommatoria, rimane dunque:
$$P(A|B)=\sum_{s\in A \cap B}P(s|B)$$
Applicando la definizione di probabilità condizionata dunque:
$$P(A|B)=\sum_{s\in A \cap B} \frac{P(s)}{P(B)}=\frac{P(A \cap B)}{P(B)}$$
**Che da un dunque una generalizzazione della formula della probabilità condizionata per gli eventi complessi come il rapporto tra la probabilità congiunta tra l'evento $A$ e l'evento condizionante e la probabilità dell'evento condizionante.**

> [!example]- Esempio
> Intuitivamente si restringe lo spazio campione a $B$:
> 	*Considerato il lancio di dadi con $S=\{1,2,3,4,5,6\}$ e $B=\{1,2,3\}$  con $P(B)=\frac{1}{2}$ volendo sapere la probabilità che l'esito sia $A=\{1,2\}$ con $P(s)=\frac{2}{6}$ si avrà dunque $P(A\cap B)=P({1,2})=\frac{2}{6}$ sapendo che si avveri $B$ sarà: $P(s|B)=\frac{2/6}{1/2}=\frac{2}{3}$*
> 	
> A questo risultato si arriva anche intuitivamente considerati i casi favorevoli in cui l'esito è $s$ restringendosi ai casi in cui l'esito è in $B$: 
> 
> | 1         | 2         | 3     | 4   | 5   | 6   |
> | --------- | --------- | ----- | --- | --- | --- |
> | **B** *A* | **B** *A* | **B** |     |     |     |
> Attenendosi alla definizione di Laplace la probabilità calcolata come casi favorevoli su casi possibili totali restringendosi ai casi in cui si avvera $B$ è $P(B)=\frac{2}{3}$

#### Eventi indipendenti
Due eventi sono indipendenti quando $P(A|B)=P(A)$
Per cui $B$ non influenza $A$.
Dall'espressione della probabilità condizionata essendo:
$$P(A|B)=\frac{P(A \cap B)}{P(B)}$$
Sarà nel caso di eventi indipendenti essendo $P(A|B)=P(A)$:
$$P(A\cap B)=P(A)P(B)$$
**Per cui la probabilità congiunta di due eventi indipendenti è pari al prodotto delle probabilità dei singoli eventi.** ^i95zzm
### Teorema della probabilità totale

Considerata una partizione dello spazio campione composta da  eventi complessi $B_{1}\cup B_{2}\cup \dots \cup B_{N}=S$ disgiunti per cui $\forall i,k \in N,\ i\neq k\Rightarrow B_{i} \cap B_k=0$ è possibile calcolare la probabilità di un evento $A$ come:
$$P(A)=\sum_{i=1}^NP(A|B_{i})P(B_{i})$$
### Teorema di Bayes

Considerata una partizione dello spazio campione composta da  eventi complessi $B_{1}\cup B_{2}\cup \dots \cup B_{N}=S$ **disgiunti** per cui $\forall i,k \in N,\ i\neq k\Rightarrow B_{i} \cap B_k=0$ si vuole considerando un evento $A$ come  possibile "effetto" dei diversi eventi $B_{k}$  considerata in queste condizioni:

- $P(A|B_{k})$ probabilità di avere $A$ a causa di $B_{k}$.
- $P(B_{k}|A)$ probabilità che la causa di $A$ sia $B_{k}$ la **probabilità a posteriori**

Il teorema di Bayes consente di valutare la probabilità che l'evento $B_{k}$ sia effettivamente la causa di $A$ **(probabilità a posteriori)** nel momento in cui interagiscono più possibili cause attraverso la formula:
$$P(B_{k}|A)=\frac{P(A|B_{k})P(B_{k})}{\sum_{i=1}^nP(A|B_{i})P(B_{i})}$$

> [!example]- Esempio
> *Intuitivamente, considerato un esperimento per il quale esce una pallina colorata da un urna casuale, lo spazio campione sarà:
> $$
> S = \{(B_{1}, R), (B_{1}, B), (B_{2}, R), (B_{2}, B), (B_{3}, R)\}
> $$
> Note le probabilità che la pallina uscita sia uscita da ciascuna come:
> 
> - $B_{1}$: urna con 2 palline rosse e 1 blu con $P(B_{1})=\frac{1}{3}$*
> - $B_{2}$: urna con 1 rossa e 2 blu con $P(B_{2})=\frac{1}{3}$
> - $B_{3}$: urna con 3 rosse con $P(B_{3})=\frac{1}{3}$
> 
> Si estrae una pallina e l'evento osservato è $A=\{\text{rossa}\}$.
> 
> Le probabilità condizionate sono:
> $$
> P(A|B_{1})=\frac{2}{3} \quad
> P(A|B_{2})=\frac{1}{3} \quad
> P(A|B_{3})=1
> $$
> 
> Applicando Bayes, ad esempio per $B_{1}$:
> $$
> P(B_{1}|A) = \frac{P(A|B_{1})\,P(B_{1})}
> {P(A|B_{1})\,P(B_{1}) + P(A|B_{2})\,P(B_{2}) + P(A|B_{3})\,P(B_{3})}
> $$
> E quindi:
> $$
> P(B_{1}|A) = \frac{\frac{2}{3}\cdot\frac{1}{3}}
> {\frac{2}{3}\cdot\frac{1}{3} + \frac{1}{3}\cdot\frac{1}{3} + 1\cdot\frac{1}{3}}
> = \frac{2/9}{2/9 + 1/9 + 3/9}
> = \frac{2/9}{6/9}
> = \frac{1}{3}
> $$
> Quindi, osservando una pallina rossa, le probabilità a posteriori sono $P(B_{1}|A)=\tfrac{1}{3}$, $P(B_{2}|A)=\tfrac{1}{6}$ e $P(B_{3}|A)=\tfrac{1}{2}$*
> 