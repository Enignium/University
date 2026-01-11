# Dipolo magnetico 

Considerata una barretta di materiale magnetico è possibile tramite una carica di prova $q$ in movimento a velocità $\vec{v}$ mappare le linee di campo del campo di induzione magnetica statico, si osserva che le linee di campo sono linee chiuse uscenti dal polo $N$ del materiale ed entranti dal polo $S$ 
Spezzando la barretta magnetica si osserva che il comportamento persiste ed in ciascuna barretta ottenuta si formerà un polo $N$ ed un polo $S$ con linee di campo aventi lo stesso comportamento.

**Si osserva che considerando una spira circolare conduttiva attraversata da una corrente continua $i$ che questa diventa sorgente di un campo di induzione magnetico $\vec{B}$ con linee di campo aventi la stessa forma del campo generato da una barretta di materiale magnetico.** 
	*Le linee saranno uscenti dal verso che vede la corrente scorrere in senso antiorario*

Si può associare a questa spira di forma circolare la grandezza momento di dipolo magnetico con S superficie delimitata dalla spira ed $\vec{n}$ normale a questa superficie tale da vedere la corrente scorrere in senso antiorario:
$$\vec{\mu}_{m}=iS\vec{n}$$
Unità di misura $\mu_{m}$ ${A}{m^2}$ 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1]]

### Spira conduttiva immersa in un campo di induzione magnetica
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1]]

Considerata una spira attraverso la quale scorre una corrente $i$ immersa in un campo di induzione magnetica esterno $\vec{B}=B\vec{i}$ uniforme, per la seconda legge di Laplace un elemento infinitesimo subirà una forza pari a  $d\vec{F}_{l}=id\vec{l}\times \vec{B}$


Valutando la forza sperimentata dal segmento $AC$ del conduttore:
$$\vec{F}_{AC}=i\int_{A}^Cd\vec{l}\times \vec{B}$$
In questo percorso $d\vec{l}\times \vec{B}=-dyB\vec{k}$ per cui:
$$\vec{F}_{AC}=i\int_{A}^Cd\vec{l}\times \vec{B}=-\vec{k}Bi\int dy=-\vec{k}Bil_{AC}$$
Lungo il percorso $CD$ e $SA$ essendo nullo il prodotto vettoriale $d\vec{l}\times \vec{B}$ sarà nulla la forza sperimentata da questi segmenti del conduttore.

Per quanto riguarda il segmento $DS$ sarà $d\vec{l}\times \vec{B}=dyB\vec{k}$ per cui:
$$\vec{F}_{DS}=i\int_{A}^Cd\vec{l}\times \vec{B}=-\vec{k}Bi\int dy=\vec{k}Bil_{DS}$$
**Per cui sui lati di questa spira è applicata una coppia di forze che avrà l'effetto di porre la spira in rotazione**

Essendo il momento di un sistema sul quale risultante è nullo indipendente dal polo, per cui scegliendo come polo il punto $S$:
$$\vec{T}=SA\times -\vec{k}Bil_{AC}$$
Il cui modulo sarà chiamando $d$ la distanza tra $S$ ed $A$:
$$T=dl_{AC}Bi=SBi$$
**Per cui l'intensità del momento della coppia di forze applicata alla spira dipende dalla sezione della spira dalla corrente e dal modulo del campo** 

$$\vec{T}=SBi\vec{j}$$
Se questo è il momento torcente della spira con un singolo avvolgimento, fossero fatti $n$ avvolgimenti per ottenere il momento complessivo basterebbe moltiplicare per $n$.


Per analogia con il [[Dipolo elettrico]]  essendo questa spira equiparabile ad un dipolo magnetico immerso in un campo di induzione magnetica statica, ed essendo per il dipolo elettrico $\vec{T}=\vec{P}\times \vec{E}$ per il dipolo magnetico sarà:
$$\vec{T}=\vec{\mu}_{m}\times \vec{B}$$
Se tenuta ferma la spira si caricherà di un energia potenziale in analogia al caso elettrico pari a:
$$U=-\vec{\mu}_{m}\cdot \vec{B}$$

### Campo generato dalla spira circolare in un punto dell'asse della spira
![[Università/Fisica II/IMG_RESOURCES/Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1]]
Considerata una spira conduttiva attraverso la quale passa una corrente $i$ posta su un piano perpendicolare al piano del foglio, si vuole considerare il campo di induzione magnetica generato  dalla spira in un punto $P$ dell'asse del foglio. 

Il campo generato da ciascun tratto della spira sarà per la prima legge di Laplace:
$$d\vec{B}(P)=\frac{\mu_{0}}{4\pi} i \frac{d\vec{l}\times\vec{u_{r}}}{r^2}$$
In ciascun tratto della spira in questa espressione varierà solo $d\vec{l}\times \vec{u}_{r}$. Considerati i percorsi infinitesimi $d\vec{l}$ della corrente nei punti della spira che intersecano il piano del foglio, questi saranno sorgenti dei campi infinitesimi $d\vec{B}_{1}$ e $d\vec{B}_{2}$.

Essendo i vettori $d\vec{l}$ ed $\vec{u}_r$ perpendicolari il modulo prodotto $|d\vec{l}\times \vec{u}_{r}|=dl$
 
**Si osserva così che  ai fini del calcolo del campo complessivo per ciascuna coppia di percorsi $d\vec{l}$ simmetrici rispetto all'asse della spira i campi generati si annulleranno a vicenda le componente sull'asse $y$ e sommeranno le componenti sull'asse $x$**

Per cui nel per ogni $d\vec{B}$  ai fini del calcolo dell'intensità bisognerà tenere in conto solo le componenti sull'asse $x$: $dBsen\alpha$,
notando che $sen\alpha=\cos \theta$ sarà possibile esprimere $dB=\frac{\mu_{0}}{4\pi r^2} idl\cos \theta$, per cui il campo complessivo sarà:
$$B=\int\frac{\mu_{0}}{4\pi r^2} idl\cos \theta=dB=\frac{\mu_{0}}{4\pi r^2} i\cos\theta \int dl=\frac{\mu_{0}}{4\pi r^2} i\cos\theta 2\pi R$$
Osserviamo che $r\cos \theta=R$ per cui esprimendo $\cos \theta=\frac{R}{r}$ sarà:
$$B=\frac{\mu_{0}}{4\pi r^3} i2\pi R^2$$
Inoltre per il teorema di Pitagora $r=\sqrt{x^2+R^2 }$ e $\pi R^2$ si osserva essere la sezione $S$ della spira per cui:
$$B=\frac{\mu_{0}}{2\pi(\sqrt{x^2+R^2 })^3} iS$$
Esprimendo vettorialmente questo campo, osservando che questo ha componenti solo lungo l'asse x sarà necessario moltiplicarne l'intensità per il versore $\vec{i}$, osservando che $\mu_{m}=iS\vec{i}$ sarà considerato $x\gg R$ :
$$\vec{B}(x)=\frac{\mu_{0}\vec{\mu}_{m}}{2\pi x^3}$$
**Per cui il campo di induzione magnetica generato da una spira circolare in un punto dell'asse della spira alla distanza $x$ dal centro della spira molto maggiore rispetto al raggio è proporzionale a $\frac{1}{x^3}$ ed al momento di dipolo magnetico $\mu_{m}$**