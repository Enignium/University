Consideriamo i vettori $\vec{F}_{A},\vec{F}_{B},\vec{F}_{C}\vec{F}_{D}$ applicati rispettivamente nei punti $A,B,C,D$
Si dice sistema di vettori applicati l'insieme di questi vettori.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1]]

Il risultante di un  sistema di vettori sarà dato dalla somma dei vettori che compongono il sistema, in questo caso:
$$\vec{R}=\vec{F}_{A}+\vec{F}_{B}+\vec{F}_{C}+\vec{F}_{D}$$
Il momento di un sistema sarà dato dalla somma dei [[Momento di un vettore|momenti]] rispetto ad un polo $O$ dei singoli vettori che compongo il sistema, in questo caso:$$M_o = \vec{OA}\times\vec{F_{A}} + \vec{OB}\times\vec{F_{B}} + \vec{OC}\times\vec{F_{C}}+\vec{OD}\times\vec{F_{D}}$$
**Due sistemi di vettori applicati sono equivalenti se i due hanno lo stesso risultante e lo stesso momento rispetto ad un polo $O$**
 
Considerato un sistema di $n$ vettori applicati nei punti $P_{1} \dots P_{k} \dots P_{n}$ il cui risultante $\vec{R}=0$:
$$\vec{M}_{O}=\sum_{k=1}^n  \vec{OP_{k}}\times \vec{F}_{k}$$
Si può sostituire $\vec{OP_{k}}=O\Omega+\Omega \vec{P}_{k}$ per cui
$$\vec{M}_{O}=\sum_{k=1}^n  \vec{OP_{k}}\times \vec{F}_{k}=\sum_{k=1}^n  (\vec{O\Omega}+\Omega \vec{P}_{k})\times \vec{F}_{k}=\sum_{k=1}^{n}\vec{O\Omega}\times \vec{F}_{k}+\sum_{k=1}^n \vec{\Omega P_{k}}\times \vec{F}_{k}$$
Ma considerando che $\vec{O\Omega}$ non ha indice di sommatoria e che $\sum_{k=1}^{n}\vec{F}_{k} = \vec{R}=0$ :
- $\sum_{k=1}^{n}\vec{O\Omega}\times \vec{F}_{k}=\vec{O\Omega}\times \sum_{k=1}^{n}\vec{F}_{k}=0$ 
- $\sum_{k=1}^n\vec{\Omega P_{k}}\times \vec{F}_{k}=\vec{M_{\Omega}}$
Per cui:
$$\vec{M}_{O}=\vec{M}_{\Omega}$$
**Il momento di angolare di un sistema il cui risultante sia nullo è indipendente dal polo**
## Coppia di vettori
Il più semplice sistema di vettori a risultante nullo prende il nome di coppia di vettori ed è costituito da due vettori che hanno uguale direzione e modulo ma verso opposto con rette di applicazione parallele.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1|300]]
In questo caso:
$$\vec{R}=\vec{F}_{A}-\vec{F}_{B}=0$$
E considerando il momento di questo sistema di vettori rispetto al polo fatto coincidere col punto di applicazione $A$ del vettore $\vec{F}_{A}$:
$$\vec{M_{A}}=\vec{AA}\times \vec{F}_{A}+\vec{AB}\times \vec{F}_{B}$$
Ma il vettore $\vec{AA}$ è nullo, per cui questo momento si ridurrà a $\vec{M}_{A}=\vec{AB}\times \vec{F}_{B}$ ed avrà come area l'area del parallelogramma compreso tra i vettori $\vec{AB}$ e $\vec{F}_{B}$ per cui il modulo del momento sarà uguale a:
$$M_{A}=F_{B}*AB*sen\alpha=Fb*d$$
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1]]
**Il momento di una coppia di vettori ha modulo pari al prodotto del modulo di uno dei due vettori per la distanza d del polo dalla retta di applicazione del vettore.**
**Essendo nullo il risultante del sistema di vettori, questo risultato vale per qualunque polo**

## Definizione di baricentro
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1]]
Considerato un [[Sistemi di vettori|sistema di vettori]] paralleli $\vec{F}_{k}=f(k)\vec{u}$ è possibile calcolarne il [[Momento di un vettore|momento]] rispetto al polo $O$ come:
$$\vec{M}_{O}=\sum_{k=1}^n\vec{OP_{k}}\times f(k)\vec{u}$$
In queste condizioni è possibile individuare un punto $F$ per cui il momento del sistema potrà essere calcolato come il momento del risultante dei vettori del sistema $\vec{R}$ applicato al punto $F$ rispetto allo stesso polo per cui:
$$\vec{M}_{O}=\vec{OF}\times \vec{R}$$
Facendo coincidere il polo $O$ con l'origine di una terna cartesiana ortogonale, il punto $F$ può essere individuato come:
$$\vec{r}_{F}=\sum_{k=1}^n \vec{r}_{k}\frac{f_{k}}{\sum_{k=1}^nf_{k}}$$
**Per cui il punto $F$ corrisponde alla media pesata dei punti di applicazione dei vettori che compongono il sistema con coefficienti di peso  il rapporto tra la parte scalare del singolo vettore e la somma delle parti scalari di tutti i vettori che compongono il sistema**

Se il sistema di vettori applicati è rappresentato dalle forze peso il punto $F$ prende il nome di baricentro del sistema

### Baricentro e centro di massa 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1|800]]
Considerato un sistema di vettori rappresentanti le forze peso $\vec{f}_{k}=m_{k}\vec{g}$, il baricentro sarà:
$$\vec{r}_{F}=\sum_{k=1}^n \vec{r}_{k}\frac{m_{k}g}{\sum_{k=1}^nm_{k}g}=\sum_{k=1}^n \vec{r}_{k}\frac{m_{k}}{M}=\vec{r_{cm}}$$
**Per cui in queste condizioni se la forza di gravità $g$ è costante il baricentro coincide con il [[Sistemi di particelle e Centro di massa|centro di massa]]**
