Un conduttore omhnico ha una struttura nella quale in seguito al legame chimico gli atomi che lo compongono cedono uno o più elettroni periferici caricandosi positivamente e lasciando gli elettroni ceduti distribuiti su tutto il volume del solido e si muovono di moto caotico in modo tale da rendere nullo il flusso attraverso una qualsiasi sezione del conduttore. In presenza di un campo  sul moto termico si impone  il moto dovuto alla sollecitazione del campo.

Con l'ipotesi che la velocità media $\underline{\vec{v}}$ con la quale si muovono le cariche all'interno del conduttore ohmico sia **costante** dovrà essere costante la quantità di moto che avrà una componente dovuta alla sollecitazione del campo ed una componente dovuta a tutti i processi di interazione che ostacolano il percorso degli  elettroni dal punto di potenziale più basso a punti di potenziale più alto  definiti  urti che avvengono all'interno del reticolo cristallino del conduttore:
$$\frac{d\vec{P}}{dt}=\frac{d\vec{P}}{dt}_{campo}+\frac{d\vec{P}}{dt}_{urti}=0$$
**Per cui la sollecitazione ha una componente forzante ed una resistente al moto**
**Essendo contrastata la velocità dagli urti l'energia del sistema si manifesterà sotto forma di calore e non sotto forma cinetica.**

### Legge di Ohm in forma microscopica

Considerato un tempo medio $\tau$ tempo di rilassamento dipendente dalla temperatura che intercorre tra un urto ed un altro all'interno del conduttore. All'aumentare della temperatura aumenterà anche $\tau$ e che all'istante $t=0$ l'elettrone preso in considerazione sia uscito da un urto, per $\tau$ secondi questo sarà soggetto solo alla sollecitazione del campo elettrostatico. 

Sommando la velocità con la quale l'elettrone esce dall'ultimo urto $\vec{v}(0)$ su tutti gli elettroni e la dividiamo per il numero di elettroni otteniamo la velocità media che essendo una somma di un numeri elevatissimo di valori casuali: 
$$<\vec{v(0)}>=0$$
Nell'intervallo che va da $t=0$ a $t=\tau$ considerando di poter studiare il moto degli elettroni attraverso gli strumenti della fisica classica ed essendo questo soggetto solo al campo elettrostatico e considerando l'accelerazione istantanea uguale all'accelerazione media:
$$q\vec{E}=m\vec{a}=m\vec{{\underline a}}=m\frac{<v(\tau)>-<v(0)>}{\tau}=\frac{m<\vec{v(\tau)}>}{\tau}=\frac{m\vec{v}_{d}}{\tau}$$
Definendo velocità di deriva $\vec{v}_{d}=<\vec{v}(\tau)>$ il valore medio della velocità acquisita dagli elettroni dopo $\tau$ secondi da un evento di urto per effetto della forzante campo elettrostatico 

Per cui la velocità media con cui si muovono gli elettroni di conduzione del conduttore ohmico vale definendo $\mu=\frac{q\tau}{m}$ mobilità  :
$$\vec{v}_{d}=\frac{q\tau \vec{E}}{m}=\mu \vec{E}$$
Per cui in un conduttore ohmnico definendo $\sigma=\frac{\rho q\tau}{m}$ conducibilità con unità di misura $\frac{A}{mV}$ elettrica si ottiene la legge di Ohm in forma microscopica:
$$\vec{J}=\rho \vec{v_{d}}=\frac{\rho q\vec{E}\tau}{m}=\sigma \vec{E}$$
**Per cui il materiale ohmnico esposto al campo elettrostatico risponde al campo elettrostatico generando al suo interno una densità di corrente parallela al campo elettrostatico e proporzionale allo stesso**

## Legge di ohm in forma integrale

