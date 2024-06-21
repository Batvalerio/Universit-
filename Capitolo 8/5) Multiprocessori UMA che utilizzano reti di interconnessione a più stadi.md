- Un’architettura multiprocessore completamente diversa è basata sulla ==**connessione 2 x 2**==, che ha due ingressi e due uscite. I messaggi che arrivano a una qualsiasi delle linee di ingresso possono essere smistati a ciascuna delle linee di uscita.
- I messaggi contengono fino a quattro parti: il campo ==**Modulo**== indica quale memoria usare, l==’**Indirizzo**== specifica un indirizzo entro il modulo, ==il **Codice Operativo**== indica l’operazione (come READ o WRITE), e il campo opzionale ==**Valore**== può contenere un operando, cioè una parola a 32 bit che deve essere scritta con un WRITE.
- Le connessioni 2 x 2 possono essere sistemate in molti modi per costruire reti di connessione a più stadi più ampie. Una possibilità è la semplice ed economica classe delle ==**reti omega**.== 
- Nelle reti omega, abbiamo otto CPU connesse a otto memorie, attraverso dodici connessioni. Più in generale, per n CPU e n memorie, sono necessari
    
    \log nlogn
    
    stadi con
    
    n/2n/2
    
    connessioni per stadio, per un totale di
    
    (n/2) \log n(n/2)logn
    
    connessioni. Questo è molto meglio di
    
    n^2n2
    
    punti di incrocio, specialmente per grandi valori di n.
![[Pasted image 20240516173109.png]]                                                                            
- Lo schema di collegamento ==della **rete omega**== è spesso chiamato ==**mescolamento perfetto**== (perfect shuffle), poiché la miscela dei segnali in ciascuno stadio ricorda un mazzo di carte tagliato e quindi mescolato carta per carta.
- Per vedere come funziona una rete omega, si considera un esempio in cui la CPU 011 vuole leggere una parola dal modulo di memoria 110. La CPU manda un messaggio READ alla connessione 1D, contenente 110 nel campo Modulo. Lo switch prende il primo bit di 110 e lo usa per l’instradamento.
- Man mano che il messaggio si muove attraverso le reti di connessione, i bit della parte sinistra del numero del modulo non sono più necessari. È possibile in ogni caso utilizzarli, registrando nella rete di interconnessione il numero di linea entrante, in modo che la risposta possa trovare la propria via al ritorno.
- Nello stesso tempo in cui tutto questo sta avvenendo, la CPU 001 vuole scrivere una parola nel modulo di memoria 001. Qui avviene un processo analogo, con il messaggio instradato rispettivamente attraverso le uscite superiore, superiore e inferiore.
- Se la CPU 000 volesse contemporaneamente accedere al modulo di memoria 000, la sua richiesta cadrebbe in conflitto con quella della CPU 001 a livello della connessione 3°, ed una di esse dovrebbe aspettare. A differenza dell’interruttore crossbar, la rete omega è ==una **rete bloccante**==, cioè non tutti gli insiemi di richieste possono essere elaborati simultaneamente.
- È chiaramente desiderabile diffondere i riferimenti alla memoria in modo uniforme per tutti i moduli: una tecnica comune consiste nell’utilizzare i bit di ordine basso come numeri del modulo. I sistemi di memoria in cui parole consecutive sono in moduli differenti, sono detti ==**interallacciati**==; le memorie interallacciate massimizzano il parallelismo.
- È anche possibile progettare reti di connessione che siano non bloccanti e che offrano più cammini da ciascuna CPU a ciascun modulo di memoria, per distribuire meglio il traffico 