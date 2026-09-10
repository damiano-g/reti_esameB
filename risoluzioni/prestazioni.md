# Esempio di risoluzione — Prestazioni, throughput e ritardi

## Obiettivo
Mostrare come stimare il tempo di trasferimento e riconoscere il collo di bottiglia.

## Esempio
Un link ha banda `20 Mbps` e si deve trasferire un file di `50 Mbit`.

## Procedura
1. Verifica le unità: il file è già in bit, quindi il calcolo è diretto.
2. Tempo ideale di trasmissione:
   - `tempo = dati / banda = 50 / 20 = 2,5 secondi`
3. Se il testo aggiunge ritardi di propagazione o attesa, questi vanno sommati separatamente.
4. Se il problema chiede throughput utile, bisogna sottrarre l’overhead o considerare il collo di bottiglia.

## Risposta
Il tempo minimo di trasmissione è `2,5 s`, a cui si aggiungono eventuali ritardi richiesti dal testo.

## Osservazioni utili all’esame
- Distinguere sempre banda nominale e throughput utile.
- Controllare le unità prima di fare qualsiasi divisione.
- Isolare il link più lento se c’è una catena di collegamenti.

## Errori comuni
- Scambiare Mbps con MB/s.
- Dimenticare i ritardi non di trasmissione.
- Applicare il calcolo senza verificare il collo di bottiglia.
