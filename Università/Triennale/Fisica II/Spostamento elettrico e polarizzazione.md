## Isolante immerso in un campo elettrostatico

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1]]
Considerato un isolante immerso in un campo elettrostatico, le cariche che lo compongono subiranno una deformazione in quanto non essendo disposti a muoversi potranno disporsi solo diversamente nella loro posizione, con le cariche negative attratte in direzione opposta al campo e le cariche positive spinte via

Si crea così nell'atomo un momento di dipolo $\vec{P}=q\vec{d}$

In risposta al campo elettrostatico si producono all'interno del volume $\tau$ di materiale isolante un certo numero di dipoli elementari $\vec{P}_{k}$
## Polarizzazione
Si definisce polarizzazione del mezzo una grandezza espressa come la somma di tutti i dipoli $\vec{P}_{k}$ ed il volume stesso:$$\vec{P_{o}}(x,y,z,\vec{E})=\frac{\sum_{k=1}^n\vec{P}_{k}}{\tau}$$Questa quantità si misura in $\frac{C}{m^2}$, ha la stessa unità di misura della densità superficiale di carica.

Assumendo le ipotesi di omogeneità (per cui le proprietà del materiale sono costanti in qualsiasi suo punto) ed isotropia (per cui la risposta del mezzo non dipende dalla direzione delle sollecitazione) e di bassa intensità del campo elettrico
 
 Per ipotesi di isotropia $\vec{P}_{o}\parallel\vec{E}$ e $\vec{P}_o(\vec{E})$ (non dipende dalla posizione)
È possibile approssimare $\vec{P}_{o}$ ad un legame polinomiale con $\vec{E}$ arrestandosi al primo ordine:
$$\vec{P_{o}}\approx\epsilon_{0}\chi _{e}\vec{E}$$
Con $\chi_{e}$ costante adimensionale suscettibilità elettrica.

La costante di proporzionalità $\epsilon_{0}$ aggiusta dimensionalmente l'espressione in quanto l'unità di misura della polarizzazione è $\frac{C}{m^2}$ e del campo elettrostatico $\frac{V}{m}$

Considerata [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss per l'elettrostatica|seconda equazione dell'elettrostatica in forma differenziale]] per cui $\nabla \vec{E}=\frac{\rho_{sorg}}{\epsilon_{0}}$ , in presenza di fenomeni di polarizzazione si forma una distribuzione di carica tale che l'equazione diventa:
$$\nabla \vec{E}=\frac{\rho_{sorg}+\rho_{pol}}{\epsilon_{0}}$$
Si genera dunque una distribuzione di carica di polarizzazione che insieme alla sorgente modifica il campo elettrostatico per sovrapposizione degli effetti.

Si dimostra inoltre che:$$\nabla \vec{P}_{o}=-\rho_{pol}$$Per cui:$$\nabla \vec{E}\epsilon_{0}=\rho_{sorg}-\nabla \vec{P}_{o}=\nabla \vec{E}\epsilon_{0}+\nabla \vec{P}_{o}=\rho_{sorg}$$Dalla quale:
$$\nabla(\epsilon_{0}\vec{E}+\vec{P}_{o})=\rho_{sorg}=\nabla[\epsilon_{0}\vec{E}(1+\chi_{e})]$$
Per cui definendo $1+\chi_{e}=\epsilon_r$ costante dielettrica relativa si ottiene: 
$$\nabla(\epsilon_{0}\epsilon_{r}\vec{E})=\rho_{sorg}$$
E con $\epsilon_{0}\epsilon_{r}=\epsilon$ si generalizza:
$$\nabla \vec{E}=\frac{\rho_{sorg}}{\epsilon}$$
**Per cui tutte le relazioni valide nel vuoto o nell'aria si correggono  nota la costante dielettrica relativa.**

Si definisce spostamento elettrico la grandezza:
$$\vec{D}=\epsilon_{0}E(1+\chi_{e})=\epsilon_{0}\epsilon _{r}\vec{E}=\epsilon \vec{E}$$
Da cui: 
$$\nabla \vec{D}=\rho_{sorg}$$