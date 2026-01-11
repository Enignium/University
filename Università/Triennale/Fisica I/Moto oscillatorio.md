## Oscillatore armonico
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1]]

Considerata una massa puntiforme disposta su un vincolo liscio e legata orizzontalmente ad una molla di forza con posizione di equilibrio centrato nell'origine del sistema di riferimento.
In seguito ad una deformazione, come lo spostamento della massa alla posizione $x_{0}$ la molla risponde con una forza $\vec{F}_{k}$ proporzionale alla deformazione:
$$\vec{F}_{el}=-kx \vec{}i$$
In queste condizioni essendo il moto rettilineo la risultante $\vec{R}$ delle forze applicate alla molla sarà:
$$\vec{R}=\vec{F}_{el}=m\vec{a}$$
Da cui è possibile essendo il moto rettilineo ricavare l'equazione differenziale lineare di secondo ordine omogenea a coefficienti costanti  che rappresenta la legge oraria:
$$\frac{d^2x}{dt^2}=-\frac{k}{m}x$$
Note le condizioni iniziali $x_{0}$ e $v_{0}$ attraverso il metodo delle funzioni di prova si ricava la funzione x(t):
$$x(t)=x_{0}\sin(\omega_{0} t+\theta)$$
Una funzione sinusoidale di periodo $T=\frac{2\pi}{\omega}$ e pulsazione $\omega_{0}=\sqrt{\frac{k}{m} }$

**Per cui ci si rende conto che la velocità è massima quando la massa passa per il punto di equilibrio e minima nei punti di inversione del moto $x_{0}$ e $-x_{0}$**
**L'accelerazione sarà massima negli stessi punti**
## Oscillatore smorzato
Considerata una massa puntiforme immersa in un fluido viscoso che reagisce al moto con una forza resistente $\vec{F}_{res}=-bv$  disposta su un vincolo liscio e legata orizzontalmente ad una molla di forza con posizione di equilibrio centrato nell'origine del sistema di riferimento che risponde alle deformazioni con una forza elastica $\vec{F}_{k}$ il risultante delle forze applicate sarà:
$$\vec{R}=-kx \vec{i}-b\vec{v}=m\vec{a}$$
Essendo il moto rettilineo proiettando quest'equazione sull'asse x si ottiene l'equazione differenziale:
$$\frac{d^2x}{dt}=-\frac{b}{m} \frac{dx}{dt}-\frac{k}{m}x$$
**L'equazione ammetta la soluzione banale $x(t)=0$ per cui esisterà sempre un istante $t$ nel quale la massa si fermerà nel punto di equilibrio**

La natura della fase transitoria del moto dipende dal rapporto tra i coefficienti $\frac{b}{m} e \frac{k}{m}$
Utilizzando il metodo delle funzioni di prova la funzione $x(t)$ sarà del tipo:
$$x(t)=Ae^{st}$$
Per cui sostituendo all'equazione differenziale:
$$s^2Ae^{st}+\frac{b}{m}sAe^{st}+\frac{k}{m}Ae^{st} = 0$$
Dividendo tutto per $Ae^{st}$ si ottiene l'equazione caratteristica associata all'equazione differenziale:
$$s^2+\frac{b}{m}s+\frac{k}{m}=0$$
Le radici $s_{1},s_{2}$ saranno uguali a:
$$s_{1},s_{2}=\frac{-\frac{b}{m}\pm \sqrt{\left( \frac{b}{m}\right)^2-4\frac{k}{m}}}{2}=-\frac{b}{2m}\pm \sqrt{\left( \frac{b}{2m} \right)^2-\frac{k}{m} }$$
Con $\Delta={\left( \frac{b}{2m} \right)^2-\frac{k}{m} }$
#### Caso di oscillatore sovrasmorzato
Se il discriminante $\Delta$ è maggiore di $0$ l'oscillatore sarà sovrasmorzato e le due saranno radici reali e distinte saranno del tipo:
$$\begin{array}
 ,s_{1}=-\frac{b}{2m}+\sqrt{\Delta }\\
s_{2}=-\frac{b}{2m}-\sqrt{\Delta }
\end{array}$$

**In questo caso la componente relativa alla forza resistente al moto vincerà sulla forza elastica**
La legge oraria sarà del tipo:
$$x(t)=A_{1}e^{[-\frac{b}{2m}+\sqrt{\Delta}]t}+A_{2}e^{[-\frac{b}{2m}-\sqrt{\Delta}]t}$$
L'andamento sarà la somma di due esponenziali decrescenti:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1]]
#### Caso di oscillatore sottosmorzato
Se il discriminante $\Delta$ è minore di $0$ l'oscillatore sarà sottosmorzato e le due radici saranno complesse e coniugate del tipo:
$$\begin{array}
 ,s_{1}=-\frac{b}{2m}+j\sqrt{\Delta }\\
s_{2}=-\frac{b}{2m}-j\sqrt{\Delta }
\end{array}$$

**In questo caso la componente relativa alla forza elastica al moto vincerà sulla forza resistente al moto**
La legge oraria sarà del tipo:
$$x(t)=A*e^{-\frac{b}{2m}t}\cos[\sqrt{-\Delta }*t+\phi]$$
L'andamento sarà i prodotto tra una sinusoide ed un esponenziale decrescente e sarà:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1]]
#### Smorzamento critico
Se il discriminante $\Delta$ è uguale di $0$  le due radici saranno reali e coincidenti
$$
 s_{1}=s_{2}=-\frac{b}{2m}$$

