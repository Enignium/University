![[Drawing 2025-04-02 17.06.42.excalidraw 1]]
## Energia potenziale

Ricordiamo la definizione di [[Lavoro ed energia cinetica#Lavoro Elementare|Lavoro Elementare]]
$$\delta L = \vec{F}*\vec{dl}$$
$$
L_{ab} = \int_{a}^{b} \vec{F}*\vec{dl}$$Dipende solo dagli estremi di integrazione e non dal percorso *l*,  la forza sarà **conservativa** e sarà valido dire che :
$$L_{ab} = \int_{a}^{b} \vec{F}*\vec{dl} = U(a) - U(b)$$
Ricordando il [[Teorema di Torricelli]] questa cosa sarà vera solo se ciò che sta sotto la funzione sotto integrale è un differenziale: perciò definisco una funzione scalare della posizione $U(\vec{r})$ tale che $$
\vec{F}*\vec{dl} = -dU$$
*Nota: Il segno meno viene da una convenzione.*

Chiamo la funzione  $U(\vec{r})$ **Energia Potenziale**

Per cui il lavoro elementare coincide con la variazione di energia potenziale nel percorso infinitesimo  $\vec{dl}$ presa col segno meno.

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1]]Considerando una forza conservativa il cui punto di applicazione descrive una traiettoria chiusa ci rendiamo conto che:
$$\oint_a^a \vec{F}*\vec{dl} = U(a) - U(a) = 0$$ Del resto se scomponessi il percorso nei percorsi da A a B e da B ad A ricordando che essendo conservativa la forza il risultato dipende solo dal percorso: 
$$\oint_a^a \vec{F}*\vec{dl} = {}_{l1}\int_a^b \vec{F}*\vec{dl}{\text{ }}+ {}_{l2}\int_b^a \vec{F}*\vec{dl}  = {}_{l1}\int_a^b \vec{F}*\vec{dl}{\text{ }}- {}_{l2}\int_a^b \vec{F}*\vec{dl} = 0$$

### Esempio unidimensionale

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1]]
Consideriamo una massa che sotto applicazione di una forza conservativa si muove in una sola dimensione
$$\vec{F}=F*\vec{i}$$
$$\vec{dl}=\vec{i}*dx$$
$$\delta L=\vec{F}*\vec{dl} = F_x*dx$$
$$
L_{ab} = \int_{x_a}^{x_b} \vec{F}*\vec{dl} = \int_{x_a}^{x_b} F_x*dx = -\Delta U = U(x_a) - U(x_b) 
$$
Per il [[Teorema di Torricelli]] $F_x*dx$ è uguale a $-dU$ e quindi 
$$F_x = -\frac{dU}{dx}$$
Quindi la parte scalare di una forza conservativa è la derivata dell'energia potenziale presa col segno meno

Questo ci dice che la forza punta nel verso in cui l'energia potenziale decresce ed è nulla nel momento in cui questa resta costante.
## Energia meccanica
Definisco una grandezza di nome Energia meccanica come somma di energia cinetica e potenziale:
$$
E_m = K + U
$$
### Principio di conservazione dell'energia meccanica

Su una massa sulla quale agisce una singola forza conservativa questa coinciderà con la risultante delle forze applicate e ricordando il [[Lavoro ed energia cinetica#Teorema delle forze vive|Teorema delle forze vive]] 

$$
L_{ab} =
U(a) - U(b) = K(b) - K(a) =
-\Delta U = \Delta K

$$
Da cui portando tutto ciò che riguarda a al primo membro e tutto ciò che riguarda b al secondo ottengo che:
$$U(a) + K(a) = U(b) + K(b)
$$
**Per cui trovo come risultato che se la forza applicata alla massa è conservativa l'energia meccanica si conserva.**

Questo principio vale anche nel caso in cui non agisce solo una forza conservativa ma ne agiscono molte, in quanto 
$$
\vec{R} = \vec{F_1} + \vec{F_2}
$$
e per la linearità dell'operatore integrale 
$$
 L_{AB} =  \int_{a}^{b} \vec{R}*\vec{dl} = \int_{a}^{b} \vec{F_1}*\vec{dl} + \int_{a}^{b} \vec{F_2}*\vec{dl} = U_1(a) - U_1(b) + U_2(a) - U_2(b) = K(b) - K(a) 
$$
Portando tutto ciò che riguarda a al primo membro otteniamo:
$$
U_1(a) + U_2(a) +  K(a) = U_1(B) + U_2(B) + K(B) 
$$Per cui se su una massa agiscono più forze conservative per questa massa vale il principio di conservazione dell'energia meccanica.

Nel caso generale l'energia meccanica calcolata in punto è pari alla somma dell'energia cinetica calcolata in quel punto e tutte le componenti potenziali date dalle forze conservative agenti sulla massa:
$$E_{m}(P) =  K(P)+U_{1}(p) + U_{2}(p) +\dots+U_{n}(p)
$$
## Esempi di forze conservative
#### Forza peso

![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1]]
Consideriamo la Forza peso $\vec{F_p} = -mg\vec{j}$ e calcoliamo il lavoro che compie su una massa che si muove da a a b
Ed orientiamo il nostro sistema di riferimento in modo tale da ottenere il versore $\vec{j}$  antiparallelo a $\vec{F_p}$Il prodotto scalare fra $\vec{F_p}$ e $\vec{dl}$ chiaramente è:
$$
\begin{array}{l}
\vec{F_p} = -mg\vec{j}\\\vec{dl} =  \vec{i}dx+\vec{j}dy+\vec{k}dz\\\vec{F_p} * \vec{dl} = -mg\vec{j} * \vec{j}dy = -mgdy
\end{array}
$$
Dunque:

$$L_{ab} = \int_a^bm\vec{g}*\vec{dl} =\int_a^b -mgdy =-mg\int_a^bdy = -mgy\Big|_a^b = -mgy_b + mgy_a
$$

Dal risultato è chiaro come il lavoro dipende solo dal punto iniziale e dal punto finale del percorso, per cui la forza peso è conservativa.


*Nota: Tutte le forze costanti sono conservative (Se la forza è costante sotto il segno di integrale è tutto costante ed il risultato è una funzione lineare.)

