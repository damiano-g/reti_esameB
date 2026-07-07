
#### Spiegare riga per riga la risposta ottenuta attraverso il comando nslookup

---

```
---

Got answer:
HEADER
opcode = QUERY, id=1, rcode=NOERROR
header flags: response, auth. answer, want recursion, recursion avail
questions=1, answrs=1, authority records=0, additional=0

QUESTIONS:
;query di tipo pointer su dominio di tipo reverse (addr.arpa): richiede il nome di dominio relativo al name server con indirizzo IP 159.149.70.7 (nb-> in nomi di dominio sono scritti con gerarchia inversa)
7.70.149.159.in-addr.arpa, type=PTR, class=IN 

ANSWERS:
;risposta da addr.arpa: il server si chiama ananke.crema.unimi.it
	-> 7.70.149.159.in-addr.arpa
	   name=ananke.crema.unimi.it
	   ttl=86400 (1 day)
	   
---

;risposta alla query
Server: ananke.crema.unimi.it
Address: 159.149.70.7

---

Got answer:
;header: definisce i flag e lo stato della richiesta
HEADER:

;ricevuta query con id=2 e codice risposta NOERROR
opcode = QUERY, id=2, rcode=NOERROR

;siamo all'interno di una risposta, è stata richiesta ricorsione e la ricorsione è disponibile (non si viene ricontattati fino al completamento della conversione)
header flags: response, want recursio, recursion avail.

;contiene una domanda, tre risposte, nessun record autorevole e tre addizionali
questions=1, answers=3, authority records=0, additional=3

QUESTIONS

[...]

ANSWERS:

;viene restituito il server di posta per il dominio unimi.it
-> unimi.it
   
   ;valore di preferenza (priorità) associato al server e nome del server
   MX preference=15, mail exchanger = unimix1.unimi.it
   
   ;durata in secondi della permanenza in cache del resource record
   ttl=59911 (16 hours 38 mins 31 secs)
   
AUTHORITY RECORDS
[...]

ADDITIONAL RECORDS

;restituisce l'indirizzo IP del server unimix.unimi.it
-> unimix.unimi.it
   internet address = 159.149.10.81
   ttl=59911 (16 hours 38 mins 31 secs)
```