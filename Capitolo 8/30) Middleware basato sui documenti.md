#### Introduzione ai Middleware

Il middleware è uno strato software che si sovrappone alla rete di base, fornendo un'interfaccia consistente per le applicazioni e gli utenti. Si tratta di un livello intermedio tra il sistema operativo e le applicazioni, che facilita la comunicazione, la gestione dei dati e altre funzionalità distribuite. 

#### Esempio del World Wide Web

Un esempio significativo di middleware è il World Wide Web, inventato nel 1989 da Tim Berners-Lee al CERN. Il Web ha rivoluzionato il modo in cui accediamo e condividiamo informazioni.

#### Paradigma del Web

Il paradigma originale del Web è semplice: ogni computer può contenere uno o più documenti, chiamati pagine Web, che possono includere testo, immagini, icone, suoni, filmati e link ipertestuali (hyperlink) ad altre pagine Web. Quando un utente richiede una pagina Web tramite un browser, questa viene visualizzata sullo schermo; facendo clic su un link, la pagina corrente viene sostituita con quella selezionata. Il Web è essenzialmente un grande grafo diretto di documenti interconnessi tramite hyperlink.

#### Indirizzamento delle Pagine Web

Ogni pagina Web ha un indirizzo unico, chiamato URL (Uniform Resource Locator), che segue la forma:
```
protocollo://nome-DNS/nome-file
```
Il protocollo più comune è HTTP (Hypertext Transfer Protocol), ma esistono anche altri protocolli come FTP (File Transfer Protocol). Un URL completo specifica il protocollo, il nome DNS dell'host che contiene il file e il nome del file locale.

#### Funzionamento del Web

Il Web funziona su un modello client-server. L'utente rappresenta il client, e il sito Web rappresenta il server. Quando l'utente fornisce un URL al browser, questo esegue una serie di passi per recuperare la pagina Web richiesta. Ad esempio, per l'URL `http://www.acm.org/dl/faq.html`, il processo è il seguente:

1. Il browser interroga il DNS per ottenere l'indirizzo IP di `www.acm.org`.
2. Il DNS risponde con l'indirizzo IP, ad esempio `199.22.69.151`.
3. Il browser stabilisce una connessione TCP alla porta 80 dell'indirizzo `199.22.69.151`.
4. Richiede il file `dl/faq.html`.
5. Il server `www.acm.org` invia il file `dl/faq.html`.
6. La connessione TCP viene rilasciata.
7. Il browser visualizza il testo contenuto in `dl/faq.html`.
8. Il browser recupera e visualizza tutte le immagini contenute in `dl/faq.html`.

#### Evoluzione del Web

Il Web si è evoluto includendo molte caratteristiche aggiuntive rispetto al modello di base. Tra queste:

- **Foglio di stile (CSS):** Permettono di controllare la presentazione grafica delle pagine.
- **Pagine Web dinamiche:** Generate al momento in risposta alle interazioni dell'utente.
- **Script client-side:** Piccoli programmi eseguiti sul computer dell'utente, spesso scritti in linguaggi come JavaScript.

Questi avanzamenti, sebbene significativi, esulano dalla trattazione di base sul funzionamento del Web.

### Conclusione

Il Web rappresenta un esempio fondamentale di middleware che ha trasformato l'accesso e la condivisione delle informazioni. Comprendere il suo funzionamento di base e l'evoluzione offre una solida base per esplorare altri strati middleware e le loro applicazioni nelle reti di computer.
![[Pasted image 20240520083458.png]]