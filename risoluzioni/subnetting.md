# Esempio di risoluzione — Indirizzamento IP e subnetting

## Obiettivo
Mostrare come risolvere un esercizio tipico di subnetting con suddivisione in sottoreti uguali.

## Esempio
Data la rete `192.168.10.0/24`, ricavare 4 sottoreti uguali.

## Procedura
1. Serve un numero di sottoreti pari a 4.
2. Il numero di bit da “prendere” dalla parte host deve soddisfare `2^n >= 4`.
3. Con `n = 2` otteniamo 4 sottoreti.
4. Il prefisso passa quindi da `/24` a `/26`.
5. Con `/26` ogni sottorete ha `2^(32-26) = 64` indirizzi totali, cioè `62` host utili.

## Sottoreti risultanti
- `192.168.10.0/26`
  - host: `192.168.10.1` – `192.168.10.62`
  - broadcast: `192.168.10.63`
- `192.168.10.64/26`
  - host: `192.168.10.65` – `192.168.10.126`
  - broadcast: `192.168.10.127`
- `192.168.10.128/26`
  - host: `192.168.10.129` – `192.168.10.190`
  - broadcast: `192.168.10.191`
- `192.168.10.192/26`
  - host: `192.168.10.193` – `192.168.10.254`
  - broadcast: `192.168.10.255`

## Osservazioni utili all’esame
- Network address e broadcast non si assegnano a host.
- Se l’esercizio chiede VLSM, conviene ordinare le reti dalla più grande alla più piccola.
- È sempre utile scrivere prima il prefisso finale e poi i range host.

## Errori comuni
- Confondere numero di sottoreti con numero di host.
- Dimenticare che il broadcast è l’ultimo indirizzo del blocco.
- Fare calcoli senza controllare l’allineamento del blocco.
