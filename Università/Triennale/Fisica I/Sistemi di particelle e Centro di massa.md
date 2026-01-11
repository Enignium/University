
Consideriamo $k$ masse $m_n$ e consideriamo il sistema composto dall'insieme di queste masse
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1]]
Considerando applicate alla massa $m_{n}$ forze interne le forze di interazione tra le masse del sistema e forze esterne  tutte le altre,  per ogni massa $m_{n}$ e ricordando che date le due generiche masse $i,j$ le forze interne con $i\neq j$:
$$\vec{F}_{i,j}+\vec{F}_{j,i}=0$$
Ogni particella avrà:
- Il suo vettore velocità $\vec{v_{n}}$
- Il suo vettore accelerazione $\vec{a_{n}}$
- Il suo vettore quantità di moto $\vec{P_{n}}(t) = m_{n}v_{n}(t)$
- Il suo vettore $\vec{R_{f_{n}}} =\sum_{i=1}^{k-1}\vec{F}_{Int_{i}} +\sum_{j=1}^l\vec{F}_{Ext_{j}}$

Per cui il moto di una singola particella sarà condizionato sia dalle forze interne che dalle forze esterne.

Si può calcolare la quantità di moto dell'intero sistema come:
$$\vec{P}_{sistema}(t)=\sum_{i=0}^k\vec{P}_{i}$$
## Definizione di centro di massa e leggi del centro di massa

Si definisce centro di massa un punto associato ad un sistema di masse individuato come la media pesata delle posizioni istantanee di tutte le masse con coefficienti di peso  il rapporto tra la singola massa e la massa totale del sistema.

Scegliendo un sistema di assi cartesiani allora:
*$$\vec{r}_{cm}=\sum_{i={0}}^k\vec{r}_{k}(t) \frac{m_{k}}{M} $$
	Si nota che nell'individuare questo punto pesano maggiormente le masse più grandi.* 

- Se la distribuzione di masse ha un asse di simmetria allora il centro di massa apparterrà a quest'asse.
- Se esistono più assi di simmetria, il centro di massa coinciderà con il centro di simmetria
- Se posso scomporre una distribuzione di masse in due sottosistemi allora il centro di massa del sistema complessivo sarà $\vec{r}_{cm}=\frac{\vec{r}_{cm_{1}}M_{1}+\vec{r}_{cm_{2}}M_{2}}{M_{1}+M_{2}}$
### Prima legge del centro di massa

Definendo $\frac{d\vec{r}_{cm}(t)}{dt}=\vec{v}_{cm}$ , moltiplicando per la massa complessiva $M$ il centro di massa e derivando rispetto al tempo si osserva:
$$M \vec{v}_{cm}(t)=\sum_{i={0}}^k\vec{v}_{i}(t)m_{i}=\vec{P}_{sistema}(t)$$

**Il centro di massa ha la proprietà di muoversi come se tutta la massa del sistema fosse concentrata in se ed acquisisce una quantità di moto che coincide con quella dell'intero sistema** 
### Seconda legge del centro di massa

Derivando rispetto al tempo $M\vec{v}_{cm}(t)$ si ottiene:
$$\frac{d\vec{P}_{sistema}}{dt}=M\vec{a}_{cm}=\sum_{i=0}^km_{i}\vec{a}_{i}(t)=\sum_{i=0}^kR_{f_{i}}$$
Ma ricordando che $\vec{R_{f_{i}}}=\sum_{i=1}^{k-1}\vec{F}_{Int_{i}} +\sum_{j=1}^l\vec{F}_{Ext_{j}}$ e che $\vec{F}_{i,j}+\vec{F}_{j,i}=0$ i contributi delle forze interne si annulleranno a vicenda, per cui:
$$M\vec{a}_{cm}=\sum_{i=0}^kR_{Ext_{i}}$$
**Il centro di massa si muove come se ad esso fosse applicato il risultante delle sole forze esterne applicate al sistema**
## Centro di massa ed energia cinetica 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1]]

