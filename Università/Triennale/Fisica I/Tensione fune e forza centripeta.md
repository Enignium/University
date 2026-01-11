Consideriamo un corpo che ancorato ad una fune ideale di lunghezza *L* inestensibile e di massa trascurabile ruoti descrivendo una traiettoria circolare.


![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1]]
Valutiamo la risultante delle forze applicate in tre diversi punti del moto: A B C

## Variazioni Tensione della fune
### Punto A:
Prendendo come riferimento un asse parallelo alla forza tensione della fune,
Nella posizione la risultante delle forze applicate sarà:
$$\vec{R} = \vec{T_{a}} + m\vec{g}$$
E sarà uguale alla forza centripeta. La proiezione di quest'equazione sull'asse delle ascisse sarà nulla. Dunque l'accelerazione sarà solo di tipo **centripeto**. Ricordando che $a_{centripeta} = \frac{V_{t}^2}r$ ed applicando la [[Leggi della dinamica#Seconda legge della Dinamica|seconda legge della dinamica]]:
$$T_{a} - mg = \frac{mV_{t_{a}}^2}{L}$$ Da cui segue che :
$$T_{a} = m(\frac{V_{t_{a}}^2}{L} + g)$$
Questa sarà la posizione nella quale la massa sentirò più intensa la tensione della fune, si sentirà  più pesante.

### Punto B:

Prendendo come riferimento un asse parallelo alla forza peso, nella posizione la risultante delle forze applicate sarà:
$$\vec{R} = \vec{T_{b}} + m\vec{g}$$
E sarà uguale alla forza centripeta. La proiezione di quest'equazione sull'asse delle ascisse sarà nulla. Dunque l'accelerazione sarà solo di tipo **centripeto**. Ricordando che $a_{centripeta} = \frac{V_{t}^2}r$ ed applicando la [[Leggi della dinamica#Seconda legge della Dinamica|seconda legge della dinamica]]:
$$T_{b} + mg = \frac{mV_{t_b}^2}{L}$$ Da cui segue che :
$$T_{b} = m(\frac{V_{t_{b}}^2}{L} - g)$$
In questa posizione la tensione sarà minima, inoltre per mantenere la traiettoria circolare e la tensione della fune la condizione  $T_{b} + mg = \frac{mV_{b}^2}{L}  \geq 0$ deve essere verificata, dunque la velocità minima di passaggio dal punto b dovrà essere:
$$V_{b_{min}} = \sqrt{Lg }$$
### Punto C:
Prendendo come riferimento una coppia di assi cartesiani ortogonali uno parallelo alla fune ed uno tangenziale alla traiettoria circolare.
In questo caso la risultante
$$\vec{R} = \vec{T_{c}} + m\vec{g}$$
Avrà **proiezioni su entrambi gli assi** dunque scomponendo l'equazione vettoriale attraverso le sue proiezioni sugli assi:
$$
\begin{array}
am*a_{c} = T_{c} - mg\cos\theta \\
m*a_{t} = -mg\sin\theta
\end{array}
$$
Per cui $T_{c}$ sarà uguale a:
$$T_{c}=m\frac{V_{t_c}^2}{L} + mg\cos \theta = m(\frac{V_{t_c}^2}{L}+g\cos \theta)$$
## Considerazioni Energetiche 
Essendo in ciascun punto la risultante delle forze applicate:
$$\vec{R} = \vec{T} + m\vec{g}$$
Essendo $\vec{T}$ sempre perpendicolare alla traiettoria l'unica forza compiere [[Lavoro ed energia cinetica#Definizione di lavoro|lavoro]] è la forza peso , una [[Forze conservative ed energia meccanica||forza conservativa]], dunque l'[[Forze conservative ed energia meccanica#Energia Meccanica|energia meccanica]] sarò uguale a:
$$E_{m} =K + U_{fpeso} =mgy + \frac{1}{2}mv^2$$
### Punto A:
 Calcolata ne punto A, essendo questo a quota 0 , questa sarà solo cinetica:$$E_{m}(A) =\frac{1}{2}mv^2$$
### Punto B:
 Calcolata nel punto B di quota $2L$ con l'ipotesi di avere tensione della fune nulla nel punto b *(Quindi velocità pari alla minima uguale a $\sqrt{Lg}$*):

$$E_{m}(B) =\frac{1}{2}mLg + mg 2L$$  
### Punto C:
Calcolata nel punto C generico invece troverò la quota $y = L - L\cos \theta =L(1-\cos \theta)$ per cui 
$$E_{m}(C) =\frac{1}{2}mv_{c}^2 + mg L(1-\cos \theta)$$
### Considerazioni
Agendo solo forze conservative l'energia meccanica si mantiene costante, dunque 
$$E_{m}(A) = E_{m}(B) = E_{m}(C)$$ E da questa uguaglianza fissato un dato ottengo informazioni relativo allo stato del moto in ciascuno di questi punti 