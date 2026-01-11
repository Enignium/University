
## Carica circuito RLC
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3]]
Considerato di partire da condizioni in cui la rete è scarica per cui all'istante $t=0$ avviene la chiusura di un commutatore tale da far sì che $v_{C}(0)=0$ e $i_{L}(0)=0$, ipotizzando che la rete sia schermata , fissa ed indeformabile sarà possibile applicare la legge di Kirchoff alla maglia per cui 
$$E=Ri(t)+\frac{q(t)}{C}+L \frac{di}{dt}$$
Ricordando che $i=\frac{dq}{dt}$ e che la forza elettromotrice è costante derivando ambo i membri  rispetto al tempo sarà:
$$0=\frac{dE}{dt}=R \frac{di}{dt}+\frac{i(t)}{C}+L \frac{d^2i}{dt^2}$$
Questa equazione differenziale lineare omogenea a coefficienti costanti ha una soluzione banale per cui $i=0$.

**Questa soluzione fisicamente descrive la fase di regime nella quale il condensatore si comporta da circuito aperto e l'induttore come cortocircuito, per cui la corrente che attraversa la rete è nulla. In questa fase resta solo la differenza di potenziale ai capi del condensatore che vale esattamente $E$**

Rimane l'analisi del transitorio, per cui dividendo tutto per L sarà:
$$\frac{R}{L} \frac{di}{dt}+\frac{i(t)}{LC}+ \frac{d^2i}{dt^2}=0$$
Attraverso il metodo delle funzioni di prova si osserva la soluzione essere del tipo $i(t)=Ae^{st}$ per cui sostituendo:
$$\frac{R}{L} sAe^{st}+\frac{1}{LC}Ae^{st}+ s^2Ae^{st}=0$$
Dividendo tutto per $Ae^{st}$ si ottiene l'equazione caratteristica:
$$s^2+\frac{R}{L}s+\frac{1}{LC}=0$$
Equazione di secondo grado che a seconda del valore del determinante potrà avere radici reali e distinte, complesse e coniugate o reali e coincidenti.

Nel caso di discriminante maggiore di $0$ saremo nel caso di smorzamento asintotico per cui l'andamento sarà un esponenziale decrescente che andrà a $0$ asintoticamente

Nel caso di discriminante uguale a 0 saremo nel caso di smorzamento critico nel per cui si raggiungerà lo $0$ nel tempo più rapido possibile

Nel caso di discriminante minore di $0$ saremo nel caso di smorzamento oscillante.

La soluzione è analoga a quella del [[Moto oscillatorio#Oscillatore smorzato|oscillatore smorzato]]

## Circuito RLC alternata
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 2]]

Considerato un circuito RLC che parte da condizioni iniziali nulle per cui $v_{C}(0)=0$ e $v_{L}(0)=0$ che il dielettrico all'interno del conduttore non sia in saturazione per cui $\epsilon \vec{E}=\vec{D}$ e che lo stesso valga per il materiale ferromagnetico all'interno del induttore per cui $\mu \vec{H}=\vec{B}$ e che valga l'ipotesi di parametri concentrati per cui applicando la legge di kirchoff alla maglia:
$$V_{0}\cos(wt)=Ri(t)+L \frac{di}{dt}+v_{C}$$
Esprimendo tutto in termini di $i(t)$, dunque esprimendo $v_{C}=\frac{q}{C}$ ed essendo $i(t)=\frac{dq}{dt}$ sarà $q=i(t)dt$ per cui:
$$V_{0}\cos(wt)=Ri(t)+L \frac{di}{dt}+\frac{1}{C}\int i(t)dt$$
Per togliere l'integrale deriviamo entrambi i membri rispetto al tempo:
$$-wV_{0}\sin(wt)=R \frac{di}{dt}+L \frac{d^2i}{dt^2}+\frac{i(t)}{C}$$
La soluzione di questa equazione sarà del tipo
$$i(t)=I_{0}sen(wt+\phi)$$
In alternativa è possibile esprimere tutto in termini di differenza di potenziale ai capi del condensatore $v_{C}(t)$ come:
$$v_{0}\cos(wt)=LC \frac{d^2vc}{dt}+RC \frac{dv_{c}}{dt}+v_{c}(t)$$
e la soluzione sarebbe del tipo:
$$v_{c(t)}=V_{0}sen(wt+\phi)$$

Passando all'analisi fasoriale mettendo in ingresso un segnale complesso $\dot{V}=V_{0}e^{jwt}$

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 2 1]]
Sarà possibile calcolare la $Z_{eq}=R+jwL-\frac{j}{wC}=R+j\left( wL-\frac{1}{wC} \right)$
Per cui essendo $\dot{V}=Z\dot{I}$ sarà:
$$\dot{I}=\frac{\dot{V}}{Z}=\frac{V_{0}e^{jwt}}{R+j(wL-\frac{1}{wC})}$$
Esprimendo in forma polare $\frac{V_{0}}{R+j\left( wL-\frac{1}{wC} \right)}$ l'ampiezza sarà:
$$|\frac{V_{0}}{R+j\left( wL-\frac{1}{wC} \right)}|=\frac{V_{0}}{\sqrt{R^2+\left( wL-\frac{1}{wC} \right)^2 }}$$
La fase:
$$\angle\frac{V_{0}}{R+j\left( wL-\frac{1}{wC} \right)}=tg^{-1}\left( \frac{\frac{1}{wC}-wL}{R} \right)$$
Per cui sarà:
$$\dot{I}=\frac{V_{0}}{\sqrt{R^2+\left( wL-\frac{1}{wC} \right)^2 }}e^{tg^{-1}\left( \frac{\frac{1}{wC}-wL}{R} \right)}e^{jwt}$$
Per cui calcolando $v(t)$ come $\mathrm{Re}(\dot{I})$ sarà:
$$i(t)=\frac{V_{0}}{\sqrt{ R^2+\left( wL-\frac{1}{wC} \right)^2 }}\cos(wt+{tg^{-1}\left( \frac{\frac{1}{wC}-wL}{R} \right)})$$

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 2 1 1]]

**Si nota che l'ampiezza della corrente è massima alla frequenza di risonanza $w_{0}=\sqrt{\frac{1}{LC}}$ alla quale la rete si comporta come puramente resistiva in quanto i comportamenti reattivi degli altri dipoli che compongono la rete si compensano, a questa frequenza l'impedenza della serie è puramente resistiva **