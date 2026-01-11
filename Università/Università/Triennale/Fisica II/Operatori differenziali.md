
Considerato l'operatore $\nabla(\cdot)$ definito come: $\nabla=\left( \frac{\partial \cdot}{\partial x}, \frac{\partial \cdot}{\partial y}, \frac{\partial \cdot}{\partial z} \right)=\vec{i} \frac{\partial \cdot}{\partial x}+\vec{j}\frac{\partial \cdot}{\partial y}+\vec{k}\frac{\partial \cdot}{\partial z}$ 
## Gradiente di un campo scalare

Applicando l'operatore $\nabla$ ad un campo scalare $C(x,y,z)$ si ottiene un campo vettoriale: il gradiente del campo scalare:
$$\nabla C=\frac{\partial C}{dx}\vec{i}+\frac{\partial C}{dy}\vec{j}+\frac{\partial C}{dz}\vec{z}$$
Che da un indicazione della variazione spaziale del campo scalare.
Moltiplicando scalarmene il gradiente di un campo per un vettore spostamento infinitesimo $d\vec{l}$ si ottiene:
$$\nabla C\cdot d\vec{l}= \frac{\partial C}{\partial x}dx+\frac{\partial C}{\partial y}dy+\frac{\partial C}{\partial z}dz=dC$$
**Da cui si ottiene che essendo il prodotto scalare tra il gradiente e lo spostamento infinitesimo quando avviene lungo le superfici di livello nullo in quanto lungo queste $C$ resta costante, il gradiente e' perpendicolare alle curve di livello e punta nel verso in cui il campo cresce.**
**Per cui il gradiente mi da un informazione relativa a direzione e verso lungo la quale ci si deve spostare per avere la massima variazione della grandezza che si sta esaminando**

## Divergenza di un campo vettoriale

Applicando l'operatore $\nabla$ ad un campo vettoriale $\vec{v}(x,y,z)$ attraverso un prodotto scalare si ottiene un campo scalare: la divergenza del campo vettoriale
$$\nabla \cdot \vec{v}(x,y,z)=\frac{\partial v_{x}}{\partial x}+\frac{\partial v_{y}}{\partial y}+\frac{\partial v_{z}}{\partial z}$$
Un campo con divergenza nulla si dice solenoidale

## Rotore di un campo vettoriale


Applicando l'operatore $\nabla$ ad un campo vettoriale $\vec{v}(x,y,z)$ attraverso un prodotto vettoriale si ottiene un campo vettoriale: il rotore del campo vettoriale
$$\nabla \times \vec{v}=\begin{vmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
v_x & v_y & v_z
\end{vmatrix}$$
