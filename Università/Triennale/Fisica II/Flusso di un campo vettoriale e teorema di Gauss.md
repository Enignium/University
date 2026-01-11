## Flusso di un campo vettoriale 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1]]

Considerato un campo vettoriale $\vec{v}(x,y,z)$ ed una superficie $S$ si definisce flusso elementare di $\vec{v}$ attraverso $S$ considerato $dS$ un infinitesimo di superficie orientato dalla normale $\vec{n}$ attraverso cui passa una sola linea di campo: 
$$d\phi(\vec{v})=\vec{v}\cdot \vec{n}dS=v\cos \theta dS$$
	*Il segno di questo flusso elementare dipenderà dall'angolo compreso tra $\vec{v}(x,y,z)$ nel punto in cui si trova $ds$ ed $\vec{n}$* 

Il flusso complessivo sarà:
$$\phi(\vec{v})=\int_{S}d\phi(\vec{v})=\int_{S}\vec{v}\cdot \vec{n}dS$$
### Caso campo uniforme superficie planare
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1]]

Nel caso in cui si volesse determinare il flusso di un campo vettoriale uniforme attraverso una superficie orientata planare allora essendo in questo caso l'angolo compreso tra la normale alla superficie $\vec{n}$ ed il campo in ciascun punto del piano sarà:
$$\phi_{s}(\vec{v})=\int_{S}\vec{v}\cdot \vec{n}dS=\int_{S}vdS=v\cos \theta\int_{S}dS=S \cdot v\cos \theta $$

### Caso superficie chiusa
Considerata una superficie chiusa $S$ che racchiude al suo interno un volume $\tau$ il flusso sarà:
$$\phi_{S}(\vec{v})=\oint_{S}\vec{v}\cdot \vec{n}ds$$
Il segno del flusso in queste condizioni descrive:

- Nel caso di flusso positivo un campo con più linee di campo uscenti che entranti rispetto alla superficie implica la presenza di una sorgente interna al volume delimitato dalla superficie chiusa $S$
- Nel caso di flusso negativo un campo con più linee entranti che uscenti rispetto alla superficie che implica la presenza di un pozzo interno al volume delimitato  dalla superficie chiusa $S$
- Il flusso nullo implica che escono tante linee di campo quante ne entrano

## Teorema di Gauss per l'elettrostatica
Per il teorema di Gauss il flusso del [[Campo elettrostatico coulombiano|campo elettrostatico]] attraverso una superficie chiusa orientata $S$ è uguale al rapporto tra la carica netta interna alla superficie e la costante dielettrica del mezzo:
$$\phi_{S}(\vec{E}_{Q})=\oint_{S}\vec{E}\cdot \vec{n}dS=\frac{Q_{int.sup}}{\epsilon_{0}}$$
Il campo elettrostatico coulombiano ha linee di campo radiali rispetto alla sorgente ed è costante su tutte le superfici sferiche concentriche per cui con $S$  superficie sferica di raggio $R$ con il campo che vale in ogni punto della superficie $E(R)=\frac{Q}{4\pi \epsilon_{0}R^2}=cost$ sempre parallelo alla normale $n$ alla superficie:
$$\phi_{S}(\vec{E})=\oint_{S} \vec{E}\cdot \vec{n}dS=\oint_{S}EdS=E\oint_{S}dS=E\cdot S=\frac{Q}{4\pi \epsilon_{0}R^2}4\pi R^2=\frac{Q}{\epsilon_{0}}$$
**Questo teorema evidenzia come la carica sia sorgente del campo elettrostatico**
### Teorema di Gauss in forma generale
Per il Teorema di Gauss il flusso di un campo vettoriale calcolato attraverso una superficie chiusa $S$ equivale all'integrale esteso al volume $\tau$ contenuto dalla superficie chiusa $S$ della [[Operatori differenziali#Divergenza di un campo vettoriale|divergenza]] del campo.

$$\phi_{S_{chiusa}}(\vec{v})=\oint_{S}\vec{v}\cdot nds=\int_{\tau}\nabla \cdot \vec{v}d\tau$$
Dalla quale sapendo che $\phi_{S}(\vec{E})= \frac{Q_{int\tau}}{\epsilon_{0}}$ e che $Q_{int_{\tau}}=\int_{\tau}\rho d\tau$:
$$\phi_{S_{chiusa}}(\vec{E})=\int_{\tau}\nabla \cdot \vec{E}d\tau=\frac{Q_{int\tau}}{\epsilon_{0}}=\frac{1}{\epsilon_{0}}\int_{\tau}\rho d\tau$$
Per cui otteniamo:
$$\nabla \cdot \vec{E}=\frac{\rho}{\epsilon_{0}}$$
La prima equazione di Maxwell in forma differenziale.

## Teorema di Stokes

Per il teorema di Stokes l'integrale di linea di un campo vettoriale lungo il percorso chiuso $l$ e uguale al flusso del rotore dello stresso calcolato attraverso qualsiasi superficie aperta che abbia $l$ come bordo per cui:
$$\oint_{l}=\vec{v}\cdot dl=\phi(\nabla \times \vec{v})=\int (\nabla \times \vec{v})\cdot \vec{n}ds$$
con $\vec{n}$ orientato in modo tale da vedere il percorso lungo $l$ in senso antiorario

### Teorema di Stokes per l'elettrostatica
Applicando il teorema di Stokes al campo elettrostatico si ottiene:
$$\oint_{lA}^A\vec{E}\cdot d\vec{l}=0=\int_{S}(\nabla \times \vec{E})\cdot \vec{n}ds$$
Per cui
$$\nabla \times \vec{E}=0$$
Il campo elettrostatico e' un campo irrotazionale 