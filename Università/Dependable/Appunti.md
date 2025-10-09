![[Slide 2.pdf#page=20&rect=16,213,499,513|03, p.20|300]]
Un simulatore nel nostro caso è solo un set di iterazioni che cambiano lo stato con il passare del tempo.

![[Slide 2.pdf#page=20&rect=35,233,486,275|03, p.20|300]]

Una forma per indicare un passaggio ad uno stato successivo
# Inizialization

> [!PDF|important] [[Slide 2.pdf#page=21&selection=4,14,4,15&color=important|03, p.21]]
> > Initialization
> 
> 
Il primo passo per creare il proprio simulatore è l'inizializzazione di tutte le variabili, in particolare dobbiamo creare tutti i possibili eventi al tempo 0 ed aggiungere questi in un calendario.
Il calendario va implementato come una sequenza di eventi, dato che quando lo stato deve cambiare in corrispondenza dell'evento, l'evento deve diventare il nuovo stato. Solitamente quindi viene usata una lista ordinata in cui il valore attuale della lista corrisponde all'evento. L'evento deve pure essere valutato come possibile e si deve considerare la possibilità di inserire nuovi eventi.

> [!PDF|red] [[Slide 2.pdf#page=23&selection=4,18,4,19&color=red|03, p.23]]
> > Simulation running
> La simulazione è composta da 4 passaggi:
> - La fase di inizializzazione, con il caricamento della lista degli eventi nel calendario. Tutto partendo dal tempo 0. Ogni evento k $(e_k, \tau_k)$ verrà caricato con il momento in cui dovrà avvenire.
> - Definizione del tempo tra un salto e l'altro
> $$\tau = \tau + \tau_k $$
> - Aggiornamento al prossimo stato, eliminando gli eventi non compatibili e aggiornando tutte le variabili necessarie compreso i nuovi eventi
>  $$x_{k+1} = \delta (x_k,e_k) $$
> - Ordinamento della lista

> [!PDF|important] [[Slide 2.pdf#page=24&selection=4,28,4,29&color=important|03, p.24]]
> > An example: a queuing system
> > 
> I clienti arrivano ad intervalli irregolari, se il server è pieno, i clienti che arrivano vengono messi in coda. Quando il servizio è completo, i clienti lasciano il server e questo passa da pieno a libero
> Il numero di clienti è sconosciuto, quindi di volta in volta bisogna ricalcolare il tempo per il prossimo evento.
> 
> - **Stato del sistema:** numero di clienti in coda, stato del server
> - **Entità:** server, clienti, coda
> - **Attributi:** (da specificare in base al modello, ad esempio: tempo di arrivo del cliente, tempo di servizio, ecc.)
> - **Eventi:** arrivo del cliente, partenza del cliente, inizio del servizio (evento dipendente), fine della simulazione
> - **Attività:** tempi di inter-arrivo e tempi di servizio
> -  **Ritardi:** tempi di attesa dei clienti

# Definizione della funzione $\delta$

> [!PDF|note] [[Slide 2.pdf#page=26&selection=4,0,4,5&color=note|03, p.26]]
> > Event
> In base agli eventi le azioni cambiano:
L'arrivo di un cliente (ammettendo fosse libero il server prima) fa si che il server diventi occupato e che i prossimi clienti vadano in coda. La dimensione della coda aumenta con l'arrivo dei clienti. Lo stato del server quindi può essere: Occupato oppure Libero. L'arrivo di un cliente è considerato un evento indipendente e non dipende dallo stato del sistema.
