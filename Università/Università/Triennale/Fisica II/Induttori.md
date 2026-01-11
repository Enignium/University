## Flusso del campo di induzione magnetica concatenato con una linea chiusa
![[Università/Fisica II/IMG_RESOURCES/Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1|450]]
Considerata una superficie chiusa $S$ orientata attraverso la normale uscente $\vec{n}$ , calcolando il flusso del [[Campo di induzione magnetica statico]] $\vec{B}$ attraverso $S$ dalla prima [[Equazioni della magnetostatica#Prima legge della magnetostatica|prima legge della magnetostatica]] sarà $\phi_{S}(\vec{B})=\oint_{S}\vec{B}\cdot \vec{n}dS=0$, dividendo la superficie attraverso il percorso chiuso $l$ in due superfici $S_{1}$ ed $S_{2}$.

Orientato il percorso $l$ in senso antiorario bisognerà considerare in senso positivo il flusso attraverso $S_{1}$ e negativo il flusso attraverso $S_{2}$ dato l'orientamento della normale. 
Da cui:
$$\phi(\vec{B})=\oint_{S}\vec{B}\cdot \vec{n}dS=\int_{S_{1}}\vec{B}\cdot \vec{n}_{1}dS_{1}-\int_{S_{2}}\vec{B}\cdot \vec{n}_{2}dS_{2}=0$$
Dunque:
$$\int_{S_{1}}\vec{B}\cdot \vec{n}_{1}dS_{1}=\int_{S_{2}}\vec{B}\cdot \vec{n}_{2}dS_{2}$$
**Per cui il flusso del campo di induzione magnetica concatenato con una linea chiusa è uguale qualunque sia la superficie che io considero concatenata con quella linea chiusa**

## Coefficiente di autoinduzione 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1]]
Volendo calcolare il flusso concatenato con il percorso $l$ della corrente $i$ orientato in senso antiorario del campo di induzione magnetica $\vec{B}$ generato da $i$ , essendo questo uguale per qualsiasi superficie, si sceglie la superficie limitata planare delimitata dal percorso. 
Essendo per la [[Campo di induzione magnetica statico#Prima legge di Laplace|prima legge di Laplace]] $\vec{B}(P)=\frac{\mu_{0}i}{4\pi}\oint_{l} \frac{d\vec{l}\times \vec{\mu_{r}}}{r^2}$ sarà:
$$\phi_{S}(\vec{B})=\frac{\mu_{0}i}{4\pi}\int_{S}\left[\oint \frac{d\vec{l}\times \vec{\mu}_{r}}{r^2}\right]\cdot \vec{n}dS$$
**Si definisce coefficiente di autoinduzione $L$ il rapporto tra il flusso del campo $\vec{B}$ generato dalla corrente $i$ concatenato con il percorso della corrente che lo genera e la corrente $i$:**
$$L=\frac{\phi(\vec{B})}{i}=\frac{\mu_{0}}{4\pi}\int_{S}\left[\oint \frac{d\vec{l}\times \vec{\mu}_{r}}{r^2}\right]\cdot \vec{n}dS$$
Questa grandezza dipende dalla geometria del dipolo e dal mezzo nel quale è immerso.

L'unità di misura è l'Henry $H$ 

## Solenoide
Si definisce solenoide un dispositivo illimitato composto da un conduttore ideale avvolto in spire.
Il comportamento di un solenoide si può approssimare in un dispositivo la cui lunghezza degli avvolgimenti è molto maggiore rispetto al raggio della singola spira.

Si deduce la direzione del flusso qualitativamente considerando le linee di campo generate dalla spira nei punti in cui si trovano sul piano del foglio approssimando il loro comportamento a quello in cui a generare il campo sia un percorso rettilineo della corrente, questa approssimazione è valida nel momento in cui la spaziatura tra le spire è molto ridotta
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1]]
Per ciascuna spira il flusso concatenato con il percorso della spira attraverso la superficie della spira sarà $\phi_{S}=\int_{S}\vec{B}\cdot \vec{n}ds$ ma essendo $\vec{B}$ ed $\vec{n}$ paralleli il prodotto scalare farà il modulo $B$ per cui per ciascun avvolgimento sarà:
$$\phi_S(\vec{B})=B\int_{S}ds=BS$$ Da cui il flusso auto concatenato totale del campo attraverso l'intero dispositivo sarà $\phi_{S}=NBS$ con $N$ numero di avvolgimenti.

Per calcolare il modulo del campo si considera un percorso chiuso rettangolare:
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1]]
Dalla [[Equazioni della magnetostatica#Seconda legge della magnetostatica|seconda legge della magnetostatica]] la circuitazione del campo ad induzione magnetica $\oint \vec{B}\cdot d\vec{l}=\mu_{0}\sum_{k=0}^ni_{k}$ per cui:
$$\oint \vec{B}\cdot d\vec{l}=\int_{S}^P\vec{B}\cdot d\vec{l}+\cancel{ \int_{P}^R\vec{B}\cdot d\vec{l} }+\cancel{ \int_{R}^V\vec{B}\cdot d\vec{l} }+\cancel{ \int_{V}^S\vec{B}\cdot d\vec{l} }=Bd=\mu_{0}n_{conc}i$$
Da cui:
$$B=\frac{\mu_{0}n_{conc}}{d}i$$
Immaginando che la spaziatura tra le spire sia costante si definisce il numero di spire per unità di lunghezza $n=\frac{N}{l_{tot}}$ per cui:
$$B=\mu_{0}ni$$Per cui essendo questo il modulo del campo di induzione magnetica statico generato dal dispositivo il flusso auto-concatenato sarà esprimibile come:
$$\phi(B)=N\mu_{0} \frac{N}{l_{tot}}iS$$
Ed il coefficiente di autoinduzione del solenoide sarà:
$$L=\frac{\mu_{0}N^2S}{l_{tot}}$$
## Inserimento di un materiale ferromagnetico all'interno del solenoide 

Immaginando di inserire un materiale ferromagnetico all'interno del solenoide in una condizione nella quale questo è privo di magnetizzazione al momento dell'inserimento e con l'ipotesi che l'intensità di corrente in questo istante sia nulla. 

Essendo in [[Magnetizzazione e campo  magnetico#Permeabilità magnetica relativa|presenza di materia]] il campo generato dal solenoide sarà $\vec{B}=\mu_{0}\vec{H}+\mu_{0}\chi_{m}\vec{H}$ con $\chi_{m}\vec{H}=\vec{M}$. 

Si osserva che in queste condizioni essendo $H=\frac{B}{\mu_{0}}$ essendo $B=\mu_{0}ni$ il modulo campo generato dal solenoide, sarà $H=ni$.

All'istante iniziale essendo nulla l'intensità di corrente sarà nullo il campo magnetico e sarà nulla la [[Magnetizzazione e campo  magnetico|magnetizzazione]]. 

Si osserva che facendo crescere $i$ fino ad un valore $i_{max}$ $H$ e $B$ cresceranno linearmente con $i$.
I dipoli generati all'interno del mezzo per effetto della magnetizzazione raggiungeranno l'allineamento per effetto della corrente $i_{max}$, per cui aumentando ulteriormente l'intensità di corrente la magnetizzazione smetterà di crescere, rendendo il legame non più lineare.

**Diminuendo a questo punto la corrente, ai fini del calcolo del campo $\vec{B}$ resterà il contributo relativo alla magnetizzazione, per cui verrà tracciato un percorso diverso per $i$ che decresce verso $0$, per cui per annullare il campo di induzione magnetica generato dal magnete posto all'interno del solenoide sarà necessario invertire il senso della corrente.** 

Questo andamento prende il nome di ciclo di isteresi
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1]]
Da quì si osserva che la relazione di proporzionalità tra $\vec{B}=\mu \vec{H}$ vale solo in una regione di linearità.