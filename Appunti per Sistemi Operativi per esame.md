### Appunti Universitari sui Sistemi Operativi

#### Introduzione ai Sistemi Operativi

- **Definizione**: 
  - Un sistema operativo (SO) è un software di sistema che gestisce l'hardware del computer, le risorse software e fornisce servizi comuni per i programmi applicativi. Funziona come intermediario tra l'utente e l'hardware del computer, permettendo l'esecuzione dei programmi e la gestione delle risorse in modo efficiente e sicuro.

- **Funzioni Principali**:
  - **Gestione dei Processi**: Il SO crea, elimina, sospende e riprende i processi. Gestisce la sincronizzazione e la comunicazione tra processi tramite meccanismi come semafori, mutex e pipe. Un processo rappresenta un programma in esecuzione e comprende il codice eseguibile, le variabili, le risorse allocate e il contesto di esecuzione.
  - **Gestione della Memoria**: Il SO tiene traccia di ogni byte di memoria in uso e libero, determina quale processo riceve memoria, quando e quanto, e dealloca la memoria quando non è più necessaria. Questo include tecniche di allocazione dinamica della memoria, paginazione e segmentazione per ottimizzare l'uso della memoria fisica e virtuale.
  - **Gestione dell'I/O**: Il SO gestisce l'interazione con i dispositivi di input/output come tastiere, monitor, stampanti e dischi rigidi. Fornisce un'interfaccia astratta per l'accesso ai dispositivi hardware, permettendo ai programmi di eseguire operazioni di I/O senza dover conoscere i dettagli hardware specifici.
  - **Gestione del File System**: Il SO gestisce la lettura e scrittura di dati nei file, l'organizzazione dei file in directory e la protezione dei dati. Il file system fornisce un modo organizzato e strutturato per memorizzare e recuperare i dati, supportando funzionalità come i permessi di accesso, la compressione e la cifratura.
  - **Sicurezza e Protezione**: Il SO protegge i dati e le risorse dall'accesso non autorizzato e garantisce l'integrità dei dati. Implementa politiche di sicurezza come l'autenticazione degli utenti, il controllo degli accessi, la gestione delle autorizzazioni e la rilevazione di intrusioni.

- **Storia dei Sistemi Operativi**:
  - **Anni '50 e '60**: I primi sistemi operativi furono sviluppati per mainframe e minicomputer. Erano semplici, spesso eseguivano un programma alla volta e non avevano funzioni di multitasking. L'introduzione dei primi SO batch, come GM-NAA I/O, ha permesso l'esecuzione sequenziale di programmi senza intervento umano continuo.
  - **Anni '70 e '80**: Introduzione del multitasking e del time-sharing. UNIX, sviluppato nei Bell Labs, è uno dei primi sistemi operativi a supportare il multitasking e il multiutente. Altri esempi includono VMS per i minicomputer e MS-DOS per i primi personal computer.
  - **Anni '90 e 2000**: Diffusione dei sistemi operativi per personal computer, come Windows, macOS e Linux. Introduzione di GUI (Graphical User Interface) che rendono i computer più accessibili agli utenti non tecnici. Lo sviluppo dei sistemi operativi mobili, come iOS e Android, rivoluziona l'uso dei dispositivi portatili.
  - **Oggi**: I sistemi operativi moderni supportano una vasta gamma di dispositivi, dai supercomputer ai dispositivi mobili. Sono altamente complessi e integrano funzioni avanzate di gestione delle risorse, sicurezza, virtualizzazione e interfacce utente intuitive.

#### Processi e Thread

