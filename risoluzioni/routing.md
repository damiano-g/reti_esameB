# Esempio di risoluzione — Routing e instradamento

## Obiettivo
Mostrare come scegliere la rotta corretta con il principio del **longest prefix match**.

## Esempio
La tabella di routing contiene:

- `10.0.0.0/8` → `R1`
- `10.1.0.0/16` → `R2`
- `0.0.0.0/0` → `R3`

Devi inoltrare un pacchetto verso `10.1.2.3`.

## Procedura
1. Verifica quali rotte sono compatibili con la destinazione.
2. `10.0.0.0/8` è compatibile.
3. `10.1.0.0/16` è compatibile ed è più specifica.
4. `0.0.0.0/0` è la default route, quindi è sempre compatibile ma meno specifica.
5. Si sceglie la rotta con prefisso più lungo.

## Risposta
La destinazione `10.1.2.3` viene inoltrata a `R2`.

## Osservazioni utili all’esame
- Non si sceglie la prima rotta valida.
- Si sceglie la rotta più specifica tra quelle compatibili.
- Se nessuna rotta più specifica coincide, entra in gioco la default route.

## Errori comuni
- Ignorare il longest prefix match.
- Confondere rete di destinazione e host specifico.
- Trascurare la default route.
