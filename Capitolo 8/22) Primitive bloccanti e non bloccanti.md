Le primitive per lo scambio di messaggi possono essere divise in due categorie: primitive bloccanti e primitive non bloccanti (o sincrone e asincrone). Ogni categoria presenta vantaggi e svantaggi che devono essere considerati durante la progettazione dei sistemi multicomputer.

#### Primitive Bloccanti

1. **Send Bloccante**: Il processo mittente si blocca durante la trasmissione del messaggio e viene riattivato solo dopo il completamento della trasmissione.
2. **Receive Bloccante**: Il processo ricevente si blocca fino a quando non arriva un messaggio nel buffer specificato.

#### Primitive Non Bloccanti

1. **Send Non Bloccante con Copia**: La send restituisce immediatamente il controllo al mittente, ma una copia del messaggio viene creata nello spazio kernel per garantire che il mittente possa continuare il calcolo senza attendere.
2. **Send Non Bloccante con Interruzione**: Il mittente riceve un segnale di interruzione quando il messaggio è stato effettivamente spedito, consentendo al mittente di continuare l'esecuzione senza copie aggiuntive.
3. **Copia in Scrittura**: Il buffer del messaggio è marcato come copia in scrittura fino a quando il messaggio non è stato effettivamente spedito, evitando la copia anticipata. Tuttavia, questo metodo richiede operazioni di gestione aggiuntive e può causare copie aggiuntive se non implementato correttamente.

### Scelte per il Mittente

1. **Send Bloccante**: È la scelta più semplice e appropriata in molte situazioni, specialmente se sono disponibili thread multipli.
2. **Send Non Bloccante con Copia**: Evita il blocco del mittente, ma comporta un tempo CPU sprecato per la copia del messaggio.
3. **Send Non Bloccante con Interruzione**: Evita il blocco del mittente e la copia anticipata, ma la gestione delle interruzioni a livello utente può essere complicata e soggetta a corse critiche.
4. **Copia in Scrittura**: Evita il blocco del mittente e la copia anticipata, ma richiede operazioni di gestione aggiuntive e può causare copie aggiuntive.

La scelta migliore dipende dalle esigenze specifiche del sistema e dalle prestazioni desiderate.

### Considerazioni Aggiuntive

Altre considerazioni includono la distinzione tra primitive sincrone e asincrone, che può variare a seconda del contesto e delle definizioni adottate. Inoltre, il comportamento delle primitive di receive può essere sia bloccante che non bloccante, con conseguenze diverse sulla programmazione e sulle prestazioni del sistema.

### Conclusioni

Le primitive di scambio messaggi nei multicomputer offrono una varietà di opzioni per la comunicazione tra processi, ciascuna con vantaggi e svantaggi unici. È importante scegliere la strategia più adatta alle esigenze specifiche del sistema e valutare attentamente le prestazioni e la complessità dell'implementazione.
![[Pasted image 20240519123546.png]]