Lo studio della diffusione di malattie è un campo cruciale della Network Science.
L'epidemia di **SARS** del 2003 fornisce un esempio emblematico di come la struttura della rete influenzi la propagazione.
### Il Caso del Super-Spreader (SARS 2003)
Tutto ebbe origine quando un medico della provincia cinese del Guangdong, già esposto a pazienti con "polmonite atipica", soggiornò al **Metropole Hotel** di Hong Kong.
In una sola notte, **infettò 16 ospiti**. Questi individui, spostandosi verso Hanoi, Singapore e Toronto, innescarono focolai globali.

> [!info] Il Concetto di Super-Spreader
> Gli epidemiologi scoprirono che il medico era un **Super-Spreader**: un individuo responsabile di un numero sproporzionato di contagi.
> In termini di reti, un super-spreader è un **HUB**: un nodo con un grado eccezionalmente alto.
> Proprio come gli hub tengono unita la rete (vedi robustezza), essi sono anche i vettori principali per la diffusione rapida dei patogeni.

## Modellazione Epidemica Classica

L'epidemiologia tradizionale si basa su due ipotesi fondamentali semplificative:
1.  **Compartimentalizzazione:** Ogni individuo è classificato in base allo stadio della malattia (es. Sano, Infetto, Guarito).
2.  **Mescolamento Omogeneo (Homogeneous Mixing):** Si assume che ogni individuo abbia la stessa probabilità di entrare in contatto con chiunque altro.

Si differenziano gli individui in diverse categorie quali:

* **S (Susceptible):** Individui sani che non hanno ancora contratto il patogeno.
* **I (Infectious):** Individui infetti e contagiosi.
* **R (Recovered):** Individui guariti che hanno sviluppato immunità (o sono deceduti/rimossi).
- **Immuni**: Individui che non possono essere infetti.
- **Latenti**: individui che sono stati esposti alla malattia ma non sono ancora contagiosi.
## Modello SI (Susceptible-Infected)

È il modello più semplice, adatto a descrivere malattie incurabili o fasi iniziali di un'epidemia dove non c'è guarigione.
La dinamica prevede solo due stati:
$$S \xrightarrow{\beta} I$$
Una volta infetti, si rimane infetti per sempre.

Per descrivere matematicamente la diffusione di un patogeno nel modello SI, è necessario definire le variabili e i parametri fondamentali che governano la dinamica.

Ecco le grandezze principali:

