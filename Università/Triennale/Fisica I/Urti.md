## Definizione di urto

Consideriamo due masse in moto ciascuna lungo la propria traiettoria distanti tra loro in modo tale da considerare trascurabile la loro forza di interazione reciproca:
![[Università/Triennale/Fisica I/IMG_RESOURCES/Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1]]
La [[Impulso e quantità di moto|quantità di moto]] per ciascuna massa sarà:
$$
\vec{P_{n}}(t) = m_{n}\vec{v}_{n}(t) \\
$$
Per cui ricordando la [[Leggi della dinamica#seconda legge della dinamica|seconda legge della dinamica]] per ciascuna massa la risultante delle forze applicate sarà:
$$\vec{R}= \sum_{r = 1}^k\vec{F}_{r}=\frac{d\vec{P}}{dt}=m_{n}\frac{d\vec{v_{n}}}{dt} = m_{n}\vec{a}_{n}$$
![[Università/Triennale/Fisica I/IMG_RESOURCES/Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1]]
Consideriamo che le due masse si avvicinino l'una verso l'altra, all'avvicinarsi delle due masse la loro forza di interazione aumenterà di intensità ed in accordo con la [Leggi Della Dinamica#seconda legge della dinamica|terza legge della dinamica]]  le due forze saranno dirette lungo la congiungente delle due masse, uguali in modulo ed opposte in verso.:
$$\begin{array}
a\vec{F}_{1,2} + \vec{F}_{2,1} = 0 
\end{array}$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1]]
In queste condizioni la risultante delle forze applicate di ciascuna massa sarà:
$$\begin{array} \\
\vec{R_{1}}= \vec{F}_{2,1}+\sum_{r = 1}^k\vec{F}_{r}=\frac{d\vec{P}}{dt}=m_{1}\frac{d\vec{v_{1}}}{dt}\\\vec{R_{2}}= \vec{F}_{1,2}+\sum_{r = 1}^k\vec{F}_{r}=\frac{d\vec{P}}{dt}=m_{2}\frac{d\vec{v_{2}}}{dt}

\end{array}$$
Ricordando che l' [[Impulso e quantità di moto|impulso]] della risultante delle forze applicate è uguale alla variazione della quantità di moto :
$$\vec{J}_{R,t_{0},t_{1}}=\int_{t_{0}}^{t_{1}}\vec{R}*dt=\int_{t_{0}}^{t_{1}}\frac{d\vec{P}}{dt}*dt=\int_{t_{0}}^{t_{1}}d\vec{P}=\vec{P}(t_{1})-\vec{P}({t_{0}})$$
Per cui andando a considerare il sistema formato dall'insieme delle masse $m_1$ ed $m_2$ ed andando a considerare **forze interne al sistema** le forze d'interazione tra le due masse e forze esterne tutte le altre, l'impulso della risultante per le due masse sarà e definendo $t_{i}$ l'istante iniziale dell'urto e $t_{f}$ l'istante finale:

$$\begin{array}
\vec{J}_{R_{1},t_{i},t_{f}}=\int_{t_{i}}^{t_{f}}(\vec{F}_{2,1}+\vec{R}_{1ext})*dt=\vec{P}_{1}(t_{f})-\vec{P}_{1}({t_{i}}) \\
\vec{J}_{R_{2},t_{i},t_{f}}=\int_{t_{i}}^{t_{f}}(\vec{F}_{1,2}+\vec{R}_{2ext})*dt=\vec{P}_{2}(t_{f})-\vec{P}_{2}({t_{i}}) 
\end{array}$$

All'avvicinarsi delle due masse le forze interne aumenteranno di intensità rendendo così trascurabile nel momento del contatto l'impulso relativo alle forze esterne.
Le forze interne sono infatti **forze di carattere impulsivo** quindi raggiungono un picco elevato nell'intervallo nel quale si manifesta l'urto:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
Per cui se sommo membro a membro i due integrali trascurando l'impulso delle forze esterne e ricordando che si tratta di forze uguali ed opposte:
$$\int_{ti}^{t_f}\vec{F}_{2,1}dt +\int_{ti}^{t_f}\vec{F}_{1,2}dt = \int_{ti}^{t_f}\vec{F}_{1,2} + \vec{F}_{2,1}dt = 0 = \Delta \vec{P}_{1} + \Delta \vec{P}_{2} = \Delta(\vec{P_{1}}+\vec{P}_{2})$$
Per cui la variazione della quantità di moto del sistema delle due masse resta costante nel corso di un urto.
$$\vec{P}_{1i}+\vec{P}_{2_{i}}=\vec{P}_{1f}+\vec{P}_{2f}$$

**Dunque un urto è un fenomeno nel quale la quantità di moto del sistema composto dalle masse che rimane costante**

## Classificazioni energetiche
### Urto elastico 

Se nell'urto oltre a conservarsi la quantità di moto $\vec{P}$ del sistema si conserva anche [[Lavoro ed energia cinetica|l'energia cinetica]] del sistema di masse sarà:
$$m_{1}\vec{v}_{1i}+m_{2}\vec{v}_{2i}=m_{1}\vec{v_{1f}}+m_{2}\vec{v_{2f}}$$
Nel caso unidimensionale quest'equazione vettoriale diventerà un equazione scalare e tramite la relazione precedente sulla conservazione della quantità di moto potremo risolvere il seguente sistema:
$$
\begin{cases}
m_{1}\vec{v}_{1i}+m_{2}\vec{v}_{2i}=m_{1}\vec{v_{1f}}+m_{2}\vec{v_{2f}}\\ \\
\frac{1}{2}m_{1}v_{1i}^2+\frac{1}{2}m_{2}v_{2i}^2 = \frac{1}{2}m_{1}v_{1f}^2+\frac{1}{2}m_{2}v_{2f}^2 

\end{cases}
$$
### Urto Completamente anelastico 
In un urto totalmente anelastico tra due masse che si muovono in direzioni opposte, la conservazione della quantità di moto è l'unica legge fisica che si applica, poiché l'energia cinetica non si conserva. Una parte dell'energia cinetica si trasforma in altre forme di energia, come calore o deformazione.

La quantità di moto prima dell'urto è:

$$
p_{\text{iniziale}} = m_1 v_1 + m_2 v_2
$$

Dopo l'urto, quando le due masse si muovono con una velocità comune \( v_f \), la quantità di moto finale è:

$$
p_{\text{finale}} = (m_1 + m_2) v_f
$$

Poiché la quantità di moto si conserva, possiamo uguagliare le due espressioni:

$$
m_1 v_1 + m_2 v_2 = (m_1 + m_2) v_f
$$

Risolvendo per la velocità finale \( v_f \):

$$
v_f = \frac{m_1 v_1 + m_2 v_2}{m_1 + m_2}
$$

L'energia cinetica totale prima dell'urto è:

$$
E_{\text{cinetica, iniziale}} = \frac{1}{2} m_1 v_1^2 + \frac{1}{2} m_2 v_2^2
$$

Dopo l'urto, l'energia cinetica totale sarà:

$$
E_{\text{cinetica, finale}} = \frac{1}{2} (m_1 + m_2) v_f^2
$$

La differenza tra l'energia iniziale e quella finale rappresenta l'energia dissipata durante l'urto.

Se le masse sono uguali e le velocità opposte, la velocità finale sarà zero. L'energia dissipata dipenderà dalla differenza tra le velocità iniziali e la velocità finale risultante.
