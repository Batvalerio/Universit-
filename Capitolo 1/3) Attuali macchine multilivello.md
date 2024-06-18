![[Pasted image 20240405155746.png]]                                                       
1. Livello -1= ==Il livello dei dispositivi== che qui non è rappresentato si troverebbe al di sotto del livello 0 e costituisce il vero e proprio hardware della macchina, ma a noi interessa solo saperlo perché il suo studio e di competenza dell'ingegneria elettronica.
2. Livello 0 = ==Il livello della logica digitale== contiene le ==porte== (gate) che pur essendo composte da componenti analogici (come i transistor), possono essere correttamente modellate come dispositivi digitali; è possibile combinare queste memorie a gruppi di 16,32,64 bit formando dei ==registri==. 
3. Livello 1 = ==Il livello di micro-architettura o micro-programmazione== è quello che contiene la memoria locale formata da un gruppo di registri (in genere da 8 a 32 bit) e un circuito chiamato ==ALU== (Arithmetic Logic Unit, unità aritmetico-logica), capace di effettuare semplici operazioni aritmetiche. I registri sono connessi alla ALU per formare un ==percorso dati== lungo il quale questi ultimi si spostano. In alcune macchine le operazioni del percorso dati sono controllate da un programma chiamato ==microprogramma==,mentre su altre è controllato direttamente dall'hardware 
4. Livello 2 = ==Il livello delle istruzioni macchina== è costituito da quello che viene chiamato ==livello ISA== (Instruction Set Architecture Level, livello di architettura dell'insieme d'istruzioni) differente per ogni macchina a tal punto che ogni produttore di computer deve rilasciare un "manuale di riferimento del linguaggio macchina".
5. Livello 3 = ==Il livello del sistema operativo== viene definito come un livello "ibrido" perché qui alcune istruzioni sono interpretate dal sistema operativo, mentre altre sono interpretate in modo diretto dal microprogramma. 
 **I tre livelli inferiori non sono progettati per i programmatori ma sono concepiti principalmente per eseguire interpreti e traduttori scritti da professionisti chiamati ==programmatori di sistema==** 
6. Livello 4 = ==Il livello dell'assembly o del linguaggio assemblativo== fornisce un ai programmatori un modo per scrivere programmi per i livelli 1,2 e 3 in forma meno difficoltosa rispetto a quella dei linguaggi delle rispettive macchine virtuali. Il programma che esegue la traduzione è chiamato ==assemblatore== 
7. Livello 5 = ==Il livello del HLL== consiste generalmente di linguaggi chiamati ==linguaggi di alto livello== definiti per essere usati dai programmatori di applicazioni. I programmi scritti i questi linguaggi sono generalmente tradotti al livello 3 o al livello 4 da un traduttore detto ==compilatore==; in casi meno frequenti è anche possibile che essi siano interpretati.
  **L'insieme dei tipi di dati, delle operazioni e delle funzionalità di ciascun livello è detto ==architettura==**  
**Invece lo studio di come progettare le parti di un computer visibili ai programmatori è chiamato ==architettura degli elaboratori==**  


   