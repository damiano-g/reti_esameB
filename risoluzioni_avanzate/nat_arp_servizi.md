# Esempio avanzato di risoluzione — NAT, ARP e servizi applicativi

## Traccia
Una LAN privata `192.168.1.0/24` usa un router con NAT e IP pubblico `203.0.113.5`.
Un client `192.168.1.10:49152` contatta un server web esterno `198.51.100.20:80`.
Il router effettua PAT (NAT con traduzione anche delle porte).
Descrivere:
1. cosa succede al pacchetto in uscita
2. come torna la risposta
3. dove entra in gioco ARP

## Procedura
### 1. Uscita dalla LAN
Il client invia:
- sorgente: `192.168.1.10:49152`
- destinazione: `198.51.100.20:80`

Il router sostituisce la sorgente con:
- `203.0.113.5:porta_nat`

La traduzione è registrata nella tabella NAT/PAT.

### 2. Risposta dal server
Il server risponde a:
- destinazione: `203.0.113.5:porta_nat`

Il router consulta la tabella NAT e ricostruisce l’associazione:
- verso interno: `192.168.1.10:49152`

### 3. Ruolo di ARP
Prima di inviare il frame sulla LAN, il router deve conoscere il MAC del next hop o del client. Se non lo conosce, emette una richiesta ARP in broadcast.

## Risposta didattica
Il pacchetto in uscita viene tradotto in IP pubblico con porta esterna associata. La risposta torna al router, che usa la tabella NAT per riscrivere la destinazione verso il client privato. ARP serve per la consegna a livello 2 nella rete locale.

## Errori tipici
- Dimenticare che con PAT cambiano anche le porte.
- Confondere il flusso verso l’esterno con quello di ritorno.
- Saltare il passaggio ARP quando il MAC non è noto.

## Come riconoscere il tema in prova
Parole chiave: `NAT`, `PAT`, `ARP`, `porta`, `IP pubblico`, `IP privato`, `socket`, `HTTP`.
