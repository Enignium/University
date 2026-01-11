## Condensatori ideali
Considerati due conduttori in equilibrio elettrostatico ed il [[Conduttori in equilibrio elettrostatico#Legame tra potenziale superficiale e carica del conduttore|legame tra potenziale superficiale e carica del conduttore]] nei conduttori:
$$\begin{array}
qq_{1}=c_{1,1}V_{1}+c_{1,2}V_{2}\\ \\
q_{2}=c_{2,1}V_{1}+c_{2,2}V_{2}
\end{array}$$**I due conduttori costituiscono un condensatore ideale se le cariche $q_{1}$ e $q_{2}$ sono uguali ed opposte** per cui se:
$$\begin{array}
qq_{1}=q\\
q_{2}=-q \\
V_{1}>0 \\
V_{2}<0
\end{array}$$
Per essere vera questa condizione dovrà essere:
$$\begin{array}
aC_{1,1}=C_{2,2}=C\\ \\
C_{2,1}=C_{1,2}=-C_{1,1}=-C
\end{array}$$
In quanto:
$$\begin{array}
qq_{1}=CV_{1}-CV_{2}=C(V_{1}-V_{2})=q\\
q_{2}=-CV_{1}+CV_{2}=-C(V_{1}-V_{2})=-q \\
\end{array}$$

**Un conduttore ideale è un bipolo costituito da due conduttori ideali (armature del condensatore) separati da un dielettrico in induzione completa** 

La capacità del condensatore è il rapporto tra la carica sull'armatura positiva e la differenza di potenziale tra le due armature:
$$C=\frac{Q}{V_{1}-V_{2}}$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1|150]]
## Condensatori a facce piane e parallele
Considerati due conduttori a facce piane e parallele di sezione $S$ posti ad una distanza tale da essere molto minore rispetto alla diagonale per minimizzare gli effetti di bordo per cui nei pressi dei bordi del condensatore delle linee di campo sfuggono dalle lamine.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 1|150]]
Essendo il caso minimizzati gli effetti di bordo equiparabile a quello del [[Singolo e doppio strato uniformemente carico#Doppio strato uniforme|doppio strato uniforme]] il campo nella regione , essendo $\vec{E}$ costante:
$$V=\int_{a_{1}}^{a_{2}}\vec{E}\cdot \vec{d}lvec=E\int_{a_{1}}^{a_{2}}dl=Ed$$
Per cui tra le due armature sarà:
$$E=\frac{\sigma}{\epsilon_{0}}=\frac{V}{d}$$
E tra le due armature sarà presente una differenza di potenziale:
$$V_{1}-V_{2}=V=\frac{\sigma d}{\epsilon_{0}}$$
Esprimendo $q=\sigma S$:
$$C=\frac{q}{V_{1}-V_{2}}=\frac{\sigma S}{\frac{\sigma d}{\epsilon_{0}}}=\frac{\epsilon_{0}S}{d}$$
**Per cui la capacità dipende solo dalla geometria dei del condensatore e dal mezzo in cui è immerso**
### Inserimento di un dielettrico tra le armature
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 4]]
Considerato un condensatore a facce piane e parallele con interposto tra le due armature un materiale omogeneo isotropo che in risposta al campo elettrostatico si [[Spostamento elettrico e polarizzazione|polarizza]].

All'interno del volume dell'isolante la densità di carica si compensa facendo rimanere scoperta una lamina carica negativamente  con densità $\sigma'_{-}$ affacciata all'armatura positiva ed una carica negativamente con densità  $\sigma'_{+}$affacciata all'armatura negativa effettivamente generando un campo di verso opposto a quello interno al condensatore.

