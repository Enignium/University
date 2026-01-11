
## Dipolo elettrico
 Considerato un sistema composto da due cariche uguali ma opposte di segno poste ad una distanza  $d$ fissa tra di loro viene associato a questo sistema dipolo elettrico al grandezza momento del dipolo elettrico:
 $$\vec{P}=q\vec{d}$$
 Considerata una qualsiasi superficie chiusa che contiene il dipolo il [[Flusso di un campo vettoriale e teorema di Gauss|flusso]] attraverso questa sarà sempre uguale a 0 in quanto usciranno tante linee di campo quante ne entreranno.
 ![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1|350]]
### Campo generato da un dipolo elettrico
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1]]
Il campo generato da un dipolo elettrico è la sovrapposizione dei campi generati dalle due cariche che lo costituiscono:
$$\vec{E}(P)=\vec{E}_{+q}(P)+\vec{E}_{-q}(P)$$ Si osserva che le componenti lungo l'asse $x$ si cancellano a vicenda per cui il campo risultante sarà la somma delle proiezioni sull'asse $y$ dei campi generati dalle singole cariche:
$$\vec{E}(P)=2E_{y}\vec{j}$$
Con:
- $E_{y}=\frac{q}{4\pi\epsilon_{0}r^2}sen\beta$
-  $rsen\beta=\frac{d}{2}$ per cui $sen\beta=\frac{d}{2r}$
- $r=\sqrt{\left( \frac{d}{2} \right)^2+x^2 }$

Per cui:
$$\vec{E}(P)=\frac{2q}{4\pi \epsilon_{0}r^2}sen\beta=\frac{\cancel{2}q}{4\pi\epsilon_{0}r^2} \frac{d}{\cancel2r}=\frac{P}{4\pi\epsilon_{0}r^3}=\frac{P}{4\pi\epsilon_{0}\left(\sqrt{\left( \frac{d}{2} \right)^2+x^2 }\right)^3}$$
**Da cui se $x\gg d$ si può trascurare $\frac{d}{2}$ e si nota che il campo è proporzionale a $\frac{1}{x^3}$** 

### Potenziale elettrostatico del dipolo elettrico 
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1]]
Considerato un punto generico $P$ tale che la distanza $r$ tra il punto ed il centro del dipolo ed il punto $P$ sia $r\gg d$. Con questa ipotesi le distanze $r_{-}$ ed $r_{+}$ saranno circa uguali ad $r$

Il potenziale calcolato nel punto $P$ per sovrapposizione sarà:
$$V(P)=V_{+}(P)+V_{-}(P)=-\frac{q}{4\pi\epsilon_{0}r_{-}}+\frac{q}{4\pi \epsilon_{0}r_{+}}=\frac{q[r_{-}-r_+]}{4\pi\epsilon_{0}r_{r}r_{+}}$$
Ed essendo $r_{-}\approx r_{+}\approx r$ e $r_{-}-r_{+}\approx d\cos \theta$
$$\frac{q[r_{-}-r_+]}{4\pi\epsilon_{0}r_{r}r_{+}}=\frac{{P\cos \theta}}{4\pi\epsilon_{0}r^2}$$
**Si nota che il potenziale coulombiano associato ad un dipolo decresce proporzionalmente ad ${\frac{1}{r^2}}$*

## Dipolo immerso in un campo costante

Considerato un dipolo immerso in un campo elettrostatico costante $E_{Q}=cost$
Il dipolo sarà soggetto ad una coppia di forze uguali in modulo ed opposte in verso tali per cui il momento torcente del campo sperimentato dal dipolo sia indipendente dal polo e calcolandolo scegliendo come polo la posizione di una delle due cariche:
$$\vec{T}=\vec{P}\times \vec{E}$$
Con modulo $PEsen\theta$
Il dipolo per effetto di questa coppia di forze si disporrà parallelamente alle linee di campo.
Per far ruotare il dipolo in direzione opposta bisogna applicare una coppia di forze opposte a quelle sperimentate dal dipolo per effetto del campo in modo tale da ottenere un momento torcente esattamente opposto:
$$\vec{T}=-\vec{P}\times \vec{E}$$
Integrando il modulo del momento torcente che applico per compensare la rotazione dovuta alla presenza del campo tra $\theta_{i}$ e $\theta_{f}$ angoli che il dipolo forma con la direzione delle linee di campo
Considerando un $\theta_{i}$ generico e $\theta_{f}=\frac{\pi}{2}$:
$$\int_{\theta_{i}}^{\pi/2}-PEsen\theta d\theta=PE\cancel{\cos \frac{\pi}{2}}-PE\cos \theta_{i}$$
**Questa quantità che è uguale a $-PE\cos \theta_{i}=-\vec{P}\cdot \vec{E}=U$ e ci fornisce una misura dell'energia potenziale immagazzinata in un dipolo fisso immesso in campo elettrostatico uniforme**