*Considerato un conduttore di volume $V_{o}$ contenente $N$ particelle uguali di carica $q$, definendo $n=\frac{N}{V_{o}}$ concentrazione portatori di carica mobile sarà $\rho=\frac{Q}{V_{o}}=\frac{Nq}{V_{o}}=nq$ per cui sostituendo:*
*$$\vec{J}=\frac{nq^2\tau}{m}\vec{E}$$*
*Dalla quale si osserva che $\vec{J}$ è sempre parallela ad $\vec{E}$*
\
Si definisce il reciproco della conducibilità resistività
$$\frac{1}{\sigma}=\rho_{es}$$
Per cui esprimendo $\vec{J}=\frac{1}{\rho_{es}}\vec{E}$ presa in considerazione una sezione di un conduttore attraverso cui passa un corrente $i=cost$ calcolando l'integrale di linea del campo elettrostatico $\vec{E}$ lungo un percorso parallelo all'asse del conduttore:
$$\int_{A}^B\vec{E}\cdot dl=\rho_{es}\int_{A}^B\vec{J}\cdot dl=\rho_{es} J\int_{A}^Bdl=\rho_{es} Jl_{AB}=V(A)-V(B)$$
Moltiplicando e dividendo per $S$ ricordando che $J\cdot S$ da l'intensità di corrente e definendo $R=\frac{\rho_{es} l_{AB}}{S}$ resistenza misurata in ohm $\Omega$ con $1\Omega=\frac{1V}{1A}$:
$$\frac{\rho_{es} JSl_{Ab}}{S}=\frac{\rho_{es} il_{AB}}{S}=Ri=V(A)-V(B)$$
Per cui considerando $V$ la differenza di potenziale si ottiene la legge di ohm in forma integrale:
$$V=Ri$$


## Resistenze
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1]]

Il legame tra tensione e corrente attraverso le resistenze è lineare in quanto: $V=Ri$
Che sia $V=+Ri$ o $V=-Ri$ dipende dal senso della corrente che attraversa il bipolo

Da un punto di vista energetico il resistore dissipa energia sotto forma di colore, spesa dal generatore del campo.

La potenza dell'energia dissipata è uguale a $P=V_{AB}i=Ri^2=\frac{V_{AB}^2}{R}$

## Collegamento serie e parallelo resistenze
### Collegamento serie

Date due resistenze in serie, saranno attraversate dalla stessa corrente e considerato un punto intermedio $C$:
$$\begin{array}
aV_{A}-V_{C}=V_{AC}=V_{R_{1}}=R_{1}i \\
V_{C}-V_{B}=V_{CB}=V_{R_{2}}=R_{2}i \\
V_{A}-V_{C}+V_{C}-V_{B}=V_{AB}=R_{1}i+R_{2}i
\end{array}$$
Per cui una resistenza equivalente alle due resistenze in serie ha resistenza:
$$\frac{V_{A}-V_{B}}{i}=R_{1}+R_{2}$$
L'equivalente di una serie di resistenze è la somma delle resistenze

### Collegamento parallelo

Date due resistenze in parallelo, ciascuna sarà attraversata da una corrente diversa ma sperimenteranno la stessa differenza di potenziale data la conservatività del campo elettrostatico per cui:

$$\begin{array}
aV_{A}-V_{B}=R_{1}i_{1} \\
V_{A}-V_{B}=R_{2}i_{2}
\end{array}$$
Inoltre la somma delle correnti $i_{1}$ ed $i_{2}$ deve essere uguale alla corrente entrante al nodo per cui:
$$i=i_{1}+i_{2}=\frac{V_{AB}}{R_{1}}+\frac{V_{AB}}{R_{2}}$$
Per cui la resistenza equivalente che dovrà avere $R_{eq}=\frac{V_{AB}}{i}$ sarà:
$$R_{eq}=\frac{V_{AB}}{\frac{V_{AB}}{R_{1}}+\frac{V_{AB}}{R_{2}}}=\frac{1}{\frac{1}{R_{1}}+\frac{1}{R_{2}}}$$
