#### Introduzione al Paradigma degli Oggetti
Nel contesto dei sistemi distribuiti, il paradigma degli oggetti rappresenta un'evoluzione significativa rispetto a quelli basati su documenti o file. Un oggetto, in questo paradigma, è una collezione di variabili e procedure d'accesso, chiamate metodi. I processi non accedono direttamente alle variabili, ma devono invocare i metodi dell'oggetto per effettuare operazioni su di esse. Questo approccio incapsula lo stato e il comportamento, migliorando la modularità e la sicurezza del sistema.

#### CORBA: Un Sistema Basato su Oggetti a Tempo di Esecuzione
CORBA (Common Object Request Broker Architecture) è un esempio prominente di un sistema distribuito basato su oggetti. Progettato per ambienti eterogenei, CORBA permette ai processi client di chiamare metodi su oggetti situati su server remoti. Questo è reso possibile grazie agli ORB (Object Request Brokers), che fungono da intermediari tra client e server, gestendo la comunicazione e l'interoperabilità tra piattaforme diverse.

- **IDL (Interface Definition Language)**: CORBA utilizza IDL per definire le interfacce degli oggetti, specificando i metodi esposti e i tipi dei parametri. Le specifiche IDL vengono compilate in codice stub e skeleton per il client e il server rispettivamente, facilitando la chiamata dei metodi remoti.

- **Comunicazione Client-Server**: I client devono ottenere un riferimento all'oggetto remoto, che può essere acquisito direttamente dal creatore dell'oggetto o tramite directory di oggetti. Le chiamate ai metodi sono effettuate impacchettando i parametri e inviandoli tramite il client ORB al server ORB, che esegue effettivamente il metodo sull'oggetto.

- **IIOP (Internet Inter-ORB Protocol)**: Nella versione 2.0, CORBA ha standardizzato il protocollo di comunicazione tra ORB, migliorando l'interoperabilità tra diverse implementazioni ORB.

Un problema significativo di CORBA è che gli oggetti sono localizzati su un singolo server, il che può portare a colli di bottiglia in termini di prestazioni quando molti client tentano di accedere agli stessi oggetti.

#### Globe: Un Sistema Distribuito Scalabile su Scala Globale
Globe è un sistema distribuito basato su oggetti progettato per scalare a miliardi di utenti e trilioni di oggetti, risolvendo alcuni dei limiti di CORBA attraverso due idee chiave: la replica degli oggetti e la flessibilità.

- **Replica degli Oggetti**: In Globe, gli oggetti possono essere replicati per distribuire il carico delle richieste. Questo è essenziale per evitare che un singolo oggetto diventi un collo di bottiglia.

- **Flessibilità del Sistema**: Globe permette a oggetti e utenti di comportarsi in modi diversi, pur mantenendo un modello globale coerente. Ogni oggetto ha la propria strategia di replicazione, consistenza e sicurezza, gestita internamente senza richiedere interventi esterni.

- **Oggetti Condivisi Distribuiti**: Gli oggetti Globe sono progettati come entità con stato interno accessibile solo tramite metodi. Questo approccio, basato su interfacce a tabelle di puntatori, permette di utilizzare diversi linguaggi di programmazione e garantisce l'accesso controllato allo stato degli oggetti.

- **Strategie di Replicazione**: Globe supporta diverse strategie di replicazione, tra cui:
  - **Replicazione Attiva**: Tutte le copie dell'oggetto sono uguali e eseguono aggiornamenti sequenziali.
  - **Master-Slave**: Una copia master gestisce gli aggiornamenti e sincronizza le copie slave.
  - **Rappresentanti Senza Stato**: Solo una copia mantiene lo stato, mentre le altre inoltrano le richieste ad essa.

- **Localizzazione degli Oggetti**: Globe utilizza un server di localizzazione costruito come un albero per trovare oggetti in tutto il mondo, rendendo lo schema praticabile anche per oggetti mobili.

In sintesi, Globe offre una soluzione scalabile e flessibile per la gestione di oggetti distribuiti su scala globale, superando i limiti di sistemi come CORBA.