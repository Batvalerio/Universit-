1. ==**Schedulazione Monodimensionale e Bidimensionale**:== In un monoprocessore, la schedulazione è monodimensionale, dove la domanda principale è “qual è il prossimo processo da eseguire?”. In un multiprocessore, la schedulazione diventa bidimensionale, dove lo schedulatore deve decidere non solo quale processo eseguire, ma anche su quale CPU eseguirlo.
    
2. ==**Processi Correlati e Non Correlati**:== In alcuni sistemi, tutti i processi non sono correlati (ad esempio, nei sistemi time-sharing), mentre in altri lo sono (ad esempio, negli ambienti di sviluppo dei programmi). Questo può complicare ulteriormente la schedulazione.
    
3. ==**Uso del Programma Make**:== Il programma make è comunemente usato per gestire l’ambiente di sviluppo. Quando si lancia, make inizia la compilazione solo di quei file di codice da ricompilare, tenendo conto dei cambiamenti ai file header o di codice.
    
4. ==**Schedulazione in Multiprocessori**:== Le versioni più recenti di make, progettate per multiprocessori, possono iniziare tutte le compilazioni contemporaneamente. In questo caso, ha senso considerare i processi come un gruppo e tenerne conto durante la schedulazione.
