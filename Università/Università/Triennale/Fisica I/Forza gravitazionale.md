## Definizione forza gravitazionale

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2]]

Date due masse $m$ ed $M$ con $M >> m$ e tracciata la congiungente delle due masse, tra queste si sviluppa una [[Leggi della dinamica#Terza legge della dinamica|coppia di forze di azione e reazione]] per cui:
$$\vec{F}_{M,m} + \vec{F}_{m,M} = 0$$
Consideriamo che $\frac{F_{mM}}{M}=a_{M} \approx 0$ 
Per cui consideriamo il polo $O$ nella posizione della massa $M$ che rimane fissa nello spazio.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1]]
La forza con la quale interagiranno le due masse sarà una forza di tipo [[Forze centrali|centrale]] e del tipo:
$$F_{M,m} = f(r)*\vec{u}_{r}$$
Con
$$f(r) = -G\frac{mM}{r^2}$$
Con $G=6.674*10^{-11} Nm^2/kg^2$
## Considerazioni energetiche
La forza di interazione delle due masse sarà direttamente proporzionale alle masse ed inversamente proporzionale al quadrato della distanza. Il segno meno indica che si tratta di una forza di tipo attrattivo. 
Calcolando il [[Lavoro ed energia cinetica#Lavoro elementare|lavoro elementare]] considerando che $d\vec{l}*u\vec{r} =dr$:
$$\delta L=F_{M,m}*d\vec{l} = f(r)dr = -G\frac{mM}{r^2}dr$$
Dunque calcolando il [[Lavoro ed energia cinetica#Definizione di lavoro|lavoro]] che la forza compie sulla massa $m$ che si muove lungo la sua traiettoria dal punto A al punto B:
$$L_{AB}=\int_{A}^B\vec{F}*d\vec{l}=-\int_{A}^BG\frac{mM}{r^2}dr=GmM{}\int_{A}^B\frac{1}{r^2}dr=-GmM\frac{1}{r}\Big|^B_{A}= \frac{GmM}{r_{A}} - \frac{GmM}{r_{B}}$$
Essendo che il lavoro dipende solo dal punto iniziale e dal punto finale la forza gravitazionale è una [[Forze conservative ed energia meccanica|forza conservativa]] con
$U(r)=-\frac{GmM}{r}$ 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1]]
Per cui ricordando che la parte scalare della forza è la derivata presa col segno meno dell'energia potenziale:
**$$f(r)=-\frac{du}{dr}$$ La forza punta sempre nel verso in cui l'energia potenziale decresce**

Se il risultante delle forze applicate coincide con la forza gravitazionale, [[Forze conservative ed energia meccanica#Principio di conservazione dell'energia meccanica|si conserverà l'energia meccanica]].

**In queste condizioni fissata l'energia meccanica saranno ammissibili tutte quelle distanze r per cui l'energia potenziale è minore dell'energia meccanica, se così non fosse l'energia cinetica dovrebbe essere negativa.**

Per cui:$$0<r<r_{f}$$
### Energia potenziale efficace 

L' [[Forze conservative ed energia meccanica#Energia meccanica|energia meccanica]] sarà:
$$E_{m}=\frac{1}{2}mv^2-G\frac{mM}{r}= cost$$
Centrando il polo nell'origine e ricordando il calcolo della  [[Derivata di un versore]]:
$$\vec{v}=\frac{d\vec{r}}{dt}=\frac{dr}{dt}*\vec{u}_{r}+r(t)\frac{d\vec{u_{r}}}{dt}=v_{r}\vec{u}_{r}+wr\vec{u_{n}}$$
Noto che: 
$v^2 = \vec{v}*\vec{v} = v_{r}^2 + w^2r^2$
È così possibile  scomporre l'espressione dell'energia meccanica in:
$$E_{m}=\frac{1}{2}mv_{r}^2+\frac{1}{2}mw^2r^2-G\frac{mM}{r}= cost$$
Così ricordando la definizione di [[Momento di un vettore#Momento di inerzia|momento di inerzia]] è possibile scomporre l'energia cinetica $E_{k}$ in:
$$\begin{array}
EE_{k_{traslazionale}} = \frac{1}{2}mv_{r}^2\\E_{k_{rotazionale}} = \frac{1}{2}Iw^2
\end{array}$$
Allo stesso modo si può calcolare il [[Momento di un vettore#Definizione di momento angolare|momento angolare]] della massa $m$ come:
$$\vec{L}_{O}=\vec{r}(t)\times m[v_{r}\vec{u}_{r}+wr\vec{u}_{n}]=\vec{r}(t)\times mwr\vec{u}_{n}$$
Il cui modulo sarà $L_{O} = mr^2w = cost$ per cui potrò esprimere $w$ come:
$$w=\frac{L_{O}}{mr^2}$$
Potremo così sostituendo $w$ di nuovo esprimere l'energia meccanica come:
$$E_{m} = E_{k_{traslazinale}} + \frac{1}{2}m\frac{L_{O}^2}{m^2r^4}r^2-\frac{GmM}{r}=E_{k_{traslazionale}}+U_{eff}(r) = cost$$
Definendo $$U_{eff} = \frac{L_{O}^2}{2mr^2} -\frac{GmM}{r} $$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1]]
Ed a seconda dell'energia meccanica saranno ammissibili solo le distanze $r$ tali che $U_{eff}(r)<E_{m}$
- Con $Em_{1}$ traiettoria aperta di tipo parabolico
- Con $Em_{2}$ traiettoria ellittica
- Con $Em_{3}$ traiettoria circolare
## Legame forza peso e forza gravitazionale  
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1]]
Consideriamo che la massa della terra sia distribuita uniformemente, potremmo dunque ai fini dello studio della forza gravitazionale considerare tutta la sua massa come concentrata al suo centro.
Consideriamo inoltre una massa $m$ che si trova ad una quota $h\ll R_{T}\approx 6400Km$ seguirà che l'energia potenziale associata alla forza gravitazionale subita dalla massa $m$ sarà:
$$U(r)=-\frac{GmM}{(R_{T}+h)}$$
Moltiplicando e dividendo per $R_{T}-h$ e considerando trascurabile $h^2$ rispetto a $R_{T}^2$: 
$$U(r)=-\frac{GmM}{(R_{T}^2-h^2)}*(R_{T}-h) \approx  -\frac{GmM}{R_{T}} + \frac{GmM}{R_{T}^2}*h$$
Ricordando che 
$$-\frac{dU}{dr} = f(r)$$
La parte costante della relazione ottenuta sopra sarà irrilevante *(Contano le differenze di energia pontenziale , le parti costanti sono irrilevanti )*
Notiamo che  $\frac{GM}{R_{T}^2}=g$ ed otteniamo otteniamo una funzione energia potenziale che dipende solo dalla quota $h$: 
$$U(h) = mgh$$
**Dunque la forza peso è un espressione semplificata della forza gravitazionale con la quale la terra attrae le masse che si trovano ad una distanza trascurabile rispetto al raggio terrestre.**
## Velocità di fuga
Per calcolare la velocità minima con la quale deve muoversi una massa per non risentire delle forza di attrazione terrestre devo trovare il termine $v_{fuga}$ tale per cui si azzera l'espressione dell'[[Forze conservative ed energia meccanica#Energia meccanica|energia meccanica]] per cui:

$$\begin{array}
EE_{m}=\frac{1}{\text{2}} mv_{fuga}^2-\frac{GmM}{R_{T}} = 0 \\
\frac{1}{2}mv_{fuga}^2=\frac{GmM}{R_{T}}
\end{array}$$
Per cui noto che l'espressione della velocità di fuga non dipende dalla massa.

## Traiettoria di una massa soggetta a forza peso

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1]]
Considerando una forza alla quale è applicata solo la forza gravitazionale esercitata dalla massa  tutta concentrata al suo centro, la massa per effetto di questa forza potrà a seconda della sua energia meccanica:
-  Cadere verso il centro 
-  Muoversi di moto circolare per effetto della forza gravitazionale che agisce da forza centripeta

Nel caso in cui la massa prosegue di moto circolare:
$$F_{M,m} = G\frac{mM_{T}}{r^2}=ma_{centripeta}=mw^2r$$
Per cui:
$$\frac{M_{T}G}{r^3}= w^2=\left( \frac{2\pi}{T} \right)^2$$
Da cui vediamo che il cubo del raggio  della distanza è proporzionale al quadrato del periodo di rotazione.

## Leggi di Keplero
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1]]
### Prima legge di Keplero
Le orbite dei pianeti sono ellissi, con il Sole posto in uno dei fuochi dell'ellisse.

### Seconda legge di Keplero
La linea immaginaria che congiunge un pianeta al Sole spazza aree uguali in tempi uguali. In altre parole, la velocità areolare del pianeta è costante. 
Questo nelle forze centrali la [[Forze centrali#Velocità areale forza centrale|velocità areale è costante]] 
### Terza legge di Keplero
Il quadrato del periodo orbitale di un pianeta è proporzionale al cubo della semiasse maggiore della sua orbita ellittica. 
Questo viene dalla relazione descritta sopra per cui:
$$\frac{M_{S}G}{r^3}=\left( \frac{2\pi}{T} \right)^2$$
