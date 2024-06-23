## Architettura dei Calcolatori

### Approccio Strutturale
L'approccio strutturale all'architettura dei calcolatori si focalizza sull'organizzazione e interconnessione delle componenti hardware del sistema. Si tratta di comprendere come la CPU, la memoria, i dispositivi di input/output e altri componenti interagiscono per eseguire programmi.

### Pietre Miliari nell'Architettura dei Computer
1. **ENIAC (1945)**: Il primo computer elettronico general-purpose, composto da 18.000 valvole termoioniche, utilizzato per calcoli balistici.
2. **IBM System/360 (1964)**: Introduce il concetto di compatibilità binaria tra diverse macchine, rivoluzionando l'industria dei computer.
3. **Intel 4004 (1971)**: Il primo microprocessore su singolo chip, con 2.300 transistor e una velocità di clock di 740 kHz.
4. **IBM PC (1981)**: Standardizza il mercato dei personal computer, rendendo i computer accessibili al grande pubblico.
5. **Architettura RISC (anni '80)**: Introduce un set di istruzioni ridotto per migliorare l'efficienza del processore.

### Tipologie di Computer
1. **Supercomputer**: Utilizzati per calcoli estremamente complessi, come simulazioni climatiche e ricerche scientifiche.
2. **Mainframe**: Sistemi potenti per elaborare grandi quantità di dati, spesso utilizzati in banche e grandi aziende.
3. **Minicomputer**: Predecessori dei server moderni, utilizzati per applicazioni di medio livello.
4. **Personal Computer (PC)**: Usati per scopi personali e aziendali, con una vasta gamma di applicazioni.
5. **Dispositivi mobili**: Smartphone e tablet, che combinano funzionalità computazionali con portabilità e connettività.

### Unità Metriche
- **Bit e Byte**: Un bit è la più piccola unità di informazione, mentre un byte è composto da 8 bit.
- **Kilobyte (KB)**: 1 KB = 1024 byte.
- **Megabyte (MB)**: 1 MB = 1024 KB.
- **Gigabyte (GB)**: 1 GB = 1024 MB.
- **Terabyte (TB)**: 1 TB = 1024 GB.

## Organizzazione dei Sistemi di Calcolo

### Processori
- **CPU (Central Processing Unit)**: Il cervello del computer, esegue le istruzioni del programma.
  - **ALU (Arithmetic Logic Unit)**: Esegue operazioni aritmetiche e logiche.
  - **CU (Control Unit)**: Controlla l'esecuzione delle istruzioni e coordina le operazioni dell'ALU, dei registri e della memoria.
  - **Registri**: Memoria interna alla CPU per lo stoccaggio temporaneo di dati e istruzioni.

### Memoria Principale
- **RAM (Random Access Memory)**: Memoria volatile utilizzata per memorizzare temporaneamente dati e istruzioni durante l'esecuzione di programmi.
- **ROM (Read-Only Memory)**: Memoria non volatile contenente istruzioni permanenti, come il firmware del sistema.

### Memoria Secondaria
- **Hard Disk**: Dispositivo di memorizzazione non volatile con capacità elevate ma velocità inferiore rispetto alla RAM.
- **SSD (Solid State Drive)**: Dispositivo di memorizzazione non volatile, più veloce degli hard disk tradizionali, grazie all'assenza di parti mobili.

### Input/Output
- **Dispositivi di Input**: Tastiere, mouse, scanner, che permettono agli utenti di immettere dati nel computer.
- **Dispositivi di Output**: Monitor, stampanti, altoparlanti, che permettono al computer di comunicare informazioni agli utenti.

## Livello Logico Digitale

### Porte Logiche e Algebra di Boole
- **Porte Logiche**: Elementi fondamentali dei circuiti digitali che eseguono operazioni logiche.
  - **AND**: Restituisce vero solo se entrambi gli input sono veri.
  - **OR**: Restituisce vero se almeno uno degli input è vero.
  - **NOT**: Inverte lo stato dell'input.
  - **NAND, NOR, XOR, XNOR**: Varianti delle porte logiche di base con comportamenti specifici.
- **Algebra di Boole**: Sistema matematico per l'analisi e la semplificazione delle espressioni logiche.

### Circuiti Logici Digitali Elementari
- **Multiplexer (MUX)**: Seleziona uno tra diversi input basato su segnali di controllo.
- **Demultiplexer (DEMUX)**: Distribuisce un singolo input su diversi output basato su segnali di controllo.
- **Flip-Flop**: Elemento di memoria che può immagazzinare un singolo bit di dati, utilizzato per costruire registri e memorie.

### Memoria
- **SRAM (Static RAM)**: Memoria veloce e volatile che non necessita di refresh per mantenere i dati.
- **DRAM (Dynamic RAM)**: Memoria volatile che necessita di refresh periodici per mantenere i dati, ma offre una maggiore densità di memorizzazione rispetto a SRAM.

### Chip della CPU e Bus
- **Chip della CPU**: Esempi includono Intel i7, AMD Ryzen, che rappresentano famiglie di microprocessori con diverse prestazioni e caratteristiche.
- **Bus**: Canali di comunicazione tra le varie componenti del computer.
  - **Bus Dati**: Trasporta i dati tra CPU, memoria e dispositivi di input/output.
  - **Bus Indirizzi**: Trasporta gli indirizzi di memoria.
  - **Bus Controllo**: Trasporta segnali di controllo per coordinare le attività del sistema.

## Interfacce

### Esempio di Microarchitettura
- **Microarchitettura**: Struttura interna della CPU che definisce come vengono implementate le varie unità funzionali, come pipeline e unità di esecuzione, per ottimizzare le prestazioni.

### Esempio di ISA: IJVM
- **IJVM (Instruction Set Architecture)**: Esempio di architettura di set di istruzioni utilizzata per comprendere come le istruzioni sono codificate e eseguite a basso livello.

## Livello ISA

### Panoramica del Livello ISA
- **ISA (Instruction Set Architecture)**: La parte dell'architettura del computer che definisce le istruzioni che la CPU può eseguire, inclusi tipi di istruzioni, formati e modalità di indirizzamento.

### Tipi di Dati
- **Interi**: Numeri senza decimali, utilizzati per operazioni aritmetiche di base.
- **Floating Point**: Numeri con decimali, utilizzati per calcoli più complessi.
- **Caratteri**: Simboli alfanumerici rappresentati da codici numerici.

### Formati delle Istruzioni
- **Formati R, I, J**: Diversi modi di codificare le istruzioni.
  - **Formato R**: Per operazioni aritmetiche e logiche.
  - **Formato I**: Per istruzioni con immediati e operazioni di accesso alla memoria.
  - **Formato J**: Per istruzioni di salto.

### Indirizzamento
- **Modalità di Indirizzamento**: Metodi per specificare gli operandi.
  - **Immediato**: L'operando è incluso nell'istruzione stessa.
  - **Diretto**: L'istruzione specifica l'indirizzo della memoria.
  - **Indiretto**: L'istruzione specifica un indirizzo che contiene l'indirizzo dell'operando.
  - **Indicizzato**: L'operando è specificato attraverso un registro di base e un offset.

### Tipi di Istruzioni
- **Istruzioni Aritmetiche**: ADD, SUB, MUL, DIV.
- **Istruzioni Logiche**: AND, OR, NOT, XOR.
- **Istruzioni di Controllo**: JMP, BEQ, BNE, che alterano il flusso di esecuzione.

### Flusso di Controllo
- **Branching**: Alterazione del flusso di esecuzione del programma basato su condizioni.
- **Loop**: Ripetizione di un blocco di istruzioni fino a quando una condizione specifica non è soddisfatta.

### Architettura e Programmazione ARM
- **ARM**: Architettura RISC utilizzata in una vasta gamma di dispositivi, dai microcontrollori ai server.
- **Programmazione ARM**: Utilizzo del linguaggio Assembly ARM per scrivere programmi ottimizzati per l'architettura ARM.

## Livello del Linguaggio Assemblativo

### Introduzione al Linguaggio Assemblativo
- **Assembly**: Linguaggio di basso livello che rappresenta le istruzioni macchina in modo leggibile per l'uomo, permettendo un controllo fine sull'hardware.

### Macroistruzioni
- **Macro**: Gruppi di istruzioni che possono essere riutilizzati per semplific

are la programmazione e ridurre la complessità del codice.

### Il Processo di Assemblaggio
- **Assembler**: Strumento che traduce il codice Assembly in codice macchina eseguibile dalla CPU.

### Collegamento e Caricamento
- **Linker**: Strumento che combina vari moduli di codice oggetto in un singolo programma eseguibile.
- **Loader**: Software che carica il programma eseguibile in memoria per l'esecuzione.

## Introduzione ai Sistemi Operativi

### Storia dei Sistemi Operativi, Concetti di Base dei SO
- **Evoluzione**: Dai primi batch system ai moderni sistemi operativi multitasking e multiutente.
- **Concetti di Base**: Gestione delle risorse, astrazione dell'hardware, fornitura di un'interfaccia utente.

### Struttura di un SO, Introduzione al Linguaggio C
- **Monolitico**: Un kernel unico che contiene tutte le funzionalità del sistema operativo.
- **Microkernel**: Un kernel ridotto al minimo che delega molte funzioni ai servizi in user space.
- **Linguaggio C**: Largamente utilizzato nello sviluppo di sistemi operativi per la sua efficienza e controllo a basso livello.

### Processi e Thread
- **Processi**: Istanza di un programma in esecuzione, con spazio di indirizzamento e risorse proprie.
- **Thread**: Sub-unità di un processo che condivide le risorse del processo principale ma ha il proprio flusso di esecuzione.

### Gestione della Memoria
- **Paginazione**: Divisione della memoria in blocchi di dimensioni fisse chiamati pagine, per la gestione efficiente della memoria.
- **Segmentazione**: Divisione della memoria in segmenti di dimensioni variabili per riflettere la struttura logica del programma.

### File System
- **Organizzazione**: Struttura ad albero che organizza file e directory.
- **Gestione**: Metodi per l'allocazione, accesso, protezione e recupero dei dati memorizzati.

### Input/Output
- **Gestione I/O**: Metodi per la comunicazione tra la CPU e le periferiche.
- **Driver**: Software che permette al sistema operativo di controllare e comunicare con un dispositivo hardware.

## Architetture per il Calcolo Parallelo

### Parallelismo nel Chip
- **Multithreading**: Capacità di un singolo core di eseguire più thread simultaneamente.
- **Hyper-Threading**: Tecnologia di Intel che permette a un singolo core di processore di apparire come due core logici al sistema operativo, migliorando il parallelismo.

### Coprocessori
- **GPU (Graphics Processing Unit)**: Utilizzata per elaborazione parallela massiva, particolarmente efficiente per calcoli grafici e scientifici.
- **DSP (Digital Signal Processor)**: Ottimizzato per elaborazioni di segnali digitali come audio e video.

### Multiprocessori
- **SMP (Symmetric Multiprocessing)**: Architettura in cui tutti i processori condividono la stessa memoria fisica.
- **AMP (Asymmetric Multiprocessing)**: Architettura in cui i processori hanno ruoli specifici e possono avere memorie separate.

### Multicomputer
- **Cluster**: Gruppo di computer interconnessi che lavorano insieme come un singolo sistema per eseguire calcoli paralleli.
- **Grid Computing**: Utilizzo di risorse computazionali distribuite su una rete per eseguire compiti complessi.

### Virtualizzazione
- **Hypervisor**: Software che crea e gestisce macchine virtuali, permettendo l'esecuzione di più sistemi operativi su un singolo hardware fisico.
- **VM (Virtual Machine)**: Emulazione di un computer che esegue un sistema operativo, fornendo un ambiente isolato per l'esecuzione di applicazioni.

## Introduzione alla Programmazione su ARM

### Sistemi di Numerazione ed Algebra di Boole
- **Sistemi di Numerazione**: Binario, ottale, esadecimale.
- **Algebra di Boole**: Fondamentale per il design dei circuiti logici digitali, con operazioni come AND, OR, NOT.

### Sistemi Digitali e Codifica
- **Codifica dei Dati**: ASCII, Unicode, codifica binaria.
- **Sistemi Digitali**: Concetti di base su come i dati sono rappresentati e manipolati a livello hardware.

### Architettura ARM
- **Caratteristiche**: Architettura RISC, basso consumo energetico, alta efficienza.
- **Utilizzo**: Ampiamente utilizzata in dispositivi mobili, embedded, e anche in server.

### Programmazione in ARM
- **Linguaggio Assembly ARM**: Sintassi e istruzioni specifiche per i processori ARM.
- **Esempi di Programmi**: Codici di esempio per comprendere le operazioni di base, come l'aritmetica, la gestione della memoria, e il controllo del flusso.