- **Processi**: Un processo è un'istanza di un programma in esecuzione. Comprende il codice eseguibile, lo stato del programma (registri della CPU, program counter), e la memoria allocata (stack, heap, ecc.). I processi sono unità di isolamento con spazi di indirizzamento separati e non condividono direttamente la memoria. La gestione dei processi include:
  - **Creazione e terminazione**: Un processo può essere creato tramite chiamate di sistema come `fork` (in UNIX) o `CreateProcess` (in Windows). La terminazione di un processo può essere volontaria (quando il processo termina la sua esecuzione) o forzata dal SO.
  - **Stati dei processi**: Un processo può trovarsi in diversi stati: nuovo (creazione), pronto (in attesa di essere eseguito), in esecuzione, bloccato (in attesa di un evento), e terminato.
  - **Comunicazione tra processi (IPC)**: Meccanismi come pipe, messaggi, shared memory e semafori permettono ai processi di comunicare e sincronizzarsi.

- **Thread**: Un thread è l'unità più piccola di esecuzione all'interno di un processo. I thread di un processo condividono lo stesso spazio di indirizzamento e risorse come heap e variabili globali, ma ciascuno ha il proprio stack e registri. Questo permette una condivisione efficiente delle risorse, ma richiede meccanismi di sincronizzazione per evitare condizioni di competizione. La gestione dei thread include:
  - **Creazione e terminazione**: Un thread può essere creato all'interno di un processo esistente e terminato quando completa la sua esecuzione o viene terminato forzatamente.
  - **Sincronizzazione**: L'accesso concorrente alle risorse condivise richiede meccanismi di sincronizzazione come mutex, lock, semafori e barriere per evitare condizioni di race e deadlock.
  - **Modelli di threading**: Esistono vari modelli per la gestione dei thread, come il modello many-to-one, one-to-one e many-to-many, che determinano la relazione tra i thread a livello utente e i thread del kernel.

- **Modello Statico di Multiprogrammazione**: 
  - Nel modello statico, il numero di processi eseguiti contemporaneamente è fissato e non varia durante l'esecuzione del sistema. Questo modello è semplice da implementare ma poco flessibile.
  - Le risorse vengono allocate ai processi in maniera statica e rimangono assegnate fino al completamento dei processi. Non è possibile aggiungere o rimuovere processi dinamicamente.
  - Il sistema operativo deve pianificare i processi in modo tale che il numero massimo di processi in esecuzione non superi il limite prestabilito. Questo richiede una gestione accurata delle risorse per garantire l'uso ottimale.
  - Ogni processo è isolato dagli altri, e i cambi di contesto tra processi avvengono in modo controllato e predeterminato, minimizzando i costi di contesto.

#### Scheduling

- **First-Come, First-Served (FCFS)**: 
  - I processi vengono eseguiti nell'ordine di arrivo. Questo algoritmo è semplice da implementare ma può causare problemi di "convoglio" (convoy effect), dove un processo lungo può bloccare l'esecuzione di processi più brevi, aumentando il tempo medio di attesa.
  - **Vantaggi**: Semplice da implementare, senza necessità di stime dei tempi di esecuzione.
  - **Svantaggi**: Può causare lunghe attese per i processi brevi, inefficienza nella gestione delle risorse.

- **Shortest Job First (SJF)**: 
  - I processi con il minor tempo di esecuzione vengono eseguiti per primi. Questo algoritmo minimizza il tempo medio di attesa ma richiede la conoscenza a priori dei tempi di esecuzione, il che non è sempre possibile.
  - **Vantaggi**: Ottimizza il tempo medio di attesa, riduce il tempo totale di esecuzione.
  - **Svantaggi**: Difficile da implementare in modo preciso, può causare starvation dei processi lunghi.

- **Shortest Remaining Time Next (SRTN)**: 
  - Variante preemptive dello SJF. Il processo con il minor tempo di esecuzione rimanente viene eseguito per primo. Questo può migliorare la reattività del sistema rispetto allo SJF non preemptive.
  - **Vantaggi**: Migliora la reattività, ottimizza il tempo di esecuzione per i processi brevi.
  - **Svantaggi**: Richiede conoscenza precisa del tempo di esecuzione rimanente, complessità nella gestione delle preemption.

