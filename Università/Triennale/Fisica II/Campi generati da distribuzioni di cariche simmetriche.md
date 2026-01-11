 
Noto che la carica è sorgente del capo dato il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss per l'elettrostatica|teorema di gauss per l'elettrostatica]] distribuzioni di carica simmetrica generano campi simmetrici dato il principio per cui la simmetria degli effetti non può essere inferiore alla simmetria delle cause.

## Campi generati da distribuzioni a simmetria sferica
Considerata una distribuzione di carica sferica di volume $\tau=\frac{4}{3}\pi R^3$ uniforme per cui $$\frac{\Delta Q}{\Delta \tau}=cost=\frac{dq}{dt}=\frac{Q}{\tau}=\rho=\frac{Q}{\frac{4}{3}\pi R^3}$$
Con $Q=\int_{\tau}\rho d\tau=\frac{4}{3}\pi R^3\rho$

Spostandosi su ciascuna superficie sferica di raggio $r<R$ contenuta nel volume centrata nel centro della sfera non si ha la capacità  di distinguere la propria posizione. 
	*Fissato r essendo $\rho$ costante trovo Q costante in tutti i punti della superficie sferica*

Essendo tale la simmetria della distribuzione di carica dovrà essere lo stesso anche per il [[Campo elettrostatico coulombiano|campo elettrostatico]]
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1|250]]

### Campo elettrostatico generato da una distribuzione di carica uniforme nel volume della sfera
Considerata una superficie sferica chiusa di raggio $r < R$ e la distribuzione di carica a densità volumetrica costante $\rho$ applicando il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss per l'elettrostatica|teorema di Gauss per l'elettrostatica]] ricordando che in queste condizioni $\vec{E} \parallel \vec{n}$:
$$\oint_{4\pi r^2}\vec{E}\cdot \vec{n}ds=\oint_{4\pi r^2}Eds=E\oint_{4\pi r^2}ds=E {4}\pi r^2=\frac{Q_{int}}{\epsilon_{0}}$$
Per cui:
$$E {4}\pi r^2=\frac{\frac{4}{3}\pi r^3\rho}{\epsilon_{0}}$$
Da cui:
$$E(r)=\frac{\rho}{3\epsilon_{0}}r$$

Si osserva che il campo cresce linearmente con $r$.
Quando si raggiunge $r>R$ la carica netta però comincia a non crescere più con $r$ per cui:
$$E 4\pi r^2=\frac{\frac{4}{3}\pi R^3\rho}{\epsilon_{0}}$$
Da cui:
$$E(r)=\frac{R^3\rho}{3\epsilon_{0}r^2}$$
Si osserva quindi che il campo decresce proporzionalmente a $\frac{1}{r^2}$ 
	*Sostituendo $Q$ a $\frac{4}{3}\pi R^2\rho$  si nota che si torna all'espressione $E(r)=\frac{Q}{4\pi r^2\epsilon_{0}}$ per cui con $r>R$ il campo è indistinguibile da un campo coulombiano generato da una carica puntiforme*

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1]]
### Campo elettrostatico generato da una distribuzione di carica uniforme sulla superficie della sfera
Considerata una superficie sferica chiusa di raggio $r < R$ e la distribuzione di carica uniforme a densità superficie di carica costante $\sigma$ applicando  il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss per l'elettrostatica|teorema di Gauss per l'elettrostatica]] si osserva che la carica $Q$ interna alla superficie è nulla, dunque sarà nullo pure il campo 

Considerato il caso in cui la superficie sferica di chiusa sia di raggio $r>R$ allora:
$$\oint_{4\pi r^2}\vec{E}\cdot \vec{n}ds=\oint_{4\pi r^2}Eds=E\oint_{4\pi r^2}ds=E {4}\pi r^2=\frac{Q_{int}}{\epsilon_{0}}$$
Con $Q_{int}=\sigma 4\pi R^2$ per cui:
$$E 4\pi r^2=\frac{\sigma_{4}\pi R^2}{\epsilon_{0}}$$
Da cui si nota che il campo è proporzionale a $\frac{1}{r^2}$

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1]]
## Campi generati da distribuzioni a simmetria cilindrica
Considerata una distribuzione di carica cilindrica di altezza $H\gg r$ volume $\tau=\pi R^2H$ uniforme per cui $$\frac{\Delta Q}{\Delta \tau}=cost=\frac{dq}{dt}=\frac{Q}{\tau}=\rho=\frac{Q}{\pi R^2H}$$
Spostandosi su ciascuna superficie laterale di qualsiasi cilindro di raggio $r < R$ contenuto nel volume non si ha la capacità  di distinguere la propria posizione.
	*Fissato r essendo $\rho$ costante trovo Q costante in tutti i punti della superficie cilindrica*

Essendo tale la simmetria della distribuzione di carica dovrà essere lo stesso anche per il [[Campo elettrostatico coulombiano|campo elettrostatico]] 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1]]Applicando il [[Flusso di un campo vettoriale e teorema di Gauss|teorema di gauss]] calcolando il flusso attraverso una superficie cilindrica chiusa di raggio $r<R$c coassiale rispetto alla distribuzione cilindrica di carica e considerando trascurabile il flusso relativo alle basi del cilindro e considerando che il campo in qualunque punto della superficie è parallelo alla normale alla superficie:
$$\phi_{S}(\vec{E})=\oint_{S}\vec{E}\cdot \vec{n}ds=\cancel{\int_{base_{1}}+\int_{base_{2}}+}\int_{2\pi rl}Eds=E 2\pi rl$$
Per cui:
$$E 2\pi rH=\frac{\rho \pi r^2H}{\epsilon_{0}}$$
Da cui si ottiene che$$E(r)=\frac{\rho}{2\epsilon_{0}}r$$
Quindi con $r<R$ il campo è proporzionale a $r$
Considerato il caso in cui $r > R$ invece la carica netta interna alla superficie sarà sempre uguale a $Q=\rho \pi R^2H$ per cui:
$$E 2\pi rH=\frac{\rho \pi R^2H}{\epsilon_{0}}$$
Da cui:
$$E(r)=\frac{\rho R^2}{2r\epsilon_{0}}$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2]]