## Growth e Preferential Attachment

Le reti reali differiscono dai modelli di [[3 Random Network|Random Network]] per due importanti caratteristiche:
- **Growth**: Le reti reali sono il risultato di un processo di crescita che incrementa continuamente il numero di nodi $N$ mentre i [[3 Random Network#Modelli di Random Network|modelli di Random Network]] assumono che il numero di nodi $N$ sia fisso. 
- **Preferential Attachment**: Nelle reti reali i nuovi nodi tendono a collegarsi ai nodi più connessi mentre i nodi nei Random Network scelgono randomicamente i nodi con cui collegarsi. 

## Il modello Barabasi-Albert 

 Il modello Barabasi-Albert è un modello di rete che cerca di includere le proprietà di Growth e Preferential Attachment in modo tale da catturare il comportamento delle reti reali osservate non rappresentato dai modelli Random Network.

La costruzione della rete inizia con $m_{0}$ nodi collegati tra loro arbitrariamente assicurandosi che ciascun nodo abbia almeno un collegamento. 
![[Università/Magistrale/Complex Social Networks/Slides/5.pdf#page=13&rect=88,30,274,208&color=red|5, p.13]]

A questo punto lo sviluppo della rete segue due step: 
- **Growth**: Per cui a ciascun timestep si aggiunge ad $m$ nodi presenti nella rete un collegamento ad un **nuovo** nodo appena aggiunto alla rete che avrà così $m$ collegamenti iniziali. 
- **Preferential Attachment**: La probabilità $\Pi(k)$ che il nodo aggiunto sia connesso ad un generico nodo $i$ di grado $k_{i}$ si esprime come:
 $$\Pi(k_{i})=\frac{k_{i}}{\sum_{j=1}^{N-1}k_{j}}$$

> [!danger] Attenzione
> Si considera la somma dei gradi fino ad $N-1$ perchè non si considera il nodo appena aggiunto.

> [!caution] Osservazione
> Il Preferential Attachment è un meccanismo probabilistico.
> 
> ** Un nuovo nodo appena aggiunto è libero di collegarsi a qualunque nodo della rete che sia un hub o abbia un collegamento singolo, tuttavia sarà molto più probabile che questo sia collegato ad un nodo con alto grado.**
> 
> Dopo $t$ timestep il modello Barabasi-Albert genererà una rete con $N=t+m_{0}$ nodi e $m_{0}+mt$ collegamenti.
> La rete ottenuta ha una distribuzione dei gradi [[4 The Scale-Free Property#Distribuzione Power Law|Power Law]] con $\gamma=3$
  
## Dinamica dei Gradi

Per comprendere l'emergere della proprietà Scale-Free è necessario analizzare l'evoluzione temporale del modello Barabasi-Albert (BA).
Consideriamo il grado $k_i$ come una variabile reale continua. Il tasso con cui un nodo esistente $i$ acquisisce nuovi collegamenti è dato da:

$$\frac{dk_{i}}{dt} = m \Pi(k_{i}) = m \frac{k_{i}}{\sum_{j}^{N-1}k_{j}}$$
È possibile esprimere $\sum_{j}^{N-1}k_{j}=2mt-m=m(2t-1)$ 

Sostituendo e considerando grandi valori di $t$ per cui è possibile non considerare il termine $-1$ al denominatore:
$$\frac{dk_{i}}{dt} = \frac{k_{i}}{2t}$$

Integrando questa equazione differenziale, con la condizione iniziale che il nodo $i$ entra nella rete al tempo $t_i$ con grado $m$ (ovvero $k_i(t_i)=m$), si ottiene la legge che descrive la crescita del grado nel tempo:
$$k_{i}(t) = m \left( \frac{t}{t_{i}} \right)^{\beta} \quad \text{con } \beta = \frac{1}{2}$$

Dove $\beta$ è definito come **esponente dinamico** (*dynamical exponent*).

> [!caution] Osservazione
>
> Il grado di *ogni* nodo aumenta seguendo una legge di potenza caratterizzata dallo stesso esponente $\beta$. Tutti i nodi obbediscono alla stessa legge dinamica.
>
>  La crescita dei gradi è sublineare. Questo è conseguenza della natura crescente del modello BA: ogni nuovo nodo ha a disposizione un bacino di nodi esistenti sempre più ampio a cui connettersi. Pertanto, col passare del tempo, i nodi esistenti devono competere per i nuovi link con un numero sempre maggiore di altri nodi.

Dall'equazione $k_{i}(t) = m (\frac{t}{t_{i}})^{\beta}$ emerge chiaramente il ruolo dell'età del nodo.

Poiché $t_i$ appare al denominatore:
* Più piccolo è $t_i$ (ovvero prima il nodo è arrivato nella rete), maggiore sarà il suo grado $k_i(t)$.
* I nodi più vecchi acquisiscono link a un tasso più elevato rispetto ai nodi giovani.

> [!intuito] Intuito
> Questo fenomeno è noto come **First-Mover Advantage** (vantaggio della prima mossa).
> Gli Hub in una rete Scale-Free sono grandi non per una qualità intrinseca superiore, ma semplicemente perché sono **più vecchi**: sono arrivati prima e hanno avuto più tempo per accumulare collegamenti attraverso il meccanismo di attaccamento preferenziale.

## Ruolo della Crescita e dell'Attaccamento Preferenziale

Il modello Barabasi-Albert assume la presenza simultanea di **Crescita** ($N$ aumenta) e **Attaccamento Preferenziale**. Per verificare se entrambi gli ingredienti siano necessari per l'emergere della proprietà Scale-Free, vengono analizzati due modelli alternativi in cui manca uno dei due elementi.
### Assenza di Attaccamento Preferenziale
In questo scenario la rete **cresce** (si aggiunge un nodo ad ogni step) ma **manca l'attaccamento preferenziale**.
* I nuovi nodi scelgono i nodi a cui collegarsi in modo **casuale uniforme** (tutti i nodi hanno la stessa probabilità $\Pi = 1/(m_0+t-1)$).

Ne segue che:

* La distribuzione dei gradi risultante è **Esponenziale**:
$$P(k) \sim e^{-\frac{k}{m}}$$    
* La funzione esponenziale decade molto più velocemente di una Power Law.

> [!caution] Osservazione
> L'assenza di attaccamento preferenziale elimina la possibilità di avere Hubs. Poiché tutti i nodi accumulano link con la stessa probabilità, manca il fenomeno del *"rich-get-richer"* (i ricchi diventano più ricchi). Di conseguenza, **la rete non è Scale-Free**

### Assenza di Crescita
In questo scenario **esiste l'attaccamento preferenziale**, ma la rete ha un numero di nodi $N$ **fisso** (non cresce).
* Il modello inizia con $N$ nodi e ad ogni step si aggiungono solo link tra i nodi esistenti seguendo la logica preferenziale.

Ne segue che:

* Inizialmente il sistema sembra seguire una Power Law, ma non è stabile.
* Con il passare del tempo, la distribuzione converge verso una Gaussiana attorno al grado medio.
* Al limite ($t \to \infty$), la rete diventa un **grafo completo** (tutti collegati con tutti), dove tutti i nodi hanno grado $k \approx N-1$.

> [!caution] Osservazione
> L'assenza di crescita porta alla perdita di stazionarietà. La rete si "satura" evolvendo verso un grafo completo. Sebbene ci sia l'attaccamento preferenziale, senza l'afflusso continuo di nuovi nodi "poveri" (a basso grado), la competizione si appiattisce e **la proprietà Scale-Free non emerge**.
### Il ruolo delle due proprietà.

L'analisi dei modelli A e B dimostra che Crescita e Attaccamento Preferenziale sono **entrambi necessari simultaneamente** per generare una rete Scale-Free.

1.  **Solo Crescita (no PA):** Porta a una distribuzione stazionaria ma **Esponenziale**.
2.  **Solo PA (no Crescita):** Porta a una distribuzione non stazionaria che collassa su una **Gaussiana/Grafo Completo**.
3.  **Crescita + PA (Modello BA):** Genera la distribuzione stazionaria **Power-Law** (Scale-Free).