Passando ai sistemi distribuiti, entriamo in un ambito dove la comunicazione e la cooperazione tra nodi separati fisicamente svolgono un ruolo centrale. Rispetto ai multicomputer, i sistemi distribuiti presentano diverse caratteristiche distintive:

1. **Struttura dei nodi**: Nei sistemi distribuiti, ogni nodo è un computer completo con una gamma completa di periferiche, a differenza dei multicomputer in cui i nodi sono più specializzati.

2. **Distanza geografica**: Mentre i multicomputer possono trovarsi fisicamente vicini, magari nella stessa stanza, i nodi dei sistemi distribuiti possono essere disseminati ovunque nel mondo e collegati tramite Internet.

3. **Esecuzione del software**: Nei multicomputer, tutti i nodi eseguono lo stesso sistema operativo, condividono un unico file system e appartengono a un'amministrazione comune. Nei sistemi distribuiti, i nodi possono eseguire diversi sistemi operativi, ognuno con il proprio file system, e appartenere a amministrazioni diverse.

4. **Accoppiamento dei nodi**: Nei sistemi distribuiti, i nodi sono generalmente più debolmente accoppiati rispetto ai multicomputer. Questo può essere sia un vantaggio, consentendo una maggiore flessibilità nelle applicazioni, sia una sfida, rendendo più complessa la programmazione a causa della mancanza di un modello comune.

Le applicazioni tipiche dei sistemi distribuiti includono l'accesso a computer remoti tramite telnet e rlogin, l'accesso a informazioni tramite il World Wide Web e FTP, la comunicazione da persona a persona attraverso chat e posta elettronica, e molte altre. Tuttavia, ogni applicazione deve affrontare la sfida di coordinare le operazioni su macchine distanti, spesso con hardware e sistemi operativi eterogenei.

Per fornire un'interfaccia uniforme su una rete eterogenea, i sistemi distribuiti utilizzano spesso un middleware, uno strato di software sopra il sistema operativo che fornisce strutture dati e operazioni per consentire a processi e utenti su macchine remote di interagire in modo coerente.

In sostanza, i sistemi distribuiti mirano a trasformare un insieme di computer debolmente connessi in un sistema coerente basato su un concetto comune. Questo può essere raggiunto attraverso l'implementazione di middleware e protocolli di comunicazione che facilitano la cooperazione tra i nodi del sistema.
![[Pasted image 20240519151942.png]]![[Pasted image 20240519152016.png]]