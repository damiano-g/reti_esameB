# Esempio di risoluzione — TCP/UDP

## Obiettivo
Mostrare un esercizio tipico su TCP con finestre, RTT e trasferimento dati.

## Esempio
Un file di `120 KB` deve essere trasmesso con TCP. Si assume:
- `MSS = 10 KB`
- `RTT = 100 ms`
- nessuna perdita
- finestra abbastanza ampia da non bloccare il trasferimento

## Procedura
1. Calcola quanti segmenti servono:
   - `120 KB / 10 KB = 12 segmenti`
2. In uno scenario semplificato, ogni RTT può completare un ciclo di invio e ACK.
3. Se la finestra è sufficiente, il limite principale diventa il numero di RTT necessari.
4. Con un approccio didattico base, si considera spesso un RTT iniziale di handshake o avvio, se richiesto dal testo.

## Risposta didattica
Il numero di segmenti è 12. Il tempo totale dipende dal numero di RTT richiesti dal testo e da eventuali fasi di avvio. In assenza di ulteriori vincoli, si imposta il calcolo per cicli RTT e si ottiene il trasferimento completo in più round.

## Osservazioni utili all’esame
- TCP richiede sempre attenzione a MSS, RTT e finestra.
- Conviene disegnare una timeline prima dei conti.
- UDP non ha la stessa dinamica di affidabilità e controllo di flusso di TCP.

## Errori comuni
- Confondere byte e bit.
- Dimenticare il numero di segmenti.
- Applicare formule senza dichiarare le ipotesi.