**In questo caso l'oscillatore raggiungerà l'equilibrio nel tempo più breve possibile**
La legge oraria sarà del tipo:
$$x(t)=A_{1}e^{-\frac{b}{2m}t}+A_{2}e^{-\frac{b}{2m}t}$$
L'andamento sarà:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1]]
## Oscillatore forzato
Considerata una massa puntiforme immersa in un fluido viscoso che reagisce al moto con una forza resistente $\vec{F}_{res}=-bv$  disposta su un vincolo liscio e legata orizzontalmente ad una molla di forza con posizione di equilibrio centrato nell'origine del sistema di riferimento che risponde alle deformazioni con una forza elastica $\vec{F}_{k}$ ed una forza $F=F_{0}\cos(wt)\vec{i}$ applicata alla massa il risultante delle forze applicate sarà:
$$\vec{R}=m\vec{a}=-b\vec{v}-kx \vec{i}+F_{0}\cos(wt)\vec{i}$$
Essendo il moto rettilineo proiettando quest'equazione sull'asse x si ottiene l'equazione differenziale non omogenea:
$$\frac{d^2x}{dt}=-\frac{b}{m} \frac{dx}{dt}-\frac{k}{m}x+\frac{F_{0}}{m}\cos(wt)$$
Questa equazione differenziale lineare non omogenea sarà ottenibile per il principio di sovrapposizione degli effetti come la somma di una soluzione particolare più una soluzione omogenea associata:
$$x(t)=x_{P}(t)+x_{omogass}(t)$$
**Il contributo relativo all'omogenea associata coincide con il caso dell'oscillatore smorzato ed andando a $0$ si tratta di un contributo relativo alla fase transitoria del moto per cui dopo un certo istante $t$ vale $x(t)=x_P(t)$ **

Per quanto riguarda la soluzione particolare essendo il termine noto una funzione sinusoidale a frequenza $\omega$ la soluzione dovrà essere una funzione sinusoidale alla stessa frequenza per cui:
$$x_{P}(t)=A\cos(wt+\phi)$$
 Attraverso il metodo delle funzioni di prova derivando e sostituendo nell'espressione dell'equazione differenziale si trovano i valori di $A$ e $\phi$ e considerando $w_{0}=\sqrt{\frac{k}{m}}$ $$\begin{array}
aA=\frac{\frac{F_{0}}{m}}{\sqrt{ (w_{0}^2-w^2)^2-\left( \frac{b}{m} \right)^2} } \\
\phi=\tan^{-1}(\frac{\frac{b}{m}}{w_{0}^2-w^2})
\end{array}$$
Per cui in presenza di forzante $\vec{F}$ viene sostenuta l'oscillazione con un moto del tipo:
$$x(t)=\frac{\frac{F_{0}}{m}}{\sqrt{ (w_{0}^2-w^2)^2-\left( \frac{b}{m} \right)^2} } *\cos(wt+\tan^{-1}(\frac{\frac{b}{m}}{w_{0}^2-w^2}))$$

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1|300]]

**Con $w$ della forzante uguale ad $w_{0}$ propria della molla l'ampiezza dell'oscillazione tende all'infinito, questo fenomeno prende il nome di risonanza**
## Considerazioni Energetiche
### Caso senza forza resistente al moto
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1]]

 Consideriamo una massa soggetta ad una forza elastica e  facendo riferimento alla [[Lavoro ed energia cinetica#Definizione di lavoro|definizione di lavoro]]  
$$\vec{R} = m\vec{g} + \vec{R}_n + \vec{F_{el}} = \vec{F_{el}} $$
$$\vec{R}=  \vec{F_{el}} = -kx\vec{i}$$
$$\vec{\delta L}= \vec{F_{el}} *\vec{dl} = -kx*dx$$Per cui 
$$L_{ab} = \int_{a}^{b} \vec{F}*\vec{dl}  = \int_{x_a}^{x_b}-kx*dx = -k\frac{x^2}{2}\Big|_{xa}^{xb}= -\frac{1}{2}kx^2_b+\frac{1}{2}kx^2_a$$ 
Da cui vediamo che il risultato dipende solo dal punto iniziale e dal punto finale del percorso, per cui la forza è conservativa e $U(x) = \frac{1}{2}kx^2$ 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1]]
Anche dal grafico di $U(x)$ vedo come la forza punta sempre nella direzione nella quale l'energia potenziale decresce.

Il moto dell'oscillatore armonico oscilla tra $x_0$ e $-x_0$ , la velocità a queste due posizioni è nulla, dunque essendo [[Forze conservative ed energia meccanica|l'Energia Meccanica]] 
$$
E_m(x) = \frac{1}{2}mv_x^2 + \frac{1}{2}kx^2_x 
$$
quando la componente cinetica sarà uguale a 0 troveremo il valore costante dell'energia meccanica, costante in quanto agiscono solo forze conservative:
$$
E_m(x_0) = \frac{1}{2}kx_{0}^2 = cost
$$
### Caso con forza resistente al moto
Considerando di partire con condizioni iniziali:
$$\begin{array} \\
x(0) = x_{0} \\
v_{0} = 0
\end{array}$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1]]
In presenza di $\vec{F_{res}} = -b\vec{v}$  , sapendo che l'[[Forze conservative ed energia meccanica#Energia potenziale|Energia Potenziale]] associata alla $\vec{F_{el}}=-kx$ è $U=\frac{1}{\text{2}}kx^2$ 
Allora sapendo $\vec{v}$ è nulla in $x_{0}$ e sarà nulla anche quando il moto  sarà esaurito e sarà stato raggiunto il punto $x=0$ in condizioni di equilibrio sarà:
$$\begin{array}
EE_{m}(x_{0}) =  U(x_{0})+K(x_{0}) =\frac{1}{2}kx_0^2\\E_{m}(0) =U(0)+K(0) = 0 \\
\Delta E_{m} = -\frac{1}{2}kx^2 = L_{fnoncons_{ab}}
\end{array}$$
