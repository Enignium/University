![[Pasted image 20251029171343.png|700]]
# Andamento della dimensione media dei cluster

Nel grafico c è rappresentata la variazione della dimensione media dei cluster, indicata con $s$, in funzione della probabilità $p$

- Quando la probabilità $p$ è molto bassa, la maggior parte dei nodi rimane isolata o forma gruppi di pochissimi elementi: in questa fase i cluster sono piccoli e la media di $s$ assume valori bassi

- Man mano che $p$ aumenta, i nodi attivi diventano più numerosi e iniziano a connettersi tra loro. I piccoli cluster cominciano a fondersi, creando strutture sempre più grandi: di conseguenza la dimensione media di $s$ cresce rapidamente

- Questo processo continua fino a raggiungere la soglia critica di percolazione $p_c$, dove i cluster si uniscono in modo massivo e si forma per la prima volta una componente gigante che attraversa la rete

- In corrispondenza di questo punto, la media di $s$ raggiunge il suo massimo valore: è il momento in cui la rete passa dallo stato frammentato a quello globalmente connesso

- Dopo la soglia $p_c$, la maggior parte dei nodi entra a far parte del cluster gigante, mentre i pochi cluster rimanenti, che non ne fanno parte, sono piccoli e numericamente scarsi

- Poiché la media di $s$ viene calcolata escludendo il cluster percolante, la media della dimensione dei cluster residui diminuisce oltre $p_c$

# Andamento della Probabilità $P_{\infty}$

Nel grafico d è mostrato come varia $P_{\infty}$, la probabilità che un nodo scelto a caso appartenga alla componente più grande del sistema, in funzione della probabilità di connessione $p$

- Quando $p$ è molto piccolo, la rete è composta da tanti cluster isolati di piccole dimensioni. In questa fase non esiste una componente gigante, quindi $P_{\infty}$ = 0: nessun nodo può far parte di un cluster che si estende su scala globale

- Man mano che _p_ aumenta, i cluster iniziano a fondersi, ma fino alla soglia critica $p_c$ la rete rimane comunque frammentata; la probabilità di trovare un nodo nella componente più grande resta praticamente nulla

- Raggiunta la soglia di percolazione $p_c$, avviene un cambiamento improvviso: i cluster si uniscono e compare una componente gigante che connette una frazione significativa dei nodi della rete

- Da questo punto in poi, $P_{\infty}$ diventa maggiore di zero e cresce rapidamente al crescere di $p$: più nodi sono attivi, più alta è la probabilità che un nodo qualsiasi appartenga al cluster percolante

Per valori di $p$ molto alti, quasi tutti i nodi fanno parte della componente gigante e $P_{\infty}$ tende a 1, indicando che la rete è ormai quasi completamente connessa