| Simbolo                 | Descrizione                                                                                                                 | Condizioni Iniziali / Note                 |
| :---------------------- | :-------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------- |
| **$N$**                 | Numero totale di individui (nodi del network).                                                                              | Popolazione costante.                      |
| **$S(t)$**              | Numero di individui **suscettibili** (sani) al tempo $t$.                                                                   | $S(0) \approx N$ (tutti sani all'inizio).  |
| **$I(t)$**              | Numero di individui **infetti** al tempo $t$.                                                                               | $I(0) \approx 0$ (pochi infetti iniziali). |
| **$\langle k \rangle$** | Numero medio di contatti di un individuo.                                                                                   | Grado medio della rete.                    |
| **$\beta$**             | **Tasso di trasmissione**: probabilità che la malattia venga trasmessa da un infetto a un suscettibile nell'unità di tempo. | Parametro intrinseco del patogeno.         |
### Equazione Differenziale
La variazione nel tempo della frazione di infetti $i(t) = I(t)/N$ è descritta dalla seguente equazione logistica:

$$\frac{di}{dt} = \beta \langle k \rangle i (1-i)$$

Dove $(1-i)$: Frazione di suscettibili.

> [!dimostrazione]- Dimostrazione
>  1.  Ogni individuo infetto ha in media $\langle k \rangle$ contatti per unità di tempo.
> 2.  La probabilità che un contatto avvenga con un individuo suscettibile è $S(t)/N = s(t)$.
> 3.  Quindi, ogni infetto genera $\beta \langle k \rangle s(t)$ nuove infezioni.
> 4.  Poiché ci sono $I(t)$ individui infetti totali, il numero di nuovi infetti è:
>     $$\frac{dI}{dt} = \beta \langle k \rangle  \frac{S(t)}{N} I(t)$$
> 5.  Dividendo tutto per $N$ e sostituendo $s(t) = 1 - i(t)$, otteniamo:
>     $$\frac{di}{dt} = \beta \cdot \langle k  \rangle \cdot i \cdot (1-i)$$

Risolvendo l'equazione differenziale con condizione iniziale $i(0) = i_0$, si ottiene l'andamento temporale della frazione di infetti:

$$i(t) = \frac{i_{0} e^{\beta\langle k\rangle t}}{1 - i_{0} + i_{0} e^{\beta\langle k\rangle t}}$$

> [!dimostrazione]- Passaggi dell'Integrazione
> Partendo da $\frac{di}{dt} = \beta \langle k \rangle i (1-i)$, separiamo le variabili:
> $$\frac{di}{i(1-i)} = \beta \langle k \rangle dt$$
> Scomponiamo in fratti semplici: $\frac{1}{i(1-i)} = \frac{1}{i} + \frac{1}{1-i}$.
> Integriamo entrambi i lati:
> $$\int \left(\frac{1}{i} + \frac{1}{1-i}\right) di = \int \beta \langle k \rangle dt$$
> $$\ln i - \ln(1-i) = \beta \langle k \rangle t + C$$
> $$\ln \left( \frac{i}{1-i} \right) = \beta \langle k \rangle t + C$$
> Esponenziamo: $\frac{i}{1-i} = A e^{\beta \langle k \rangle t}$ (dove $A = e^C$).
> Usando la condizione iniziale $t=0, i=i_0$, troviamo $A = \frac{i_0}{1-i_0}$.
> Risolvendo algebricamente per $i(t)$, si ottiene la formula finale.

![[Università/Magistrale/Comples Social Networks/Slides/10.pdf#page=13&rect=179,33,357,234|10, p.13]]

Analizzando il grafico di questa funzione, possiamo distinguere **due regimi dinamici** fondamentali che spiegano come l'epidemia accelera e poi frena.

> [!intuito] Interpretazione dei Regimi
>
> **1. Regime Esponenziale (Fase Iniziale)**
> * **Quando:** All'inizio dell'epidemia, quando $i$ è molto piccolo ($i \ll 1$).
> * **Meccanismo:** Gli individui infetti sono circondati quasi esclusivamente da individui suscettibili. Il patogeno non trova "muri" e si diffonde con la massima efficienza.
> * **Approssimazione Matematica:**
>   $$i(t) \approx i_0 e^{\beta \langle k \rangle t}$$
>   L'esponente (velocità di crescita) è direttamente proporzionale alla contagiosità $\beta$ e alla connettività media della rete $\langle k \rangle$.
>
> **2. Regime di Saturazione (Fase Finale)**
> * **Quando:**  La frazione di infetti si avvicina al 100% ($i \to 1$).
> * **Meccanismo:** Col passare del tempo, diventa sempre più difficile per un infetto trovare qualcuno che non sia già malato. La "riserva" di suscettibili si esaurisce.
> * **Approssimazione Matematica:** La velocità di variazione si annulla:
>   $$\frac{di}{dt} \to 0$$
>   Il sistema raggiunge l'equilibrio solo quando **tutta la popolazione è infetta**.

# Modello Susceptible-Infected-Susceptible (SIS)

Molti patogeni vengono sconfitti dal sistema immunitario o dalle cure mediche, ma non conferiscono un'immunità permanente (es. il raffreddore comune).
Questo scenario è descritto dal modello **SIS**, che estende il modello SI introducendo la possibilità di **guarigione** (recovery) senza immunità.
### Dinamica del Modello
Gli individui infetti guariscono a un tasso fisso $\mu$ (recovery rate) e tornano ad essere **suscettibili**.

$$S \xrightarrow{\text{infezione}} I \xrightarrow{\text{guarigione}} S$$

L'equazione differenziale che descrive la variazione degli infetti nel tempo aggiunge un termine di rimozione all'equazione del modello SI:

$$\frac{di}{dt} = \underbrace{\beta\langle k\rangle i(1-i)}_{\text{Nuovi Contagi}} - \underbrace{\mu i}_{\text{Guarigioni}}$$

La soluzione analitica di questa equazione è:

$$i(t) = \left( 1 - \frac{\mu}{\beta\langle k\rangle} \right) \frac{C e^{(\beta\langle k\rangle - \mu)t}}{1 + C e^{(\beta\langle k\rangle - \mu)t}}$$

A differenza del modello SI (dove tutti finiscono infetti), il modello SIS prevede **due possibili esiti** a lungo termine, dipendenti dalla competizione tra il tasso di contagio e il tasso di guarigione.
### 1. Stato Endemico ($\mu < \beta\langle k\rangle$)
Se il virus si diffonde più velocemente di quanto le persone guariscano:
* La curva degli infetti cresce inizialmente (curva logistica).
* Si raggiunge un asintoto costante $i(\infty) < 1$. Non tutti sono infetti contemporaneamente, ma la malattia **persiste stabilmente** nella popolazione.
* In questo stato, il numero di nuovi contagi bilancia esattamente il numero di guarigioni. 

È possibile esprimere il valore asintotico di $i$ come: $$i(\infty) = 1 - \frac{\mu}{\beta\langle k\rangle}$$
### 2. Stato "Disease-Free" ($\mu > \beta\langle k\rangle$)
Se il tasso di guarigione è sufficientemente alto da superare la capacità di diffusione del virus:
* L'esponente della soluzione diventa negativo.
* La frazione di infetti $i(t)$ decresce esponenzialmente nel tempo.
* L'epidemia si spegne e il patogeno **scompare** dalla popolazione.

### Basic Reproductive Number ($R_0$)

Il parametro fondamentale che determina quale dei due stati si verificherà è il **numero di riproduzione di base** ($R_0$).

$$R_{0}=\frac{\beta\langle k\rangle}{\mu}$$

> [!info] Definizione di $R_0$
> Rappresenta il numero medio di individui suscettibili che un singolo individuo infetto contagia durante il suo intero periodo infettivo, in una popolazione interamente suscettibile.

* **Se $R_0 > 1$:** Ogni malato ne infetta più di uno $\to$ **Stato Endemico** (l'epidemia si auto-sostiene).
* **Se $R_0 < 1$:** Ogni malato ne infetta meno di uno $\to$ **Estinzione** (l'epidemia muore).

## Modello Susceptible-Infected-Recovered (SIR)

Per molti patogeni, come la maggior parte dei ceppi influenzali, gli individui **sviluppano immunità** dopo essere guariti dall'infezione.

Questo scenario non può essere descritto dai modelli SI o SIS, poiché gli individui, una volta guariti, non tornano ad essere suscettibili.

Nasce così il modello **SIR**, che introduce un terzo stato fondamentale:
* **Removed (R):** Individui "rimossi" dalla popolazione attiva. Questo compartimento include chi è guarito (ed è diventato immune) o chi è deceduto. Dal punto di vista della diffusione del patogeno, questi individui non contano più: non possono essere infettati né infettare altri.

La dinamica è unidirezionale:
$$S \xrightarrow{\text{infezione}} I \xrightarrow{\text{guarigione}} R$$

Il sistema è descritto da tre equazioni differenziali accoppiate. Poiché la popolazione totale è costante, vale la relazione di conservazione $s(t) + i(t) + r(t) = 1$.

Il sistema di equazioni che governa la dinamica è:

$$
\begin{cases}
\frac{ds}{dt} = -\beta\langle k\rangle i (1-r-i) \\
\frac{di}{dt} = -\mu i + \beta\langle k\rangle i (1-r-i) \\
\frac{dr}{dt} = \mu i
\end{cases}
$$

> [!intuito] Intuito
> Nelle equazioni sopra, il termine $(1 - r - i)$ è equivalente a $s(t)$.
> * Il termine $\beta\langle k\rangle i s(t)$ (ovvero $\beta\langle k\rangle i (1-r-i)$) rappresenta i **nuovi contagi**: vengono sottratti ai Suscettibili e aggiunti agli Infetti.
> * Il termine $\mu i$ rappresenta le **guarigioni**: vengono sottratte agli Infetti e aggiunte ai Rimossi.

### Dinamica Temporale

A differenza dei modelli precedenti, l'evoluzione temporale delle tre popolazioni mostra un comportamento caratteristico a "onda" (epidemic wave).

![[Università/Magistrale/Comples Social Networks/Slides/10.pdf#page=23&rect=64,56,282,224|10, p.23]]

> [!info] Analisi della Dinamica (vedi grafico)
> * **Suscettibili ($s$, curva grigia):** Decresce monotonicamente nel tempo man mano che la popolazione si ammala. Un punto cruciale è che $s(t)$ **non arriva necessariamente a zero**: l'epidemia può spegnersi lasciando una parte della popolazione sana (immunità di gregge).
> * **Infetti ($i$, curva verde):** Segue una curva a campana.
>     1. Cresce esponenzialmente nella fase iniziale ($R_0 > 1$).
>     2. Raggiunge un **picco massimo** ($I_{max}$), che rappresenta il culmine dell'epidemia.
>     3. Decresce fino a zero quando il numero di suscettibili scende sotto una soglia critica e non è più sufficiente a sostenere il contagio.
> * **Rimossi ($r$, curva viola):** Cresce nel tempo seguendo l'accumulo dei guariti, fino a stabilizzarsi su un valore asintotico finale $R_{\infty}$.

## Network Epidemics

I modelli epidemiologici classici (omogenei) si basano su assunzioni che spesso non riflettono la realtà dei sistemi complessi:
1.  Ignorano la struttura della rete di contatti.
2.  Assumono che chiunque possa infettare chiunque (mescolamento omogeneo).
3.  Assumono che tutti gli individui abbiano lo stesso numero medio di contatti $\langle k \rangle$.

Tuttavia, sappiamo che le reti reali sono spesso **Scale-Free**, caratterizzate da una forte eterogeneità nella distribuzione dei gradi. Questa topologia influenza drasticamente la velocità e la modalità di diffusione dei patogeni.
## Modello SI su Network

Quando un patogeno si diffonde su una rete, gli individui con più connessioni (alto grado $k$) hanno una probabilità molto maggiore di entrare in contatto con un infetto e, a loro volta, di trasmettere la malattia.

Per catturare questo fenomeno senza dover tracciare ogni singolo nodo, si utilizza la **Degree Block Approximation**.

### Degree Block Approximation

L'idea è raggruppare i nodi in classi basate sul loro grado $k$. Si assume che nodi con lo stesso grado siano **statisticamente equivalenti**.

Definiamo $i_k$ come la frazione di nodi infetti all'interno della classe di grado $k$:

$$i_{k} = \frac{I_{k}}{N_{k}}$$

La densità totale di infetti nella rete $i$ sarà quindi la media pesata delle densità locali:
$$i = \sum_{k} P(k) i_{k}$$
![[Università/Magistrale/Comples Social Networks/Slides/10.pdf#page=28&rect=91,104,274,225|10, p.28]]

> [!info] Interpretazione Visiva (Slide 28)
> L'immagine mostra come la rete venga scomposta in "scatole" (blocchi colorati), ognuna contenente nodi con lo stesso numero di connessioni ($k=1, k=2, \dots$).
> L'analisi epidemiologica viene svolta calcolando come evolve l'infezione all'interno di ciascuna scatola e come le scatole interagiscono tra loro.

### Le Equazioni Dinamiche

Invece di un'unica equazione differenziale, abbiamo ora un sistema di equazioni accoppiate, una per ogni classe di grado $k$.
La variazione nel tempo della frazione di infetti con grado $k$ è data da:

$$\frac{di_{k}}{dt} = \beta \cdot (1 - i_{k}) \cdot k \cdot \Theta_{k}$$

Dove:
* $\beta$: Probabilità di trasmissione.
* $(1 - i_k)$: Frazione di nodi di grado $k$ ancora suscettibili.
* $k$: Numero di contatti che ogni nodo del gruppo possiede (potenziali vie di infezione).
* $\Theta_k$: Funzione di densità che rappresenta la **frazione di vicini infetti** di un nodo suscettibile di grado $k$.

### Ruolo del Grado $k$ nella Velocità di Infezione

Risolvendo numericamente le equazioni, si osserva che l'epidemia non colpisce tutti allo stesso modo.

![[Università/Magistrale/Comples Social Networks/Slides/10.pdf#page=31&rect=80,63,285,224|10, p.31]]

> [!intuito] Hub come "Super-Spreaders"
> Il grafico mostra l'andamento di $i_k(t)$ per diverse classi di grado:
> * **Curva Viola ($k=20$):** I nodi con alto grado (Hub) si infettano molto rapidamente all'inizio dell'epidemia. La curva sale verticalmente.
> * **Curva Arancione ($k=1$):** I nodi periferici si infettano molto più lentamente.
>
> **Conclusione:** Gli Hub sono il motore che accelera la diffusione nella fase iniziale.

