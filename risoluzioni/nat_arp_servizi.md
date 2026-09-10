# Esempio di risoluzione — NAT, ARP e servizi applicativi

## Obiettivo
Mostrare una traccia tipica con NAT e risoluzione ARP.

## Esempio
Un host interno `192.168.1.10` deve raggiungere un server esterno. Il router effettua NAT con IP pubblico `203.0.113.5`.

## Procedura
1. L’host interno invia il pacchetto con indirizzo sorgente privato.
2. Il router sostituisce l’IP sorgente privato con l’IP pubblico e, se necessario, modifica anche la porta.
3. Se il router non conosce il MAC del next hop nella rete locale, usa ARP per risolverlo.
4. La risposta di ritorno viene tradotta nella direzione opposta grazie alla tabella NAT.

## Risposta didattica
All’esterno il traffico appare provenire da `203.0.113.5`, mentre all’interno la connessione resta associata a `192.168.1.10` e alla porta privata corrispondente.

## Osservazioni utili all’esame
- NAT modifica l’indirizzo sorgente, spesso anche la porta.
- ARP serve per associare IP e MAC nella rete locale.
- Le tabelle NAT vanno lette in entrambe le direzioni.

## Errori comuni
- Confondere indirizzo privato e pubblico.
- Saltare i passaggi ARP.
- Non distinguere livello 2 e livello 3.
