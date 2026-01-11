
Si differenziano materiali in base alle loro proprietà conduttive in:
- Isolanti se le cariche al loro interno sono fisse
- Conduttori se le cariche al loro interno sono disponibili a muoversi

## Definizione di corrente

Dato un conduttore di sezione $S$ si definisce corrente $i$ il flusso di cariche che attraversa la sezione in un determinato intervallo di tempo: 
$$i=\frac{\Delta Q}{\Delta t}$$
Si misura in Ampere:$$1A=\frac{1C}{1S}$$ Se quantità di carica che attraversa la sezione del conduttore è costante nel tempo allora:
$$i=\frac{\Delta Q}{\Delta t}=\frac{dq}{dt}=cost$$
Questo è regime di corrente continua.
**La carica dunque si muove in una direzione privilegiata e ciò è possibile solo sollecitando il conduttore con un campo elettrostatico, così non fosse le cariche si muoverebbero in modo caotico e tante cariche attraversebbero la sezione in un verso quante lo farebbero nell'altro**

## Densità di corrente elettrica

Definendo la grandezza densità di corrente elettrica come il prodotto tra la densità volumetrica di carica mobile e la velocità con la quale le cariche si muovono  $$\vec{J}(\vec{r},t)=\rho(\vec r,t)\vec{v}(\vec r,t)$$
	*Nota: in corrente continua $\vec{J},\rho,\vec{v}$ dipende solo dalla posizione e non dal tempo*

Misurata in $\frac{A}{m^{2}}$. $\vec{J}$  è parallela o antiparallela a $\vec{v}$ a seconda del segno di $\rho$
È possibile definire la corrente come:
$$i=\phi_{SezConduttore}(\vec{J})$$
## Equazione di continuità
Immaginando di avere una superficie chiusa $S$ orientata attraverso la normale uscente che racchiude un volume $\tau$ con densità di carica mobile $\rho>0$
**Calcolando il flusso: si ottiene l'equazione di continuità in forma integrale**
$$\phi_{S}(\vec{J})=\oint \vec{J}\cdot \vec{n}dS=- \frac{\partial Q_{int}}{\partial t}=-\frac{\partial}{\partial t}\int_{\tau} \rho d\tau$$
Dalla quale applicando il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss in forma generale]]:
$$\phi_{S}(\vec{J})=\int_{\tau}\nabla \vec{J}d\tau=-\frac{\partial}{\partial t}\int_{\tau} \rho d\tau=\int_{\tau}-\frac{\partial\rho}{\partial t}d\tau$$
**Da cui si ottiene l'equazione di continuità in forma differenziale:**
$$\nabla \vec{J}=-\frac{\partial\rho}{\partial\tau}$$
Nello specifico in corrente continua:
$$\begin{array}
	a\nabla \vec{J}=-\frac{\partial\rho}{\partial\tau}=0 \\
- \frac{\partial Q_{int}}{\partial t}=0
\end{array}$$
**Essendo quindi $\phi_{S}(\vec{J})=0$ in corrente continua si avrà qualsiasi sia il volume del conduttore tanta carica che esce quanta ne entra, tutte le linee di flusso in uscita saranno bilanciate da linee di flusso in entrata, le linee di campo saranno chiuse.*
*![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1|350]]

## Corrente continua

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1]]

Considerato il caso in cui  ci si trova in regime di corrente continua per cui vale:$$i=\frac{\Delta Q}{\Delta t}=\frac{dq}{dt}=cost$$$$\begin{array}
	a\nabla \vec{J}=-\frac{\partial\rho}{\partial\tau}=0 \\
\phi_{S(}(\vec{J})=- \frac{\partial Q_{int}}{\partial t}=0
\end{array}$$
E ipotizzando che la velocità con la quale si muovano le cariche sia costante per cui $\vec{v}=\frac{dx}{dt}\vec{i}=cost$
e sia costante pure $\rho>0$ per cui:
$$\vec{J}=\rho \vec{v}$$
Sarà parallelo a $\vec{v}$ e le linee di campo saranno chiuse.

Prendendo in considerazione un volume $\tau$ interno alla superficie $S$ della sezione del conduttore dentro cui fluiscono le cariche essendo in regime di corrente continua sarà:
$$\phi_{S}(\vec{J})=\phi_{S_1}(\vec{J})+\phi_{S_{2}}(\vec{J})+\cancel\phi_{S_{lat}}(\vec{J})=0$$
Dove si nota che $\phi_{S_{1}}=-\phi_{S_{2}}$
E notando che $\vec{v} \parallel \vec{n}$:
$$\phi_{S_{2}}(\vec{J})=\oint_{S}\vec{J}\cdot \vec{n}dS_{2}=\oint_{s}\rho \frac{\Delta x}{\Delta t}d{S_{2}}=\rho\frac{\Delta x}{\Delta t}S=\frac{\rho}{\Delta t}\Delta\tau=\frac{\Delta Q}{\Delta t}=i$$
**Si nota che $\phi_{S_{2}=}=-i$ a riprova del fatto che le cariche compiono una traiettoria chiusa e qualsiasi volume scelto tante ne entreranno quante ne usciranno.**

Inoltre posso definire cosi l'intensità di corrente continua come il flusso attraverso una sezione del conduttore dell'intensità di corrente

**Noto inoltre che in $\Delta t$ secondi attraverserà la sezione del conduttore tutta la carica che entra in un volume $\Delta \tau=S\Delta x$** 


## Corrente di spostamento

Considerata l'equazione di continuità in forma differenziale $\nabla \vec{J}=-\frac{\partial\rho}{\partial t}$ e la seconda equazione dell'elettrostatica in forma differenziale per cui $\nabla \vec{E}=\frac{\rho}{\epsilon}$, trovando da questa $\rho=\nabla \vec{E}\epsilon$ posso esprimere: 
$$\nabla \vec{J}=-\frac{\partial}{\partial t}\left(\nabla\epsilon \vec{E}\right)$$
Invertendo l'ordine di derivazione e portando tutto al primo membro:
$$\nabla \vec{J}+\nabla\left[\frac{\partial}{\partial}\epsilon\vec{E}\right]=0$$
Mettendo in evidenza $\nabla$:
$$\nabla\left[\vec{J}+\frac{\partial}{\partial t}\epsilon \vec{E}\right]=0$$
**Da cui si evidenzia come in presenza di fenomeni dipendenti dal tempo si aggiunge alla densità di corrente di conduzione omnica un tipo di densità di corrente di spostamento definita come:**
$$\vec{J}_{spostamento}=\epsilon \ \frac{\partial\vec{E}}{\partial t}$$
Calcolandone il flusso si ottiene la'intensità di corrente di spostamento:
$$\phi_{S}(\vec{J}_{spost})=i_{spost}$$

### Principio di Kirchoff al nodo
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1]]

Conseguenza dell'ipotesi $\frac{-\partial Q}{\partial t}=\phi(\vec{J})=0$ è il principio di Kirchof**f per cui la somma algebrica delle correnti entranti e le correnti uscenti da un nodo è $0$** per cui considerato un nodo ed una superficie  sferica orientata  $S$ che racchiude il nodo ed assegnati in modo arbitrario i versi della corrente:

$$\phi_{S}(\vec{J})=0=\oint_{S_{1}}\vec{J}\cdot \vec{n_{1}}ds_{1}+\oint_{S_{2}}\vec{J}\cdot \vec{n_{2}}ds_{2}++\oint_{S_{3}}\vec{J}\cdot \vec{n_{3}}ds_{3}=i_{1}-i_{2}-i_{3}$$

kirchof maglia
