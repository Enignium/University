Consideriamo una massa che soggetta ad una forza si sposta lungo un percorso *l* 
e consideriamo lo spostamento infinitesimo lungo la traiettoria $\vec{dl}$

![[Drawing 2025-04-02 17.06.42.excalidraw]]

### Lavoro elementare 
Definiamo Lavoro elementare 
$$
	\delta L = \vec{F}*\vec{dl} 
$$
Essendo un prodotto scalare questo sarà uguale a 
$$
F*dl*cos\theta = F_xdx + F_ydy + F_zdz
$$
E potrà essere :
- > 0  , dunque  $\theta$  < $\frac{\pi}{2}$ Lavoro Motore
- - < 0  , dunque  $\theta$  > $\frac{\pi}{2}$ Lavoro Resistente
- - = 0  , dunque  $\theta$  = $\frac{\pi}{2}$ Lavoro Nullo

Unità di misura: J (joule) 
$1 J = 1N * 1m$

Questa sarà una quantità scalare e sarà relativa all'elemento infinitesimo di percorso $\vec{dl}$ 
### Definizione di lavoro

Per ottenere il lavoro che la forza compie sulla massa m lungo il percorso *L* bisogna ripetere l'operazione del calcolo del lavoro elementare su tutto il percorso e sommarne il risultati, dunque posso ottenere il lavoro complessivo come: 
$$\int_{a}^{b} \vec{F}*\vec{dl}$$La forza agisce sulla massa cambiando lo stato energetico di questa. Il lavoro è un processo attraverso il quale viene scambiata l'energia, **il lavoro è dunque una forma di energia in transito.**
L'energia è una quantità che si conserva ma può cambiare forma.
### Teorema delle forze vive
Consideriamo di calcolare il lavoro che la risultante delle forze applicate compie su una massa:
$$
\sum_{i=0}^n \vec{F}_n = \vec{R}
$$
$$ L_{AB} = \int_{a}^{b} \vec{R}*\vec{dl} $$
Ricordando che essendo $\vec{dl}$ un differenziale questo sarà uguale a 
$$
\vec{dl} = \frac{\vec{dl}}{dt} *dt
$$
dove essendo $\frac{\vec{dl}}{dt}$ la derivata temporale dello spostamento sarà uguale a $\vec{v}$  dunque:
$$ L_{AB} =  \int_{a}^{b} \vec{R}*\vec{dl} = m \int_{a}^{b}\frac{\vec{dv}}{dt} *\vec{v} * dt = m \int_{a}^{b}\vec{v} * \vec{dv}$$

$\vec{v}(t)$ sarà parallelo a $\vec{dv}$ dunque $\vec{v} * \vec{dv} = v(t)dv$ perciò 
$$
L_{AB} = m\int_{a}^{b}v * dv = m*\frac{v^2}{2}\Big|_a^b = \frac{1}{2}mV_b^2 -\frac{1}{2}mV_a^2 = \Delta K$$
Questo appena enunciato è detto **Teorema delle forze vive**
Definendo la quantità $K = \frac{1}{2}mV_b^2$  energia cinetica , una quantità sempre maggiore di 0.
