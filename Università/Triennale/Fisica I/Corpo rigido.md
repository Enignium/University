## Definizione di corpo rigido
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1|200]]
**Considerato un sistema di masse vale il vincolo di corpo rigido se le distanze tra le masse del sistema sono costanti.**
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1]]
Con questo vincolo se un corpo rigido trasla rispetto ad un sistema di riferimento inerziale $S$ basta conoscere la velocità con cui il sistema $S'$ trasla rispetto ad S in quanto nota la posizione dell'origine $\Omega$ per il vincolo di corpo rigido la distanza tra tutti i punti dovrà sempre essere la stessa.

Se oltre a traslare il corpo rigido ruotasse per ottenere la posizione istantanea degli altri punti oltre a conoscere la posizione dell'origine $\Omega$ serve conoscere l'inclinazione degli assi, per ciascun versore del sistema di riferimento $S'$ dovranno essere notte le proiezioni sugli assi di  $S$. Per cui:
$$\begin{array}
ii'=\cos \alpha_{i} \vec{i}+\cos \beta_{}\vec{j}+\cos \gamma_{i} \vec{k}\\j'=\cos \alpha_{j} \vec{i}+\cos \beta_{j}\vec{j}+\cos \gamma_j\vec{k}\\k'=\cos \alpha_{k} \vec{i}+\cos \beta_{j}\vec{j}+\cos \gamma_k\vec{k}
\end{array}$$
## Rototraslazione di un corpo rigido
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 1]]
Considerato il sistema $S'$ che ruota lungo un asse fisso e trasla rispetto al sistema di riferimento $S$, dal punto di vista del sistema di riferimento $S$ un punto generico $A$ del corpo rigido solidale con il sistema di riferimento $S'$ è individuabile come: $$\vec{r}_{A}=\vec{r}_{A}'+\vec{O\Omega}$$E ricordando che dal punto di vista di $S'$ la velocità con cui ciascun punto del corpo rigido è nulla, dal punto di vista di $S$:
$$\vec{v}_{A}=\vec{v}'_{A}+\vec{w}\times \vec{r}'+\vec{v}_{\Omega}=\vec{w}\times \vec{r_{A}}'+\vec{v}_{\Omega}$$
**Se si fa coincidere il centro di massa con l'origine del sistema di riferimento $S'$ l'espressione della dinamica rototraslazionale di un corpo rigido si riduce a:**$$\vec{v_{A}}=\vec{v}_{cm}+\vec{w}\times\vec{r}_{A}'$$
**Per cui nota la velocità del centro di massa e la velocità angolare con la quale il corpo rigido ruota attorno ad un asse ho informazioni relative alla velocità di ciascuna massa.**
## Traslazione di un corpo rigido
Nel caso in cui il corpo rigido solidale con il sistema di riferimento $S'$ si muova traslando rispetto ad $S$ e non ruotando l'espressione della dinamica traslazionale del corpo rigido si riduce a:
$$\vec{v_{A}}=\vec{v}_{cm}$$
## Rotazione di un corpo rigido
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2]]
Nel caso in cui il corpo rigido solidale con il sistema di riferimento $S'$ si muova ruotando rispetto ad $S$ e non traslando l'espressione della dinamica traslazionale del corpo rigido si riduce a:
$$\vec{v_{A}}=\vec{w}\times \vec{r}_{A}'$$
Dal punto di vista del sistema di riferimento $S$ il momento angolare di una massa che compone il sistema rispetto all'origine del sistema di riferimento , considerando il sistema discreto sarà:
$$\vec{L}=\sum_{k=1}^n\vec{r}_{k}\times m_{k}\vec{v}_{k}=\sum_{k=1}^n\vec{r}_{k}\times m_{k}(\vec{w}\times \vec{r}_{k}')$$
Scomponendo il vettore posizione in una componente parallela all'asse di rotazione ed una ortogonale $r'_{k}=z'_{k}\vec{k}+\vec{\rho}_{k}$ dal punto di vista di $S$ ciascuna massa che compone il sistema si muoverà di moto circolare uniforme con velocità tangenziale $v_{tk}=\rho_{k}w$ 

Nel calcolo del momento angolare allora $\vec{w}\times \vec{r}'_{k}=\vec{w}\times \vec{\rho}_{k}$ per cui:
$$\vec{L}=\sum_{k=1}^n\vec{r}_{k}\times m_{k}(\vec{w}\times \rho_{k})$$
Per l'identità per cui $\vec{a}\times(\vec{b}\times \vec{c})=\vec{b}(\vec{a}\vec{c})-\vec{c}(\vec{a}b)$ sarà:
$$\vec{L}=\sum_{k=1}^n\vec{w}(\vec{r}_{k}\vec{\rho}_{k}m_{k})-\sum_{k=1}^n \vec{\rho}_{k}(\vec{r}_{k}\vec{w}m_{k})=\vec{L}_{\parallel}+\vec{L}_{\perp}$$
Osservando che: 
$$\begin{array}{l}
\vec{r}_{k}\vec{p}_{k}=\rho_{k}^2 \\
\vec{r}_{k}\vec{w}=wz_{k}
\end{array}$$
Sarà:
$$\begin{array}{l}
\vec{L}_{\parallel}=\sum_{k=1}^nm_{k}\rho_{k^2}w\vec{k}=Iw\vec{k}\\
\vec{L}_{\perp}=\sum_{k=1}^nz_{k}m_{k}w\vec{\rho}_{k}
\end{array}$$
**Se l'asse di rotazione $Z$ è un asse di simmetria per ciascuna coppia di masse simmetriche ci sarà un vettore $\vec{\rho}$ opposto per cui il termine $\vec{L}_{\perp}$ sarà nullo. In questo caso:**
$$\vec{L}=\vec{L}_{\parallel}=I\vec{w}$$
## Energia cinetica di un corpo rigido

Considerato un corpo rigido che si muove di moto rototraslazionale solidale con il sistema di riferimento centrato nel centro di massa, dal punto di vista del sistema di riferimento fisso $S$:
$$\vec{v}_{k}=\vec{v}_{cm}+\vec{w}\times \vec{r}_{k}'$$
Per cui calcolando [[Lavoro ed energia cinetica#Teorema delle forze vive|l'energia cinetica]] del sistema come somma dell'energia cinetica delle singole masse che lo compongono:
$$K=\sum_{k=1}^n \frac{1}{2}m_{k}(\vec{v}_{cm}+\vec{w}\times \vec{r}'_{k})^2=\sum_{k=1}^n \frac{1}{2}m_{k}\vec{v}_{cm}^2+\sum_{k=1}^n \frac{1}{2}m_{k} (\vec{w}\times \vec{r}'_{k})^2+\sum_{k=1}^n m_{k}\vec{v}_{cm}(\vec{w}\times \vec{r}'_{k})$$
Il terzo attendo si scopone in $\vec{v}_{cm}\vec{w}\times \sum_{k=1}^nm_{k}\vec{r}_{k}'= 0$ quindi si elimina.

Scomponendo il vettore $\vec{r}_{k}'$ in una componente parallela ed una ortogonale all'asse di rotazione:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1|150]]
$$\vec{r}_{k}'=\vec{k}z_{k}+\vec{\rho}_{k}$$
Nel secondo addendo dunque il prodotto vettoriale $\vec{w}\times r'_{k}$ diventa $\vec{w}\times(\vec{k}z_{k}+\vec{\rho}_{k})$ che si riduce a $\vec{w}\times \vec{\rho}_{k}$ che di modulo fa $w\rho_{k}$ essendo i due vettori perpendicolari.

Per cui ricordando che il momento di inerzia del sistema è la somma dei momenti di inerzia delle singole masse $I=\sum_{k=1}^nm_{k}\rho^2_{k}$:  l'energia cinetica sarà:

$$K=\frac{1}{2}Mv_{cm}^2+\sum_{k=1}^n \frac{1}{2} m_{k}\rho_{k}^2w^2=\frac{1}{2}Mv_{cm}^2+ \frac{1}{2} Iw^2$$

Con il primo tempo che tiene conto dell'energia cinetica traslazionale ed il secondo traslazionale [[Derivata di un versore]] 