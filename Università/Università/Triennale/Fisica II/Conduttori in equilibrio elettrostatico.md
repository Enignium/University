
Considerato un conduttore questo è in equilibrio elettrostatico se presa una qualsiasi superficie al suo interno il flusso del campo elettrostatico è nullo

## Carica di un conduttore in equilibrio elettrostatico

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1]]
Conferita una carica $q$ al conduttore con l'ipotesi che il conduttore resti in equilibrio elettrostatico dovrà essere vero che:

- La carica si distribuisca sulla superficie del conduttore
- La superficie del conduttore sia equipotenziale
- Il campo generato da $q$ sia $\frac{\sigma}{\epsilon_{0}}$ 

Se la carica non fosse distribuita sulla superficie del conduttore le cariche libere all'interno del conduttore interagirebbero con il campo generato dalla carica $q$ in modo tale dal far sì che presa una superficie $S$ interna al conduttore:
$$\phi_{S}(\vec{E})\neq 0$$
**E si violerebbe l'ipotesi di equilibrio elettrostatico in quanto ci sarebbe un campo elettrostatico interno al conduttore e le cariche mobili fluirebbero**

Se la superficie del conduttore non fosse equipotenziale le cariche sulla superficie fluirebbero in quanto sulla superficie si avrebbe:
$$\nabla V\neq 0=-\vec{E}$$
Sarebbe presente un campo elettrostatico superficiale che porterebbe a far fluire le cariche.
**Per cui il gradiente deve essere perpendicolare alla superficie del conduttore in quanto spostandosi lungo la superficie dovrà essere:**
$$\nabla V\cdot d\vec{l}=dV=0$$

### Campo elettrostatico generato da un conduttore in equilibrio elettrostatico 
Per trovare quanto vale il modulo del campo scegliamo una superficie cilindrica orientata verso l'esterno e valutiamo il flusso:
$$\phi_{S}(\vec{E})=\oint \vec{E}\cdot \vec{n}ds=\cancel\phi_{B_{1}}+\phi_{B_{2}}+\cancel\phi_{lat}=ES=\frac{Q_{int}}{\epsilon_{0}}=\frac{\sigma S}{\epsilon_{0}}$$
Per cui:
$$\vec{E}=\frac{\sigma}{\epsilon_{0}}\vec{n}$$
### Distribuzione di carica superficiale in conduttori in equilibrio elettrostatico 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1|225]]
Considerati due conduttori sferici di raggi $R_{a}$ ed $R_{b}$ con $R_{a}\gg R_{b}$  che per condizione di equilibrio elettrostatico si caricano superficialmente con densità superficiale di carica $\sigma_{a}$ e $\sigma_b$. Essendo distribuzioni di [[Campi generati da distribuzioni di cariche simmetriche#Campo elettrostatico generato da una distribuzione di carica uniforme sulla superficie della sfera|cariche sferiche superficiali]] il potenziale sarà 
$$\begin{array}
VV_{a}=\frac{q_a}{4\pi \epsilon_{0}R_{A}} \\
V_{b}=\frac{q_{b}}{4\pi \epsilon_{0}R_{B}}
\end{array}$$

Cortocircuitando i due conduttori le cariche si riarrangiano per mantenere la condizione di equilibrio elettrostatico portando $V_{a}=V_{b}$ per cui esprimendo le cariche come $\sigma S=\sigma_4\pi r^2$:
$$\frac{\sigma_{a}4\pi R^2_{a}}{4\pi\epsilon_{0}R_{a}}=\frac{\sigma_{b}4\pi R^2_{b}}{4\pi\epsilon_{0}R_{b}}$$

Per cui:
$$\frac{\sigma_{a}}{\sigma_{b}}=\frac{R_{a}}{R_{b}}$$
Si nota che con $R_{b} \ll R_{a}$ $\sigma_{b}\ll \sigma_a$
**La distribuzione di carica superficiale $\sigma$ è uniforme solo se il conduttore è sferico, in generale maggiore è la regione di curvatura del conduttore maggiore sarà la distribuzione di carica in quella regione.**

Per cui il campo è più intenso nei pressi delle punte.
## Capacità

Si definisce capacità di un conduttore in equilibrio elettrostatico il rapporto tra la carica conferita ed il potenziale al quale si porta la superficie:
$$C=\frac{q}{V}$$
L'unità di misura della capacità è il Farad:$$1F=\frac{1C}{1V}$$
## Problema generale dell'elettrostatica
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1]]
Considerati $n$ conduttori immersi in un mezzo.
Ciascun conduttore avrà una sua superficie S, carica, densità superficiale e sarà sorgente di un campo.

