
#### Si descriva passo passo una comunicazione FTP passiva che utilizza i seguenti parametri

- username: nome dello studente
- password: matricola dello studente
- indirizzo del client: 135.22.48.77 porta 52397
- indirizzo del server: 77.105.33.1 porta 1928
- comando inviato: ls

---

```
ftp ftpserver

;comando USER consente di inviare lo username
C: USER damiano.ghibaudo

;risposta del server: risposta in formato machine readable e human readable (codici 3xx comunicano successo della comunicazione, ma richiedono ulteriori passaggi)
S: 331 Guest login ok

;comando PASS consente di inviare la password dell'utente
C: PASS 62349A

;server comunica successo del processo di autenticazione (machine/human readable)
S: 230 Logged in

;il cliente chiede al server di utilizzare la modalità passiva e aspetta dal server indirizzo e porta su cui contattarlo per stabilire la connessione dati
C:PASV

;server comunica successo comunicazione e che è entrato in modalità passiva e invia il suo indirizzo ip ed il numero della porta (il numero della porta è indicato come il risultato della divisione intera con modulo <numPortaDecimale>/256)
S: 227 entering passive mode (77,105,33,1,7,136)

;client invia il comando ls
C: LS

;server comunica l'accettazione della richiesta del client ed esegue il comando
S: 150 data connection accepted from the client
<lista di file e directory>

;server comunica che le azioni richieste sono state eseguite con successo
S: 226 listing completed

;client comunica la ricezione dei dati tramite ftp
C: ftp:151bytes received in XXXseconds 151kbyte per sec

;client richiede la chiusura della connessione
C: QUIT

;server comunica la corretta ricezione del comando e l'avvenuta chiusura della connessione 
S: 221 Goodbye
```

---

#### Come cambierebbe la comunicazione presentata se si passasse da modalità passiva ad attiva?

```
ftp ftpserver

C: USER damiano.ghibaudo

S: 331 Guest login ok

C: PASS 62349A

S: 230 Logged in

;il client richiede comunicazione attiva e richiede al server di stabilire la connessione sul proprio indirizzo ip alla porta 52397
C:PORT 135,22,48,77,204,173

;server comunica la corretta ricezione del comando e di aver stabilito la connessione
S: 200 PORT command successful

C: LS

S: 150 data connection accepted from the client
<lista di file e directory>

S: 226 listing completed

C: ftp:151bytes received in XXXseconds 151kbyte per sec

C: QUIT
 
S: 221 Goodbye
```