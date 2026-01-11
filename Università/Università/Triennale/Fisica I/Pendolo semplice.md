## Pendolo semplice 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1|600]]
Considerata una massa $m$ appesa ad una fune ideale inestensibile di massa trascurabile di lunghezza $L$ nel punto di equilibrio il risultante delle forze applicate sarà $\vec{T}+m\vec{g}=0$

Spostando la massa in un punto in cui la fune forma un angolo $\theta$ rispetto alla sua posizione in equilibrio, la risultante delle forze applicate sarà sempre $\vec{R}=m\vec{g}+\vec{T}=m\vec{a}$
Proiettando questa equazione vettoriale sugli assi e notando che 
$$\begin{cases}
ma_{x}=-mgsen\theta\\ma_{y}=\vec{T}-mg\cos \theta
\end{cases}$$
	*Nota: l'accelerazione lungo l'asse $y$ equivale all'accelerazione centripeta di un moto circolare quindi essendo la traiettoria curvilinea questo contributo non potrà essere nullo altrimenti non ci sarebbe curvatura    $\vec{T}-mg\cos \theta\neq 0$*

La componente tangenziale dell'accelerazione $\frac{d^2S}{dt^2}=-gsen\theta$
Sapendo che $\Delta S=L\Delta \theta$ dividendo per $\Delta t$ entrambi i membri e facendo tendere $\Delta t \to 0$:
$$\frac{dS}{dt}=v_{t}=L\frac{d \theta}{dt}$$
Per cui dall'espressione della componente tangenziale dell'accelerazione:
$$L\frac{d^2\theta}{dt^2}=-gsen\theta$$
Questa equazione differenziale non è lineare, ma con l'ipotesi di piccole oscillazioni, per cui $\theta<10$ si approssima:
$$\frac{d^2\theta}{dt^2}=-\frac{g}{L}\theta$$
Dello stesso tipo di quella associata all'[[Moto oscillatorio#Oscillatore armonico|oscillatore armonico]] per cui attraverso il metodo delle funzioni di prova la soluzione sarà del tipo:
$$\theta(t)=A\cos(wt+\phi)$$ Con $w=\sqrt{ \frac{g}{L} }$
##  Considerazioni energetiche
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1]]



Nel caso della massa appesa ad una fune ideale di lunghezza $L$ inestensibile di massa trascurabile il risultante delle forze applicate sarà :
$$\vec{R} = \vec{T} + m\vec{g}$$
Andando a calcolarne il [[Lavoro ed energia cinetica#Definizione di lavoro|lavoro]] ed applicando il [[Lavoro ed energia cinetica#Teorema delle forze vive|Teorema delle forze vive]]:
$$L_{R} = \int_{a}^b\vec{R}*\vec{dl}=\Delta k=\int_{a}^b\vec{T}*\vec{dl} + \int_{a}^bm\vec{g}*\vec{dl}$$
Ma essendo la tensione della fune sempre ortogonale alla traiettoria ed essendo la forza peso $m\vec{g}$ [[Forze conservative ed energia meccanica#Forza Peso|conservativa]]:
$$L_{R} = \Delta K =  \int_{a}^bm\vec{g}*\vec{dl} = -\Delta U = mgy_{a} - mgy_{b}$$
Dove ottengo:$$\begin{array}
ay_{a}= L - L*\cos \theta=L(1-\cos \theta)
\\y_{b} = 0
\end{array}$$
Per cui se calcolo l' [[Forze conservative ed energia meccanica#Energia Meccanica|Energia meccanica]] ricordando che nel punto iniziale la $\vec{v}$ è 0:
$$\begin{array}
 eE_{m}(A) = mgL(1-\cos \theta)\\E_{m}(B) = \frac{1}{2}mv_{b}^2
\end{array}$$


