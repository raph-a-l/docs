---
title: Configura il tuo database server 
slug: configurare-ottimizzare-il-tuo-database-server
excerpt: Come configurare e ottimizzare il tuo database server
section: CloudDB
order: 6
---

**Ultimo aggiornamento: 03/02/2022**

## Obiettivo

I database server Cloud Database ti danno la possibilità di agire sui parametri globali del tuo server. Inoltre, è possibile visualizzare l'attività del server. 

**Questa guida ti mostra come configurare e ottimizzare il tuo database server.**

## Prerequisiti

- Disporre di un [Cloud Database](https://www.ovh.it/cloud-databases/)
- Avere accesso allo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it)

## Procedura

### Visualizza le informazioni generali del tuo database server

Nel menu a sinistra del tuo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it), clicca su Database` nella sezione `{.action}Database e seleziona l'istanza SQL. Assicurati di trovarti nella scheda `Informazioni generali`{.action}.

In questa interfaccia vengono mostrate anche le informazioni principali della tua istanza SQL. Ti consigliamo di verificarne la correttezza e assicurarti che corrispondano alle descrizioni indicate qui sotto:

|Informazione|Descrizione|
|---|---|
|Stato del servizio|Indica se l'istanza è attiva, in corso di riavvio o sospesa. Per poter eseguire operazioni, l’istanza deve essere attiva.|
|Tipo|Indica il sistema di database utilizzato dal server. MySQL è il più diffuso, ma ne esistono anche altri (come PostgreSQL e MariaDB). Ad esempio, se il tuo sito è un WordPress, il sistema MySQL è perfetto.|
|Versione|Indica la versione del sistema di database utilizzato dal server. Ti ricordiamo di verificare la compatibilità del tuo sito con la versione scelta.|
|RAM|Indica la memoria disponibile sulla tua istanza e segnala l’eventuale raggiungimento della soglia limite. I database server dispongono di risorse dedicate e garantite: la sua memoria RAM. Se necessario, è possibile aumentarla e ricevere una notifica in caso di utilizzo di tutte le risorse disponibili.|
|Infrastruttura|Indica l’infrastruttura utilizzata dall’istanza. Questa informazione è relativa all'infrastruttura di OVHcloud.|
|Datacenter|Indica il datacenter in cui è stata creata l’istanza. Assicurati che il datacenter dell'istanza sia lo stesso dell'hosting Web OVHcloud in cui è (o sarà) ospitato il tuo sito.|
|Host|Indica il server OVHcloud in cui è stata creata l'istanza. Questa informazione è relativa all'infrastruttura OVHcloud e può essere utilizzata nelle comunicazioni relative agli [incidenti](https://web-cloud.status-ovhcloud.com/).|

![Informazioni generali](images/privatesql01-General-information.png){.thumbnail}

### Autorizza un indirizzo IP (solo sull'offerta Cloud Databases)

Per il corretto funzionamento dell'accesso alla tua istanza CloudDB, è necessario indicare gli indirizzi IP o le classi di IP che possono connettersi ai tuoi database.

nel menu a sinistra del tuo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it), seleziona `Database`{.action} > Istanza SQL corrispondente. 

Clicca sulla scheda `IP autorizzati`{.action} e poi sul pulsante `Aggiungi un indirizzo IP/mask`{.action}.

![Clouddb](images/clouddb-add-ip.png){.thumbnail}

Nella finestra che appare indica l’indirizzo IP o la mask da autorizzare in `IP/mask`{.action} e poi, se vuoi, aggiungi una descrizione. Decidi se vuoi fornire un accesso soltanto ai database o anche via SFTP. Infine clicca su `Conferma`{.action}.

![Clouddb](images/clouddb-add-ip-step2.png){.thumbnail}

#### Autorizza la connessione a un hosting Web OVHcloud 

Per gli hosting Web OVHcloud è necessario autorizzare l'indirizzo IP gateway di uscita. 

Per recuperare l'indirizzo IP "**gateway**" accedi al tuo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi `su Hosting`{.action} nella colonna di sinistra. Seleziona il tuo hosting dalla lista e clicca sulla scheda `FTP - SSH`.

Ritrova la voce **"Server FTP"**, che ti indicherà il numero di cluster su cui sei, come mostrato qui di seguito.

![Clouddb](images/clouddb-add-ip-step3.png){.thumbnail}

Dopo aver recuperato il numero del cluster su cui è situato il tuo hosting, consulta la pagina ["Elenco degli indirizzi IP dei cluster e degli hosting Web"](../lista-indirizzi-ip-di-cluster-e-hosting-web/). In questa interfaccia è possibile trovare l'indirizzo IP "**gateway di uscita**" di ciascun cluster.

> [!warning]
>
> **L'indirizzo IP** del cluster non funzionerà per autorizzare la connessione al server Cloud DB, è necessario aggiungere **l'indirizzo IP "gateway di uscita"**.
>


### Modifica l'offerta del database server

