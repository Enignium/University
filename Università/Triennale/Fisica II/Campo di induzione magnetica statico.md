## Forza di Lorentz

Considerata una carica $q$ che si muove a velocità $\vec{v}$, se nella regione di spazio in cui si muove è presente un campo di induzione magnetica $\vec{B}(\vec{r})$ allora la carica sperimenta una forza perpendicolare alla velocità: 
$$\vec{F}_{L}=q\vec{v}\times \vec{B}$$
L'unità di misura di $\vec{B}$ è il tesla $T$ con $1T=\frac{1Ns}{Cm}$
Calcolando il lavoro di questa forza:
$$\delta L=\vec{F}_{l}\cdot d\vec{r}=\vec{F}_{l}\cdot \vec{v}dt=0$$

**Essendo la forza sempre perpendicolare alla velocità questa non compierà lavoro.** 
**Essendo nullo il lavoro sarà nulla la variazione di energia cinetica** 

Non variando il modulo della velocità dunque per effetto della forza ma essendo presente un accelerazione, seguirà che la carica dovrà muoversi di moto  circolare uniforme.

Per cui considerando una carica su cui è esercitata solo la forza di Lorentz:
$$\vec{R}=\vec{F}_{L}=m\vec{a}$$
Da cui ne seguirà che il modulo di $\vec{F}_{L}$ dovrà essere:
$$F_{L}=qvB=m \frac{v^2}{R}$$
Essendo l'accelerazione nel moto circolare solo centripeta e pari a $a=\frac{v^2}{R}$


## Prima legge di Laplace

Considerata una spira conduttiva attraverso la quale scorre una corrente $i$ , il tratto infinitesimo del percorso della corrente $d\vec{l}$ è sorgente di un campo di induzione magnetica statico infinitesimo otteniamo così la prima legge di Laplace che considera la corrente in forma attiva:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
$$d\vec{B}(P)=\frac{\mu_{0}}{4\pi} i \frac{d\vec{l}\times\vec{u_{r}}}{r^2}$$
Con $\mu_{0}=4\pi 10^{-7} \frac{H}{m}$ permeabilità magnetica nel vuoto 

Il campo di induzione magnetica generato dal tutto il percorso chiuso della corrente sarà uguale a:
$$\vec{B}(P)=\oint_{l}\frac{\mu_{0}}{4\pi} i \frac{d\vec{l}\times\vec{u_{r}}}{r^2}$$
### Legge di Bjort-Savart
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
Considerato il caso in cui la corrente si muove lungo il percorso che va da $x_{min}$ a $x_{max}$ 
sapendo che essendo $\alpha+\phi=\pi$ allora essendo supplementari sarà $sen\phi=sen\alpha$ ed essendo $\alpha+\theta=\frac{\pi}{2}$ allora essendo complementari $sen\alpha=\cos \theta$ da cui $sen\phi=sen\alpha=\cos \theta$,  e che $d\vec{l}=\vec{i}dx$ sarà possibile esprimere:
$$d\vec{B}(P)=\frac{\mu_{0}}{4\pi} i \frac{d\vec{l}\times\vec{u_{r}}}{r^2}=\frac{\mu_{0}}{4\pi} i \frac{dlsen\phi}{r^2}\vec{k}=\frac{\mu_{0}}{4\pi} i \frac{dx\cos \theta}{r^2}\vec{k}$$
Sapendo che $\frac{x}{d}=tg\theta=\frac{sen\theta}{\cos \theta}$ sarà $x=\frac{sen\theta}{\cos \theta}d$ da cui $dx=d\frac{d\theta}{\cos^2\theta}$, si potrà quindi esprimere:
$$d\vec{B}=\frac{\mu_{0}}{4\pi} id \frac{d\theta\cos \theta}{r^2\cos^2 \theta}\vec{k}$$
Notando che $r\cos \theta =d$ sarà:
$$d\vec{B}=\frac{\mu_{0}i}{4\pi d} {d\theta\cos \theta}\vec{k}$$
Per sapere l'intensità del campo complessivo generato da tutto il percorso allora si nota che nel percorso si varierà tra un $\theta_{min}$ ed un $\theta_{max}$ per cui:$$B(P)=\int_{\theta_{min}}^{\theta_{max}}\frac{\mu_{0}i}{4\pi d} {d\theta\cos \theta}=\frac{\mu_{0}i}{4\pi d}[sen\theta_{max}-sen\theta_{min}]$$
Per cui l'espressione del campo sarà:$$\vec{B}(P)=\frac{\mu_{0}i}{4\pi d}[sen\theta_{max}-sen\theta_{min}]\vec{k}$$
Facendo tendere $x_{min} \to-\infty$ e $x_{max} \to +\infty$ si ottiene un filo infinito percorso dalla corrente $i$ e si nota che $\theta_{min} \to -\frac{\pi}{2}$ e $\theta_{max} \to \frac{\pi}{2}$ per cui in queste condizioni sarà essendo $\left[ sen \frac{\pi}{2}-sen -\frac{\pi}{2}\right]=2$:
$$\vec{B}(P)=\frac{\mu_{0}i}{2\pi d}\vec{k}$$
**Che ci da modulo direzione e verso di un campo di induzione magnetica generato da un filo rettilineo di dimensione illimitata percorso da corrente notando che in tutti punti a distanza d costante dal filo il campo è di intensità costante**
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2]]
**Per cui il campo sarà tangenziale punto per punto alle circonferenze che poggiano sul piano perpendicolare alla filo e costante su tutte le circonferenze concentriche con il filo, queste circonferenze rappresentano le linee di campo che sono linee di campo chiuse.**


