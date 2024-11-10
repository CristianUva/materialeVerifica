# Installazione di MariaDB e utilizzo su Visual Studio Code

## Installazione di MariaDB su Ubuntu
Per installare MariaDB su Ubuntu tramite terminale, segui questi passaggi:

1. Aggiorna l'elenco dei pacchetti:
   sudo apt update
   

2. Installa il server MariaDB, Node.js e npm
   sudo apt install mariadb-server nodejs npm
   

3. Avvia il servizio MariaDB:
   
   sudo service mariadb start
   

4. Esegui lo script di sicurezza per configurare MariaDB:
   
   sudo mysql_secure_installation
   

5. Segui le istruzioni per impostare la password di root e configurare altre opzioni di sicurezza. 
    Rispondi "yes" alle seguenti domande:
   - `Change the root password?` Rispondi "yes" e imposta la password desiderata.
   - `Reload privilege tables now?` Rispondi "yes".

6. Verifica che MariaDB sia in esecuzione:
   
   sudo service mariadb status
   

## Connessione a MariaDB con Visual Studio Code

### 1. Installa l'estensione SQLTools
   - Apri Visual Studio Code e cerca l'estensione SQLTools nel marketplace delle estensioni.
   - Installa SQLTools e, se richiesto, riavvia Visual Studio Code.

### 2. Installa il driver per MariaDB
   - Vai nelle impostazioni di SQLTools e cerca il driver SQLTools MariaDB/MySQL Driver.
   - Installa il driver specifico per MariaDB/MySQL.

### 3. Configura la connessione a MariaDB
   - Vai in SQLTools nella barra laterale di Visual Studio Code e seleziona Add New Connection.
   - Compila i campi di configurazione:
     - Connection Type: MySQL/MariaDB
     - Host: `localhost`
     - Port: `3306`
     - User: `root`
     - Password: la password impostata durante l'installazione
     - Database: specifica un database se ne hai già creato uno, altrimenti lascialo vuoto.
   - Clicca su Test Connection per verificare la connessione e poi salva.

### 4. Crea un nuovo database e una tabella
   - Una volta connesso, apri un nuovo file `.sql` o usa l'editor SQL di SQLTools.
   - Crea un database:
     sql
     CREATE DATABASE esempio_db;
     
   - Utilizza il database creato:
     sql
     USE esempio_db;
     
   - Crea una tabella di esempio:
     sql
     CREATE TABLE utenti (
         id INT PRIMARY KEY AUTO_INCREMENT,
         nome VARCHAR(50),
         email VARCHAR(100)
     );
     

### 5. Inserisci dati e fai query di selezione
   - Inserisci dei dati nella tabella:
     sql
     INSERT INTO utenti (nome, email) VALUES ('Mario Rossi', 'mario.rossi@example.com');
     INSERT INTO utenti (nome, email) VALUES ('Laura Bianchi', 'laura.bianchi@example.com');
     
   - Visualizza i dati inseriti con una query di selezione:
     sql
     SELECT * FROM utenti;
     

### 6. Salva ed esegui query rapidamente
   - SQLTools permette di salvare le query e di visualizzare i risultati nella stessa finestra di Visual Studio Code, facilitando l’esplorazione e gestione del database.

Ora puoi gestire facilmente il tuo database MariaDB tramite Visual Studio Code e SQLTools, eseguendo query direttamente dall'editor!
