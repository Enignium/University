## Definizione di momento di un vettore
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]Considerato un vettore $\vec{a}$ applicato nel punto $A$ ed un polo scelto arbitrariamente $O$ ed il vettore $\vec{OA}$ il vettore che congiunge il polo al punto d'applicazione di $\vec{a}$ si dice **momento del vettore** $a$ rispetto al polo $O$ :
$$\vec{m}_{O}= \vec{OA}\times \vec{a}$$
Che in modulo sarà uguale a 
$$m_{O}=OA*a*sen(\alpha)$$
Definendo $OA*sen(\alpha)$ **braccio del momento** che descrive la distanza tra la retta di applicazione del vettore $\vec{a}$ ed il polo $O$, **per cui il momento resta invariato spostando il polo lungo la  retta parallela alla retta di applicazione del vettore $\vec{a}$ .**

### Cambio del polo

Se scegliamo un altro polo $\Omega$ sullo stesso piano otterremo un vettore momento angolare di modulo e verso possibilmente diverso, e la relazione tra i due momenti sarà:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
$$\vec{m}_{o}= \vec{m_{\Omega}} + \vec{O\Omega}\times \vec{a}$$In quanto:
$$\begin{array}\vec{m}_{O}= \vec{OA}\times \vec{a}\\\vec{m}_{\Omega}= \vec{\Omega A}\times \vec{a}\\\vec{OA} = \vec{O\Omega} + \Omega A\\\vec{m}_{O} = (\vec{O\Omega} + \Omega A) \times \vec{a} = \vec{O\Omega} \times \vec{a} + \Omega A \times \vec{a} = \vec{m_{\Omega}} + \vec{O\Omega}\times \vec{a}
\end{array}$$
## Definizione di momento torcente 

Calcolando il momento di una forza rispetto ad un polo fatto coincidere con l'origine, ottengo:
$$\vec{r}\times \vec{F} = \vec{T_{O}}$$
Notiamo che essendo un prodotto vettoriale questa grandezza si intensifica allontanando la forza dal polo ed applicandola perpendicolarmente

## Definizione di momento angolare 

Considerata una massa $m$  il momento del suo vettore quantità di moto $\vec{P(t)}=m\vec{v}(t)$ esprimerà la quantità **momento angolare** rispetto al polo $O$  $$\vec{m}_{O}= \vec{OA}\times m\vec{v}(t) = L_{O}$$
Se faccio coincidere il polo con l'origine di un sistema di assi cartesiani il vettore $\vec{OA}$ sarà uguale al vettore posizione $\vec{r}$ per cui 
$$\vec{m}_{O}= \vec{r}\times m\vec{v}(t) = L_{O}$$
### Momento torcente risultante forze applicate
Osserviamo che data una massa $m$ lungo una traiettoria nel punto A sulla quale sono applicate delle forze la cui risultante è $\vec{R}$  :
$$\frac{d\vec{L}_{O}}{dt}=\vec{T_{O}}$$
**Per cui la derivata del momento angolare di una massa è uguale al momento torcente della risultante delle forze applicate** 

Infatti:
$$\frac{d\vec{L_{O}}}{dt} = \frac{d}{dt}(\vec{r} \times \vec{P}) = \frac{d\vec{r}}{dt} \times \vec{P} + \vec{r} \times \frac{d\vec{P}}{dt}$$Poiché $\frac{d\vec{r}}{dt} = \vec{v}$  che sarà parallela a $\vec{P} = m\vec{v}$ dunque  $\frac{d\vec{r}}{dt} \times \vec{P} = 0$ e $\frac{d\vec{P}}{dt} = \vec{R}$ segue che 
$$\frac{d\vec{L}_{O}}{dt}=\vec{r} \times \vec{R}=\vec{T_{O}}$$

## Momento di inerzia 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
Considerando una massa in moto rettilineo non un uniforme, facendo  coincidere il polo con l'asse di rotazione e l'origine il suo momento angolare sarà:
$$\vec{L}_{0}=\vec{r}(t)\times m\vec{v}(t)$$
Notando che i due vettori $\vec{r}(t)$ e $\vec{v}(t)$ sono perpendicolari e ricordando il legame tra velocità scalare e velocità angolare per cui $v(t) =w(t)r$ , i modulo del momento angolare sarà pari a $L_{0}=|r||v||sen(\alpha)|=rmv(t) = mr^2w(t)$ avremo che:
$$\Big|\frac{d\vec{L}_{O}}{dt}\Big|=mr^2\frac{dw}{dt} = I*\alpha= \Big|\vec{r} \times \vec{R}\Big| = \Big|\vec{T_{O}}\Big| $$
Con $\alpha$ accelerazione angolare e definendo $I$ **momento di inerzia** 

Notiamo che essendo nullo il contributo delle forze dirette lungo la congiungente a causa del prodotto vettoriale nel calcolo del momento torcente 
$$|\vec{T_{O}}| = r*R_{Ftangenziali}$$
