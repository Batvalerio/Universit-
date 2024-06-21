#### Introduzione ai File System Distribuiti

I file system distribuiti mirano a fornire un unico file system globale che consente agli utenti di tutto il mondo di leggere e scrivere file, rispettando le autorizzazioni specificate. Questo approccio affronta sia i problemi dei file system tradizionali sia quelli specifici dei sistemi distribuiti.

#### Modelli di Trasferimento dei File

##### Modello Upload/Download

In questo modello, un processo accede a un file copiandolo dal server remoto sul client. Le operazioni di lettura e scrittura avvengono localmente, migliorando le prestazioni. Se il file viene aggiornato, viene rispedito al server al termine del processo. Vantaggi di questo modello includono semplicità ed efficienza nel trasferire file interi. Tuttavia, richiede una memoria locale sufficiente, può sprecare risorse se sono necessari solo frammenti del file e può causare problemi di consistenza con più utenti simultanei.

##### Modello di Accesso Remoto

In questo modello, il file rimane sul server e il client invia comandi per operazioni remote. Questo approccio evita la necessità di memoria locale per file interi e può gestire meglio la consistenza in presenza di accessi concorrenti.

#### Gerarchia delle Directory

I file system distribuiti supportano directory che contengono più file. Esistono due approcci principali per la vista delle directory tra i client:

1. **Vista Uniforme**: Tutti i client vedono la stessa struttura di directory (Figura 8.35b), facilitando la programmazione e l'uso.
2. **Vista Diversificata**: Client diversi possono avere viste diverse del file system (Figura 8.35c), offrendo maggiore flessibilità ma complicando la coerenza.

La decisione include se avere o meno una directory radice globale riconosciuta da tutte le macchine.

#### Trasparenza dei Nomi

Esistono due forme principali di trasparenza:

1. **Trasparenza della Localizzazione**: Il nome del percorso non rivela la posizione fisica dei file. Questo consente di spostare file senza cambiare i loro nomi, supportando la flessibilità nella gestione dello spazio.
2. **Indipendenza della Localizzazione**: Un sistema in cui i nomi dei percorsi non includono informazioni sulla macchina o sul server consente di spostare file tra server senza alterare i percorsi. Questo approccio è desiderabile ma difficile da ottenere.

#### Gestione dei Nomi nei Sistemi Distribuiti

Tre approcci comuni includono:

1. **Nomi Macchina + Percorso**: Semplice ma limita la trasparenza della localizzazione.
2. **Mount dei File System Remoti**: Facile da implementare ma non supporta bene la migrazione dei file.
3. **Spazio dei Nomi Unificato**: Offre un singolo spazio dei nomi uguale per tutte le macchine, facilitando l'uso ma difficile da progettare.

#### Semantica della Condivisione dei File

La semantica definisce il comportamento di lettura e scrittura in presenza di accessi concorrenti:

1. **Consistenza Sequenziale**: Tutte le operazioni di I/O sono viste nello stesso ordine da tutti i processi.
2. **Semantica di Sessione**: Le modifiche sono visibili solo al processo che le genera fino alla chiusura del file, momento in cui diventano visibili ad altri processi. Questo modello è semplice da implementare ma può causare problemi di consistenza in caso di accessi concorrenti.
3. **Locking e Coda di Accesso**: I file possono essere bloccati per impedire accessi concorrenti non coordinati.

#### Esempio: Andrew File System (AFS)

AFS è un sistema middleware basato sul modello upload/download, sviluppato all'Università Carnegie-Mellon. Ogni utente ha una workstation con una versione modificata di UNIX, che include il codice `venus` nel kernel e un file server `vice` nello spazio utente. Le workstation sono organizzate in celle amministrative.

AFS utilizza una directory locale `/cache` per memorizzare i file remoti e una directory `/cmu` per le celle remote condivise. Quando un file viene aperto, `venus` lo scarica nel disco locale e tutte le operazioni di I/O successive operano sulla copia nella cache. Quando il file viene chiuso, viene rimandato al server.

#### Conclusione

I file system distribuiti, come AFS, offrono un modo efficace per gestire file condivisi su larga scala, bilanciando la necessità di prestazioni, consistenza e facilità d'uso. Ogni modello di trasferimento e approccio di gestione dei nomi presenta vantaggi e svantaggi, richiedendo scelte di progettazione basate sui requisiti specifici dell'applicazione e dell'ambiente di utilizzo.