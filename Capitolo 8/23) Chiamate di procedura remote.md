Il modello di scambio di messaggi tramite RPC (Remote Procedure Call) ha rivoluzionato l'approccio alla comunicazione nei sistemi multicomputer, consentendo ai programmi di chiamare procedure su altre CPU senza dover gestire direttamente lo scambio di messaggi o l'I/O. Tuttavia, nonostante la sua eleganza concettuale, l'implementazione di RPC presenta diversi problemi significativi.

#### Concetto di RPC

L'idea alla base di RPC è semplice: permettere ai programmi di chiamare procedure su altre CPU come se fossero procedure locali. Quando un processo su una CPU (client) chiama una procedura su un'altra CPU (server), il processo client viene sospeso e l'esecuzione della procedura chiamata avviene sul server. I parametri possono essere passati attraverso i normali meccanismi di chiamata di procedura, e i risultati possono essere restituiti allo stesso modo, nascondendo al programmatore i dettagli della comunicazione remota.

#### Implementazione di RPC

L'implementazione di RPC coinvolge l'uso di stub, piccole procedure di libreria che rappresentano le procedure server nello spazio degli indirizzi del client e viceversa. Quando un client chiama una procedura remota, il client stub confeziona i parametri in un messaggio e li invia al server attraverso una chiamata di sistema. Il server riceve il messaggio, passa i parametri al server stub e chiama la procedura server. La risposta segue lo stesso percorso inverso.

#### Problemi Implementativi

1. **Parametri Puntatore**: Il passaggio di puntatori tra client e server è complicato a causa dei diversi spazi degli indirizzi. Spesso si ricorre a tecniche di copia e ripristino dei parametri anziché al passaggio per riferimento.
2. **Linguaggi Deboli**: Nei linguaggi debolmente tipati come il C, è difficile stabilire la dimensione dei parametri, specialmente per strutture dati complesse.
3. **Deduzione dei Tipi**: Non sempre è possibile dedurre i tipi dei parametri, specialmente con linguaggi permissivi come il C.
4. **Variabili Globali**: Le variabili globali non sono condivise tra client e server, causando problemi se una procedura viene spostata in una macchina remota.

### Conclusioni

Nonostante i problemi implementativi, RPC è ampiamente utilizzato nei sistemi multicomputer. Tuttavia, è necessario prestare molta attenzione e adottare restrizioni per garantire che funzioni correttamente in pratica. La sua capacità di semplificare la comunicazione remota e di nascondere i dettagli della rete ai programmatori lo rende ancora una scelta popolare per lo sviluppo di applicazioni distribuite.
![[Pasted image 20240519124251.png]]