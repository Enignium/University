## Equazione di D'Alambert
L'equazione di D'Alambert, [[Equazioni di Maxwell#Soluzione del sistema in forma differenziale|soluzione del sistema di Maxwell]] per cui ciascuna delle componenti dal campo elettrico o a induzione magnetica è ottenibile tramite:
$$\frac{\partial^2f}{\partial x^2}=\frac{1}{v^2}\frac{\partial^2f}{\partial t^\text{}}$$
Facendo l'ipotesi semplificativa che ciascuna componente $x,y,z$ dei campi $\vec{E}$ ed $\vec{B}$ che rappresentiamo genericamente con $f$ dipenda solo da $x$ e t, per cui si propagano solo in una direzione.

Si afferma che per essere un equazione delle onde la soluzione di quest'equazione sia una combinazione lineare di due funzioni per cui:
$$f(x,t)=f_{1}(x+vt)+f_{2}(x-vt)$$
La funzione $f_{2}$ rappresenta la soluzione progressiva, in quanto questa funzione evolve traslandosi nel senso positivo dell'asse $x$

La funzione $f_{1}$ rappresenta la soluzione retrograda, in quanto questa funzione evolve traslandosi nel senso positivo negativo dell'asse $x$

**Queste funzioni rappresentano l'evoluzione del campo che si propaga nello spazio viaggiando a velocità $v$** 

Immaginando come ipotesi semplificativa che $f_{1}$ sia uguale a $0$ con il metodo delle funzioni di prova si ricava:
$$f(x,t)=f_{2}(x-vt)=f_{0}sen\left[ \frac{2\pi}{\lambda}(x-vt) \right]$$
Con $\lambda$ lunghezza d'onda, definendo numero d'onda $k=\frac{2\pi}{\lambda}$ sarà:
$$f(x,t)=f_{0}sen[kx-kvt]$$
Si osserva perciò che questa è una funzione sinusoidale con frequenza $w=kv=\frac{2\pi}{T}$, questa è una soluzione armonica dell'equazione di D'Alambert:
$$f(x,t)=f_{0}sen(kx-wt)$$
Fissato il tempo $t=0$ la funzione diverrà $f(x,0)=f_{0}sen(kx)$, applicando il concetto di periodicità:
$$f_{0}sen(k(x+T_{x}))=f_{0}sen(kx)$$
Quest'identità è possibile solo se $kT_{x}=2\pi$, perciò $T_{x}=\lambda=\frac{2\pi}{k}$

Perciò la periodicità spaziale di questa funzione è la lunghezza d'onda

Fissato  $x=0$ si ottiene che $f(0,t)=-f_{0}sen(wt)$, funzione di periodo $T=\frac{2\pi}{w}$

**Si osserva dunque che la soluzione armonica dell'equazione di D'Alambert ha sia una periodicità spaziale che temporale**
## Onde piane
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 3 2 1 1 1]]

