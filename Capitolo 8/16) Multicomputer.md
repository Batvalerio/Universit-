1. **Multiprocessori:**
    
    - Offrono un modello di comunicazione semplice in cui tutte le CPU condividono una memoria comune.
    - I processi possono scrivere messaggi in memoria e leggerli da altri processi.
    - La sincronizzazione può essere realizzata con mutex, semafori, monitor e altre tecniche consolidate.
    - Tuttavia, la costruzione di multiprocessori di grandi dimensioni è difficile e costosa.
2. **Multicomputer:**
    
    - I multicomputer sono CPU strettamente accoppiate che non condividono memoria.
    - Ogni CPU ha la propria memoria.
    - Sono noti anche come cluster di computer o COWS (Clusters of Workstations).
    - Sono più facili da costruire rispetto ai multiprocessori perché utilizzano PC base con l’aggiunta di schede di rete.
3. **Obiettivo dei multicomputer:**
    
    - Mandare messaggi in tempi dell’ordine dei microsecondi anziché accedere alla memoria in tempi dell’ordine dei nanosecondi.
    - Il progetto della rete di interconnessione e delle schede di interfaccia è cruciale per ottenere buone prestazioni.
4. **Software e altre considerazioni:**
    
    - Esamineremo l’hardware dei multicomputer, il software di comunicazione a basso livello e la realizzazione della memoria condivisa in sistemi privi di essa.
    - Infine, affronteremo la schedulazione e il bilanciamento del carico.