Per sovrapposizione degli effetti:
$$\vec{E}=\vec{E}_{0}+\vec{E}'=\frac{\sigma-\sigma'}{\epsilon_{0}}$$
**Il modulo del campo diminuisce per effetto del campo generato dal fenomeno di polarizzazione e dal legame $E=\frac{V}{d}$ essendo invariata la distanza $d$ è chiaro che diminuisce il potenziale, avendo lasciato però invariata la carica dalla relazione $C=\frac{q}{V}$ si nota che riducendo così il potenziale si aumenta la capacità di un fattore $\epsilon_{r}$.**

Questa cosa ritrova prova nel fatto che ponendo
$$\epsilon_{r}=\frac{\sigma}{\sigma -\sigma'}$$
$$E=\frac{\sigma}{\epsilon_{0}\epsilon _{r}}$$
## Condensatore sferico
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1|200]]
Considerate due sferiche concentriche di raggio $r_{a}$ ed $r_{b}$ ,di conferire una carica $+q$ alla sfera interna ed ipotizzare che le superfici di queste due sfere formino un condensatore: 
Sulla superficie della sfera la carica si distribuisce uniformemente essendo la superficie sferica con densità superficiale di carica $\sigma_{a}=cost=\frac{q}{4\pi r_{a}^2}$. Inoltre la superficie si porta a potenziale $V_{A}$

Per ipotesi di induzione completa la superficie della sfera di raggio $r_{b}$ si acquisisce una carica uguale ed opposta $-q$ distribuita con densità superficiale di carica costante $\sigma_{b}=-\frac{q}{4\pi r_{b}^2}$ , la superficie viene portata inoltre a potenziale $V_{b}$.

Essendo il campo generato dalla sfera di raggio $r_{a}$ nella regione con $r_{a}<r<r_{b}$ indistinguibile dal campo coulombiano è possibile calcolare prendendo $\vec{dl}=dr\vec{u_{r}}$:
$$\int_{A}^B\vec{E}\cdot dl=\int_{A}^B\vec{E}\cdot dr\vec{u}r=\int_{r_{a}}^{r_{b}}Edr=\frac{q}{4\pi \epsilon_{0}r}\big|^{r_b}_{r_a}=q\left[ \frac{1}{4\pi \epsilon_{0}r_{A}}-\frac{1}{4\pi\epsilon_{0}r_{B}} \right]=V(A)-V(B)$$

Sostituendo in $C=\frac{q}{v_{a}-v_{b}}$
$$C=\frac{1}{ \frac{1}{4\pi\epsilon_{0}r_{a}}- \frac{1}{4\pi\epsilon_{0}r_{b}}}=\frac{r_{a}r_{b}4\pi \epsilon_{0}}{(r_{a}-r_{b})}$$


## Condensatore cilindrico 
Considerati due cilindri conduttivi coassiali di altezza $l$ di raggio $r_{a}$ e $r_{b}$  e di conferire una carica $+q$ a quel cilindro  ed ipotizzare che le superfici laterali di questi due cilindri formino un condensatore: 
Sulla superficie del cilindro la carica si distribuisce uniformemente essendo la superficie cilindrica con densità superficiale di carica $\sigma_{a}=cost=\frac{q}{2\pi r_{a}l}$. Inoltre la superficie si porta a potenziale $V_{A}$

Per ipotesi di condensatore la superficie della sfera di raggio $r_{b}$ si acquisisce una carica uguale ed opposta $-q$ distribuita con densità superficiale di carica costante $\sigma_{b}=-\frac{q}{2\pi r_{b}l}$ , la superficie viene portata inoltre a potenziale $V_{b}$.

