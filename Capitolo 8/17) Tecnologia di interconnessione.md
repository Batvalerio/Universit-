Le reti di computer possono essere organizzate in diverse topologie, ognuna con i propri vantaggi e svantaggi.

1. ==**Topologia a Stella**== 
   Nella topologia a stella, ogni nodo della rete è collegato a un singolo switch centrale. Questa configurazione è ampiamente utilizzata nelle moderne ==reti Ethernet switched==, grazie alla sua semplicità di gestione e alla capacità di isolare i guasti in modo efficiente. In questa architettura, se un nodo o un cavo si guasta, gli altri nodi non vengono influenzati, a condizione che lo switch centrale rimanga operativo. Inoltre, la topologia a stella riduce le collisioni dei dati poiché ogni nodo ha una connessione dedicata allo switch.

2. ==**Topologia ad Anello**==
   La topologia ad anello connette i nodi in una catena continua, formando un anello. In questo sistema, ogni nodo ha due cavi: uno che va al nodo alla sua sinistra e uno che va al nodo alla sua destra. Non sono necessari switch in questa configurazione, il che semplifica la rete. Tuttavia, se un singolo nodo o un collegamento si guasta, può interrompere l'intero anello. Per mitigare questo rischio, possono essere implementati meccanismi di recupero che ripristinano la connettività instradando i dati nella direzione opposta.

3. ==**Topologia a Griglia (Mesh)**==
   Una topologia a griglia è una struttura bidimensionale regolare in cui ogni nodo è connesso a più nodi vicini, formando una rete a maglia. Questa architettura è altamente scalabile e viene utilizzata in molti sistemi commerciali. Uno dei principali vantaggi della griglia è che il diametro della rete, che rappresenta il percorso più lungo tra due nodi, cresce solo con la radice quadrata del numero totale di nodi. Ciò significa che le distanze di comunicazione rimangono relativamente brevi anche in grandi reti. Una variante della griglia è il "doppio toro", dove i lati della griglia sono connessi, migliorando ulteriormente la tolleranza ai guasti e riducendo il diametro, permettendo ai nodi di comunicare attraverso il centro della griglia in meno passaggi.

4. ==**Cubo Tridimensionale**==
   Un cubo tridimensionale è una struttura regolare in cui i nodi sono organizzati in una matrice tridimensionale. Ad esempio, un cubo 2x2x2 ha otto nodi. Questa topologia può essere estesa a cubi di dimensioni maggiori, come k x k x k. Il vantaggio principale del cubo tridimensionale è la sua alta connettività e il diametro relativamente ridotto rispetto alle strutture bidimensionali, consentendo una comunicazione più rapida tra i nodi.

5. ==**Ipercubo**==
   L'ipercubo è una struttura n-dimensionale che si ottiene collegando i nodi corrispondenti di cubi di dimensioni inferiori. Ad esempio, un cubo a quattro dimensioni può essere costruito con due cubi tridimensionali, collegando i nodi corrispondenti. Questo processo può essere ripetuto per formare cubi di dimensioni superiori. Un ipercubo di dimensione n ha 2^n nodi e un diametro che cresce linearmente con n. Questo significa che il diametro dell'ipercubo è il logaritmo in base 2 del numero di nodi, rendendolo estremamente efficiente in termini di ritardo di comunicazione. Ad esempio, un ipercubo di dimensione 10 ha 1024 nodi e un diametro di soli 10, rispetto a una griglia 32x32 con 1024 nodi e un diametro di 62. Tuttavia, il costo di implementazione è più elevato a causa del maggior numero di collegamenti necessari.

#### Metodi di Commutazione

Le reti di computer utilizzano diversi metodi di commutazione per gestire il trasferimento dei dati tra i nodi.

1. ==**Commutazione di Pacchetto (Store-and-Forward)**==
   Nella commutazione di pacchetto, ogni messaggio viene suddiviso in pacchetti di lunghezza massima predeterminata. Questi pacchetti vengono inviati dal nodo sorgente al primo switch, dove vengono memorizzati completamente prima di essere inoltrati allo switch successivo. Questo processo continua fino a raggiungere il nodo di destinazione. Il principale vantaggio di questo metodo è la sua flessibilità ed efficienza. Tuttavia, introduce una latenza aggiuntiva poiché ogni pacchetto deve essere copiato completamente in ogni switch lungo il percorso. Ad esempio, se il tempo necessario per trasferire un pacchetto tra due switch è T nanosecondi, la latenza totale per attraversare quattro switch sarà 4T.

2. ==**Commutazione di Circuito**==
   La commutazione di circuito stabilisce un percorso fisso attraverso tutti gli switch dal nodo sorgente al nodo di destinazione prima di iniziare la trasmissione dei dati. Una volta stabilito il percorso, i dati fluiscono continuamente senza interruzioni o bufferizzazione intermedia negli switch. Questo metodo richiede una fase di inizializzazione per stabilire il cammino, ma una volta completata, offre una trasmissione rapida e senza interruzioni. La commutazione di circuito è particolarmente efficiente per trasmissioni di dati lunghe e continue.

3. ==**Wormhole Routing**==
   Il wormhole routing è una variante della commutazione di circuito. In questo metodo, un pacchetto viene suddiviso in sotto-pacchetti, chiamati flit (flow control digit). Non appena il primo flit raggiunge uno switch, può essere immediatamente inoltrato al prossimo switch lungo il percorso, anche se il resto del pacchetto non è ancora arrivato. Questo permette una riduzione significativa della latenza complessiva, combinando la rapidità della commutazione di circuito con la flessibilità della commutazione di pacchetto.

### Considerazioni Chiave

La scelta dell'architettura di rete e del metodo di commutazione dipende da vari fattori come la scalabilità, la tolleranza ai guasti, la latenza e i costi di implementazione. Le topologie come l'ipercubo offrono eccellenti proprietà di ritardo e scalabilità, ma a un costo maggiore in termini di fanout e complessità dei collegamenti. D'altra parte, metodi di commutazione come il wormhole routing offrono una combinazione vantaggiosa di bassa latenza e flessibilità, rendendoli ideali per reti parallele ad alte prestazioni.
![[Pasted image 20240519112142.png]]![[Pasted image 20240519112238.png]]