# Guida di studio open book — Parte A

## 1) Scopo e base dell’analisi

Questa guida sostituisce il precedente report statistico e riassume i contenuti didattici ricorrenti nei compiti di `/home/runner/work/reti_esameB/reti_esameB/Parte A`.

Base usata:
- 49 tracce totali (PDF/JPG/JPEG/DOCX).
- Estrazione testo da PDF/DOCX + OCR per immagini.
- 47 file con testo utilizzabile; 2 file senza testo estraibile affidabile (`2015-11-21.pdf`, `2025-05-23.pdf`).

> Nota di prudenza: le frequenze sotto sono **indicative** (dipendono dalla qualità OCR), ma sono sufficienti per capire quali temi dominano davvero.

## 2) Macro-temi più ricorrenti (priorità studio)

| Tema | Presenza indicativa | Priorità |
|---|---:|---|
| Trasporto TCP/UDP | alta (~43/49) | Molto alta |
| Indirizzamento IP, CIDR, subnetting (FLSM/VLSM) | alta (~39/49) | Molto alta |
| Routing/instradamento (tabelle, default route, distance vector) | alta (~37/49) | Molto alta |
| Prestazioni (throughput, banda media, ritardi, congestione, tempi trasferimento) | media (~22/49) | Alta |
| NAT + ARP/DNS/socket e servizi applicativi | medio-bassa (~10/49) | Media |

Riferimenti rappresentativi:
- Subnetting/VLSM/FLSM: `2011-01-11.pdf`, `2016-01-19.pdf`, `2024-07-23.pdf`, `2026-05-08.jpg`, `parte A esame 19 settembre.docx`.
- Routing e tabelle: `2011-01-11.pdf`, `2012-05-18.pdf`, `2012-07-18.pdf`, `2025-02-03.pdf`.
- TCP/UDP e throughput: `2011-01-11.pdf`, `2012-07-18.pdf`, `2021-05-15.pdf`, `2026-05-22.jpeg`.
- NAT/ARP/socket: `2016-01-19.pdf`, `2016-11-08.pdf`, `2017-02-16.pdf`, `2026-05-08.jpg`.

## 3) Schede operative per tema

### Tema A — Indirizzamento IP e subnetting

**Cosa chiedono tipicamente**
- Subnettare un blocco in N reti o per fabbisogni host diversi (FLSM/VLSM).
- Trovare subnet ID, intervallo host, broadcast, maschera/CIDR.
- Verificare se due host stanno nella stessa rete.

**Teoria da sapere**
- Conversione prefisso/mask, bit host vs bit rete.
- Regole di validità di network e broadcast.
- Differenza FLSM vs VLSM.

**Strategia pratica**
1. Scrivi subito prefisso e host richiesti.
2. Ordina le sottoreti per dimensione (se VLSM).
3. Assegna blocchi in ordine, controllando allineamento binario.
4. Compila una tabella finale (SubnetID, primo/ultimo host, broadcast).

**Errori comuni**
- Dimenticare che network e broadcast non sono assegnabili.
- Arrotondare male la potenza di 2 per gli host.
- Fare overlap tra sottoreti in VLSM.

**Parole chiave trigger**
`subnet`, `CIDR`, `maschera`, `broadcast`, `stessa rete`, `VLSM`, `FLSM`.

---

### Tema B — Routing e instradamento

**Cosa chiedono tipicamente**
- Decidere next-hop/interfaccia da tabella di routing.
- Spiegare o usare la rotta di default.
- Calcolare/aggiornare tabelle distance vector o leggere topologie router-host.

**Teoria da sapere**
- Longest prefix match.
- Significato operativo di default route.
- Logica base di distance vector/link-state (a livello procedurale).

**Strategia pratica**
1. Per ogni destinazione, confronta tutti i prefissi candidati.
2. Seleziona il più specifico (non il primo che trovi).
3. Traccia su schema il percorso hop-by-hop.
4. Se c’è distance vector, separa chiaramente i passi iterativi.

**Errori comuni**
- Ignorare il longest prefix match.
- Confondere rete destinazione e host specifico.
- Saltare passaggi intermedi nei calcoli distance vector.

**Parole chiave trigger**
`router`, `tabella di instradamento`, `default`, `next hop`, `distance vector`, `link state`.

---

### Tema C — TCP/UDP (segmenti, handshake, dinamica finestra)

**Cosa chiedono tipicamente**
- Diagrammi di scambio (3-way handshake, segmenti, ACK).
- Calcolo dati trasferiti/tempo su TCP con MSS, RTT, finestra.
- Confronto TCP vs UDP in scenari applicativi.

