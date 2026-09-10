# Esempio avanzato di risoluzione — Indirizzamento IP e subnetting

## Traccia
La rete `172.16.0.0/20` deve essere suddivisa in 5 sottoreti con questi fabbisogni:
- A: 500 host
- B: 200 host
- C: 120 host
- D: 60 host
- E: 30 host

Assegna gli indirizzi usando VLSM e indica per ogni sottorete:
- rete
- maschera/prefisso
- range host
- broadcast

## Procedura
### 1. Ordinare i requisiti dal più grande al più piccolo
- 500 host
- 200 host
- 120 host
- 60 host
- 30 host

### 2. Calcolare il blocco minimo per ogni rete
Serve il più piccolo numero di bit host tale che `2^h - 2 >= host richiesti`.

- 500 host → `2^9 - 2 = 510` → prefisso `/23`
- 200 host → `2^8 - 2 = 254` → prefisso `/24`
- 120 host → `2^7 - 2 = 126` → prefisso `/25`
- 60 host → `2^6 - 2 = 62` → prefisso `/26`
- 30 host → `2^5 - 2 = 30` → prefisso `/27`

### 3. Assegnare gli indirizzi in ordine
Partendo da `172.16.0.0`:

#### A — 500 host
- Rete: `172.16.0.0/23`
- Host: `172.16.0.1` – `172.16.1.254`
- Broadcast: `172.16.1.255`

#### B — 200 host
- Rete: `172.16.2.0/24`
- Host: `172.16.2.1` – `172.16.2.254`
- Broadcast: `172.16.2.255`

#### C — 120 host
- Rete: `172.16.3.0/25`
- Host: `172.16.3.1` – `172.16.3.126`
- Broadcast: `172.16.3.127`

#### D — 60 host
- Rete: `172.16.3.128/26`
- Host: `172.16.3.129` – `172.16.3.190`
- Broadcast: `172.16.3.191`

#### E — 30 host
- Rete: `172.16.3.192/27`
- Host: `172.16.3.193` – `172.16.3.222`
- Broadcast: `172.16.3.223`

## Verifica finale
- Tutte le sottoreti stanno dentro `172.16.0.0/20`.
- Le reti non si sovrappongono.
- Ogni subnet soddisfa il numero minimo di host richiesto.

## Errori tipici
- Non ordinare le reti per dimensione.
- Usare un prefisso troppo stretto per il numero di host.
- Dimenticare di sottrarre 2 indirizzi per network e broadcast.

## Come riconoscere il tema in prova
Parole chiave: `VLSM`, `fabbisogno host`, `sottoreti di dimensione diversa`, `broadcast`, `maschera`, `prefisso`.