Considerata la seconda [[Equazioni di Maxwell|equazione di Maxwell]] in forma differenziale per cui $\nabla \times \vec{E}=-\frac{\partial \vec{B}}{\partial t}$ , sapendo che la soluzione armonica all'equazione di D'Alambert è del tipo $f_{0}\cos[kx\pm wt]$ e considerata l'ipotesi semplificativa per cui le componenti di $\vec{E}$ e $\vec{B}$ dipendono solo da $x$ oltre che da $t$, essendo $\nabla \times \vec{E}$ calcolato come:
$$\nabla \times \vec{E}=\begin{vmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
E_x & E_y & E_z
\end{vmatrix}$$
Ma dipendendo per ipotesi $Ex$ , $Ey$ ed $Ez$ solo da $x$ sarà $\frac{\partial Ey}{\partial y}=0$ e $\frac{\partial Ez}{\partial z}=0$ per cui lo sviluppo di questo rotore sarà solo:
$$\nabla \times \vec{E}=\vec{j}\frac{\partial E_{z}}{\partial x}+\vec{k}\frac{\partial Ey}{\partial x}$$
Per cui sostituendo nell'espressione dell'equazione di Maxwell:
$$\vec{j}\frac{\partial E_{z}}{\partial x}+\vec{k}\frac{\partial Ey}{\partial x}=-\frac{\partial[\vec{i}B_x+\vec{j}B_y+\vec{k}B_{z}]}{\partial t}$$
Da cui si trae la conclusione che $$\frac{\partial B_{x}}{\partial t}=0$$**Per cui se l'onda si propaga solo lungo la direzione $x$ la componente $x$ del campo a induzione magnetica sarà costante.**

Analogamente seguendo gli stessi passaggi  nella quarta equazione di Maxwell si ricava che nelle stesse circostanze: 
 $$\frac{\partial E_{x}}{\partial t}=0$$

**Perciò se il campo elettromagnetico dipende solo da $x$ il campo elettrico e magnetico saranno posti su un piano perpendicolare alla direzione $x$, la componente di questi campi lungo la direzione di propagazione sarà costante e questa costante si potrà considerare uguale a $0$ in quanto stiamo valutando fenomeni dipendenti dal tempo.**

Si definisce fase dell'onda l'argomento $kx-wt$ di $f(x,t)$
 
**Si definisce fronte d'onda il luogo dei punti dello spazio individuato individuato a $t$ fissato in cui la fase è costante, dalla soluzione armonica $f(x,t)=f_{0}\cos[kx-wt]$, immaginando di fissare $t=0$ ad esempio il fronte sarebbe il luogo dei punti dello spazio di ascissa $x$, proprio il piano perpendicolare alla direzione di propagazione del campo elettromagnetico.**

**Questa tipologia di soluzione prende il nome di onda piana**

### Perpendicolarità campo elettrico e a induzione magnetica

Usando l'ipotesi semplificativa per cui il campo elettrico ha componenti non nulle solo lungo l'asse $y$ per cui $\vec{E}=\vec{j}E_{y}(x,t)$ e che quindi $\vec{E}=\vec{j}E_{0}\cos(kx-wt)$, segue che dall'equazione di Maxwell per cui:
$\nabla \times \vec{E}=-\frac{\partial \vec{B}}{\partial t}$ proiettando l'equazione vettoriale sugli assi le componenti non lungo l'asse $z$ di $\vec{B}$ saranno uguagliate a $0$ e resterà:
$$\frac{\partial Ey}{\partial x}=-\frac{\partial B_{z}}{\partial t}$$
Per cui sarà $\vec{B}=\vec{k}B_{z}(x,t)$

**Si osserva dunque che il campo elettrico e magnetico contenuti sul fronte d'onda sono perpendicolari**

Sapendo che $B_{z}=B_{0}sen(kx-wt)$ e che $E_{y}=E_{0}sen(kx-wt)$ sostituendo in $\frac{\partial Ey}{\partial x}=-\frac{\partial B_{z}}{\partial t}$ sarà:

$$E_{0}k\cos(kx-wt)=wB\cos(kx-wt)$$
Ovvero:
$$E_{0}k=wB$$
Per cui il rapporto tra $E_{0}$ intensità del campo elettrico e $B_{0}$ intensità del campo a induzione magnetica è uguale a $$\frac{E_{0}}{B_{0}}=\frac{w}{k}$$
In termini di campo magnetico sapendo che $\mu H=B$ sarà:
$$\frac{E_{0}}{H_{0}}=\mu\frac{w}{k}=\mu v=\frac{\mu}{\sqrt{ \epsilon \mu }}=\sqrt{ \frac{\mu}{\epsilon}}$$
Che nel caso specifico del vuoto o dell'aria $\sqrt{ \frac{\mu_{0}}{\epsilon_{0}}}=377\Omega$

## Ipotesi parametri concentrati

**Se un circuito è talmente piccolo tale da far si che le sue dimensioni massime siano trascurabili rispetto alla minima lunghezza d'onda, ci si trova in condizioni tali da non rendersi conto della periodicità spaziale del campo elettromagnetico, in modo tale da non rendersi conto della dipendenza spaziale del campo generato dalla presenza di generatori dipendenti dal tempo**