- **Round Robin (RR)**: 
  - Ogni processo riceve un time slice o quantum e viene eseguito in cicli. Dopo il suo turno, il processo viene messo in coda se non è terminato. Questo algoritmo è adatto per sistemi time-sharing dove è importante garantire la reattività per tutti i processi.
  - **Vantaggi**: Semplice da implementare, garantisce equità tra i processi.
  - **Svantaggi**: La scelta del quantum è critica; un quantum troppo lungo può causare scarsa reattività, mentre un quantum troppo corto puòcausare un eccessivo overhead dovuto ai frequenti cambi di contesto.

- **Priority Scheduling**: 
  - Ogni processo ha una priorità associata. I processi con priorità più alta vengono eseguiti per primi. Può essere preemptive o non-preemptive. Le priorità possono essere statiche o dinamiche, con la possibilità di aggiornamenti basati su criteri come l'età del processo o il comportamento I/O.
  - **Vantaggi**: Permette di dare la precedenza ai processi critici o urgenti.
  - **Svantaggi**: Può causare starvation per i processi a bassa priorità, necessità di meccanismi di aging per evitare la starvation.

- **Shortest Process Next (SPN)**: 
  - Variante non-preemptive dello SJF, dove il processo con il minor tempo di esecuzione previsto viene eseguito per primo. Questo algoritmo è simile allo SJF ma non prevede la preemption.
  - **Vantaggi**: Ottimizza il tempo medio di attesa per i processi.
  - **Svantaggi**: Richiede conoscenza a priori del tempo di esecuzione, possibile starvation per i processi più lunghi.

- **Scheduling a Lotteria**: 
  - I processi ricevono un numero di "biglietti" della lotteria proporzionale alla loro priorità. Viene selezionato un biglietto casuale per decidere quale processo eseguire. Fornisce una distribuzione probabilistica dell'uso della CPU.
  - **Vantaggi**: Permette una gestione flessibile delle priorità, riduce la possibilità di starvation.
  - **Svantaggi**: Non garantisce determinismo nelle prestazioni, complesso da implementare in modo efficiente.

#### Sistemi Interattivi

- **Sistemi Interattivi**: 
  - Richiedono una risposta rapida per l'interazione utente. Utilizzano algoritmi di scheduling come Round Robin e Priority Scheduling per garantire tempi di risposta accettabili. La reattività è cruciale in questi sistemi per garantire un'esperienza utente fluida.
  - **Esempi**: Sistemi operativi per desktop, applicazioni web, e giochi interattivi. In questi contesti, la latenza e la reattività sono essenziali per una buona esperienza utente.
  - **Sfide**: Gestione efficace delle risorse per evitare che processi intensivi possano compromettere la reattività. Bilanciamento tra equità e priorità dei processi per mantenere una performance stabile.

#### Sistemi Soft Real-Time

- **Definizione**: 
  - I sistemi soft real-time devono rispettare scadenze temporali, ma non in maniera stringente come i sistemi hard real-time. Se una scadenza viene occasionalmente mancata, il sistema continua a funzionare correttamente, anche se con una possibile diminuzione delle prestazioni.
  - **Esempi**: Riproduzione video e audio, sistemi di controllo in applicazioni industriali non critiche.
  - **Scheduling**: Gli algoritmi di scheduling devono garantire che la maggior parte delle scadenze vengano rispettate. Tecniche comuni includono EDF (Earliest Deadline First) e RMA (Rate Monotonic Algorithm).
    - **EDF (Earliest Deadline First)**: Assegna priorità in base alle scadenze, eseguendo per primo il processo con la scadenza più prossima. Questo algoritmo è ottimale per sistemi preemptive.
    - **RMA (Rate Monotonic Algorithm)**: Assegna priorità in base alla frequenza di esecuzione, con processi più frequenti che hanno priorità più alta. È ottimale per sistemi periodici con priorità fisse.

#### Richieste del Disco

