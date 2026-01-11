## Ispirazione Biologica: Il Neurone

![[Slides.pdf#page=43&rect=69,513,530,658|Slides, p.43]]

Si può modellare un neurone biologico come un sistema di elaborazione dell'informazione composto da tre parti funzionali:
1.  **Dendriti (Input):** Canali che ricevono segnali da altri neuroni.
2.  **Soma/Membrana (Elaborazione):** Integra i segnali ricevuti (sommatoria).
3.  **Assone (Output):** Trasmette il segnale risultante ad altri neuroni.

> [!intuito] Convertitore Analogico/Digitale
> Se si misurasse l'attività elettrica inserendo un elettrodo sull'assone, si osserverebbe che il voltaggio reagisce agli input in modo continuo (**analogico**) fino al raggiungimento di una **soglia**. 
> Superata tale soglia, il neurone emette un impulso netto (*spike*), comportandosi come un segnale discreto (**digitale**).

![[Slides.pdf#page=43&rect=70,338,446,485|Slides, p.43]]

La trasmissione del segnale avviene tramite la **sinapsi**, il punto di collegamento tra due neuroni. La sinapsi determina l'intensità (il "peso") con cui l'impulso di un neurone influenza il successivo.

### Plasticità Cerebrale

La capacità di apprendimento del cervello risiede nella sua **plasticità**, ovvero la capacità di modificare la propria struttura interna. Si differenziano tre tipi di plasticità:
1.  Modifica del **peso delle sinapsi** (rafforzamento o indebolimento del collegamento).
2.  Sviluppo di **nuove sinapsi** (creazione di nuove connessioni).
3.  Sviluppo di **nuovi neuroni** (neurogenesi).

> [!info] STDP (Spike-Time Dependent Plasticity)
> Una regola fondamentale della plasticità sinaptica è la *Spike-Time Dependent Plasticity*. 
> Il peso di una sinapsi viene incrementato se esiste una **correlazione temporale** tra l'input (pre-sinaptico) e l'output (post-sinaptico).
> *In breve: se l'input contribuisce frequentemente all'attivazione dell'output, la connessione si rafforza.*

## Modello McCulloch and Pitts (1943)

![[Slides.pdf#page=45&rect=59,546,359,655|Slides, p.45]]

È il primo tentativo matematico di modellare un neurone. Dati $n$ input $x_i$, questi vengono pesati dai coefficienti $w_i$ e sommati. Il risultato viene confrontato con una soglia $\theta$ tramite una funzione a gradino.

Definita l'attivazione interna $h$:
$$h = \sum_{i=1}^n w_{i}x_{i}$$

L'output $\hat{y}$ sarà determinato dalla soglia $\theta$:
$$
\hat{y} = \begin{cases} 
1 & \text{se } h > \theta \\
0 & \text{altrimenti}
\end{cases}
$$

> [!caution] Limitazioni del modello
> Questo modello presenta diverse semplificazioni rispetto alla complessità biologica:
> - **Somma Lineare:** Il modello usa una somma lineare degli input, mentre i neuroni biologici integrano i segnali in modo non lineare.
> - **Inibitori vs Eccitatori:** Sebbene i pesi possano essere negativi (inibitori), il modello è una semplificazione statica.
> - **Treni di impulsi:** Il cervello comunica tramite frequenze e treni di impulsi (*spike trains*) nel tempo, non tramite un singolo valore di attivazione istantaneo.

## Il Percettrone (Rosenblatt, 1957)

Il Percettrone è il primo esempio di rete neurale artificiale capace di "imparare".
![[Slides.pdf#page=45&rect=72,52,288,275|Slides, p.45]]

Collega tra loro neuroni (basati sul modello McCulloch-Pitts). L'output $\hat{y}_{j}$ è definito da una **funzione di attivazione** $\phi$ applicata alla somma pesata:
$$\hat{y}_{j}=\phi\left( \sum_{i=1}^n w_{ij}x_{i}\right)$$

### Regola di Apprendimento

L'innovazione principale è la capacità di ottimizzare i pesi $w_{ij}$ (training) confrontando l'output predetto $\hat{y}_{j}$ con l'output reale desiderato $y_{j}$.
![[Slides.pdf#page=46&rect=56,407,500,655|Slides, p.46]]

La regola di aggiornamento dei pesi è:
$$w_{ij} \leftarrow w_{ij} + \eta \cdot x_{i} \cdot (y_{j}-\hat{y}_{j})$$
Dove $\eta$ è il **learning rate** (tasso di apprendimento).

> [!intuito] Funzionamento della regola
> - Se l'output è corretto ($y_j = \hat{y}_j$), il termine $(y_j - \hat{y}_j)$ è $0$ e il peso non cambia.
> - Se l'output è sbagliato, il peso viene corretto in direzione opposta all'errore, proporzionalmente all'input $x_i$.
> - *Nota:* Se l'input $x_i$ è $0$, il peso associato non viene aggiornato, poiché quel neurone non ha contribuito all'errore.

### Il Bias

Con la sola somma $\sum w_ix_i$, se tutti gli input sono $0$, l'output sarà sempre $0$ (o comunque non attivabile se la soglia è alta). Per permettere al neurone di attivarsi anche con input nulli (shiftare la funzione di attivazione), si introduce un termine di **bias** $w_0$ (corrispondente a un input fittizio $x_0 = 1$).

![[Slides.pdf#page=47&rect=76,510,270,705|Slides, p.47]]

L'equazione diventa:
$$\hat{y}_{j}=\phi\left( w_{0j}+\sum_{i=1}^nw_{i,j}x_{i} \right)$$

### Limite della Separabilità Lineare

> [!warning] Problema dello XOR
> Il percettrone singolo è un **classificatore lineare**: può classificare solo dati separabili da un iperpiano (una retta in 2D).
> Funzioni come la **XOR** (OR esclusivo) non sono linearmente separabili e quindi non possono essere apprese da un singolo percettrone.

Esistono due soluzioni principali:
1.  **Feature Polinomiali:** Aggiungere manualmente feature non lineari (es. $x_1^2, x_1x_2$) per mappare i dati in uno spazio a dimensione superiore dove sono separabili. *Svantaggio:* Richiede intervento umano e rischia l'overfitting, inoltre aumentare le dimensioni dello spazio porta ad avere dati più distanti tra loro, rendendo necessaria l'aggiunta di ulteriori dati al dataset per non rischiare l'overfitting.
2.  **Decomposizione (Percettroni Multistrato):** Scomporre il problema non lineare in sottoproblemi lineari combinati.
    * *Esempio:* $\text{XOR}(A, B) = (A \land \neg B) \lor (\neg A \land B)$.

## Percettroni Multistrato (MLP)

Questa architettura nasce dalla combinazione di più percettroni organizzati in strati (layers).
![[Slides.pdf#page=52&rect=45,380,527,610|Slides, p.52]]

> [!success] Vantaggio: Feature Extraction
> A differenza delle feature polinomiali manuali, una rete multistrato esegue una **estrazione automatica delle feature**. I primi strati imparano combinazioni semplici (sottoproblemi lineari), che vengono combinate dagli strati successivi per risolvere problemi non lineari complessi (come la XOR).

Per ottenere un vantaggio dall'estrazione di nuove feature, dovrà essere necessario applicare alla loro combinazione lineare una funzione di attivazione **non lineare**. 

> [!note] Chiarimento
> Se la funzione di attivazione fosse ancora lineare, anche negli strati interni staremmo ottenendo linearità e la combinazione di funzioni lineari porta comunque ad una funzione lineare. Perciò per ottenere la non linearità sarà necessario introddure una funzione di attivazione non lineare.

### Backpropagation

Per addestrare una rete multistrato non basta la regola semplice del percettrone. Si usa l'algoritmo di **Backpropagation**, basato sulla *regola della catena* (chain rule) delle derivate per cui data  una funzione composta:
$$y=f(h(x))$$

Considerando una funzione composta (dove $h(x)$ è il primo strato e $f(h)$ l'output), la derivata dell'errore rispetto all'input si calcola come:
$$\frac{\partial f(h(x))}{\partial x} = f'(h(x)) \cdot h'(x)$$
### Grafi di Computazione

Per gestire queste derivate in reti complesse, si utilizzano i **grafi di computazione**: strutture dati che rappresentano il flusso delle operazioni.
Le operazioni ("nodi") nel grafo sono tipicamente di due tipi:

1.  **Combinazioni Lineari:** Somme pesate, che in forma matriciale corrispondono al *dot product*.
2.  **Combinazioni Non Lineari (Funzioni di Attivazione):** Applicate elemento per elemento per introdurre non-linearità. Esempi comuni:
    * *Gradino* (Step function - obsoleta per backprop perché non derivabile).
    * *Logistica / Sigmoide* (o Softmax per output multipli).
    * *ReLU* (Rectified Linear Unit).