**Teoria da sapere**
- Sequenze base handshake e ACK cumulativi.
- Relazione tra MSS, RTT, finestra e throughput percepito.
- Caratteristiche essenziali UDP (datagrammi indipendenti, niente controllo di flusso end-to-end come TCP).

**Strategia pratica**
1. Disegna timeline A↔B prima di fare conti.
2. Fissa ipotesi esplicite (slow start sì/no, perdita sì/no).
3. Calcola per round/RTT e verifica unità (bit/byte, ms/s).
4. Riporta il risultato finale con formula sintetica.

**Errori comuni**
- Mischiare bit e byte.
- Dimenticare overhead temporale (handshake/RTT iniziale).
- Usare crescita finestra incoerente con ipotesi date.

**Parole chiave trigger**
`TCP`, `UDP`, `MSS`, `RTT`, `finestra`, `handshake`, `ACK`, `throughput`.

---

### Tema D — Prestazioni, throughput, ritardo, congestione

**Cosa chiedono tipicamente**
- Throughput massimo o banda media applicativa.
- Tempo di trasferimento file su link con vincoli specifici.
- Effetti di ritardo, errori, buffer o controllo congestione.

**Teoria da sapere**
- Differenza tra banda nominale e throughput utile.
- Componenti del ritardo (propagazione/trasmissione/attesa).
- Effetto qualitativo di congestione e perdite su TCP.

**Strategia pratica**
1. Elenca parametri numerici e convertili subito in unità coerenti.
2. Isola il collo di bottiglia.
3. Calcola prima il caso ideale, poi applica i vincoli richiesti.
4. Verifica ordine di grandezza finale (sanity check).

**Errori comuni**
- Scambiare Mbps con MB/s.
- Dimenticare tempi non di payload (setup/attese).
- Trascurare ipotesi obbligatorie nel testo.

**Parole chiave trigger**
`throughput`, `banda media`, `ritardo`, `tempo richiesto`, `congestione`, `buffer`.

---

### Tema E — NAT, ARP, servizi applicativi/socket

**Cosa chiedono tipicamente**
- Configurare/descrivere NAT in una topologia data.
- Simulare richieste ARP e pacchetti generati.
- Ragionare su socket/porte o su output di connessioni applicative.

**Teoria da sapere**
- Traduzione indirizzi/porte in NAT.
- Risoluzione L2↔L3 in ARP.
- Ruolo delle porte TCP/UDP lato client/server.

**Strategia pratica**
1. Distingui sempre rete interna/esterna e verso della traduzione.
2. Per ARP, esplicita broadcast iniziale + risposta unicast.
3. Mantieni tabella ordinata: IP/porta sorgente-destinazione prima e dopo NAT.

**Errori comuni**
- Confondere indirizzo privato e pubblico dopo traduzione.
- Saltare i pacchetti intermedi ARP.
- Invertire source/destination port nei diagrammi.

**Parole chiave trigger**
`NAT`, `ARP`, `socket`, `porta`, `DNS`, `HTTP`.

## 4) Mappa rapida di ripasso (ultimo giro prima dell’esame)

1. **Subnetting**: sai ricavare rapidamente `/x`, host max, network/broadcast?
2. **Routing**: applichi sempre longest prefix match senza errori?
3. **TCP**: sai disegnare handshake + rounds con MSS/RTT/finestra?
4. **Throughput**: distingui banda fisica vs utile applicativa?
5. **NAT/ARP**: sai scrivere in ordine i pacchetti e le traduzioni?

Se uno di questi 5 punti è incerto, è una priorità di ripasso.

## 5) Checklist open book (operativa)

- [ ] Indice personale dei file per tema (non solo per data).
- [ ] 2-3 tracce “modello” per ciascun macro-tema già segnate.
- [ ] Formulario minimo pronto (CIDR, host utili, conversioni unità, throughput base).
- [ ] Template foglio soluzione: **Dati → Ipotesi → Procedura → Risultato**.
- [ ] Esercizi con timeline TCP già ripassati.
- [ ] Esercizi con tabelle routing/NAT già ripassati.

## 6) Come consultare i file durante l’esame

1. **Ricerca per parola chiave dell’esercizio** (es. “VLSM”, “default route”, “throughput”, “ARP”).
2. **Apri una traccia storica simile** e copia lo schema risolutivo, non i numeri.
3. **Confronta subito i vincoli** (MSS, RTT, banda, numero host, numero subnet).
4. **Evita il browsing cronologico puro**: il naming per data (`YYYY-MM-DD`) è utile, ma in prova conviene navigare per tema.
5. Se il testo è ambiguo o OCR poco chiaro (soprattutto immagini), usa una soluzione dichiarando le ipotesi in modo esplicito e coerente.
