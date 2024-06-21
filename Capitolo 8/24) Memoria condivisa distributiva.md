Il modello di memoria condivisa distribuita (DSM) è una tecnica che consente di simulare l'illusione di una memoria condivisa su un sistema multicomputer, anche se in realtà ogni nodo ha la propria memoria fisica e virtuale. Con DSM, le pagine di memoria sono distribuite tra i nodi del sistema, e quando una CPU effettua un'operazione di LOAD o STORE su una pagina non presente in memoria locale, il sistema operativo interviene per recuperare la pagina dalla memoria di un altro nodo attraverso la rete di interconnessione.

#### Implementazione di DSM

Nel sistema DSM, lo spazio degli indirizzi è diviso in pagine distribuite su tutti i nodi del sistema. Quando una CPU si riferisce a un indirizzo non locale, viene generata una trap e il sistema DSM recupera la pagina desiderata dal nodo corrispondente, permettendo così all'istruzione di completarsi con successo. La figura 8.23 mostra un esempio di come funziona DSM, con pagine distribuite tra quattro nodi.

#### Replicazione

Un miglioramento significativo al sistema base consiste nella replicazione delle pagine in sola lettura, come il testo del programma o costanti, per evitare continui trasferimenti di rete. Questo consente alle CPU di accedere localmente alle pagine replicate senza generare trap di fault di pagina. La figura 8.23 (c) illustra come funziona la replicazione di una pagina in sola lettura.

#### Condivisione Falsa

Un problema notevole con DSM è la condivisione falsa, che si verifica quando due CPU accedono a variabili diverse che si trovano nella stessa pagina. Questo può causare continui trasferimenti di pagine tra i nodi, aumentando il carico sulla rete e riducendo le prestazioni complessive del sistema.

#### Ottenere Consistenza Sequenziale

Per garantire la consistenza dei dati in un ambiente DSM, è necessario coordinare le scritture su pagine condivise tra diverse CPU. Questo viene realizzato inviando messaggi alle altre CPU per invalidare e scaricare le loro copie delle pagine prima di effettuare una scrittura. Altri approcci includono l'uso di lock per consentire a una singola CPU di modificare una pagina alla volta e la propagazione dei cambiamenti ai nodi remoti quando un lock viene rilasciato.

### Conclusioni

Nonostante le sfide associate alla gestione della memoria condivisa distribuita, DSM offre un'importante illusione di memoria condivisa su sistemi multicomputer. Tuttavia, è necessario prestare attenzione alla gestione della condivisione dei dati e alla consistenza per garantire prestazioni ottimali del sistema.
![[Pasted image 20240519131348.png]]![[Pasted image 20240519131410.png]]![[Pasted image 20240519131512.png]]