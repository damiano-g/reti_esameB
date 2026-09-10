# Esempio avanzato di risoluzione — Prestazioni, throughput e congestione

## Traccia reale di riferimento
Questa scheda è pensata per le tracce storiche di `Parte A` in cui compaiono calcoli di:
- tempo di trasmissione
- throughput utile
- collo di bottiglia
- ritardi di propagazione / trasmissione
- effetti di code o congestione

## Metodo di risoluzione
### 1. Separare i dati del problema
Individua subito:
- dimensione del file o quantità di dati da trasferire
- capacità dei link
- eventuali ritardi
- numero di salti o tratte
- presenza di ACK, buffering o congestione

### 2. Individuare il collo di bottiglia
Se il percorso ha più link in serie, la banda effettiva massima è limitata dal link più lento.

### 3. Normalizzare le unità
Prima di calcolare:
- `Mb/s` e `MB/s` non sono equivalenti
- `ms` va convertito in secondi se serve
- `KB` / `MB` / `KiB` vanno interpretati come nel testo della prova

### 4. Calcolare il tempo base
Formula tipica:
- `tempo = dati / banda`

Poi, se richiesto:
- somma i ritardi di propagazione
- aggiungi eventuali tempi di attesa / trasmissione per hop
- considera overhead o finestre se il problema li introduce

## Schema di risposta
Usa sempre questo ordine:
1. collo di bottiglia
2. conversione unità
3. tempo base
4. aggiunte richieste dal testo
5. controllo finale di coerenza

## Errori tipici
- sommare le bande invece di prendere il minimo
- confondere throughput con banda nominale
- dimenticare la conversione tra bit e byte
- trattare il ritardo di propagazione come tempo di trasmissione

## Template da copiare in prova
**Dati:** ...

**Collo di bottiglia:** ...

**Calcolo del tempo base:** ...

**Ritardi aggiuntivi:** ...

**Risultato finale:** ...

## Come usare questa scheda
Cerca nelle tracce reali parole come:
`throughput`, `ritardo`, `propagazione`, `trasmissione`, `congestione`, `banda`, `tempo di trasferimento`.
