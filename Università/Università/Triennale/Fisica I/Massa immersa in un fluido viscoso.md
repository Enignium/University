Quando una massa attraversa un fluido viscoso il mezzo esercita una forza resistente al moto proporzionale alla velocità $\vec{F}_=-b\vec{v}$ con $b$ costante che dipende dalle proprietà del fluido
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1]]
Considerato una massa $m$ lasciata cadere in un fluido viscoso le uniche forze agenti saranno la forza resistente $\vec{F}$ e la forza di gravita $m\vec{g}$. Il risultante delle forze sarà:
$$\vec{R}=m\vec{a}=mg-b\vec{v}$$
Ma sapendo che: $$m\vec{a}=m\frac{d\vec{v}}{dt}$$ Sostituendo e proiettando l'equazione vettoriale lungo l'asse y si ottiene:
$$m\frac{dv}{dt}=mg-bv$$ **Questa è un equazione differenziale lineare non omogenea, si nota all'aumentare della velocità l'accelerazione si riduce man mano, esiste dunque un valore di velocità limite $v_{T}=\frac{mg}{b}$  tale per  cui l'accelerazione si annulla e la velocità non aumenterà più.**

Essendo l'equazione differenziale omogenea lineare la soluzione  sarà la somma di due soluzioni una particolare ed una omogenea associata:
$$v(t)=v_{omass(t)}+v_{P}$$
La soluzione particolare sarà $v_{T}=\frac{mg}{b}$, la soluzione omogenea associata si ottiene ponendo:
$$m\frac{dv}{dt}+bv=0$$
Per cui:
$$\frac{dv}{dt}=-\frac{b}{m}v$$
Col metodo delle funzioni di prova si ricava che la soluzione è del tipo $v(t)=Ae^{\alpha t}$ per cui derivando e sostituendo: 
$$A\alpha e^{\alpha t}=-\frac{b}{m}Ae^{\alpha t}$$
Da cui si ricava che $\alpha=-\frac{b}{m}$ per cui:
$$v(t)=Ae^{-\frac{b}{m}t}+\frac{mg}{b}$$
In condizioni iniziali nulle, per cui $v(0)=0$ si ottiene che $A=-\frac{mg}{b}$
Per cui:
$$v(t)=\frac{mg}{b}-\frac{mg}{b}e^{-\frac{b}{m}t}=\frac{mg}{b}(1-e^{-\frac{b}{m}t})=v_{T}(1-e^{-\frac{b}{m}t})$$