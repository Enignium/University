## Prima equazione cardinale della dinamica 
Come dimostrato in [[Sistemi di particelle e Centro di massa#Seconda legge del centro di massa|seconda legge del centro di massa]] :
$$M\vec{a}_{cm}=\sum_{i=0}^kR_{Ext_{i}}$$
**Il centro di massa si muove come un punto materiale con massa pari alla massa totale del sistema e soggetto a una forza uguale alla risultante delle forze esterne agenti.**
## Seconda equazione cardinale della dinamica 
Considerato un sistema di masse ciascuna avente il suo vettore quantità di moto $P_{n}(t)$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1]]
Facendo coincidere il polo $O$ con l'origine di una terna di assi cartesiani sarà possibile calcolare il [[Momento di un vettore#Definizione di momento angolare|momento angolare]] dell'intero sistema come somma dei momenti angolari delle singole masse:
$$\vec{L}_{O}=\sum _{k=1}^n\vec{r}_{k}(t)\times m_{k} \vec{v}_{k}(t)$$
Derivando rispetto al tempo:$$\frac{d\vec{L}_{O}}{dt}=\sum_{k=1}^n \frac{d\vec{r}_{k}(t)}{dt}\times m_{k}\vec{v}_{k}(t) + \sum _{k=1}^n\vec{r}_{k}(t)\times m_{k}\vec{a}_{k}(t)$$
Essendo $\frac{d\vec{r}_{k}(t)}{dt}=\vec{v}_{k}(t)$ parallelo a $m_{k}\vec{v}_{k}(t)$ la prima sommatoria si annulla e ricordando la [[Leggi della dinamica|seconda legge della dinamica]] per cui $m_{k}\vec{a}_{k}=\vec{R}_{k}$, rimane quindi:
$$\frac{d\vec{L}_{O}}{dt}=\sum _{k=1}^n\vec{r}_{k}(t)\times m_{k}\vec{a}_{k}(t) = \sum _{k=1}^n\vec{r}_{k}(t)\times \vec{R}_{k}$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1]]

Considerato un sistema composto da due masse  $\sum _{k=1}^n\vec{r}_{k}(t)\times \vec{R}_{k}$ sarà uguale a :
$$\begin{array}a\vec{r}_{1}(t)\times(\sum_{i=1}^{k-1}\vec{F}_{Int_{1}} +\sum_{j=1}^l\vec{F}_{Ext_{1}})\\+\\\vec{r}_{2}(t)\times(\sum_{i=1}^{k-1}\vec{F}_{Int_{2}} +\sum_{j=1}^l\vec{F}_{Ext_{2}})

\end{array}$$
Se considero i contributi di questa sommatoria relativi alle forze interne sapendo che $\vec{F}_{2,1}=-\vec{F}_{1,2}$:
$$\vec{r}_{1}\times\vec{F}_{21}+\vec{r}_{2}\times{\vec{F}_{12}}=\vec{r}_{1}\times(-\vec{F}_{12})+\vec{r}_{2}\times{\vec{F}_{12}}=(\vec{r}_{2}-\vec{r_{1}})\times \vec{F}_{1,2}$$
Ma $\vec{r}_{2}-\vec{r}_{1}=\Delta \vec{r}$ che è parallelo alle forze di interazione che sono sempre dirette lungo la congiungente tra le due masse, dunque il prodotto vettoriale farà $0$ ed i contributi relativi alle forze interne si annullano a coppie per cui:
$$\frac{d\vec{L}_{O}}{dt}= \sum _{k=1}^n\vec{r}_{k}(t)\times \vec{R}_{ext_{k}}=\sum_{k=1}^n\vec{T}_{O_{ext_{k}}}$$
**La derivata del momento angolare complessivo del sistema fatta rispetto al tempo coincide con la somma dei [[Momento di un vettore#Definizione di momento torcente|momenti]] fatti rispetto al polo dei risultanti delle forze esterne applicati alle singole masse**

Il momento angolare di un corpo rigido che ruota attorno ad un asse di rotazione passando per il [[Sistemi di particelle e Centro di massa#Definizione di centro di massa e leggi del centro di massa|centro di massa]] ha un unica componente parallela all'asse di rotazione per cui:
$$\vec{L}_{O}=I\vec{w}$$
Allora:
$$\frac{dL_O}{dt}=I \frac{d^2\theta}{dt^2}=\sum_{k=1}^n\vec{T}_{O_{ext_{k}}}$$
**Il momento angolare totale di un sistema si conserva se la somma dei momenti delle forze esterne è nulla**.