## Definizione campo elettrostatico coulombiano
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
Considerato di fissare nell'origine di una terna cartesiana una carica puntiforme $Q$ e posizionare in un punto $P$ una carica di prova puntiforme $q_{0}>0$ si definisce campo elettrostatico la funzione vettoriale della posizione:
$$\vec{E}_{Q}(P)=\lim_{ q_{0} \to 0}\frac{\vec{F}_{Q,q_{0}}}{q_{0}}$$
	*Nota: il passaggio a limite ha lo scopo di far sì che la carica di prova non alteri la distribuzione di carica sorgente*
	*L'unità di misura del campo elettrostatico è $\frac{N}{C}$ o $\frac{V}{m}$* 

Nel caso in cui la forza $\vec{F}_{Q,q}$ fosse la [[Forza Elettrostatica Coulombiana|forza elettrostatica coulombiana]] allora $\vec{E}_{Q}$ rappresenta il  campo elettrostatico coulombiano.
$$\vec{E}_{c}(P)=\lim_{ q_{0} \to 0}\frac{\vec{F}_{Q,q_{0}}}{q_{0}}=\frac{1}{4\pi\epsilon_{0}} \frac{Q}{r^2}\vec{u}_r$$

**Per cui la presenza di una carica fissa in un riferimento inerziale altera le proprietà dello spazio essendo sorgente di un campo elettrostatico. L'entità di quest'alterazione è percepibile attraverso il posizionamento di una carica di prova.**

Noto l'andamento del campo in un determinato punto è possibile risalire alla forza che la carica $q$ posta nel punto $P$ per effetto della carica $Q$ sorgente del campo come:
$$\vec{F}_{Q,q}(P)=q\vec{E}_{Q}(P)$$
La forza elettrostatica ha modulo costante in tutte le superfici sferiche concentriche centrate nella carica $Q$ 

**Le [[Campi scalari e vettoriali#Definizione di campo vettoriale|linee di campo]] saranno le linee radiali uscenti dall'origine nel quale è posizionata la sorgente del campo:**
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1|200]]
	*Nota: le linee sono più fitte nei pressi dell'origine.
	Con Q negativa le linee sono radiali entranti*
## Integrale di linea del campo elettrostatico 

Esprimendo il [[Lavoro ed energia cinetica|lavoro]] della [[Forza Elettrostatica Coulombiana|forza elettrostatica coulombiana]] e dividendo tutto per $q$ si osserva:
$$\frac{L_{AB}}{q}=\frac{\int_{A}^Bq\vec{E}_{q}\cdot d\vec{l}}{q}=\frac{U(A)}{q}-\frac{U(B)}{q}$$
Da cui:
$$\int_{A}^B\vec{E}\cdot d\vec{l}=V(A)-V(B)$$
**Per cui l'integrale di linea del campo elettrostatico  è pari alla variazione del potenziale elettrostatico lungo un percorso presa con il segno meno** 
Per cui:
$$\oint \vec{E}\cdot d\vec{l}=0$$

Le [[Campi scalari e vettoriali#Definizione di campo scalare|superfici di livello]] del potenziale elettrostatico sono rappresentate da superfici sferiche concentriche centrate nella posizione in cui è presente la carica  $Q$ e si infittiscono all'avvicinarsi verso l'origine:

Essendo che $\int_{A}^B\vec{E}\cdot d\vec{l}=V(A)-V(B)$per il [[Teorema di Torricelli]] sarà:
$$-\vec{E}\cdot d\vec{l}=dV=V(x+dx,y+dy,z+dz)-V(x,y,z)=\frac{\partial V}{\partial x}dx+\frac{\partial V}{\partial y}dy+\frac{\partial V}{\partial z}dz$$
Per cui:
$$dV=-[E_{x}(x,y,z)\vec{i}+E_{y}(x,y,z)\vec{j}+E_{z}(x,y,z)\vec{k}]\cdot[\vec{i}dx+\vec{j}dy+\vec{k}dz]=-[E_xdx+E_{y}dy+E_{z}dz]$$
Dunque:
$$\begin{array}
EE_{x}(x,y,z)=-\frac{\partial V}{\partial x} \\
E_{y}(x,y,z)=-\frac{\partial V}{\partial y} \\
E_{z}(x,y,z)=-\frac{\partial V}{\partial z}
\end{array}$$
 Da cui si osserva che il campo punta sempre nel verso in cui il potenziale decresce.

**Essendo $\vec{E}(P)\cdot d\vec{l}=0$ camminando lungo percorsi in cui resta costante il potenziale elettrostatico, si osserva che il campo è perpendicolare alle superfici di livello e che questo è più intenso nei luoghi in cui più rapidamente varia il potenziale elettrostatico**

Per cui il campo elettrostatico e' il [[Operatori differenziali#Gradiente di un campo scalare|gradiente]] preso col segno meno del potenziale elettrostatico:
$$-\nabla V=\vec{E}=-\frac{\partial V}{\partial x}\vec{i}-\frac{\partial V}{\partial y}\vec{j}-\frac{\partial V}{\partial z}\vec{k}$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1|300]]

Il potenziale elettrostatico è costante in tutte le superfici sferiche concentriche centrate nella carica sorgente, per cui il fatto che il campo sia a queste ortogonali torna.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2|300]]
## Campo generato da una distribuzione di carica
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2]]

Considerata una carica $Q > 0$  non puntiforme ricordando che **per il campo elettrostatico vale il principio di sovrapposizione degli effetti** per cui l'effetto della presenza di più sorgenti è la somma degli effetti che si avrebbero facendo agire ciascuna sorgente separatamente, è possibile scomporre la distribuzione di carica $Q$ in cariche infinitesime $dq$ sorgenti di campi infinitesimi $d\vec{E}$:
$$d\vec{E}=\frac{1}{4\pi\epsilon_{0}} \frac{dq}{|\vec{r}-\vec{R}|^2}\cdot\vec{u}_{\vec{r}-\vec{R}}$$
Per cui il campo complessivo:
$$\vec{E}_{Q}(\vec{r})=\int_{CARICHE}d\vec{E}(\vec{r})=\frac{1}{4\pi\epsilon_{0}}\int \frac{dq}{|\vec{r}-\vec{R}|^2}\cdot\vec{u}_{\vec{r}-\vec{R}}$$
Lo stesso varrà per il [[Forza Elettrostatica Coulombiana#Potenziale elettrostatico|potenziale elettrostatico]]:
$$V(P)=\int \frac{dq}{4\pi\epsilon_{0}|\vec{r}-\vec{R}|}$$
**Per cui dato il campo elettrostatico coulombiano e' possibile sintetizzare tutti gli altri campi.**

## Legame tra potenziale elettrostatico e campo elettrostatico unidimensionale

Considerato un [[Campo elettrostatico coulombiano]] unidimensionale : $\vec{E}(x)=\vec{i}E_{x}=\vec{i}\frac{dV}{dx}$ con andamento:
$$E_x(x) = \begin{cases}
0 & \text{se } x < 0 \\[8pt]
\cos t & \text{se } 0 \leq x \leq d \\[8pt]
0 & \text{se } x > d
\end{cases}$$
Il potenziale sarà costante negli intervalli in cui sarà nullo il campo e decrescerà linearmente negli intervalli in cui il campo è  costante.

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1]]