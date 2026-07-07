
[[reti2-2019-05-15-16.01.20.mp4]]

#### Si predisponga un file di zona di un DNS che contiene tutte le informazioni sulle macchine che compongono il dominio example.sistemi.org come di seguito specificato

- Un resource record di tipo SOA con name server primario **ns1.example.sistemi.org**
- Due resource record di tipo NS per il name server primario **ns1.example.sistemi.org** ed il name server secondario **ns2.example.sistemi.org**
- Due resource record di tipo MX per il mail exchanger **mx.example.sistemi.org** e **mail.example.sistemi.org**
- Quattro resource record di tipo A per l'assegnamento degli indirizzi IP alle macchine del dominio: (1) name server ns1 con indirizzo 192.168.1.2; (2) name server ns2 con indirizzo 192.168.1.3; (3) mail exchanger mx con indirizzo 192.168.1.4; (4) mail exchanger mail con indirizzo 192.168.1.5
- Si supponga che i servizi www e ftp siano accessibili sulla macchina 192.168.1.6 (example.sistemi.org). Utilizzare alias e canonical name per la risoluzione dei nomi

---

```
; direttive del file di zona

;per tutti i record che non hanno un fully qualified name (terminano con punto) vengono espansi con il contenuto della direttiva ORIGIN
$ORIGIN example.sistemi.org.

; direttiva che indica il TTL, ovvero la durata in secondi dei resource record in cache
$TTL 3600

;SOA (Start Of Authority): definizione del server autorevole per la zona
example.sistemi.org. IN SOA ns1.example.sistemi.org. admin.example.sistemi.org. (
	
	;componenti del SOA
	
	;seriale: identifica la versione del file di zona. NB->può essere modificato unicamente dal master  
	321646516874654
	
	;refresh time: specifica in secondi l'intervallo con cui gli slave controllano la presenza di un nuovo file di zona e scaricano la versione più aggiornata
	10800
	
	;retry: tempo di attesa in secondi prima di un nuovo tentativo successivamente ad un refresh fallito
	3600
	
	;expire: timer che indica la scadenza della validità della versione corrente del file di zona; alla scadenza il server smette di tradurre
	604800
	
	;minumum TTL: sovrascrive il TTL di default
	86400
)

;resource record di tipo NS; specifica i server primario e secondario per la zona example.sistemi.org.
;Struttura: <etichetta_zona>  <TTL>(opzionale, sovrascrive default) IN <tipo>(NS->Name Server) <indirizzo del server>
example.sistemi.org.   2400 IN NS ns1.example.sistemi.org. ;primario 
example.sistemi.org.		IN NS ns2.example.sistemi.org. ;secondario
;è possibile inserire un NS esterno alla zona di autorità (dominio esterno); se una query punta al ns esterno, viene generata e inviata una nuova query al ns esterno stesso, che ritorna il proprio ip (stessa cosa per MX); ad esempio
example.sistemi.org.        IN NS ns1.google.com

;resource record di tipo MX: specificano i mail exchanger per la zona
;Struttura: <etichetta_zona>  <TTL>(opzionale, sovrascrive default) IN <tipo>(MX->Mail exchanger) <Priorità>(Numerico. Determina la distribuzione del carico di lavoro - inversamente proporzionale) <nome del server>
example.sistemi.org.   IN MX 10 mx.example.sistemi.org. ;primario 
example.sistemi.org.   IN MX 20 mail.example.sistemi.org. ;secondario
;è possibile inserire un MX esterno alla zona di autorità (dominio esterno)

;resource record di tipo A: specifica gli indirizzi IP delle macchine di dominio
;Struttura: <nome del server>  <TTL>(opzionale, sovrascrive default) IN <tipo>(A) <ip> 
ns1  IN A 192.168.1.2
ns2  IN A 192.168.1.3
mx   IN A 192.168.1.4
mail IN A 192.168.1.5
; non vengono inseriti gli IP di eventuali server esterni (vedi sopra)

;www e ftp sono alias per il canonical name example.sistemi.org.
www IN CNAME example.sistemi.org.
ftp IN CNAME example.sistemi.org.

example.sistemi.org. IN A 192.168.1.6
```