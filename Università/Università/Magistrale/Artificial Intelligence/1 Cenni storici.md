## Cenni storici sull' intelligenza artificiale

Il primo modelli di intelligenza artificiale proposto è un modello di intelligenza artificiale simbolica che si distingue per un approccio basato su:

- Fondamenti di conoscenza, un insieme di informazioni pregresse.
- Logica, utilizzata per correlare le conoscenze assimilate
- Inferenza, l'assimilazione di nuovi fatti tramite la correlazione tra fatti già noti attraverso processi logici

Il limite di questo approccio storicamente è stato il costo computazionale necessario per essere scalato sufficientemente da essere applicato a problemi reali.

L'approccio successivo è stato quello dei "Sistemi Esperti", l'obbiettivo di un sistema di intelligenza artificiale capace di ragionare come un umano in qualsiasi area possibile dell'intelligenza artificiale simbolica viene rimpiazzato da un approccio di alta specializzazione sulla soluzione di singoli problemi.

**Il modello di intelligenza artificiale moderno è un modello "data driven" in cui il concetto di ragionamento dell'intelligenza artificiale simbolica viene sostituito dal concetto di apprendimento.** 

La chiave dietro l'intelligenza artificiale moderna sono i "Neural Networks" 

## Task AI

I compiti che si vuole le AI possano svolgere:
- Percezione, la percezione è la facoltà di ricevere input dall'esterno e comprenderne l'entità
- Azione, l'abilità di agire in un mondo fisico o digitale
- Ragionamento, Ottenere nuova conoscenza attraverso l'elaborazione delle conoscenze pregresse
- Apprendimento, Comprendere la relazione tra un input ed un output
- Natural language processing, La capacità di interagire con un utente attraverso il linguaggio naturale
## AI Moderna
![[Slides.pdf#page=1&rect=74,438,298,607|Slides, p.1]]

Il modello moderno di intelligenza artificiale si basa sul concetto di machine learning. 

### Approccio classico
Si può evidenziare la differenza tra gli approcci classici ed il machine learning osservando il seguente schema:
![[Slides.pdf#page=1&rect=74,614,275,701|Slides, p.1]]
Questo approccio classico si basa sulla codifica delle regole a priori attraverso le quali viene ottenuta la risposta, questo implica che la conoscenza delle regole è necessaria per risolvere il problema

### Approccio data driven
![[Slides.pdf#page=1&rect=291,614,499,694|Slides, p.1]]
Vengono date in input le risposte ad un problema oltre al problema stesso, con l'obiettivo di estrarre informazioni relative alle regole che consentono di ottenere quelle risposte dato il problema.

## Approcci specifici al machine learning
![[Slides.pdf#page=1&rect=68,299,465,430|Slides, p.1]]
Si differenziano tre approcci d'apprendimento:
- Supervised learning, attraverso il quale si cerca di ottenere una predizione sull'output, questo è fatto principalmente attraverso due tecniche: regressione (predizione di numeri dato un input) e classificazione(predizione di una classe data un input), in questo approccio deve esistere un qualche genere di "supervisore" che conosce il corretto output per ogni input.
- Unsupervised learning, attraverso il quale si cerca 
- Reinforcement learning,

### Supervised learning
Dati dei dati di questo tipo l'obiettivo è dato un nuovo input (valore di umidità) cercare di predire sulla base degli 
Output passati il valore di uscita relativo(valore di temperatura)
Attraverso la classificazione è possibile predirre dato un nuovo input la classe di un dato nuovo output

I dataset necessari per effettuare questo tipo di learning devono essere composti da input (features) e degli output già noti (labels)
![[Slides.pdf#page=1&rect=63,62,407,194|Slides, p.1]]

### Unsupervised learning 
Senza conoscere le informazioni relativi alle classi degli input precedenti non è possibile classificare con l'unsupervised learning, tuttavia è  possibile effettuare del clustering, per il quale si raggruppano i dati che hanno proprietà simili. 

È possibile effettuare anche anomaly detection, attraverso il quale dati dei dati raggruppati in cluster è possibile osservare gli output anomali che non si raggruppano con gli altri. 

Il dataset necessario ad effettuare il learning unsupervised differisce da quello del supervised per l'assenza delle label.

### Reinforcement learning

Obbiettivo del reinforcement learning è la capacità di effettuare pianificazione, facendo sì che l'agente intelligente percepisca l'ambiente circostante ed effettui delle azioni che abbiano un effetto sull'ambiente.
	*Esempio: un sistema che vuole predirre le mosse successive nel gioco degli scacchi*

Nella percezione sarà necessario distinguere il rumore, e bisognerà tenere in conto l'aleatorità degli effetti dell'azione.

Il reinforcement learning si basa sul concetto di "Learn by experience" ed il concetto di "Reward", allenando il sistema a tornare in stati in cui ha ricevuto ricompense se percepisce stati dell' ambiente simili a quelli in cui ha effettuato quell'azione quando ricompensato.
