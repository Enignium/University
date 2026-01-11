## Leggi di trasformazione velocità ed accelerazione 

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 1 1|800]]

Considerato un sistema di riferimento $S$ ed un sistema di riferimento $S'$  che trasla rigidamente rispetto ad $S$ con velocità ed accelerazione uguale per tutti i suoi punti coincidenti quindi con quella dell'origine $\Omega$ e ruota attorno al suo asse con velocità angolare $\omega$ e accelerazione angolare $\alpha$ .

Gli osservatori solidali con $S$ ed $S'$ valutano il moto dello stesso punto attraverso i vettori posizione $r(t)$ e $\vec{r}'(t)$ legati dalla relazione:
$$\vec{r}(t)=\vec{r}'+\vec{O\Omega}$$
I vettori posizione di ciascun sistema di riferimento  avranno proiezioni:
$$\begin{array} \\
\vec{r}(t)=\vec{i}x(t)+\vec{j}y(t)+\vec{k}z(t) \\
r'(t)=\vec{i}'x'(t)+\vec{j}'y'(t)+\vec{k}'z'(t)
\end{array}$$
### Trasformazione della velocità 
Derivando rispetto al tempo si ottiene il legame tra le velocità relative a ciascun sistema di riferimento:
$$\vec{v}(t)=\vec{\frac{dr}{dt}}=\frac{\vec{dr'}}{dt}+\frac{\vec{dO\Omega}}{dt}$$
Con $\frac{\vec{dO\Omega}}{dt}=\vec{v_{\Omega}}$ velocità con la quale $S'$ trasla rispetto alla terna fissa 
Per quanto riguarda $\frac{d\vec{r'}}{dt}$ questo varia sia perché cambiano le componenti cartesiane che perché ruotano i versori degli assi. Per cui:
$$\begin{array}
a\frac{\vec{dr'}}{dt}=\frac{d\vec{i}'x'(t)}{dt}+\frac{d\vec{j}'y'(t)}{dt}+\frac{d\vec{k}'z'(t)}{dt}= \\
\vec{w}\times \vec{i}'x'(t)+\vec{i}'\frac{dx'(t)}{dt}+\vec{w}\times \vec{j}'y'(t)+\vec{j}'\frac{dy'(t)}{dt}+\vec{w}\times \vec{k}'z'(t)+\vec{k}'\frac{dz'(t)}{dt}= \\
\vec{w}\times[\vec{i}'x'(t)+\vec{j}'y'(t)+\vec{k}'z'(t)]+\vec{i}'\frac{dx'(t)}{dt}
\vec{j}'\frac{dy'(t)}{dt}
\vec{k}'\frac{dz'(t)}{dt}= \\
\vec{w}\times r'(t)+\vec{v}'(t)
\end{array}$$
Tenuto conto di ciò si ottiene la legge di trasformazione delle velocità al variare del sistema di riferimento:
$$\vec{v}(t)=\vec{v}'(t)+\vec{v}_{t}(t)$$
Con $v_{t}=w\times r'(t)+\vec{v}_{\Omega}$ velocità di trascinamento.
### Trasformazione dell'accelerazione
Dal punto di vista dell’osservatore solidale con la terna fissa, l’accelerazione è la derivata della velocità $\vec{v}(t)$ rispetto al tempo:
$$\vec{a}(t)=\frac{d\vec{v}}{dt}=\frac{d\vec{v}'}{dt}+\frac{d\vec{v}_{\Omega}}{dt}+\frac{d\vec{w}\times \vec{r}'(t)}{dt}$$
Con $\frac{d\vec{v}_{\Omega}}{dt}=a_{\Omega}$ accelerazione traslazionale con la quale $S'$ accelera nel suo moto traslazionale  rispetto ad $S'$.
Per quanto riguarda $\frac{d\vec{v'}}{dt}$ questo varia sia perché cambiano le componenti cartesiane che perché ruotano i versori degli assi. Per cui:
$$\begin{array}
a\frac{\vec{dv'}}{dt}=\frac{d\vec{i}'v_{x}'(t)}{dt}+\frac{d\vec{j}'v_{y}'(t)}{dt}+\frac{d\vec{k}'v_{z}'(t)}{dt}=\\
\vec{w}\times[\vec{i}'v_{x}'(t)+\vec{j}'v_{y}'(t)+\vec{k}'v_{z}'(t)]+\vec{i}'\frac{dv_{x}'(t)}{dt}
\vec{j}'\frac{dv_{y}'(t)}{dt}
\vec{k}'\frac{dv_{z}'(t)}{dt}= \\
\vec{w}\times v'(t)+\vec{a}'(t)
\end{array}$$
Per quanto riguarda invece la derivata di $\vec{w}\times \vec{r}'(t)$:
$$\begin{array}
a\frac{d}{dt}\vec{w}\times r'(t)=\frac{d\vec{w}}{dt}\times r'(t)+\vec{w}\times \frac{d\vec{r}'}{dt}=\vec{\alpha}\times r'(t)+\vec{w}\times[v'(t)+ \vec{w}\times r'(t)]=\\
\vec{a}\times r'(t)+\vec{w}\times v'(t)+\vec{w}\times[\vec{w}\times r'(t)]
\end{array}
$$
Per cui tenendo conto di tutti i contributi:
$$\vec{a}(t)=2\vec{w}\times v'(t)+\vec{a}'(t)+\vec\alpha \times \vec{r}'(t)+\vec{w}\times[\vec{w}\times \vec{r}'(t)]+\vec{a}_{\Omega}$$
Per cui definendo accelerazione di Coriolis $\vec{a}_{c}=2\vec{w}\times v'(t)$ e accelerazione di trascinamento $\vec{a}_{t}=\vec{a}_{\Omega}+\alpha \times r'(t)+\vec{w}\times[\vec{w}\times \vec{r}'(t)]$
L'espressione dell'accelerazione diventa:
$$\vec{a}(t)=\vec{a}'(t)+\vec{a}_{t}+\vec{a}_{c }$$