Considerati due sistemi di riferimento $S$ ed $S'$ con il sistema $S'$ con l'origine posizionata nel centro di massa di un sistema di masse a questo solidale ed in moto traslazione rispetto ad $S$.
Per il [[Moto relativo ai sistemi di riferimento|moto relativo ai sistemi di riferimento]] e non essendo in rotazione $S'$:

$$\begin{align*}
\vec{r}_m &= \vec{r}_m' + \vec{r}_{cm} \\
\vec{v}_m &= \vec{v}_m' + \vec{v}_{cm}
\end{align*}$$
Inoltre dal punto di vista $S'$:
$$\begin{align*}
\vec{r}_{cm}' &= 0 = \sum_{k=1}^n \frac{m_k \vec{r}'_k}{M} &&\Rightarrow &&\sum_{k=1}^n m_k \vec{r}'_k = 0 \\
\vec{v}_{cm}' &= \sum_{k=1}^n \frac{m_k \vec{v}_k'}{M} = 0 &&\Rightarrow &&\sum_{k=1}^n m_k \vec{v}_k' = 0 \\

\end{align*}$$
Calcolando [[Lavoro ed energia cinetica#Teorema delle forze vive|l'energia cinetica]] del sistema:

$$K=\sum_{m=1}^n \frac{1}{2} m_m v_m^2=\sum_{m=1}^n \frac{1}{2} m_m (v'_{m}+v_{cm})^2=\sum_{m=1}^n \frac{1}{2}m_{m}v_{m}'^2+\sum_{m=1}^n \frac{1}{2}m_{m}v_{cm}^2+\frac{1}{2}*2\sum_{m=1}^nm_{m}\vec{v}'_{m}\vec{v}_{cm}\\
$$
Ma:
- $\sum_{m=1}^n \frac{1}{2}m_{m}v_{m}'^2$ = $K'$ 
- $v_{cm}$ è una costante quindi  $\sum_{m=1}^n \frac{1}{2}m_{m}v_{cm}^2$=$\frac{1}{2}Mv_{cm}^2$ 
-  $\sum_{m=1}^nm_{m}\vec{v}'_{m}\vec{v}_{cm}$ sapendo che $\sum_{k=1}^n m_k \vec{v}_k' = 0$ fa $0$ 
Quindi:
$$K=K'+\frac{1}{2}Mv_{cm}^2$$
**L'energia cinetica vista da un sistema di riferimento inerziale $S$ è la somma dell'energia cinetica vista dal riferimento centrato e solidale con il centro di massa più l'energia cinetica del centro di massa**

Nel sistema di riferimento $S'$ in cui vedo il centro di massa fermo questa quantità si riduce a solo $K'$ ed è minima rispetto tutti gli altri sistemi di riferimento.
## Centro di massa e momento angolare
Il [[Momento di un vettore#Definizione di momento angolare|momento angolare]] di un sistema di masse posto un polo nell'origine di una terna di assi cartesiani si calcola come:
$$\vec{L}_{O}=\sum_{k=1}^n\vec{r}_{k}\times m_k\vec{v}_{k}$$

Considerando un altro sistema di riferimento $S'$ che trasla rispetto al primo e solidale con un sistema di masse di cui il centro di massa coincide con l'origine,  cambiando il polo dall'origine del primo sistema di riferimento all'origine del secondo, che coincide con il centro di massa, ricordando la relazione di [[Momento di un vettore#Cambio del polo|cambio del polo]] con $\vec{r}_{cm}$ vettore che congiunge il polo $O$ al polo $Cm$ :
$$\vec{L}_{o}=\sum_{k=1}^n\vec{r}_{cm}\times m_{k}\vec{v}_{k}+\sum_{k=1}^n\vec{r}_{k}'\times m_{k}\vec{v}_{k}=\sum_{k=1}^n\vec{r}_{cm}\times m_{k}\vec{v}_{k} + \vec{L}_{Cm}$$
Ma sapendo che $\vec{r}_{cm}$ è costante e che $\sum_{k={1}}^nm_{k}\vec{v}_{k}=M\vec{v}_{cm}$
$$\vec{L}_O= \vec{L}_{Cm}+\vec{r}_{cm}\times M\vec{v}_{cm}$$
Dal punto di $S'$ ricordando che:
$$\begin{align*}
\vec{r}_k &= \vec{r}_k' + \vec{r}_{cm} \\
\vec{v}_k &= \vec{v}_k' + \vec{v}_{cm}
\end{align*}$$
$$L_{Cm}'=\sum_{k=1}^nr'_{k}\times m_{k}\vec{v}'_{k}=\sum_{k=1}^n (\vec{r}_{k}-\vec{r}_{cm})\times m_{k}v_{k}'=\sum_{k=1}^n\vec{r}_{k}\times m_{k}\vec{v}_{k}'-\sum_{k=1}^n\vec{r}_{cm}\times m_{k}v_{k}'$$
Ma essendo :
- $\sum_{k=1}^n m_k \vec{v}'_k = 0$ il termine $-\sum_{k=1}^n\vec{r}_{cm}\times m_{k}\vec{v}_{k}'$ fa $0$
- Il termine $\sum_{k=1}^n\vec{r}_{k}\times m_{k}\vec{v}_{k}'$ diventa $\sum_{k=1}^n\vec{r}_{k}\times m_{k}(\vec{v}_{k}-\vec{v}_{cm})$  che si scompone in $\sum_{k=1}^n\vec{r}_{k}\times m_{k}\vec{v}_{k}-\sum_{k=1}^n\vec{r}_{k}\times m_{k}\vec{v}_{cm}$ che è uguale a $\vec{L}_O-M\vec{r}_{cm}\times \vec{v}_{cm}$

Per cui:
$$\begin{align*}
\vec{L}'_{cm} &= \vec{L}_{O} - M \vec{r}_{cm} \times \vec{v}_{cm} \\
\vec{L}_{cm}  &= \vec{L}_{O} - \vec{r}_{cm} \times M \vec{v}_{cm} \\
\vec{L}_{cm}  &= \vec{L}'_{cm}
\end{align*}$$
**Per cui** **il momento angolare rispetto al centro di massa è invariante per traslazioni del sistema di riferimento, purché il nuovo sistema si muova solidalmente con il centro di massa**
## Lavoro sui sistemi 
Considerato che le masse componenti un sistema individuate dal vettore $\vec{r}_{k}$ si spostino per effetto delle forze che agiscono sul sistema di una quantità infinitesima $d\vec{r}_{k}$ il lavoro infinitesimo di queste forze sarà:
$$\delta L=\delta L_{intcons}+\delta L_{intnoncons}+\delta L_{extcons}+\delta L_{extnoncons}=dK$$
I lavori delle forze conservative saranno uguali a $-dU_{int}$ e $-dU_{ext}$ per cui:
$$\delta L_{noncons}=d(k+U_{int}+U_{ext})=dE_{m}$$

**Per cui il lavoro delle forze non conservative interne ed esterne al sistema sarà uguale alla variazione di energia meccanica del sistema.**

## Teorema degli assi paralleli
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1]]
Dato un corpo rigido messo in rotazione su un asse $Z$ passante per il centro di massa il [[Momento di un vettore#Momento di inerzia|momento di inerzia]] complessivo del sistema ottenuto come  somma dei singoli momenti di inerzia delle masse del corpo rispetto all'asse di rotazione fatto passare per il centro di massa sarà $I_{cm}$, per qualsiasi altro asse il momento di inerzia complessivo del sistema sarà:
$$I=I_{cm}+d^2M$$ **Con $M$ massa totale del sistema e $d$ distanza tra l'asse passante per il centro di massa ed il nuovo asse di rotazione, per cui il momento d'inerzia è minimo per assi di rotazione passanti per il centro di massa**


