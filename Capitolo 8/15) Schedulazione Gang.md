La condivisione dello spazio ha il vantaggio di eliminare la multiprogrammazione e l'overhead del cambio di contesto, ma presenta lo svantaggio del tempo perso quando una CPU resta inattiva in attesa di diventare nuovamente pronta. Per risolvere i problemi di comunicazione tra thread di processi diversi, è stato sviluppato l'algoritmo ==di schedulazione gang.== 

La schedulazione gang prevede tre componenti principali:
1. I thread correlati sono schedulati come un'unità, chiamata gang.
2. Tutti i membri di una gang sono eseguiti simultaneamente su CPU diverse in timesharing.
3. Tutti i membri di una gang iniziano e finiscono le loro porzioni di tempo insieme.

Questo metodo funziona perché tutte le CPU sono sincronizzate e schedulate insieme all'inizio di ogni quanto di tempo. Se un thread si blocca, la CPU rimane inattiva fino alla fine del quanto.

L'esempio descritto illustra un sistema con sei CPU e cinque processi (A-E) per un totale di 24 thread pronti. Durante ogni intervallo di tempo, un gruppo di thread (una gang) è schedulato su tutte le CPU, garantendo che i thread possano comunicare efficacemente tra loro all'interno dello stesso quanto di tempo.

Questa strategia risolve il problema della comunicazione inefficiente, come mostrato nelle figure citate, assicurando che i thread di un processo possano inviare e ricevere messaggi senza i ritardi causati dall'indipendenza della schedulazione.