## Seconda legge di Laplace

Considerato un conduttore di sezione costante attraverso il quale scorre una corrente continua $i=\frac{dq}{dt}=\frac{\Delta q}{\Delta t}=cost$ con cariche che si muovono ad una velocità di deriva costante$\vec{v}=\vec{i} \frac{dx}{dt}=\vec{i}\frac{\Delta x}{\Delta t}=cost$, immaginando che nella regione in cui si trova il conduttore sia presente un campo di induzione magnetica statico uniforme $\vec{B}(\vec{r})$.

Considerando la forza di Lorentz sperimentata dalla carica $\Delta q$ che attraversa la sezione del conduttore nel tempo $\Delta t$ sarà:
$$\Delta \vec{F}_{l}=\Delta q\vec{i}\frac{\Delta x}{\Delta t}\times \vec{B}$$
Che si potrà esprimere, considerando $\Delta\vec{l}=\vec{i}\Delta x$ come:
$$\Delta \vec{F}_{l}=\frac{\Delta q}{\Delta t} \vec{i} \Delta x\times \vec{B}=i\Delta\vec{l}\times \vec{B}$$
Passando al limite per $\Delta \to 0$ otteniamo la seconda legge di Laplace che considera la corrente in forma passiva:
$$d\vec{F}_{l}=id\vec{l}\times \vec{B}$$


P**er cui considerato un circuito chiuso in cui circola corrente continua immerso in un campo di induzione magnetica statico uniforme ciascuna carica mobile risente di una forza pari al prodotto vettoriale tra lo spostamento infinitesimo $d\vec{l}$ ed il vettore $\vec{B}$.**

Per conoscere la forza percepita da tutto il circuito considerata l'ipotesi di B costante:
$$\vec{F}_{l}=\oint_{l} id\vec{l}\times \vec{B}=i\left[\oint_{l}d\vec{l}\right] \times \vec{B}$$
## Legame tra campo di induzione magnetica statico e campo elettrostatico 

Per la prima legge di laplace considerato un percorso attraversato da corrente il campo di induzione magnetica statico generato dall corrente nel suo percorso sarà:
$$d\vec{B}(P)=\frac{\mu_{0}}{4\pi} i \frac{d\vec{l}\times\vec{u_{r}}}{r^2}$$
In regime di corrente continua $i=\frac{dq}{dt}=\frac{\Delta q}{\Delta t}$ ed in un conduttore omnico la velocità delle cariche è costante per cui$\vec{v_{d}}=\frac{d\vec{l}}{dt}=\frac{\Delta \vec{l}}{\Delta t}$, per cui la relazione della prima legge di laplace la posso considerare in termini finiti come:
$$\Delta\vec{B}(P)=\frac{\mu_{0}}{4\pi} \frac{\Delta q}{\Delta t} \frac{\Delta\vec{l}\times\vec{u_{r}}}{r^2}$$
Essendo queste non più derivate è possibile esprimendo $\vec{v_{d}}=\frac{\Delta \vec{l}}{\Delta t}$, moltiplicando e dividendo per $\epsilon_{0}$ riarrangiare i termini come:
$$\Delta\vec{B}(P)={\mu_{0}}\epsilon_{0} \vec{v_{d}} \times\frac{\Delta q}{{4\pi}r^2\epsilon_{0}}\vec{u_{r}}$$
Facendo di nuovo tendere $t  \to 0$ sarà:
$$d\vec{B}(P)={\mu_{0}}\epsilon_{0} \vec{v_{d}} \times\frac{d q}{{4\pi}r^2\epsilon_{0}}\vec{u_{r}}=\mu_{0}\epsilon_{0}\vec{v}_{d}\times d\vec{E}(P)$$
Da qui il legame tra campo di induzione magnetica statico e [[Campo elettrostatico coulombiano]] 