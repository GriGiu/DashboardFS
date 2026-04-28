# DashboardFS
Dashboard simulatore di traffico per freeswitch
Per fare partire il progetto , scaricare su una cartella e lanciare il server http con il comando : python3 -m http.server 8000
Aprire poi il browser all'indirizzo : http://localhost:8000

## Descrizione del progetto
DashboardFS è una web application interattiva per la stima della capacità massima di elaborazione di chiamate (sessioni) in un ambiente FreeSWITCH, basata su benchmark multi‑thread reali di due piattaforme server: 
- **AMD Opteron 2×1.7 GHz** (benchmark MT 1 198) 
- **Xeon E5‑2650 v3 (4 vCPU)** (benchmark MT 11 657).

L’applicativo consente di:
- Selezionare il tipo di traffico (G711a RTP, G711a SRTP, G711a Recording, NoMedia, ecc.)
- Definire un benchmark target, il CPS (Call Per Second) desiderato e una soglia CPU massima (%)
- Calcolare in tempo reale il numero massimo di sessioni sostenibili e la corrispondente utilizzazione CPU
- Visualizzare curve interattive (Plotly) che mostrano:
  1. Sessioni massime al variare del benchmark (CPS fisso)
  2. Sessioni massime al variare del CPS (benchmark fisso)
  3. Curva di salita (rampa) CPU% → Sessioni fino al limite soglia
- Consultare una tabella con i dati di riferimento usati per le stime (origini, configurazioni hardware, risultati grezzi)

I risultati sono ottenuti tramite interpolazione lineare sui punti non saturanti e non transcodificanti, quindi si tratta di stime indicative per dimensionamento e capacity planning.