Per modificare l'offerta del tuo database server, accedi al tuo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi su `Database`{.action} nel pannello di sinistra. Seleziona il nome del tuo database server.
Nella scheda **"Informazioni generali"**, visualizzata di default, clicca su `...`{.action} a destra della voce "RAM" e poi su `Modifica la quantità di RAM`{.action} per accedere all'ordine di questo passaggio.

![clouddb](images/private-sql-order-ram01.png){.thumbnail}

Scegli la quantità di RAM desiderata e clicca su `Seguente`{.action}. e scegliere la durata scelta.

> [!primary]
>
> Se hai ancora qualche mese prima della scadenza, verrà effettuato un prorata.
> Questo prorata sarà basato sulla data di scadenza del server CloudDB e non su quello del buono d'ordine.
> 

Dopo la conferma dei contratti, verrai reindirizzato al buono d'ordine da cui sarà possibile pagare la modifica. L'operazione diventerà effettiva entro qualche ora.

> [!warning]
>
>  Se disponi attualmente di un server CloudDB gratuito grazie al tuo
> hosting Performance, la modifica dell'offerta ti farà perdere la sua
> gratuità.
> 

### Modifica la configurazione del tuo database server

Accedi allo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi su `Database`{.action} nel pannello di sinistra. Seleziona il nome del tuo server CloudDB. 

#### Istanza MySQL e MariaDB

- Clicca sulla scheda `Configurazione`.

Nel riquadro **"Configurazione generale di MySql"** troverai la configurazione attualmente definita per il tuo database. Puoi modificarla direttamente e cliccare su `Applica`{.action}.

![clouddb](images/private-sql-config02.png){.thumbnail}

- **Temp**: Directory dei file temporanei. **/dev/shm** corrisponde alla memoria RAM dell'istanza. **/tmp** corrisponde all'hard disk dell'istanza.
- **MaxAllowedPacket**: Dimensione massima dei pacchetti
- **Max_user_connections**: Numero di connessioni simultanee autorizzate per utente.
- **AutoCommit**: Definisce se le richieste sono automaticamente confermate (committed) o no.
- **Interactive_timeout**: Tempo in secondi durante il quale il server attende l'attività su una connessione interattiva prima di chiuderla.
- **InnodbBufferPoolSize**: Scelta della dimensione della memoria buffer.
- **MaxConnessioni:** Numero di connessioni simultanee autorizzate sul database.
- **Wait_timeout**: Tempo in secondi durante il quale il server attende l'attività su una connessione non interattiva prima di chiuderla.
- **Event_scheduler**: Consente di avviare l'esecuzione di richieste programmate direttamente sul server MySQL.
- **sql_mode** : L'opzione **sql_mode** influisce sull'interpretazione della sintassi SQL e sulle verifiche di convalida dei dati eseguite da MySQL/MariaDB. Uniquement disponible pour MariaDB.

> [!primary]
> Quando si verifica un errore sul tuo sito indicando **"Too many connections"**, è dovuto al superamento del numero di connessioni simultanee sul tuo database.
> In questo caso, puoi aumentare la variabile **"MaxConnections"** se non è al massimo.
>

> [!primary]
>
> <b>Tmpdir</b>:  
> \- /dev/shm: Il database server assegnerà metà della memoria RAM a questa directory per ottenere migliori performance.
>
> \- /tmp: Il server assegnerà sul suo hard disk uno spazio illimitato per questa directory, ma sarà molto meno performante. Ti consigliamo di utilizzare questa directory solo per operazioni occasionali di grande impatto.
>

> [!primary]
>
> sql_mode :
> - NO_ENGINE_SUBSTITUTION,NO_AUTO_CREATE_USER : Mode par défaut de MariaDB 10.1.
> - STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION : Mode par défaut de MariaDB 10.2 et supérieur.
>
> Nous vous recommandons de toujours utiliser le mode par défaut, sauf si votre base de données a été mis à jour depuis une version ayant un mode par défaut différent de la version actuelle.
>

Effettua le modifiche necessarie e clicca su `Conferma`{.action}.

> [!warning]
>
> Qualsiasi modifica richiede il riavvio del database server.
> 

#### Instance PostgreSQL

Non è possibile modificare la configurazione di un'istanza PostgreSQL. 

ma è possibile attivare estensioni sui database. Clicca sulla scheda `Database`, poi sull'icona della tabella del tuo database sotto la colonna "**Estensioni"**

![clouddb](images/private-sql-config03.png){.thumbnail}

### Modifica la versione MySQL, PostgreSQL o MariaDB del database server

Per conoscere la versione di MySQL, PostgreSQL o MariaDB del Vostro database server, dovete collegarvi alla scheda **"Informazioni generali"** dopo aver scelto il Vostro database server.

La versione attuale compare nella riga **"Versione"**.

Per modificare questa versione, clicca su `Modifica la versione`{.action}.

![clouddb](images/private-sql-config04.png){.thumbnail}


#### **Come conoscere la versione esatta di PostgreSQL che uso?**

Inserisci questo comando in phpPgAdmin cliccando sul **tuo database**, rubrica **"SQL"**, poi su `Esegui`{.action}:

```
select version();
```

####  **Come conoscere la versione esatta del mySQL o MariaDB che uso?**

