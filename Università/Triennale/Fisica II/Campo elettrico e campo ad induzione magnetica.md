## Sorgenti campo elettrico 

Ogni qual volta in una regione di spazio è presente un campo di induzione magnetica $\vec{B}(\vec{r},t)$ variabile nel tempo, generato da una corrente variabile a sua volta nel tempo $i(t)$ dunque in presenza di densità di corrente $\vec{J}(\vec{r},t)$ a sua volta variabile, la variazione di $\vec{B}$ per la [[Circuto RL#Legge di Faraday-Neumann-Lenz|legge di Faraday-Neumann-Lenz]] genererà nella regione di spazio che rappresenta la linea chiusa con la quale è concatenato il campo $\vec{B}$ un campo elettrico e varrà:$$\frac{\partial\phi(\vec{B})}{\partial t}=-v(t)=\oint_{l}\vec{E}\cdot dl$$
**Si osserva così che a differenza del [[Campo elettrostatico coulombiano|campo elettrostatico]] l'integrale di linea del campo elettrico non è sempre uguale a $0$ per cui non è indipendente dal percorso.**


In alternativa è possibile generare un campo Elettrico avendo nello spazio una densità di carica volumetrica $\rho(t)$ dipendente dal tempo 

Quando si è in presenza di un circuito in cui le correnti dipendono dal tempo per poter applicare i principi di risoluzione dei circuiti è necessario assicurarsi che il circuito sia fisso, indeformabile e schermato da campi di induzione magnetica variabili nel tempo per evitare la generazione forze elettromotrice.

## Sorgenti campo di induzione magnetica 

Può capitare che il campo a induzione magnetica sia generato dalla corrente di spostamento , ovvero dalla derivata temporale del flusso della densità di [[Corrente#Corrente di spostamento|corrente di spostamento]] $J_{spost}=\epsilon\frac{\partial E}{\partial t}$, per cui:
$$\phi(\epsilon\frac{\partial E}{\partial t})$$
## Caso circuito con mobile 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1]]

Considerato un circuito immerso in campo di induzione magnetica statico $\vec{B}(t)$ in cui è possibile spostare un lato del circuito, il flusso del campo $\vec{B}$ varierà per effetto della variazione della superficie essendo con $x$ larghezza e $d$ altezza della superficie del circuito $\phi(\vec{B})=Bxd$ per cui  la variazione del flusso sarà:
$$\frac{\partial \phi(\vec{B})}{\partial t}=B \frac{dx}{dt}d$$ Con $\frac{dx}{dt}=v$ ovvero la velocità scalare con la quale si muove il lato del circuito.
Si dovrà dunque considerare in serie al circuito una FEM $E=Bdv$

## Caso spira chiusa 

Considerata una spira chiusa di un materiale di resistenza $R=\frac{\rho l}{S}$, immaginando che questa spira possa ruotare attorno ad un asse $Z$ con una velocità angolare $w=cost=\frac{d\theta}{dt}=\frac{\Delta \theta}{\Delta t}$ ed immaginando che questa spira sia immersa in un campo di induzione magnetica costante $\vec{B}=B_{0}\vec{k}$

In questa condizione il flusso del campo attraverso la spira sarà $\phi(\vec{B})=SB_{0}$ ma durante la rotazione ruoterà anche la normale, per cui varierà il flusso che in generale sarà $\phi(\vec{B})=SB_{0}\cos \theta$ , ma essendo la rotazione costante sarà $\theta(t)=\cancel{\theta(0)}+wt$ per cui sarà $\phi(\vec{B})=SB_{0}\cos wt$ per cui sarà:
$$FEM=\frac{\partial \phi(\vec{B})}{\partial t}=-SB_{0}wsen(wt)$$