# Analisi dettagliata della cartella `Parte A`

## 1) Perimetro e metodo

Analisi effettuata sui file presenti in `/home/runner/work/reti_esameB/reti_esameB/Parte A`.

- File totali analizzati: **49**
- Formati presenti: **PDF, JPG, JPEG, DOCX**
- Ispezione contenuti: estrazione testo da PDF/DOCX dove possibile (40 file leggibili su 49)
- Nota: 9 file non hanno testo estraibile direttamente (scansioni/immagini o PDF non testuali), quindi la classificazione tematica per questi è inferita solo dal nome file.

## 2) Raggruppamento per formato

| Formato | Numero file | Percentuale |
|---|---:|---:|
| PDF | 41 | 83,67% |
| JPG | 6 | 12,24% |
| JPEG | 1 | 2,04% |
| DOCX | 1 | 2,04% |
| **Totale** | **49** | **100%** |

## 3) Raggruppamento per anno (con dettaglio formato)

| Anno | Totale | PDF | JPG | JPEG | DOCX |
|---|---:|---:|---:|---:|---:|
| 2011 | 4 | 4 | 0 | 0 | 0 |
| 2012 | 5 | 5 | 0 | 0 | 0 |
| 2013 | 1 | 1 | 0 | 0 | 0 |
| 2014 | 3 | 3 | 0 | 0 | 0 |
| 2015 | 3 | 3 | 0 | 0 | 0 |
| 2016 | 4 | 4 | 0 | 0 | 0 |
| 2017 | 5 | 5 | 0 | 0 | 0 |
| 2018 | 3 | 3 | 0 | 0 | 0 |
| 2019 | 1 | 1 | 0 | 0 | 0 |
| 2021 | 1 | 1 | 0 | 0 | 0 |
| 2022 | 3 | 3 | 0 | 0 | 0 |
| 2023 | 1 | 0 | 1 | 0 | 0 |
| 2024 | 6 | 4 | 2 | 0 | 0 |
| 2025 | 4 | 4 | 0 | 0 | 0 |
| 2026 | 4 | 0 | 3 | 1 | 0 |
| **Totale** | **49** | **41** | **6** | **1** | **1** |

## 4) Pattern ricorrenti nei nomi file e nelle date

### 4.1 Pattern dei nomi

| Pattern nome file | Occorrenze |
|---|---:|
| `YYYY-MM-DD.ext` | 47 |
| `YYYY_MM_DD.ext` | 1 |
| Nome descrittivo non standard (`parte A esame 19 settembre.docx`) | 1 |

**Osservazioni:**
- Pattern dominante fortemente standardizzato su data ISO con trattini.
- Presente una sola variazione con underscore (`2022_02_24.pdf`).
- Un solo file con naming descrittivo libero (DOCX).

### 4.2 Distribuzione per mese (dai file con data nel nome)

| Mese | Frequenza |
|---|---:|
| 01 | 6 |
| 02 | 9 |
| 03 | 3 |
| 05 | 7 |
| 06 | 5 |
| 07 | 9 |
| 09 | 4 |
| 10 | 1 |
| 11 | 4 |

**Osservazioni:**
- Picchi in **febbraio** e **luglio** (9 ciascuno).
- Concentrazione coerente con sessioni d’esame tipiche (invernale/estiva).

## 5) Classificazione per tipologia di esercizio/compito

La classificazione è stata dedotta dai contenuti testuali disponibili (40 file leggibili) tramite parole chiave ricorrenti.

### 5.1 Macro-tipologie rilevate

| Macro-tipologia | Indicatori principali | File in cui compare (su 40 leggibili) | Occorrenze keyword (stima) |
|---|---|---:|---:|
| Indirizzamento e subnetting | `IP`, `subnet`, `maschera` | 39 | 191 |
| Instradamento e topologie | `router`, `switch`, `routing`, `link state`, `distance vector` | 36 | 142 |
| Trasporto TCP/UDP | `TCP`, `UDP`, `window`, `handshake`, `socket` | 36 | 103 |
| NAT e servizi/applicazione | `NAT`, `DNS`, `HTTP`, `firewall`, `ARP` | 32 | 66 |
| Prestazioni/congestione | `throughput`, `ritardo`, `delay`, `congestione` | 14 | 21 |

### 5.2 Temi ricorrenti più frequenti (keyword singole)

| Tema | Frequenza |
|---|---:|
| IP | 134 |
| TCP | 74 |
| Router | 68 |
| Switch | 66 |
| NAT | 62 |
| Subnet | 51 |
| UDP | 21 |
| Throughput | 14 |

**Lettura sintetica:** la cartella `Parte A` contiene soprattutto prove basate su esercizi di **indirizzamento IP/subnetting**, **instradamento (router/switch)** e **protocolli di trasporto (TCP/UDP)**, con presenza regolare di **NAT**.

## 6) File non leggibili testualmente (senza OCR)

Questi file non hanno fornito testo estraibile diretto:

- `2015-11-21.pdf`
- `2025-05-23.pdf`
- `2023-03-24.jpg`
- `2024-03-22.jpg`
- `2024-07-05.jpg`
- `2026-03-20.jpg`
- `2026-05-08.jpg`
- `2026-05-22.jpeg`
- `2026-06-25.jpg`

## 7) Sintesi finale sulla struttura della cartella `Parte A`

La cartella `Parte A` è strutturata come archivio cronologico di compiti/esami (quasi sempre **Prova/Compito A**) con naming prevalentemente basato sulla data. La struttura mostra:

1. **Forte uniformità di naming** (quasi tutti i file in formato data).
2. **Prevalenza netta del formato PDF** nelle annate storiche, con aumento recente di materiale immagine (JPG/JPEG) in alcuni anni.
3. **Continuità tematica didattica** su nuclei classici di reti: IP/subnetting, routing/switching, TCP/UDP, NAT.
4. **Periodicità temporale tipica degli appelli** (picchi in febbraio e luglio).

In pratica, `Parte A` appare come una raccolta storica coerente di tracce d’esame orientate a esercizi tecnico-applicativi di reti di calcolatori, organizzata principalmente per data.
