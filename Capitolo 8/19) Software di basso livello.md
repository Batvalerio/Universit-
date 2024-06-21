#### Problema dell'Eccesso di Copia

Il principale nemico della comunicazione ad alte prestazioni nei sistemi multicomputer è l'eccesso di copie dei pacchetti. Idealmente, ci sono tre copie: dalla RAM alla scheda di interfaccia nel nodo sorgente, dalla scheda di interfaccia sorgente a quella di destinazione e dalla scheda di interfaccia alla RAM del nodo di destinazione. Tuttavia, in molti sistemi, il numero di copie può essere maggiore, specialmente se la scheda di interfaccia è mappata nello spazio degli indirizzi del kernel invece che in quello utente. Questo implica che un processo utente debba fare una chiamata di sistema, causando ulteriori copie dei pacchetti nella memoria del kernel sia in entrata che in uscita, per evitare fault di pagina durante la trasmissione. Questi passaggi aggiuntivi possono duplicare il ritardo e ridurre la larghezza di banda.

#### Mappatura della Scheda di Interfaccia nello Spazio Utente

Per migliorare le prestazioni, alcuni multicomputer mappano la scheda di interfaccia direttamente nello spazio utente, permettendo al processo utente di trasferire i pacchetti senza coinvolgere il kernel. Questo approccio, sebbene vantaggioso per le prestazioni, introduce due problemi principali.

1. **Accesso Condiviso alla Scheda di Interfaccia**:
   - **Problema**: Se diversi processi in esecuzione su un nodo devono accedere alla rete, sorge la questione di quale processo mappi la scheda di interfaccia nel proprio spazio di indirizzi. Se la scheda è assegnata a un solo processo, gli altri non possono spedire pacchetti. Inoltre, se arriva un pacchetto per un processo diverso da quello che ha mappato la scheda, potrebbero sorgere problemi di sicurezza e cooperazione.
   - **Soluzione**: Una possibile soluzione è mappare la scheda di interfaccia nello spazio di indirizzi di tutti i processi che ne hanno bisogno, utilizzando meccanismi di sincronizzazione come i mutex per evitare corse critiche. Tuttavia, questo funziona solo se i processi cooperano, il che potrebbe non essere il caso in un ambiente time-sharing con utenti diversi.

2. **Accesso del Kernel alla Scheda di Interfaccia**:
   - **Problema**: Il kernel potrebbe dover accedere alla rete di interconnessione, ad esempio per accedere a un file system su un nodo remoto. Condividere la scheda di interfaccia tra kernel e utenti non è ideale, poiché potrebbe arrivare un pacchetto per il kernel mentre la scheda è mappata nello spazio utente, o un utente potrebbe tentare di inviare un pacchetto fingendo di essere il kernel.
   - **Soluzione**: La soluzione più semplice è avere due interfacce di rete separate: una mappata nello spazio utente per il traffico delle applicazioni e l'altra nello spazio del kernel per il sistema operativo. Molti multicomputer adottano questa architettura per evitare conflitti.

#### Conclusioni

L'eccesso di copie dei pacchetti nei sistemi multicomputer può significativamente ridurre le prestazioni. Mappare la scheda di interfaccia nello spazio utente può migliorare l'efficienza, ma introduce problemi di accesso condiviso e di sicurezza. Una soluzione comune è l'utilizzo di due interfacce di rete separate per gestire il traffico delle applicazioni e del kernel, garantendo un funzionamento più sicuro e performante del sistema.

### Punti Chiave

1. **Tre copie ideali**:
   - RAM alla scheda di interfaccia nel nodo sorgente.
   - Scheda di interfaccia del sorgente a quella della destinazione.
   - Scheda di interfaccia alla RAM del nodo di destinazione.

2. **Eccesso di copie**:
   - Se la scheda di interfaccia è mappata nello spazio del kernel, sono necessarie ulteriori copie per evitare fault di pagina.
   - Cinque passaggi di copia complessivi possono duplicare il ritardo e dimezzare la larghezza di banda.

3. **Mappatura nello spazio utente**:
   - Permette ai processi di inviare pacchetti direttamente senza coinvolgere il kernel.
   - Problemi di sincronizzazione e sicurezza quando più processi condividono l'accesso alla scheda.

4. **Soluzioni proposte**:
   - Mappare la scheda di interfaccia in tutti i processi, con meccanismi di sincronizzazione.
   - Due interfacce di rete separate: una per lo spazio utente e una per il kernel.

In sintesi, gestire efficacemente le copie dei pacchetti e l'accesso alla scheda di interfaccia è cruciale per mantenere alte prestazioni nei sistemi multicomputer. La separazione delle interfacce di rete per utente e kernel è una soluzione pratica per bilanciare efficienza e sicurezza.