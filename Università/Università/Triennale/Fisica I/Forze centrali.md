## Definizione di forza centrale
Considerata una massa $m$ nel punto $P(t)$ lungo la sua traiettoria ed un polo $O$:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
Una forza è centrale se per qualsiasi punto della traiettoria della massa sulla quale questa è applicata ha una parte scalare che dipende dalla distanza $r$ fra il polo e la forza ed è sempre diretta lungo la congiungente fra il polo e la massa:
$$\vec{F}_{centrale}=f(r)*\vec{u}_{r}(t)$$
La forza è detta: 
-  Repulsiva se $f(r) > 0$
- Attrattiva se $f(r) < 0$ 
## Momento torcente forza centrale 

Si osserva che il momento di una forza centrale rispetto al suo polo è:
$$\vec{T}_{O}=\vec{OP}(t)\times \vec{F}_{centr} = 0$$
in quanto $\vec{F}_{centr}$ ed il vettore $\vec{OP}(t)$ sono paralleli.

Considerata una massa in cui è applicata solo la una forza centrale, per cui $\vec{R}_{f}=\vec{F}_{centrale}$ e ricordando che il [[Momento di un vettore#Momento torcente risultante forze applicate|momento torcente risultante forze applicate è uguale alla derivata del momento angolare della massa]] :
$$\vec{T}_{O}=\frac{d\vec{L}}{dt}=0$$
Facendo coincidere il polo con l'origine:
$$\vec{L}_{O}=\vec{r}(t)\times m\vec{v}=cost$$ Per cui essendo il prodotto vettoriale costante, il piano sul quale si trovano i due vettori deve essere costante, **dunque il moto che una massa ha per effetto di una forza centrale 
deve essere un moto piano.** 
## Velocità areale forza centrale 
La velocità areale di una massa che si muove solo per effetto di una forza centrale è costante
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
La velocità areale di una massa che si muove lungo una traiettoria ellittica dal punto $P(t)$ al punto $P(t+\Delta t)$ definita $\Delta A$ l'area compresa tra il vettore $r(t)$ ed il vettore $r(t+\Delta t)$ è la quantità:
$$\overline{V}_{areale}=\frac{\Delta A}{\Delta t} $$

Possiamo approssimare l'area $\Delta A$ come:
$$\Delta A \approx \frac{|{\vec{r}(t)\times \vec{r}(t+\Delta t)}|}{2}$$
Ricordando che:
$$\begin{array}
\vec{r}(t+dt)-\vec{r}(t)=d\vec{r}=\frac{d\vec{r}}{dt}dt =\vec{v}(t)dt\\
\vec{r}(t+dt) = \vec{r}(t) +\vec{v}(t)dt
\end{array}$$
Per cui con un certo grado di approssimazione:
$$\vec{r}(t+\Delta t) \approx \vec{r}(t)+\vec{v}(t)\Delta t$$
Per cui:
$$\Delta A \approx \frac{1}{2}{\Big|{\vec{r}(t)\times[\vec{r}(t) +\vec{v}(t)\Delta t
]}\Big|} = \frac{1}{2}{\Big|{\vec{r} \times \vec{v}(t)\Delta t
}\Big|}$$ E moltiplicando e dividendo per m al secondo membro e dividendo entrambi i membri per $\Delta t$
$$\frac{\Delta A}{\Delta t} \approx = \frac{1}{2}{\Big|\frac{{\vec{r} \times m\vec{v}(t)\Delta t
}}{m\Delta t}\Big|} = \frac{1}{2}*\frac{|\vec{L}_{O}|}m = cost$$

**Quindi una massa che si muove solo per effetto di una forza centrale si muove in modo tale che la velocità del vettore che dal polo individua la posizione istantanea della massa sia costante**
