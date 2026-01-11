
## Generatore ideale di tensione
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1]]

La forza elettromotrice $E$ è un bipolo che impone ai suoi capi una differenza di potenziale di $E$ volt indipendentemente dalla corrente che scorre nel circuito per cui:
$$V_{A}=E+V_{B}$$
Non è un legame lineare

Immaginando di chiudere in un circuito un generatore di tensione con in serie una resistenza, calcolando la potenza con la quale la resistenza dissipa l'energia  si avrà:
$$P=V_{ab}\cdot i=\frac{E^2}{R}$$
Ma con $R \to 0$ la potenza tenderebbe all'infinito, perciò questo generatore non è realizzabile perché dovrebbe essere in grado di erogare potenza infinita

Non è possibile collegare in parallelo due FEM con $E_{1}\neq E_{2}$ in quanto ogni ramo di un collegamento parallelo dovrebbe avere la stessa tensione.
![[Drawing 2025-04-02 17.06.42.excalidraw 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 2 2 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 2 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1]]
Considerate 3 FEM in serie:
$$\begin{array}
aV_{A}-V_{F}=E_{1} \\
V_{F}-V_{S}=-E_{2} \\
V_{S}-V_{B}=E_{3}
\end{array}$$
Per cui è possibile sostituire il generatore di tensione con la somma algebrica dei generatori collegati in serie.



### Legge di Kirchoff alla maglia
La somma algebrica delle forze elettromotrici che insistono sulla maglia è uguale alla somma algebrica delle differenze di potenziali ai capi degli elementi resistivi compongono la maglia.
$$\sum_{k=1} E_{k}=\sum_{j=1}^mR_{k}i_{k}$$
## Generatore reale di tensione



## Generatore di corrente

### partitore di tensione e di corrente
