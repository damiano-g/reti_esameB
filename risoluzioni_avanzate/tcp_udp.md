# Esempio avanzato di risoluzione — TCP/UDP

## Traccia
Un host deve inviare un file di `900 KB` su TCP.
Dati:
- `MSS = 1000 byte`
- finestra di congestione iniziale: `1 MSS`
- `RTT = 50 ms`
- nessuna perdita
- si trascurano gli header, salvo richiesta esplicita

Calcolare:
1. numero di segmenti
2. andamento semplificato dell’invio
3. tempo minimo teorico di trasferimento in un modello a finestre per RTT

## Procedura
### 1. Numero di segmenti
`900 KB = 900 × 1024 = 921600 byte`

`921600 / 1000 = 921,6`

Servono **922 segmenti**.

### 2. Lettura del problema
Il testo suggerisce un modello a finestre con crescita nel tempo. In una soluzione d’esame bisogna sempre dichiarare se si assume:
- finestra fissa
- slow start
- finestra sufficiente a non limitare l’invio

Qui, in assenza di ulteriori dettagli, si usa una stima teorica di base: ogni RTT consente almeno un avanzamento del trasferimento, ma la finestra iniziale da 1 MSS richiede più round per crescere.

### 3. Impostazione della soluzione
- Disegnare la timeline in RTT.
- Contare quanti segmenti entrano in ciascun round.
- Verificare quando il trasferimento termina.

## Risposta didattica
Il valore certo è il numero di segmenti: **922**.
Il tempo totale dipende dal modello TCP richiesto dal testo; se viene specificato slow start, va simulata la crescita della finestra RTT per RTT.

## Variante UDP
Se lo stesso file fosse inviato in UDP, non avresti handshake TCP né controllo di congestione end-to-end come in TCP; il problema si ridurrebbe a un semplice calcolo di trasmissione e di eventuali ritardi di rete.

## Errori tipici
- Usare KB come se fossero 1000 byte senza controllare il contesto.
- Dimenticare che TCP richiede una modellazione per round.
- Risolvere senza fissare le ipotesi sul comportamento della finestra.

## Come riconoscere il tema in prova
Parole chiave: `MSS`, `RTT`, `window`, `slow start`, `ACK`, `segmenti`, `UDP`.