Per effettuare questa operazione, inserisci questo comando in phpMyAdmin, sezione **"SQL"**, poi clicca su `Esegui`{.action}:

```
show variabili like "version";
```

> [!primary]
>
> - Prima di passare a una versione superiore, assicurati che il tuo database sia compatibile con la versione scelta.
> - La modifica è effettiva in pochi minuti.
>

> [!warning]
>
> Non è possibile passare da una versione precedente all'ultima
> direttamente. È obbligatorio passare per tutte le versioni intermedie.
> 

### Log e Metriche

#### Conoscere il tempo di esecuzione delle richieste

In questo modo è possibile visualizzare il tempo di esecuzione delle richieste sul tuo database server nelle ultime 24 ore.

Accedi allo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi su `Database`{.action} nel pannello di sinistra. Seleziona il nome del tuo database server. 

Clicca sulla scheda `Metriche` del tuo database server. Il grafico **"Statistiche dei tempi di esecuzione delle richieste"**.

![clouddb](images/private-sql-metrics01.png){.thumbnail}

#### Accesso ai log "Slow Query"

> **Definizione di "slow query log"**
> 
> Le richieste richiedono più tempo per essere eseguite. Il valore è definito a 1 secondo sui nostri database server nella variabile **"long_query_time"**.

Questi log, chiamati **"slow-query.log"**, possono essere recuperati alla radice dello spazio SFTP del tuo database server. 

Accedi allo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi su `Database`{.action} nel pannello di sinistra. Seleziona il nome del tuo database server. 

Nella scheda `informazioni generali`, consulta la sezione **"SFTP"** nel riquadro **"Informazioni di connessione"**

![clouddb](images/private-sql-SFTP01.png){.thumbnail}

Per effettuare l'accesso via **SFTP**, è possibile utilizzare Filezilla utilizzando la guida: [ Utilizzo del software FileZilla con il tuo hosting]( ../hosting_condiviso_guida_allutilizzo_di_filezilla/).

Se questo file è vuoto, significa che non hai richieste lente.


#### Monitora la RAM consumata

Accedi allo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi su `Database`{.action} nel pannello di sinistra. Seleziona il nome del tuo database server. 

Clicca sulla scheda `Metriche` dello Spazio Cliente. Il grafico **"Statistiche della memoria RAM utilizzata"**.

![clouddb](images/private-sql-metrics02.png){.thumbnail}

#### Controlla il numero di connessioni al minuto

Questo grafico permette di seguire, nelle ultime 24 ore, il carico di connessione al minuto sul tuo database server.

Accedi allo [Spazio Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.it/&ovhSubsidiary=it). Clicca sulla scheda `Web Cloud` e poi su `Database`{.action} nel pannello di sinistra. Seleziona il nome del tuo database server. 

Clicca sulla scheda `Metriche` dello Spazio Cliente. Il grafico **"Statistiche del totale delle connessioni al minuto"**.

![clouddb](images/private-sql-metrics03.png){.thumbnail}

### Ottimizza i tuoi database

 Si consiglia di mantenere il proprio database in modo da renderlo efficiente. Ciò che si intende per prestazione è che le informazioni contenute nel database sono reindirizzate il più rapidamente possibile allo script che le richiede. Per fare ciò, è necessario un database strutturato e ottimizzato.

#### **Indicizza il database**

Per aumentare la rapidità delle ricerche in caso di una richiesta, è necessario inserire un indice sui campi utilizzati nelle clausole WHERE.

Esempio: fate regolarmente una ricerca di persona sulla città. Inserisci il campo "Città" con questa richiesta:

```bash
ALTER TABLE `test` ADD INDEX ( `città`)
```
#### **Elimina il database**

Alcuni dei tuoi dati non sono più utilizzati? Archiviateli, le vostre tabelle saranno meno piene e le ricerche saranno più veloci.

#### **Limitazione della visualizzazione**

Limita la visualizzazione dei record a un numero limitato (ad esempio 10 per pagina) con la sezione LIMIT della tua richiesta SQL.

#### **Raggruppamento delle richieste**

Raggruppa le tue richieste all'inizio dello script in questo modo:

```bash
connexion_base
richiesta1
requete2
...
disconnessione_base
Visualizzazione ...
Trattamento dei dati
Canali ...
Visualizzazione ...
...
```
#### **Recupera solo i dati utili**

Nelle tue richieste SQL, verifica di selezionare solo quello di cui hai bisogno e soprattutto di non aver dimenticato i collegamenti tra le tabelle.

Esempio:

```bash
(where table1.record = tavolo2.record2)
```

#### **Evitare opzioni che utilizzano troppe risorse**

Evita di utilizzare **"HAVING"**, ad esempio. Aumenta le tue richieste. Allo stesso modo, evita di utilizzare **"GROUP BY"**, tranne quando ciò sia strettamente necessario.

## Per saperne di più

[Elenco degli indirizzi IP di cluster e hosting Web](../lista-indirizzi-ip-di-cluster-e-hosting-web/)

Contatta la nostra Community di utenti all’indirizzo <https://community.ovh.com>.


