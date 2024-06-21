1. ==**Schedulazione di Processi Indipendenti**:== Il più semplice algoritmo di schedulazione per processi non correlati utilizza una struttura dati di sistema per i processi pronti, come una lista o un insieme di liste per processi a differente priorità.
    
2. ==**Schedulazione Monoprocessore vs Multiprocessore**==: La schedulazione con una sola struttura dati utilizzata da tutte le CPU effettua il time-sharing delle CPU in gran parte come se ci trovassimo in un sistema monoprocessore, fornendo anche un bilanciamento automatico del carico.
    
3. ==**Smart Scheduling**:== Alcuni sistemi utilizzano lo smart scheduling, in cui un processo che acquisisce un lock gestito con cicli di attesa utilizza un flag a livello di processo per evidenziare che detiene correntemente un lock.
    
4. ==**Schedulazione per Affinità**:== Alcuni multiprocessori tengono conto dell’effetto della cache e utilizzano la schedulazione per affinità. L’idea base è sforzarsi di eseguire un processo sulla stessa CPU dove è stato eseguito l’ultima volta.
    
5. ==**Algoritmo di Schedulazione a Due Livelli**:== Un modo per creare questa affinità è usare un algoritmo di schedulazione a due livelli: quando un processo è creato, viene assegnato ad una CPU, ad esempio a quella che al momento ha il minor carico, e tale assegnazione dei processi alla CPU costituisce il livello superiore dell’algoritmo.
6. ==**Schedulazione Effettiva dei Processi**:== La schedulazione effettiva dei processi costituisce il livello inferiore dell’algoritmo di schedulazione a due livelli e viene effettuata da ciascuna CPU separatamente, utilizzando le priorità o altri mezzi.
    
7. ==**Massimizzazione dell’Affinità della Cache**:== Cercando di mantenere un processo sulla stessa CPU, si massimizza l’affinità della cache. Se una CPU non ha processi da eseguire, può prenderli da un’altra, piuttosto che rimanere inattiva.
    
8. ==**Vantaggi della Schedulazione a Due Livelli**:== La schedulazione a due livelli comporta tre vantaggi principali:
    
    - Distribuisce il carico tra le CPU disponibili in modo abbastanza paritario.
    - Sfrutta l’affinità della cache, dove possibile.
    - Fornendo a ciascuna CPU la propria lista dei pronti, si minimizza la contesa per le liste dei pronti, poiché i tentativi di utilizzare la lista dei pronti di un’altra CPU sono relativamente poco frequenti.
