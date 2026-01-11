## Ipotesi necessarie

Considerando di essere in presenza di un mezzo omogeneo isotropo per cui in condizioni di campi di bassa intensità esiste un legame tra lo [[Spostamento elettrico e polarizzazione|spostamento elettrico]] ed il campo elettrico $\vec{D}=\epsilon \vec{E}$ e tra il campo a induzione [[Magnetizzazione e campo  magnetico|magnetica ed il campo magnetico]] le costanti $\epsilon$ e $\mu$ sono costanti e scalari grazie all'ipotesi di mezzo omogeneo isotropo, in altre circostanze sarebbero grandezze tensoriali.

Se il mezzo ha una certa conducibilità $\sigma$ questo mostrerà esposto al campo elettrico una certa [[Corrente#Densità di corrente elettrica|densità di corrente]] per la [[Conduttori omhnici e resistenze#Legge di Ohm in forma microscopica|legge di Ohm in forma microscopica]] per cui $\vec{J}=\sigma \vec{E}$ 

Il campo elettromagnetico è composto un campo Elettrico concatenato con un campo a induzione magnetica rispettando le equazioni di Maxwell.
## Sistema di equazioni di Maxwell in forma integrale

La prima equazione di Maxwell è la [[Equazioni dell'elettrostatica#Seconda equazione dell'elettrostatica]] applicata ai casi dipendenti dal tempo per cui $$\oint_{S} E\cdot ndS=\frac{Q_{netta}(t)}{\epsilon}$$
La seconda è la [[Circuto RL#Legge di Faraday-Neumann-Lenz|legge di Faraday-Neumann-Lenz]] per cui:
$$\oint_{l} \vec{E}\cdot d\vec{l}=-\frac{\partial \phi(\vec{B})}{\partial t}$$
La terza è la prima [[Equazioni della magnetostatica#Prima legge della magnetostatica|prima legge della magnetostatica]] applicata ai casi dipendenti dal tempo per cui:
$$\oint \vec{B}\cdot ndS=0$$
La quarta è la [[Equazioni della magnetostatica#Seconda legge della magnetostatica|seconda legge della magnetostatica]] con aggiunto un contributo relativo al flusso attraverso una superficie $S$ che concatena il percorso $l$ della densità di corrente, e lo stesso per quanto riguarda la densità di corrente di spostamento:
$$\oint_{l} \vec{B}\cdot d\vec{l}=\mu i=\mu i+ \mu\phi_{S}(\sigma \vec{E})+\mu\phi_{S}\left( \epsilon\frac{\partial \vec{E}}{\partial t} \right)$$
**La soluzione di questo sistema di equazioni fornisce un espressione del campo elettromagnetico, un campo composto da un un campo elettrico concatenato con un campo a induzione magnetica.**

Questo sistema è lineare in quanto le funzioni incognite sono espresse sempre a potenza $0$ o $1$.

Le sorgenti evidenziate da queste equazioni sono la carica netta variabile nel tempo $Q(t)$ e le correnti variabili nel tempo $i(t)$ e le variazioni temporali dei flussi di $\vec{B}$ ed $\vec{E}$.
## Sistema di equazioni di Maxwell in forma differenziale 

La prima equazione di Maxwell in forma differenziale è la seconda [[Equazioni dell'elettrostatica#Seconda equazione dell'elettrostatica#Forma differenziale|seconda equazione dell'elettrostatica]] in forma differenziale applicata ai casi dipendenti dal tempo per cui:
$$\nabla \vec{E}=\frac{\rho(\vec{r},t)}{\epsilon}$$
La seconda equazione di Maxwell in forma differenziale si ottiene invertendo l'ordine di integrazione e derivazione nella legge di Faraday-Neumann-Lenz, ed applicando il teorema di Stokes per cui $\oint_{l}\vec{E}\cdot d\vec{l}=\int_{S}\nabla \times \vec{E}\cdot \vec{n}ds$ ed uguagliando gli integrali per cui :
$$\nabla \times \vec{E}=-\frac{\partial\vec{B}}{\partial t}$$
La terza equazione di Maxwell si ottiene applicando il teorema di Gauss per cui:
$$\nabla \vec{B}=0$$
Per la quarta equazione di Maxwell si applica il teorema di Stokes per cui:
$$\oint_{l} \vec{B}dl=\int_{S}\nabla \times \vec{B}\cdot ndS=\mu \int_{S}\vec{J}(r,t)\cdot \vec{n}dS+\mu \int \sigma \vec{E}\cdot ndS+\mu \int_{S}\epsilon \frac{\partial E}{\partial t}\cdot \vec{n}dS$$ Da cui:
$$\nabla \times \vec{B}=\mu \vec{J}(\vec{r},t)+\mu \sigma\vec{E}+\mu\epsilon\frac{\partial E}{\partial t}$$
Il sistema in forma differenziale sarà:
$$
\begin{cases}
\nabla \cdot \vec{E}(\vec r,t) = \dfrac{\rho(\vec r,t)}{\epsilon},\\[6pt]
\nabla \times \vec{E}(\vec r,t) = -\,\dfrac{\partial \vec{B}(\vec r,t)}{\partial t},\\[6pt]
\nabla \cdot \vec{B}(\vec r,t) = 0,\\[6pt]
\nabla \times \vec{B}(\vec r,t) = \mu \vec{J}(\vec r,t) \;+\; \mu\sigma \vec{E}(\vec r,t) \;+\; \mu\epsilon \dfrac{\partial \vec{E}(\vec r,t)}{\partial t}.
\end{cases}
$$

## Soluzione del sistema in forma differenziale

Per risolvere questo sistema di equazioni applichiamo delle semplificazioni, considerando la conducibilità elettrica $\sigma$ del mezzo in cui stiamo risolvendo il sistema nulla per cui sarà:
$$
\begin{cases}
\nabla \cdot \vec{E}(\vec r,t) = \dfrac{\rho(\vec r,t)}{\epsilon},\\[6pt]
\nabla \times \vec{E}(\vec r,t) = -\,\dfrac{\partial \vec{B}(\vec r,t)}{\partial t},\\[6pt]
\nabla \cdot \vec{B}(\vec r,t) = 0,\\[6pt]
\nabla \times \vec{B}(\vec r,t) = \mu \vec{J}(\vec r,t) \;+\; \mu\epsilon \dfrac{\partial \vec{E}(\vec r,t)}{\partial t}.
\end{cases}
$$
**Le sorgenti del campo elettromagnetico evidenziate sono $\rho(\vec{r},t)$ e $\vec{J}(\vec{r},t)$.  Una volta generato il campo si sostiene da solo e viaggia nello spazio a velocità costante raggiungendo tutti i punti dello spazio.**

Essendo che il campo una volta generato non resta confinato nella regione $\tau$ dove sono presenti le sue sorgenti, sarà possibile valutare il campo elettromagnetico nelle regioni di spazio esterne al volume $\tau$, annullando i contributi delle sorgenti nel sistema, che diventa così:
$$
\begin{cases}
\nabla \cdot \vec{E}(\vec r,t) = 0\\[6pt]
\nabla \times \vec{E}(\vec r,t) = -\,\dfrac{\partial \vec{B}(\vec r,t)}{\partial t},\\[6pt]
\nabla \cdot \vec{B}(\vec r,t) = 0,\\[6pt]
\nabla \times \vec{B}(\vec r,t) = \; \mu\epsilon \dfrac{\partial \vec{E}(\vec r,t)}{\partial t}.
\end{cases}
$$
Si osserva che fuori dalla regione contenenti le sorgenti il sistema diventa simmetrico, il campo elettrico si comporta come se fosse solenoidale ed il campo si sostiene da solo in quanto le variazioni temporali del campo elettrico portano a variazioni temporali del campo a induzione magnetica e viceversa.

Applicando l'identità vettoriale per cui $\nabla \times[\nabla \times(\vec{v})]=-\nabla^2\vec{v}+\nabla[\nabla \cdot v]$ sarà osservando che in queste condizioni $\nabla \vec{E}=0$ si osserva che:
$$\nabla \times [\nabla \times \vec{E}]=-\nabla^2\vec{E}+\nabla [\nabla \vec{E}]=-\nabla^2\vec{E}$$
Per lo stesso motivo:
$$\nabla \times [\nabla \times \vec{B}]=-\nabla^2\vec{B}+\nabla [\nabla \vec{B}]=-\nabla^2\vec{B}$$
Applicando l'operatore rotore ad ambi i membri della seconda e della quarta equazione del sistema sarà quindi:

$$-\nabla ^2\vec{E}=-\nabla \times\,\dfrac{\partial \vec{B}}{\partial t}=-\frac{\partial \nabla \times \vec{B}}{\partial t}=-\mu\epsilon\frac{\partial^2\vec{E}}{\partial t^2}$$
E:
$$-\nabla ^2\vec{B}=\mu\epsilon\nabla \times\,\dfrac{\partial \vec{E}}{\partial t}=\mu \epsilon\frac{\partial \nabla \times \vec{E}}{\partial t}=-\mu\epsilon\frac{ \partial^2\vec{B}}{\partial t^2}$$

Per cui il sistema si riduce a:

$$
\begin{cases}

\nabla^2 \vec{E}(\vec r,t) = \mu\epsilon\dfrac{\partial^2\vec{E}}{\partial t^2},\\[6pt]
\nabla^2 \vec{B}(\vec r,t) = \; \mu\epsilon \dfrac{\partial^2 \vec{B}}{\partial t^2}.
\end{cases}
$$
**È possibile proiettare quest'equazioni sugli assi ottenendo per ciascuna 3 equazioni scalari.**

Si osserva che il prodotto $\mu\epsilon$ ha come unità di misura $\frac{s^2}{m^2}$ , lo stesso che avrebbe una velocità moltiplicata per $10^-2$, facendo i conti si osserva che nell'aria o nel vuoto con $\epsilon_{r}=1$ e con $\mu_{r}=1$ sarà:
$$\epsilon \mu=\frac{1}{c^2}$$
con $c$ velocità della luce nel vuoto, nei casi in cui non dovessimo essere nel vuoto o in aria 
$\epsilon \mu$ sarebbe uguale al reciproco della velocità della luce  nel mezzo specifico $v$ al quadrato , che corrisponde anche alla velocità di propagazione del campo elettromagnetico. 
Per cui sostituendo:
$$
\begin{cases}

\nabla^2 \vec{E}(\vec r,t) = \frac{1}{v^2}\dfrac{\partial^2\vec{E}}{\partial t^2},\\[6pt]
\nabla^2 \vec{B}(\vec r,t) = \; \frac{1}{v^2} \dfrac{\partial^2 \vec{B}}{\partial t^2}.
\end{cases}
$$
**La proiezione sull'asse cartesiano di ciascuna di quest'equitazione vettoriali è l'equazione delle onde** che sarà nella forma:
$$\frac{\partial^2f}{\partial x^2}=\frac{1}{v^2}\frac{\partial^2f}{\partial t^\text{}}$$

## ~~Potenziale scalare~~

~~Esprimendo $\vec{B}(\vec{r},t)=\nabla \times \vec{A}(\vec{r},t)$ nella seconda equazione di Maxwell sarà:~~
~~$$\nabla \times \vec{E}=-\frac{\partial \nabla \times A}{\partial t}=-\nabla \times\frac{\partial A}{\partial t}$$~~
~~Portando tutto al primo membro:~~
~~$$\nabla \times \vec{E}+\nabla \times \frac{\partial A}{\partial t}=0$$~~
~~Mettendo in evidenza:~~
~~$$\nabla \times\left[ \vec{E}+\frac{\partial\vec{A}}{\partial t} \right]=0$$~~
~~Per cui il campo $\vec{E}+\frac{\partial \vec{A}}{\partial t}$ è irrotazionale, ed un campo irrotazionale può sempre essere espresso come il gradiente di una funzione scalare, per cui sarà:~~
~~$$\vec{E}+\frac{\partial \vec{A}}{\partial t}=-\nabla \phi(r,t)$$~~
~~Con $\phi(r,t)$ funzione scalare della posizione potenziale scalare.~~

~~Segue che per il [[Campo elettrico e campo ad induzione magnetica|campo elettrico]] varrà:~~
~~$$\vec{E}=-\nabla \phi(r,t) - \frac{\partial A}{\partial t}$$~~
## Vettore di Poynting

Considerato il sistema di equazioni di Maxwell in forma differenziale espresso in termini di campo magnetico $\vec{H}$:
$$
\begin{cases}
\nabla \cdot \vec{E}(\vec r,t) = \dfrac{\rho(\vec r,t)}{\epsilon},\\[6pt]
\nabla \times \vec{E}(\vec r,t) = -\mu\,\dfrac{\partial \vec{H}(\vec r,t)}{\partial t},\\[6pt]
\mu\nabla \cdot \vec{H}(\vec r,t) = 0,\\[6pt]
\nabla \times \vec{H}(\vec r,t) = \vec{J}(\vec r,t) \;+\sigma \vec{E}+\; \epsilon \dfrac{\partial \vec{E}(\vec r,t)}{\partial t}.
\end{cases}
$$
Moltiplicando ambo i membri della seconda equazione scalarmene per $\vec{H}$ e della quarta equazione per $\vec{E}$ e osservando che per identità vettoriale $\vec{H}\cdot(\nabla \times \vec{E})-\vec{E}\cdot(\nabla \times \vec{H})=\nabla(\vec{E}\times \vec{H})$, definendo $\vec{S}=\vec{E}\times \vec{H}$ vettore di Poynting, con unità di misura $\frac{W}{m^2}$ che si osserva essere una misura della densità superficiale di potenza, sottraendo la quarta equazione dalla seconda si ottiene:
$$\nabla\vec{S}=-\mu \vec{H}\cdot  \frac{\partial \vec{H}}{\partial t}-\vec{J}\cdot \vec{E}-\sigma |E|^2-\epsilon \vec{E}\cdot \frac{\partial \vec{E}}{\partial t}$$

Ricordando il concetto di densità volumetrica di energia relativa al campo elettrico ottenuta come rapporto tra energia immagazzinata in una regione e volume $w_{E}=\frac{1}{2}\epsilon E^2=\frac{1}{2}\vec{E}\cdot \vec{E}$, relativo al campo magnetico l'energia immagazzinata sarà: $w_{L}=\frac{1}{2}\mu H^2=\frac{1}{2}\mu \vec{H}\cdot \vec{H}$
Per cui si osserva che:
- $\frac{\partial w_{E}}{\partial t}=\epsilon \vec{E}\cdot \frac{\partial \vec{E}}{\partial t}$
- $\frac{\partial w_{H}}{\partial t}=\mu \vec{H}\cdot \frac{\partial \vec{H}}{\partial t}$
Si osserva inoltre che il contributo $\sigma|E|^2=\sigma \vec{E}\cdot \vec{E}$ da una misura della densità volumetrica di potenza dissipata per effetto joule mentre $\vec{J}\cdot \vec{E}$ da informazioni relative alla potenza per unità di volume spesa dalle sorgenti del campo  per alimentarlo.

Integrando in relazione al volume nel quale si trovano le sorgenti ambo i membri:
$$\int_{\tau}\nabla \vec{S}d\tau=-\int_{\tau}\vec{J}\cdot \vec{E}d\tau-\int_{\tau}\sigma|E|^2d\tau-\int_{\tau} \frac{\partial(w_{E}+w_{H})}{\partial t}d\tau$$
Invertendo alcuni termini:
$$\int_{\tau}\vec{J}\cdot \vec{E}d\tau=-\int_{\tau}\nabla \vec{S}d\tau-\int_{\tau}\sigma|E|^2d\tau-\int_{\tau} \frac{\partial(w_{E}+w_{H})}{\partial t}d\tau$$
**Con questa equazione di bilancio di potenze si evidenzia da un lato la potenza spesa dalle sorgenti per sostenere l'onda elettromagnetica ,la parte di potenza che fluisce all'esterno della regione $\tau$ dove si trovano le sorgenti e si propaga nell'ambiente circostante sotto forma di flusso del vettore di poynting , nell'altro in ordine la parte della potenza che si trasforma in calore per effetto joule,la parte di potenza spesa per sostenere le variazioni temporali di energia immagazzinata nei campi elettrici e magnetici.**

È flusso del vettore di poynting quella parte di potenza perchè per il teorema di Gauss è possibile esprimere:
$$\int_{\tau}\nabla \vec{S}d\tau=\int_{\tau}\nabla(\vec{E}\times \vec{H})d\tau=\oint_{s}\vec{E}\times \vec{H}\cdot ndS$$