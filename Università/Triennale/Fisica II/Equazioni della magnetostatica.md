## Leggi della magnetostatica

### Prima legge della magnetostatica

#### Forma integrale

Essendo le linee di campo del campo di induzione magnetica chiuse sarà sempre:
$$\phi_{S_{chiusa}}(\vec{B})=0$$
Da cui si ricava la prima legge della magnetostatica in forma integrale:
$$\phi_{S_{chiusa}}(\vec{B})=\oint_{S}\vec{B}\cdot \vec{n}ds=0$$
#### Forma differenziale

Attraverso il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Gauss in forma generale|teorema di Gauss]]:
$$0=\oint_{S}\vec{B}\cdot \vec{n}ds=\int_{\tau}\nabla \vec{B}d\tau=0$$
Da cui
$$\nabla \vec{B}=0$$
Da cui il campo a induzione magnetica è un campo solenoidale.

Data l'identità vettoriale per cui $\nabla[\nabla \times(\vec{v})]=0$
Sarà possibile esprimere $\vec{B}=\nabla \times \vec{A}(r)$:
Per cui:
$$\nabla[\nabla \times \vec{A}]=0$$
C**on $\vec{A}$ funzione vettoriale della posizione detta potenziale vettore associato univocamente al campo a induzione magnetica statico.**

### Seconda legge della magnetostatica
#### Forma integrale

Considerato un filo di lunghezza illimitata attraversato da una corrente $i$ per la legge di Bjort-Savart il campo generato da questa sorgente avrà linee di campo poste sul piano perpendicolare al filo che formano circonferenze concentriche centrate nel filo. 
Il campo in ciascun punto avrà modulo:
$$B=\frac{\mu_{0}i}{2\pi d}$$
Facendo la circuitazione in senso antiorario del campo attraverso una circonferenza essendo le linee di campo sempre tangenziali al campo sarà $\vec{B}\cdot d\vec{l}=Bdl$ per cui:
$$\oint_{l_{in senso antiorario}}\vec{B}\cdot d\vec{l}=\oint_{l}\frac{\mu_{0}i}{2\pi r}dl=\frac{\mu_{0}i}{2\pi r}\oint_{l}dl=\frac{\mu_{0}i}{2\pi r}2\pi r=\mu_{0}i$$
**Questo risultato che può essere generalizzato a qualsiasi linea chiusa da la seconda legge della magnetostatica per cui la circuitazione del campo di induzione magnetica è uguale a $\mu_{0}$ volte la  corrente concatenata dal percorso chiuso.**

Dovessero essere presenti più fili attraversati da corrente concatenati dal percorso la corrente $i$ nella circuitazione sarebbe la somma delle correnti che attraversano i fili 

*Si prendono positive le correnti che scorrono in una direzione che vede il percorso in senso antiorario, negative le altre*

#### Forma differenziale 

Attraverso il [[Flusso di un campo vettoriale e teorema di Gauss#Teorema di Stokes|teorema di Stokes]]:
$$\oint_{l}\vec{B}\cdot d\vec{l}=\phi_{S_{cheabbialcomebordo}}=\int_{S_{cheabbialcomebordo}}(\nabla \times B)\cdot \vec{n}ds=\mu_{0}i$$
Ricordando che è possibile esprimere:
$$i=\phi_{S_{conduttore}}(\vec{J})=\int_{S_{conduttore}}\vec{J}\cdot \vec{n}ds$$
Questo risultato non varia se estendo quest'integrale a tutta la superficie $S$ delimitata dal percorso $l$ che comprende la sezione del conduttore attraverso cui si calcola il flusso di $\vec{J}$  per cui si potrà esprimere:
$$\int_{S_{cheabbialcomebordo}}(\nabla \times B)\cdot \vec{n}ds=\int_{S_{cheabbialcomebordo}}\mu_{0}\vec{J}\cdot \vec{n}ds$$
Da cui
$$\nabla \times B=\mu_{0}\vec{J}$$
