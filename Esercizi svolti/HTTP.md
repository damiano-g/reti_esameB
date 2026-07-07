
#### Si consideri la seguente porzione di comunicazione tra client e server. Spiegare il significato di ogni riga.

---

```telnet
% telnet www.wordreference.com 80 ;porta 80 è server web
Trying 208.43.111.96... ;tradotto con DNS
Connected to www.wordreference.com.
Escape character is '^]'. ;carattere di escape utilizzato per inviare comandi al server telnet

;richiesta: richiede solo gli header della pagina www.wordreference.com (enit) con protocollo 1.0 
HEAD /enit/INTERNET HTTP/1.0

;la pagina è stata trovata; il server è in attesa di un altro comando. Il server utilizza il protocollo HTTP1.1
HTTP/1.1 302 Found

;viene usata una cache privata ovvero ricevuta dall'utente specifico che ha effettuato la richiesta
Cache-Control: private

;lunghezza del contenuto
Content-Length: 133

;tipo di contenuto testo html con codifica utf-8
Content-Type: text/html; charset=utf-8

;la pagina o una sua parte è reperibile all'indirizzo http://yahoo.com
Location: http://yahoo.com

Server: Microsoft-IIS/7.0

;tipo di software utilizzato; gli header che iniziano con la X non sono standard, ma vengono utilizzati dal server per dare informazioni più specifiche sul server stesso
X-AspNet-Version: 2.0.50727

;l'oggetto setta i cookie all'interno della macchina dell'utente
Set-Cookie: domain=www.wordewference.com; expires=<date>; path=/

;data di ultima modifica della pagina; utile per get condizionali con modified since
Last-Modified: <date>

Date: <date>

;chiusura della connessione. NB->HTTP1.0 utilizza connessioni persistenti, quindi necessita sempre della chiusura esplicita. HTTP1.1 è connectionless quindi non necessita di chiusura esplicita
Connection: close
```