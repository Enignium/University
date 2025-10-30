
Il caso del Belgio mostra come l’analisi delle reti possa rivelare divisioni sociali nascoste. Blondel e i suoi studenti hanno studiato la rete delle chiamate mobili del paese, dove ogni persona era un nodo e i collegamenti rappresentavano chiamate regolari. 
Applicando un algoritmo di _community detection_, hanno scoperto due grandi cluster di individui che comunicavano quasi esclusivamente all’interno del proprio gruppo linguistico: uno di francofoni e uno di fiamminghi. Questo indica che, pur condividendo lo stesso Stato, la società belga è formata da due comunità fortemente coese ma debolmente connesse tra loro.

![[Pasted image 20251030104914.png|400]]

L’immagine rappresenta la struttura delle comunità belghe ricavata dallo studio delle **chiamate telefoniche mobili**

- Ogni nodo rappresenta una _comunità_ (cioè un gruppo di persone che comunicano più spesso tra loro).

- La dimensione del nodo è proporzionale al numero di individui appartenenti a quella comunità.

- **Il colore** indica la **lingua predominante**:  

🔴 rosso → comunità francofone (Vallonia)  

🟢 verde → comunità fiamminghe (Fiandre)

Si notano **due grandi cluster** distinti, uno rosso e uno verde, con **pochissimi collegamenti tra loro**, a indicare che i due gruppi linguistici comunicano soprattutto al proprio interno. L’area **centrale e intermedia**, in cui i nodi presentano colori misti (rosso-verde), rappresenta **Bruxelles**, una regione culturalmente più ibrida dove le due lingue e culture **si intersecano maggiormente**. La rete sociale mostra **una chiara segregazione linguistica**, con una zona di transizione (Bruxelles) che funge da ponte tra le due grandi comunità.

### Zachary Karate Club

Il caso del _Zachary’s Karate Club_ rappresenta uno degli esempi più noti nello studio delle comunità nelle reti sociali. Negli anni Settanta il sociologo Wayne Zachary analizzò i rapporti tra trentaquattro membri di un club di karate, registrando le connessioni tra coloro che si frequentavano anche al di fuori dell’attività sportiva. Quando un conflitto tra il presidente e l’istruttore portò alla divisione del club in due gruppi distinti, questa separazione reale divenne la prova concreta dell’esistenza di due comunità interne già presenti nella struttura delle relazioni. Studi successivi applicarono algoritmi di _community detection_ al grafo delle interazioni e mostrarono che era possibile individuare le due fazioni semplicemente osservando la topologia della rete. Il dataset divenne così un riferimento fondamentale per testare nuovi metodi di identificazione delle comunità, guadagnando grande popolarità dopo il 2002 grazie ai lavori di Girvan e Newman. Da allora il “Karate Club” è rimasto un simbolo della network science e persino oggetto di una curiosa tradizione accademica: chi lo cita per primo in una conferenza viene ironicamente accolto nello “Zachary Karate Club Club”, ricevendo un trofeo che celebra il suo ruolo nella storia dello studio delle reti.

![[Pasted image 20251030105507.png|450]]

Dall'immagine vediamo che, nella figura a, c’è la **rete sociale dei 34 membri** del _Zachary’s Karate Club_. Ogni nodo rappresenta una persona del club e ogni collegamento una relazione di amicizia o interazione fuori dal contesto sportivo. Le **forme geometriche** (cerchi e quadrati) indicano questi due gruppi reali, mentre i **colori** rappresentano le comunità individuate da un algoritmo che ottimizza la _modularità_, una misura che valuta quanto i nodi di una comunità siano più connessi tra loro rispetto al resto della rete. Il risultato mostra che la partizione trovata dall’algoritmo coincide quasi perfettamente con la divisione reale del club: i nodi bianchi e viola appartengono a una fazione, mentre i verdi e arancioni all’altra. Nella figura b invece vediamo che lo studio venne ignorato per molti anni fino a quando iniziò ad essere considerato come caso di test.



