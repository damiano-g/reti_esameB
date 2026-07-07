
#### Mostrare un esempio di comunicazione client server nel quale un client richiede al server POP3 l'elenco dei suoi messaggi e legge il messaggio numero 5. Mostrare tutte le richieste e risposte

---

```
telnet pop3server 110

S: +OK POP3 server ready

C: user damiano

S: +OK

C: pass 62349B

S: -ERR

C: pass 62349A

S: +OK

C: list

S: 1 1234
S: 2 5678
S: 3 9101
S: .

C: retr 3

S: -ERR

C: retr 3

S: <message 3 content>
S: .

C: quit

S: +OK goodbye
```