Il problema consiste nel determinare il potenziale elettrostatico di tutti i punti nello spazio esterno ai conduttori

Per il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss per l'elettrostatica|teorema di gauss per l'elettrostatica]]  e ricordando che $\vec{E}=-\nabla V$:
$$\nabla \cdot \vec{E}=\frac{\rho}{\epsilon_{0}}=-\nabla^2V$$
Limitandosi ai punti esterni alle regioni dei conduttori la densità di carica $\rho$ è uguale a $0$ per cui risolvendola per 
$$-\nabla ^2V=0$$È possibile ottenere il potenziale desiderato.

### Legame tra potenziale superficiale e carica del conduttore
Per ciascun conduttore $k$ se $P\in S_{k}$ allora $V(P)=V_{k}$ 
Allora costruendo k funzioni tali che:
$$f_k = \begin{cases}
0 & \text{se } P\in S_{j}\text{ con } j\neq k \\
1 & \text{se } P\in S_{k}
\end{cases}$$
Costruendo il potenziale come:
$$V(P)=f_1(P)V_{1}+f_{2}(P)V_{2}+\dots+f_{n}(P)V_{n}$$
Il gradiente di questo potenziale col segno darà il campo:
$$\vec{E}=-\nabla V=-[V_{1}\nabla f_{1}+V_{2}\nabla_{2}+\dots V_{n}\nabla f_{n}]$$
Per il teorema di gauss $\frac{q_{k}}{\epsilon_{0}}=\int_{S_{k}}\vec{E}\cdot \vec{n}_{k}dS_{k}$ per cui sostituendo per ciascun conduttore sarà:
$$q_{k}=-\epsilon_{0}\left[V_{1}\oint_{Sk}\nabla f_{1}\cdot \vec{n}_{k}dS_{k}+V_{2}\oint_{Sk}\nabla f_{2}\cdot \vec{n}_{k}dS_{k}+\dots+V_{n}\oint_{Sk}\nabla f_{n}\cdot \vec{n}_{k}dS_{k}\right]$$Definendo una famiglia di coefficienti del tipo:
$$C_{ki}=-\epsilon_{0}\int_{S_{k}}\nabla f_{i}\cdot n_{k}dS_{k}$$
Questi si misurano in Farad $\frac{C}{V}$ e dipendono dalla geometria dei conduttori e dal mezzo nei quali sono immersi.

È dunque possibile esprimere $q_{k}$ come:
$$q_{k}=V_{1}C_{k,1}+V_{2}C_{k,2}+\dots+V_{n}C_{k,n}$$
**La carica su ciascun conduttore è combinazione lineare delle cariche su tutti i  conduttori per cui tra i potenziali superficiali e le cariche su ciascun conduttore esiste un legame matriciale.**
$$
\begin{bmatrix}
q_1 \\
q_2 \\
\vdots \\
q_n
\end{bmatrix}
=
\begin{bmatrix}
C_{1,1} & C_{1,2} & \cdots & C_{1,n} \\
C_{2,1} & C_{2,2} & \cdots & C_{2,n} \\
\vdots & \vdots & \ddots & \vdots \\
C_{n,1} & C_{n,2} & \cdots & C_{n,n}
\end{bmatrix}
\begin{bmatrix}
V_1 \\
V_2 \\
\vdots \\
V_n
\end{bmatrix}
$$


## Induzione
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1|150]]
In conduttore metallico immerso in un campo elettrostatico le cariche negative essendo in grado di muoversi risentono dell'azione attrattiva del campo andando a disporsi superficialmente in una regione del conduttore, le cariche negative faranno lo stesso in un altra generando così un campo interno al conduttore tale che all'interno del conduttore:
$$\vec{E}_{int}+\vec{E}=0$$
Per cui applicando questo principio immaginando ciò che avviene nella regione interna di un conduttore metallico cavo si osserva che in questa regione non si risente l'azione del campo elettrico esterno 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1|150]]