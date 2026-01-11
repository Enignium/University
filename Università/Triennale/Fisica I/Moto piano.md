 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1]]
Dato il vettore posizione $\vec{r}(t)$ che identifica la posizione di una massa lungo la sua traiettoria:
$$\vec{r}(t)=\vec{i}x(t)+\vec{j}y(t)$$
È possibile tracciarne il rapporto incrementale dato un incremento $\Delta t$:
$$\vec{v}_{media}=\frac{\Delta \vec{r}}{\Delta t}=\frac{\vec{r}(t+\Delta t)-\vec{r}(t)}{\Delta t}$$
Facendo tendere $\Delta t \to 0$ il vettore differenza si disporrà tangenzialmente al punto $P(t)$ per cui:
$$\vec{v}(t)=\frac{d\vec{r}}{dt}=\frac{ds}{dt}{\vec{u}_{t}(t)}$$
Inoltre notiamo che:
$$\vec{v}(t)=\frac{d\vec{r}}{dt}=\frac{dr}{dt}*u_{r(t)}+r(t)w\vec{u}_{n}$$
Con $\frac{dr}{dt}$ velocità radiale che indica quanto rapidamente il punto si allontana o si avvicina rispetto all'origine.
Per quanto riguarda l'accelerazione questa sarà:
$$\vec{a}=\frac{d\vec{v}}{dt}=\frac{d^2s}{dt^2}\vec{u}_{t}+\frac{ds}{dt}w\vec{u_{c}}=a_{t}\vec{u}_{t}+a_{c}\vec{u}_{c}$$
**L'accelerazione avrà una componente tangenziale alla traiettoria ed una che punta verso il centro di una circonferenza tangenziale alla traiettoria nel punto, il circolo osculatore.

Il moto nel punto verrà approssimato ad un moto circolare, dunque un moto con velocità radiale nulla **Il legame tra la velocità istantanea scalare ed il raggio del circolo osculatore $\rho$ è :
$$v(t)=\frac{ds}{dt}=w\rho$$Per cui la parte scalare dell'accelerazione centripeta:
$$a_{c}=w^2\rho=\frac{v^2(t)}{\rho}$$