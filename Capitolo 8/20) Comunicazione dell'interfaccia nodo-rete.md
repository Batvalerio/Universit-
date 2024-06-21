#### Ricezione dei Pacchetti e Problemi del DMA

La via più rapida per ricevere pacchetti sulla scheda di interfaccia in un multicomputer è utilizzare il chip DMA per copiarli dalla RAM. Tuttavia, il DMA utilizza indirizzi fisici e opera indipendentemente dalla CPU, generando vari problemi:

1. **Mappatura da Indirizzi Virtuali a Fisici**:
   - **Problema**: Un processo utente conosce solo l'indirizzo virtuale del pacchetto, non quello fisico. Richiedere una chiamata di sistema per effettuare questa mappatura vanifica il vantaggio di evitare chiamate di sistema per ogni pacchetto.

2. **Rimpiazzo delle Pagine**:
   - **Problema**: Se il sistema operativo decide di rimpiazzare una pagina mentre il chip DMA sta copiando un pacchetto, possono essere trasmessi dati errati o si può corrompere una pagina di memoria.

#### Soluzioni per i Problemi del DMA

1. **Blocco delle Pagine (Pinning)**:
   - **Metodo**: Utilizzare chiamate di sistema per bloccare e sbloccare le pagine in memoria, rendendole temporaneamente non paginabili.
   - **Problema**: Questo metodo è costoso, soprattutto per piccoli pacchetti (64 byte o meno). Per pacchetti grandi (1 KB e oltre), è tollerabile, mentre per dimensioni intermedie dipende dall'hardware.

2. **Utilizzo di Buffer del Kernel**:
   - **Contesto**: Il problema del DMA è meno rilevante per dispositivi come il disco, poiché il sistema operativo gestisce i buffer del kernel, evitando di paginare i buffer stessi.
   - **Limitazione**: Questo metodo è inefficace per la comunicazione da processo a processo, dove la latenza è cruciale.

3. **I/O Programmato**:
   - **Metodo**: Usare l'I/O programmato per gestire pacchetti in uscita, permettendo al sistema operativo di gestire fault di pagina normalmente. 
   - **Approccio Alternativo**: Usare l'I/O programmato per piccoli pacchetti e il DMA con blocco delle pagine per pacchetti grandi.

#### Utilizzo di CPU sulle Schede di Interfaccia

Le schede di interfaccia con CPU proprie (es. Myrinet) possono accelerare la comunicazione, ma richiedono attenzione per evitare corse critiche tra la CPU principale e quella della scheda.

1. **Anelli di Spedizione e Ricezione**:
   - **Struttura**: Ogni nodo ha anelli di spedizione e ricezione, con spazio per n pacchetti e una mappa di bit per indicare le posizioni valide.
   - **Funzionamento**:
     - **Mittente**: Verifica una posizione libera nell'anello di spedizione, copia il pacchetto e imposta il bit corrispondente.
     - **CPU della Scheda**: Controlla l'anello di spedizione, trasmette il pacchetto e azzera il bit corrispondente.
     - **Ricevente**: La CPU della scheda imposta un bit per indicare l'arrivo di un pacchetto, e la CPU principale azzera il bit dopo aver copiato il pacchetto.

2. **Evitare Corse Critiche**:
   - **Metodo**: La CPU principale imposta i bit, mentre la CPU della scheda li azzera, prevenendo corse critiche.
   - **Alternativa**: Usare puntatori nei buffer degli anelli, consentendo alla CPU della scheda di prelevare pacchetti tramite I/O programmato o DMA, purché le pagine siano bloccate.

### Conclusioni

L'uso del DMA per la gestione dei pacchetti nei multicomputer è complesso a causa della necessità di mappatura degli indirizzi e del rischio di rimpiazzo delle pagine. Soluzioni come il blocco delle pagine, l'uso dell'I/O programmato e la struttura degli anelli di spedizione e ricezione con mappe di bit sono cruciali per gestire efficacemente la comunicazione. L'uso di CPU dedicate sulle schede di interfaccia può migliorare le prestazioni, ma richiede meccanismi di sincronizzazione per evitare corse critiche.
![[Pasted image 20240519112801.png]]