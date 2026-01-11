
## Definizione

Ci si trova in regime di corrente alternata quando tensioni e corrente sono funzioni sinusoidali dipendenti dal tempo di uguale frequenza per cui
$$i(t)=I_{0}sen(wt+\phi)$$
$$v(t)=V_{0}sen(wt+\alpha)$$
$$w=cost$$
Bisognerà dunque sostituire le forze elettromotrici costanti con generatori di tensione sinusoidali.

**Se ho una rete elettrica lineare, dunque avente tutti i bipoli eccezion fatta per i bipoli attivi lineari, una rete scarica fissa indeformabile e schermata da campi di induzione magnetica variabili nel tempo, avendo in ingresso sollecitazioni sinusoidali si avranno in uscita sollecitazioni sinusoidali alla stessa frequenza.**

Le incognite saranno le ampiezze e le fasi delle correnti e le tensioni presenti nella rete.

### Metodo fasoriale

Rappresentando gli ingressi sinusoidali alla rete attraverso dei fasori espressi in forma $$Ae^{j\theta}=A\cos \theta+jAsen\theta$$
Sarà possibile per linearità della rete ottenere informazioni relative all'andamento che si avrebbe avendo una sola sinusoide in ingresso tramite il metodo di sovrapposizione degli effetti mettendo in ingresso l'esponenziale complesso infatti l'uscita sarà la somma dell'uscita che si avrebbe mettendo in ingresso ciascuna delle sinusoidi.

### Applicazione alle resistenze

Nel caso in cui ai capi di un elemento resistivo di una rete sia presente una tensione sinusoidale $v(t)=v_{0}sen(wt)$ essendo $v(t)=Ri(t)$ sarà:
$$i(t)=\frac{v}{R}sen(wt)$$
**Si osserva che la corrente è in fase con la tensione per quanto riguarda gli elementi resistivi**

Esprimendo la tensione come $\dot{V}=V_{0}e^{jwt}$ sarà possibile esprimere la corrente come $\dot{I}=\frac{V_{0}}{R}e^{jwt}$
### Applicazione alle capacità

Nel caso in cui ai capi di un elemento resistivo di una rete sia presente una tensione sinusoidale $v(t)=V_{0}sen(wt)$ essendo $i(t)=C \frac{dV_{c}}{dt}$ sarà:
$$i(t)=wCV_{0}\cos(wt)=wCV_{0}sen\left( wt+\frac{\pi}{2} \right)$$
Si osserva che la corrente non è in fase con la tensione per quanto riguarda gli elementi capacitivi.

**La corrente attraverso l'elemento capacitivo è in anticipo di fase di $\frac{\pi}{2}$, un quarto di periodo, rispetto alla tensione.**

Esprimendo la tensione come $\dot{V}=V_{0}e^{jwt}$ sarà possibile esprimere la corrente come $\dot{I}=CjwV_{0}e^{jwt}$, si osserva che esprimendo tensione e corrente tramite vettori rotanti permette di eliminare lo sfasamento consentendo l'operazione:
$$\frac{\dot{V_{c}}}{\dot{I}_{c}}=\frac{1}{jwC}=-\frac{j}{wC}=Z(w)$$
Dando una misura dell'impedenza associata al bipolo
### Applicazione agli induttori

Nel caso in cui a attraverso un induttore scorra una corrente $i(t)=I_{0}sen(wt)$ essendo $v_{L}(t)=L \frac{di}{dt}$ sarà:
$$v_{L}(t)=wLI_{0}\cos(wt)=wLI_{0}sen\left( wt+\frac{\pi}{2} \right)$$
Si osserva che la corrente non è in fase con la tensione per quanto riguarda gli elementi capacitivi.

**La tensione attraverso l'elemento capacitivo è in anticipo di fase di $\frac{\pi}{2}$, un quarto di periodo, rispetto alla corrente.

Esprimendo la corrente come $\dot{I}=I_{0}e^{jwt}$ sarà possibile esprimere la corrente come $\dot{V_{L}}=LjwI_{0}e^{jwt}$, si osserva che esprimendo tensione e corrente tramite vettori rotanti permette di eliminare lo sfasamento consentendo l'operazione:
$$\frac{\dot{V_{c}}}{\dot{I}_{c}}=jwL=Z(w)$$
Dando una misura dell'impedenza associata al bipolo

### Legge di Ohm generalizzata

Essendo possibile per ogni bipolo attraverso l'espressione di corrente e tensioni tramite vettori rotanti calcolare l'impedenza tramite $\frac{\dot{V}}{\dot{I}}=Z(w)$ si ottiene così la legge di Ohm generalizzata per cui per ciascun bipolo è possibile calcolare:
$$\dot{V}=Z(w)\dot{I}$$
Circuitalmente le impedenze si comportamento come le resistenze, per cui due impedenze in serie sono equivalenti alla somma delle due impedenze in quanto se:
$$\dot{V}_{AB}=\dot{V}_{1}+\dot{V}_{2}=Z_{1}\dot{I}+Z_{2}\dot{I}=\dot{I}(Z_{1}+Z_{2})$$ Per cui $Z_{eq}=\frac{\dot{V}_{AB}}{\dot{I}}=Z_{1}+Z_{2}$

Per quanto riguarda la connessione parallelo l'equivalente è come nel caso delle resistenze.