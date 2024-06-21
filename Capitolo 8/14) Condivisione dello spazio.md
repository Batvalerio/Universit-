1. ==**Schedulazione dei Multiprocessori con Processi Correlati**:== Quando esiste una correlazione tra i processi, come nel caso di un singolo processo che crea diversi thread che lavorano insieme, si può utilizzare un approccio diverso alla schedulazione dei multiprocessori. Questo approccio è noto come “space sharing” o “condivisione dello spazio”.
    
2. ==**Algoritmo di Condivisione dello Spazio**:== In questo approccio, quando si crea un insieme di thread correlati, lo scheduler controlla se ci sono tante CPU libere quanti thread. Se esistono, assegna a ciascun thread la sua CPU dedicata e partono tutti. Se non ci sono abbastanza CPU, non si fa partire nessun thread, finché non è disponibile un numero adeguato di CPU.
    
3. ==**Schedulazione Periodica**:== Periodicamente, si devono prendere decisioni di schedulazione. L’algoritmo analogo per un multiprocessore consiste nello scegliere il processo che ha bisogno del minor numero di cicli di CPU, cioè il processo il cui (numero-di-CPU x tempo di esecuzione) è il più piccolo tra i candidati.
    
4. ==**Gestione Attiva del Grado di Parallelismo**:== Un altro approccio riguarda i processi capaci di gestire attivamente il grado di parallelismo, per esempio con un server centrale che tiene traccia di quali processi siano presenti e vogliano andare in esecuzione, e delle loro richieste di CPU minime e massime.
    
5. ==**Variazione Dinamica delle Dimensioni della Partizione**:== Questo schema permette una variazione dinamica delle dimensioni della partizione, in modo che, rispetto al sistema fisso, corrisponda meglio al carico di lavoro corrente.