Il campo generato dalla [[Campi generati da distribuzioni di cariche simmetriche#Campi generati da distribuzioni a simmetria cilindrica|distribuzione di carica cilindrica]] con $r_{a}<r<r_{b}$ è: $\vec{E}=\frac{q}{2\pi rl\epsilon_{0}}\vec{u}_{n}$ e esprimendo $d\vec{l}=dr\vec{u}_{r}$ spostandosi solo radialmente:
$$\int_{A}^B\vec{E}\cdot dl=\int_{A}^B\vec{E}\cdot dr\vec{u}r=\int_{r_{a}}^{r_{b}}Edr=\frac{q}{2\pi l\epsilon_{0}}\ln(r)\big|_{r_{a}}^{r_{b}}=\frac{q}{2\pi l\epsilon_{0}}\ln\left( \frac{r_{b}}{r_{a}} \right)=V(A)-V(B)$$

Sostituendo in $C=\frac{q}{v_{a}-v_{b}}$
$$C=\frac{2\pi l\epsilon_{0}}{\ln\left(\frac{r_{b}}{r_{a}} \right)}$$
## Carica di un condensatore
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2|150]]

Per caricare un condensatore bisogna compiere lavoro spostando una carica negativa dalla armatura che si caricherà positivamente e spostandola sull'altra armatura che si caricherà negativamente. Questo genererà un campo contro il quale bisogna compiere lavoro per continuare a caricare il condensatore in quanto le cariche negative per effetto del campo si opporranno allo spostamento verso l'armatura negativa. 


Ricordando che il potenziale elettrostatico è lavoro per unità di carica è possibile calcolar il lavoro elementare svolto contro il campo per caricare il condensatore come:
$$\delta L=V\delta q$$
Per cui il lavoro complessivo esprimendo $V=\frac{q}{C}$ sarà:
$$L=\int_{0}^qV\delta q=\frac{1}{C}\int_{0}^qqdq=\frac{1}{2C}q^2=\frac{1}{2}CV^2$$
**Per cui questo lavoro viene immagazzinato nel condensatore carico sotto forma di energia che dipende dal quadrato del potenziale elettrostatico del condensatore**

## Connessione serie e parallelo condensatori 
### Connessione serie
La connessione serie è caratterizzata dal fatto per cui attraverso gli elementi connessi passa la stessa corrente.

Quando si carica un armatura del condensatore positivamente le cariche negative del conduttore al quale è attaccata la seconda armatura verranno attratte caricando negativamente l'armatura ripetendo questo processo in cascata 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1|300]]

$$\begin{array}
VVc_{1}=V_{A}-V_{H}=V_{AH} \\
Vc_{2}=V_{H}-V_{B}=V_{HB} \\
V_{C_{1}}+V_{C_{2}}=V_{AB}
\end{array}$$
È possibile sostituire i condensatori in serie con un condensatore equivalente di capacità:
$$C_{eq}=\frac{q}{V_{{AB}}}=\frac{q}{V_{C_{1}}+V_{C_{2}}}$$
Sapendo che $V_{C_{1}}=\frac{q}{c_{1}}$ e $V_{C_{2}}=\frac{q}{C_{2}}$ si ottiene:
$$C_{eq}=\frac{q}{\frac{q}{C_{1}}+\frac{q}{C_{2}}}=\frac{1}{\frac{1}{C_{1}}+\frac{1}{C_{2}}}$$

**Per cui la capacità equivalente è uguale al reciproco della somma dei reciprochi delle capacità dei condensatori che costituiscono la serie**
### Connessione parallelo 
La connessione parallelo è caratterizzata dal fatto per cui attraverso gli elementi connessi sono portati allo stesso potenziale

in una connessione parallelo la carica $q$ si scompone in $q_{1}+q_{2}=q$ per disporsi sulle armature di ciascuna armatura nella connessione parallelo
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1|300]]
$$\begin{array}
aC_{1}=\frac{q_{1}}{V_{AB}} \\
C_{2}=\frac{q_{2}}{V_{AB}}
\end{array}$$

È possibile sostituire la connessione parallelo con un condensatore equivalente che abbia capacità:
$$C_{eq}=\frac{q_{1}+q_{2}}{V_{AB}}=\frac{C_{1}V_{AB}+C_{2}V_{AB}}{V_{AB}}=C_{1}+C_{2}$$

**Per cui la capacità equivalente è uguale alla  somma delle capacità dei condensatori che costituiscono il parallelo**