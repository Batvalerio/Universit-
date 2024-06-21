Nel contesto dei multicomputer, i processi comunicano scambiandosi messaggi. Questo scambio può avvenire in due modi principali: attraverso chiamate di sistema visibili ai processi utente o attraverso un'astrazione più sofisticata che nasconde la comunicazione remota come chiamate di procedura.

#### Metodo delle Chiamate di Sistema

Nei multicomputer, la comunicazione tra processi può essere semplificata a due chiamate di libreria:

1. **Send**: Per inviare un messaggio a un processo destinatario.
   - **Chiamata**: `send(dest, &mptr)`
   - **Descrizione**: Invia il messaggio puntato da `mptr` al processo identificato da `dest`. Il chiamante viene bloccato fino a quando il messaggio non viene spedito.

2. **Receive**: Per ricevere un messaggio.
   - **Chiamata**: `receive(addr, &mptr)`
   - **Descrizione**: Blocca il chiamante finché non arriva un messaggio. Quando arriva, il messaggio viene copiato nel buffer puntato da `mptr`, e il chiamante viene sbloccato. Il parametro `addr` specifica l'indirizzo su cui il ricevente è in ascolto.

Queste chiamate di sistema possono avere molte varianti nei parametri e nelle modalità di utilizzo.

#### Indirizzamento nei Multicomputer

L'indirizzamento dei processi nei multicomputer è un aspetto critico. Una soluzione comune è rendere l'indirizzo (`addr`) un valore composto da due parti: il numero della CPU e il numero del processo o della porta sulla CPU destinataria. In questo modo, ogni CPU può gestire i propri indirizzi senza conflitti potenziali.

### Conclusioni

La comunicazione tra processi nei multicomputer può essere gestita attraverso chiamate di sistema visibili ai processi utente o attraverso un'astrazione più sofisticata che nasconde la complessità della comunicazione remota. L'indirizzamento è cruciale per garantire che i messaggi raggiungano il destinatario corretto senza conflitti.