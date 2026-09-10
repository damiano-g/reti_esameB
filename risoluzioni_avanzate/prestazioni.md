# Esempio avanzato di risoluzione — Prestazioni, throughput e congestione

## Traccia
Un collegamento tra sorgente e destinazione è composto da due link in serie:
- Link 1: `100 Mbps`
- Link 2: `20 Mbps`

Si deve trasferire un file di `200 Mbit`.
Il ritardo di propagazione totale è `30 ms`.
Calcolare:
1. collo di bottiglia
2. tempo minimo di trasmissione
3. tempo complessivo includendo la propagazione

## Procedura
### 1. Individuare il collo di bottiglia
Tra `100 Mbps` e `20 Mbps`, il collo di bottiglia è **20 Mbps**.

### 2. Calcolare il tempo di trasmissione ideale
`tempo = dati / banda`

`200 Mbit / 20 Mbit/s = 10 s`

### 3. Aggiungere il ritardo di propagazione
`30 ms = 0,03 s`

Tempo complessivo minimo:
`10 + 0,03 = 10,03 s`

## Risposta
- Collo di bottiglia: `20 Mbps`
- Tempo minimo di trasmissione: `10 s`
- Tempo complessivo minimo: `10,03 s`

## Osservazioni utili all’esame
- La banda finale è determinata dal link più lento.
- Il ritardo di propagazione si somma al tempo di trasmissione.
- Se il testo introduce ACK, code o congestione, il tempo reale può aumentare.

## Errori tipici
- Sommare le bande invece di prendere il minimo.
- Dimenticare di convertire i millisecondi in secondi.
- Confondere il tempo di trasmissione con il ritardo di propagazione.

## Come riconoscere il tema in prova
Parole chiave: `throughput`, `banda`, `ritardo`, `propagazione`, `congestione`, `collo di bottiglia`, `tempo totale`.
