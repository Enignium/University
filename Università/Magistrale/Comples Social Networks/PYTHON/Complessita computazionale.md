## Notazione theta costo computazionale
> [!PDF|red] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=162&selection=0,18,0,19&color=red|slides1, p.162]]
> > Algorithm Analysis
> 
> La complessita computazionale non si misura in temrini di tmepo ma in termini di numero di operazioni primitive, cosa si intende per operazione primitiva è descritto sotto, inoltre si assume per semplicità che ciascuna di queste operazioni sia uguale in costo

> [!PDF|note] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=163&selection=21,8,21,18&color=note|slides1, p.163]]
> > associated
> 
> Ad esempio si dovesse effettuare una ricerca lineare in un array per individuare un determinato target si dovrebbero effettuare nel caso peggiore (target nell'ultima posizione) n operazioni, nel caso migliore (target in prima posizione) una sola

> [!PDF|red] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=164&selection=4,47,4,58&color=red|slides1, p.164]]
> > growth rate
> 
> Quello che conta è il tasso di crescita della complessità dell'algoritmo, anche un algoritmo di complessità $n^2$ non varia particolarmente rispetto ad uno di complessità $n$ per piccolissimi valori di $n$


> [!PDF|note] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=165&selection=2,0,3,9&color=note|slides1, p.165]]
> > Θ-notation
> 
> Si definisce $\Theta$ la funzione che che data $f(n)$ funzione che definisce la complessità dell'algoritmo se esiste una funzione $g(n)$ tale che vale la disuguaglianza nella slide dopo una certa soglia $n_{0}$,  allora la complessità compuitazionale dell'algoritmo sarà $\Theta(g(n))$

> [!PDF|red] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=166&selection=2,0,3,9&color=red|slides1, p.166]]
> > Θ-notation
> 
> Immaginare esempio con $g(n)=n^2$ e $c_{1}=1$ e $c_{2}=2$, inoltre queste funzioni saranno sempre nel primo quadrante del piano cartesiano perchè dovranno essere input in numero positivi e costi computazionali positivi

> [!PDF|note] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=168&selection=5,27,5,46&color=note|slides1, p.168]]
> >  quadratic function
> 
> Essendo che è rilevante solo il contributo più impattante, in un espressione polinomiale di questo tipo i termini di grado più basso possono essere ignorati perchè insignificanti

La notazione $\Theta$ da un limite alla funzione che indica la complessità computazionale sia superiormente che inferiormente, in quanto il limite inferiore per definizione sarebbe $c_{1}g(n)$, tuttavia si ottiene pure un informazione relativa al caso peggiore che non potrà essere peggiore di  $c_{2}g(n)$
## Notazione O complessità computazionale

> [!PDF|red] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=170&selection=2,0,3,9&color=red|slides1, p.170]]
> > O-notation
> 
> Nei casi in cui non è possibile limitare superiormente ed inferiormente la complessità di un algortimo si utilizzano altre notazioni, un esempio di algoritmo che ricade in questo caso è l'insertion sort che si basa sulla comprazione di elementi, non essendo una comparazione predicibile a priori.
> 
In questi casi per cui sappiamo che il caso migliore è $n$ ed il peggiore è $n^2$ non abbiamo la condizione per cui il limite superiore ed inferiore siano funzioni dello stesso tipo.
Inoltre è più rilevante avere una stima del caso peggiore rispetto al caso migliore, dunque la notazione $\Theta$ diventa ridondante.
La notazione $O$ considerà solo la parte destra della disuguaglianza che definisce la notazione $\Theta$ per cui la funzione di complessità $f(n)$ dovrà non essere più larga di una certa funzione $cg(n)$ dopo una certa soglia $n_{0}$
> 
## Notazione $\Omega$ complessità computazionale

> [!PDF|red] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=173&selection=2,0,3,9&color=red|slides1, p.173]]
> > Ω-notation
> 
> La notazione $\Omega$ fornisce invece un limite inferiore sulla complessità dell'algoritmo, per cui considerà solamente la parte sinistra della disuguaglianza che definisce la notazione $\Theta$ per cui dopo una certa soglia $n_{0}$ sarà $0\leq cg(n)\leq f(n)$

## Esempio 
> [!PDF|red] [[Università/Magistrale/Comples Social Networks/Slides/1.pdf#page=176&selection=2,27,2,28&color=red|slides1, p.176]]
> > An example: prefix averages
> 
> 
```python
def prefix_average(s):
	n = len(s)
	a = [0] * n # produce una lista contenente n zeri
	for j in range(n):
		total = 0
		for i in range(j+1):
			total += s[i]
		a[j] = total / (j+1)
	return a

l = [1,2,3,4,5]
print(prefix_average(l))
```
### Stima complessità computazionale 

- $n = len(s)$ è eseguita in tempo costante

- $a = [0] * n$ viene eseguita in $O(n)$ 

- Il ciclo esterno viene eseguito n volte per cui total = 0 e a[j] = total / (j+1) sono eseguiti n volte ciascuno, per cui il numero di operazioni a loro associate è proporzionale a n per cui sarà $O(n)$

- il ciclo interno viene eseguito  j + 1 volte in funzione del valore del ciclo esterno, per cui in totale sarà eseguito $1+2+3+4+\dots+n=\frac{n(n+1)}{2}$ (serie aritmetica) per cui il contributo sarà $O(n^2)$
