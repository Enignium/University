
## Singolo strato uniforme

Considerata una superficie planare illimitata carica con densità superficiale di carica costante in modo tale che:$$\sigma=\frac{\Delta q}{\Delta S}=\frac{dq}{dS}=cost$$
Considerando una coppia di cariche infinitesime  rispetto ad un asse perpendicolare al piano e valutando su questo il campo in un generico punto P:

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1]]
**Si osserva generalizzando questo comportamento per ciascuna coppia di cariche simmetriche che le linee di campo sono perpendicolari uscenti al singolo strato uniforme**
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1|255]]

Essendo la sorgente illimitata il campo sarà costante per cui
 $$|E(x)|=cost$$
	*Nota: se la densità di carica $\sigma$ è negativa allora le linee saranno perpendicolari entranti*
 Per cui:
 $$\vec{E}=E_{0}\vec{i}$$
  
  Applicando il [[Flusso di un campo vettoriale e teorema di Gauss|teorema di Gauss]] calcolando il flusso attraverso una superficie cilindrica chiusa:
 ![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1|150]]
 Il flusso sarà non nullo solo sulle basi del cilindro per cui il flusso sarà:
 $$\phi_{base_{1}}(\vec{E})+\phi_{base_{2}}(\vec{E})=\int_{base_{1}}\vec{E}\cdot \vec{n_{1}}ds+\int_{base_{2}}\vec{E}\cdot \vec{n_{2}}ds=2ES=\frac{Q}{\epsilon_{0}}$$
 Con $Q=\sigma S$ per cui:
 $$2ES=\frac{\sigma S}{\epsilon_{0}}$$
 Per cui:
 $$E=\frac{\sigma}{2\epsilon_{0}}$$
 Si osserva che l'intensità del campo è costante.

## Doppio strato uniforme 

Considerati due lamine di estensione illimitate poste parallelamente a distanza $d$ l'una dall'altra, una carica con densità di carica superficiale costate $+\sigma$ e l'altra $-\sigma$.
Il campo prodotto da queste due lamine sarà la sovrapposizione dei campi generati dai singoli strati

Ciascuna delle lamine avrà campo di intensità $E=\frac{\sigma}{2\epsilon_{0}}$
 Per cui nelle regioni in cui i campi avranno versi opposti si compenseranno e si intensificheranno nelle regioni in cui saranno dello stesso verso.

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 2]]
Il campo nella regione tra le due lamine avrà modulo: $$E(x)=\frac{\sigma}{\epsilon_{0}}$$
Nelle altre regioni il campo sarà nullo

In questa regione essendo costante il modulo integrando si risale al valore del potenziale nel punto in cui si trova la prima lamina:$V(0)=\frac{\sigma d}{\epsilon_{0}}$ assumendo che  $V(d)=0$ in quanto:
$$\int_{0}^dE(x)dx=V(0)-\cancel{V(d)}$$

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2]]