- **First-In, First-Served (FIST)**: 
  - Le richieste vengono servite nell'ordine di arrivo. Questo metodo è semplice da implementare ma inefficiente in termini di movimento della testina del disco, poiché non ottimizza il percorso della testina stessa.
  - **Vantaggi**: Semplicità di implementazione.
  - **Svantaggi**: Può causare elevati tempi di attesa e inefficienza nei movimenti della testina.

- **Cyclic-Arm Movement (CAM)**: 
  - La testina del disco si muove in un ciclo fisso, servendo le richieste nell'ordine in cui vengono incontrate. Questo metodo è più efficiente del FIST ma può ancora risultare subottimale.
  - **Vantaggi**: Movimento prevedibile della testina.
  - **Svantaggi**: Non ottimizza il tempo di seek.

- **Shortest Seek Time First (SSTF)**: 
  - La richiesta più vicina alla posizione attuale della testina viene servita per prima. Minimizza il tempo di seek, ma può causare starvation per le richieste lontane.
  - **Vantaggi**: Riduzione del tempo medio di seek.
  - **Svantaggi**: Possibile starvation delle richieste lontane.

- **SCAN (Elevator Algorithm)**: 
  - La testina del disco si muove in una direzione servendo tutte le richieste fino alla fine, poi inverte la direzione. Questo metodo è simile al movimento di un ascensore.
  - **Vantaggi**: Bilanciamento tra riduzione del tempo di seek e prevenzione della starvation.
  - **Svantaggi**: Tempo di attesa può essere elevato per richieste vicine all'estremo del disco.

- **C-SCAN (Circular SCAN)**: 
  - Variante dello SCAN dove la testina, una volta raggiunta la fine, ritorna immediatamente all'inizio senza servire richieste nel viaggio di ritorno. Questo metodo offre un trattamento più uniforme delle richieste.
  - **Vantaggi**: Trattamento uniforme delle richieste, riduzione della variabilità nel tempo di attesa.
  - **Svantaggi**: Leggermente più complesso da implementare rispetto a SCAN.

#### Gestione della Memoria

- **Memoria Libera**: 
  - La gestione della memoria libera include tecniche di allocazione come first-fit, best-fit, e worst-fit. È importante ridurre la frammentazione sia interna che esterna.
  - **First-Fit**: Allocazione del primo blocco di memoria disponibile di dimensione sufficiente. Semplice e veloce, ma può causare frammentazione esterna.
  - **Best-Fit**: Allocazione del blocco di memoria più piccolo possibile che sia comunque sufficiente. Minimizza la frammentazione esterna ma può essere inefficiente in termini di tempo di ricerca.
  - **Worst-Fit**: Allocazione del blocco di memoria più grande disponibile. Questo metodo tende a ridurre la frammentazione interna ma può lasciare grandi blocchi di memoria inutilizzati.

#### Algoritmi di Sostituzione delle Pagine

- **FIFO (First-In, First-Out)**: 
  - La pagina più vecchia viene sostituita per prima. Semplice da implementare ma può causare il problema delle pagine "residenti da troppo tempo" che vengono sostituite anche se frequentemente utilizzate.
  - **Vantaggi**: Facilità di implementazione.
  - **Svantaggi**: Possibilità di sostituire pagine ancora utili, causando aumento dei page fault.

- **LRU (Least Recently Used)**: 
  - La pagina meno recentemente utilizzata viene sostituita per prima. Basato sull'idea che le pagine utilizzate di recente probabilmente saranno utilizzate di nuovo a breve.
  - **Vantaggi**: Generalmente riduce il numero di page fault rispetto a FIFO.
  - **Svantaggi**: Complesso da implementare, richiede gestione accurata delle informazioni di accesso.

- **Optimal**: 
  - La pagina che non sarà utilizzata per il tempo più lungo viene sostituita. Questo algoritmo è teoricamente ottimale, ma impraticabile nella realtà poiché richiede la conoscenza del futuro accesso alle pagine.
  - **Vantaggi**: Offre il numero minimo di page fault possibile.
  - **Svantaggi**: Impraticabile per l'implementazione reale, utilizzato solo come benchmark per confrontare altri algoritmi.

