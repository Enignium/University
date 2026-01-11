## Distribuzione Power Law 

Osservando reti reali si osserva che la loro distribuzione dei gradi non segue quella [[3 Random Network#Distribuzione dei gradi|poissoniana caratterizzante i Random Network]]. 

![[Università/Magistrale/Complex Social Networks/Slides/4.pdf#page=5&rect=27,12,188,192|4, p.5]]

Rappresentando in scala logaritmica la distribuzione si osserva che questa segue un andamento lineare, da cui se ne deriva che la distribuzione dei gradi di reti reali dovrà essere una distribuzione **Power Law** così definita:
$$p_{k}\sim k^{-\gamma}$$
Con $\gamma$ esponente del grado (*degree exponent*).

> [!caution] Osservazione
> Facendo il logaritmo di ambo i membri si ottiene $\log p_{k}\sim-\gamma \log k$.
> Da questo segue che nella rappresentazione in scala logaritmica la distribuzione appare una retta con coefficente angolare $\gamma$.

## La proprietà Scale-Free

**Si definisce uno Scale-Free Network una rete la cui distribuzione dei gradi segue una Power Law.**

![[Università/Magistrale/Complex Social Networks/Slides/4.pdf#page=16&rect=23,72,345,212|4, p.16]]

La distinzione principale tra un [[3 Random Network|Random Network]] ed una rete Scale-Free risiede nella *coda* della distribuzione dei gradi.


> [!caution] Osservazione
> Dal confronto tra le distribuzioni, reso più evidente dalla rappresentazione in scala logaritmica, si osserva che:
> 
> Le reti Scale-Free hanno un numero enorme di nodi con grado molto basso.
> 
> Nelle reti Random c'è un eccesso di nodi con grado uguale alla media.
> 
> Nelle reti Scale-Free la probabilità di trovare nodi con grado altissimo (**Hubs**) è significativa mentre nelle reti Random decade esponenzialmente a zero.

## Relazione tra dimensione della rete e dimensione dell'Hub più grande.

Per descrivere come la dimensione della rete impatta sulla dimensione degli Hub consideriamo il grado massimo $k_{max}$, definito *natural cutoff* per diversi tipi di rete:

- Per quanto riguarda la distribuzione dei gradi $p_{k}$ per reti a distribuzione dei gradi esponenziali il natural cutoff si dimostra essere:
$$k_{max}=k_{min}+\frac{\ln N}{\lambda}$$
- **Per quanto riguarda la distribuzione dei gradi $p_{k}$ per le reti Scale-Free il natural cutoff si dimostra essere:**
$$k_{max}=k_{min}N^{\frac{1}{\gamma-1}}$$
> [!caution] Osservazioe
> Da questa si osserva che più grande è la rete maggiore sarà il grado dell'Hub più grande. 
> 
> La dipendenza polinomiale di $k_{max}$ da $N$  nelle reti Scale-Free implica che ci possono essere differenze di ordini di grandezza differenti tra il grado minimo $k_{min}$ e il grado massimo $k_{max}$.

- Per quanto riguarda una distribuzioni dei gradi poissoniana relativa a Random Network la dipendenza di $k_{max}$ da $N$ è più lenta della dipendenza logaritmica della distribuzione esponenziale.
 
![[Università/Magistrale/Complex Social Networks/Slides/4.pdf#page=23&rect=51,65,327,222|4, p.23]]


> [!caution] Osservazione
**> Si osserva che nelle Reti Scale-Free il grado massimo cresce più rapidamente con l'aumentare delle dimensioni della rete per cui in una rete Random gli hubs non sono presenti così come invece sono presenti nelle reti Scale-Free.**

## Il significato di Scale-Free

Il termine "Scale-Free" deriva dalla fisica statistica (teoria delle transizioni di fase). Per comprendere il significato profondo di questa proprietà nelle reti, è necessario analizzare i **momenti della distribuzione dei gradi**.

L'$n$-esimo momento della distribuzione è definito come:
$$\langle k^{n}\rangle=\sum_{k_{min}}^{\infty}k^{n}p_{k}$$
Dove i momenti inferiori hanno un'interpretazione fisica diretta:
* **Primo momento ($n=1$):** Grado medio $\langle k \rangle$.
* **Secondo momento ($n=2$):** $\langle k^2 \rangle$, fondamentale per calcolare la varianza $\sigma^2 = \langle k^2 \rangle - \langle k \rangle^2$, che misura le fluttuazioni attorno alla media.

Per una rete Scale-Free, calcolando l'$n$-esimo momento nel limite asintotico (dove $k_{max} \to \infty$), si ottiene:
$$\langle k^{n}\rangle \approx C \frac{k_{max}^{n-\gamma+1}}{n-\gamma+1}$$
Il comportamento di questa equazione dipende dalla relazione tra $n$ e $\gamma$:
* Se $n - \gamma + 1 \le 0$: il momento è **finito**.
* Se $n - \gamma + 1 > 0$: il momento **diverge** all'infinito al crescere della rete.

> [!caution] Osservazione
> Poiché molte reti reali (es. Internet, WWW) hanno un esponente $2 < \gamma < 3$ si verifica una situazione critica:
> 
> 1.  Il primo momento $\langle k \rangle$ è finito.
> 2.  **Il secondo momento $\langle k^2 \rangle$ (e quindi la varianza) diverge.**
>
> Questo spiega l'origine del termine **Scale-Free** (privo di scala):
> In una rete Random (distribuzione di Poisson/Normale), le fluttuazioni sono limitate e i nodi hanno gradi vicini alla media $\langle k \rangle$, che funge da "scala" caratteristica del sistema.
> In una rete Scale-Free con $\gamma < 3$, la divergenza della varianza implica che le fluttuazioni possono essere arbitrariamente grandi. Non esiste un "nodo tipico" o una scala interna caratteristica: scegliendo un nodo a caso, questo potrebbe avere un grado minuscolo o essere un Hub gigantesco.


