# Esempio avanzato di risoluzione — Routing e instradamento

## Traccia
Un router ha questa tabella:

- `0.0.0.0/0` → `R_default`
- `192.168.0.0/16` → `R1`
- `192.168.10.0/24` → `R2`
- `192.168.10.128/25` → `R3`

Devi inoltrare i pacchetti verso:
1. `192.168.10.12`
2. `192.168.10.140`
3. `192.168.20.5`
4. `10.1.2.3`

## Procedura
### 1. Applicare il longest prefix match
Per ogni destinazione si scelgono tutte le rotte compatibili, poi la più specifica.

### 2. Analizzare i casi
#### Destinazione `192.168.10.12`
Compatibile con:
- `192.168.0.0/16`
- `192.168.10.0/24`

La più specifica è `/24` → **`R2`**

#### Destinazione `192.168.10.140`
Compatibile con:
- `192.168.0.0/16`
- `192.168.10.0/24`
- `192.168.10.128/25`

La più specifica è `/25` → **`R3`**

#### Destinazione `192.168.20.5`
Compatibile con:
- `192.168.0.0/16`

Scelta → **`R1`**

#### Destinazione `10.1.2.3`
Compatibile solo con:
- `0.0.0.0/0`

Scelta → **`R_default`**

## Risultato finale
- `192.168.10.12` → `R2`
- `192.168.10.140` → `R3`
- `192.168.20.5` → `R1`
- `10.1.2.3` → `R_default`

## Errori tipici
- Fermarsi alla prima rotta compatibile.
- Dimenticare che la default route vale solo se non c’è match più specifico.
- Confondere rete e host quando si controlla il prefisso.

## Come riconoscere il tema in prova
Parole chiave: `tabella di routing`, `next hop`, `default route`, `longest prefix match`, `instradamento`.
