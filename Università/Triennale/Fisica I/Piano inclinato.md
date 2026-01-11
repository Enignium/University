![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1]]

Considerata una massa su un piano di inclinazione $\alpha$ questa sarà soggetta alla forza peso ed alla reazione vincolare normale per cui la risultante delle forze applicate sarà:
$$\vec{R}=m\vec{g}+\vec{R}_{n}$$
Scomponendo quest'equazione vettoriale sugli assi ed applicando la [[Leggi della dinamica#seconda legge della dinamica|seconda legge della dinamica]]:
$$\begin{cases}
ma_{x}=mgsen\theta \\
ma_{y}=mg\cos \theta-mg\cos \theta=0

\end{cases}$$
Si nota che l'accelerazione è costante $a_{x}=g\sin \theta$ per cui il moto è uniformemente accelerato e la legge oraria sarà:
$$x(t)=x_{0}+v_{0}(t)+\frac{1}{2}at^2$$
Nell'ipotesi di voler far salire la massa su per il piano inclinato bisognerà attribuire una velocità iniziale $v_{0}< 0$ partendo dalla posizione iniziale $x_{0}=L$ 

Nel caso in cui fosse presente attrito lungo l'asse $x$ l'accelerazione sarebbe:
$$a_{x}=gsen\theta-\mu _{d}g\cos \theta=g(sen\theta-\mu d\cos \theta)$$
Inclinando man mano il piano facendo aumentare l'angolo theta si trova l'angolo limite $\theta_{l}$ oltre il quale  l'equilibrio si rompe e viene vinto l'attrito dinamico.
In condizioni di equilibrio con $\theta=\theta_{l}$ si ottiene:
$$a_{x}=0=g(sen\theta l-\mu s{\cos \theta l})$$ Per cui è possibile ottenere $\mu s$ come 
$$\mu_{s}=\tan(\theta_{l})$$

### Considerazioni Energetiche
#### Caso senza attrito
Consideriamo il piano inclinato in assenza di attrito ed orientiamo così gli assi:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1]]
$$ 
\vec{R} = m\vec{g} + \vec{R}_n
$$
Essendo la reazione vincolare normale $\vec{R_n}$ perpendicolare alla traiettoria questa non compirà lavoro, e non compirà lavoro nemmeno la proiezione sull'asse y della forza peso $mgcos(\theta)\vec{j}$ , anch'essa perpendicolare. Compierà lavoro resistente solo la componente parallela all'asse x della forza peso $-mgsen(\theta)\vec{i}$  dunque facendo riferimento a [[Lavoro ed energia cinetica#Definizione di lavoro|definizione lavoro]] :  
$$
L_{ab} = -\int_{x_a}^{x_b}mgsen(\theta)dx = -mgsen(\theta)x\Big|_{xa}^{xb} = mgsen(\theta)*x_a -mgsen(\theta) *x_b
$$
Notiamo infatti come 
$$\begin{array}ssen(\theta) * x_a = h_a\\sen(\theta) * x_b = h_b\end{array}$$
$$mgsen(\theta)*x_a -mgsen(\theta) *x_b = mg*h_a - mg*h_b $$
A riprova del fatto che il lavoro compiuto dalla forza peso dipende solo dalla quota iniziale e dalla quota finale.

In quanto agiscono solo forze conservative [[Forze conservative ed energia meccanica#Energia Meccanica|l'Energia Meccanica]] rimarrà costante e sarà uguale a 
$$
	E_m(a)=mgh_a + \frac{1}{2}mv_a^2 = Em(b) = mgh_b + \frac{1}{2}mv_b^2 = cost
$$
#### Caso con attrito
Consideriamo una massa che si muove con una certa velocità lungo un piano inclinato in presenza di attrito dinamico
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1]]
In questo caso essendo la reazione vincolare normale $R_{n}$ pari a $mg\cos \theta$ sarà:
$$F_{ad} = -\mu_{d}*mg\cos \theta*vers(\vec{v})$$
Ed essendo parallela alla traiettoria il lavoro sarà:
$$L_{ab} = \int_{a}^b-\mu_{d}mg\cos \theta*\vec{i} *\vec{dl} = \int_{a}^b-\mu_{d}mg\cos \theta*dx = -\mu_{d}mg\cos \theta*(x_b-x_{a}) = \Delta E_{m}$$
In presenza di forze non conservative $E_{m}$ diminuisce durante il percorso piuttosto che rimanere costante.

