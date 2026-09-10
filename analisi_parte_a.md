# Guida di studio open book — Parte A

## 1) Scopo e base dell’analisi

Questa guida è pensata per preparare un esame open book partendo dalle tracce realmente presenti in `Parte A` del repository.
L’obiettivo non è statistiche sui file, ma una mappa di studio utile per riconoscere rapidamente il tipo di esercizio e applicare una procedura corretta.

## 2) Macro-temi davvero ricorrenti

Dalle tracce storiche emergono con continuità questi filoni:

| Tema | Priorità | Cosa devi saper fare |
|---|---|---|
| Indirizzamento IP e subnetting | Molto alta | calcolare reti, broadcast, host, CIDR, VLSM/FLSM |
| Routing e tabelle di instradamento | Molto alta | longest prefix match, next hop, default route |
| TCP/UDP | Molto alta | handshake, segmenti, finestre, ACK, differenze tra protocolli |
| Prestazioni / throughput / ritardi | Alta | banda, collo di bottiglia, tempi di trasferimento |
| NAT / ARP / servizi applicativi | Media-alta | traduzioni indirizzo/porta, ARP, socket, DNS/HTTP |

## 3) Come leggere le tracce

Per ogni esercizio fai sempre questa scansione:
1. **tema**: subnetting, routing, TCP, prestazioni, NAT/ARP
2. **dati numerici**: IP, maschere, bande, ritardi, MSS, RTT, porte
3. **vincolo principale**: rete corretta, rotta più specifica, tempo totale, traduzione NAT
4. **ipotesi implicite**: cosa è esplicitato e cosa devi dichiarare tu

## 4) Schede di ripasso per tema

### 4.1 Indirizzamento IP e subnetting

Cose da saper fare subito:
- convertire prefisso in numero di host
- calcolare network, primo host, ultimo host, broadcast
- distinguere FLSM da VLSM
- assegnare blocchi senza sovrapposizioni

Procedura tipo:
1. ordina le richieste per dimensione
2. calcola il prefisso minimo per ogni rete
3. assegna gli indirizzi dal blocco più basso
4. verifica allineamento e consistenza

Errori tipici:
- dimenticare network e broadcast
- assegnare un prefisso troppo piccolo
- non ordinare le subnet in VLSM

---

### 4.2 Routing e instradamento

Cose da saper fare subito:
- applicare sempre il longest prefix match
- distinguere rotta specifica e default route
- leggere tabelle di routing senza fermarsi alla prima corrispondenza
- seguire il next hop corretto

Procedura tipo:
1. elenca tutte le rotte compatibili
2. scegli la più specifica
3. se manca una rotta, usa la default route
4. controlla il percorso finale hop-by-hop

Errori tipici:
- usare la prima rotta trovata
- confondere indirizzo host e rete
- ignorare la default route

---

### 4.3 TCP/UDP

Cose da saper fare subito:
- disegnare il 3-way handshake
- distinguere ACK cumulativi e segmenti
- ragionare su finestra e RTT
- spiegare perché UDP è diverso da TCP

Procedura tipo:
1. ricostruisci la timeline
2. annota MSS, RTT, finestra, eventuali perdite
3. calcola round per round se richiesto
4. separa chiaramente ipotesi e risultato

Errori tipici:
- confondere bit e byte
- ignorare l’handshake quando serve
- fare calcoli senza dichiarare il modello TCP assunto

---

### 4.4 Prestazioni, throughput e ritardi

Cose da saper fare subito:
- trovare il collo di bottiglia
- calcolare il tempo di trasmissione base
- sommare i ritardi richiesti dal testo
- controllare le unità

Procedura tipo:
1. individua il link più lento
2. converti le unità
3. calcola il tempo base
4. aggiungi i ritardi indicati

Errori tipici:
- sommare le bande
- confondere throughput e banda
- non convertire ms in secondi

---

### 4.5 NAT, ARP e servizi applicativi

Cose da saper fare subito:
- distinguere IP privato e pubblico
- capire quando cambia anche la porta con PAT
- spiegare il ruolo di ARP
- seguire il verso del traffico

Procedura tipo:
1. scrivi indirizzi e porte prima della traduzione
2. applica la NAT/PAT
3. descrivi il ritorno della risposta
4. inserisci ARP quando serve a livello locale

Errori tipici:
- confondere indirizzo esterno e interno
- dimenticare la traduzione della porta
- saltare il passaggio ARP

## 5) Checklist open book

- [ ] Ho un indice per tema, non solo per data
- [ ] So dove trovare una traccia simile per ogni argomento
- [ ] Ho un formulario minimo con formule e conversioni
- [ ] So risolvere almeno una traccia modello per ciascun tema
- [ ] Controllo sempre unità e ipotesi

## 6) Come usare i file durante l’esame

La strategia migliore è:
1. riconoscere il tema in pochi secondi
2. aprire una traccia storica simile
3. copiare lo schema di soluzione, non i numeri
4. scrivere sempre i passaggi intermedi
5. chiudere con un controllo di coerenza

## 7) Risorse di studio suggerite

Le schede più utili da tenere vicine sono:
- `risoluzioni_avanzate/subnetting.md`
- `risoluzioni_avanzate/routing.md`
- `risoluzioni_avanzate/tcp_udp.md`
- `risoluzioni_avanzate/prestazioni.md`
- `risoluzioni_avanzate/nat_arp_servizi.md`
- `risoluzioni_avanzate/open_book.md`

