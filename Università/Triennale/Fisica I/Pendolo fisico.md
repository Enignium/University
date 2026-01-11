![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1]]
Considerato un [[Corpo rigido|corpo rigido]] vincolato da un punto $O$ detto perno. Le forze applicate al sistema saranno la forza peso applicata al centro di massa e le reazioni vincolari che il sostegno esercita sul corpo per mantenerlo vincolato all'asse di rotazione. Il [[Sistemi di particelle e Centro di massa#Definizione di centro di massa e leggi del centro di massa|centro di massa]] coinciderà con il [[Sistemi di vettori#Definizione di baricentro|baricentro]].

In condizioni di equilibrio la retta congiungente tra $O$ e $CM$ è verticale. Per far oscillare il pendolo è necessario formare un angolo $\theta$ rispetto alla verticale. Essendo il centro di massa coincidente con il baricentro in questo caso sarà possibile calcolare il momento della forza peso applicata al sistema come:
$$\vec{T_{O}}=\vec{r}_{cm}\times M\vec{g}=-Mgdsen\theta \vec{k}$$

Sapendo che in questo caso vale $\vec{L}_{O}=I\vec{w}$ essendo i $Z_{k}=0$ e applicando la [[Equazioni cardinali della dinamica dei sistemi#Seconda equazione cardinale della dinamica|seconda equazione cardinale della dinamica]]:
$${T}_{O}=\frac{dL_{O}}{dt}=I\frac{d^2\theta}{dt}=-Mgdsen\theta$$
Da cui assumendo $\theta<10$ per cui $sen\theta=\theta$:
$$\frac{d^2\theta}{dt^2}=-\frac{Mgd}{I}\theta$$
Che risolta con il metodo delle funzioni di prova ci da la legge oraria:
$$\theta(t)=\theta_{max}\cos(wt+\phi)$$
con $w=\sqrt{\frac{Mgd}{I}}$
