# roadmap tesi  
**applicazione di modelli transformer all'analisi delle cartelle cliniche pediatriche della rete pedianet**

## 1. obiettivi tesi

utilizzare modelli linguistici basati su transformer per analizzare le cartelle cliniche pediatriche, con l'obiettivo di:

- **[ner theory]** estrarre informazioni strutturate da testi liberi (anamnesi, diagnosi, ecc.) 
- **[disease analysis]** analizzare, mappare o prevedere lo sviluppo di malattie
- **[llm fine-tuning]** valutare l'impiego di modelli di linguaggio per supportare la generazione automatica di diagnosi o altro
- **[webapp developing]** costruire una piattaforma open source dedicata a tali scopi

## 2. state of the art analysis

- rassegna della letteratura scientifica recente sull’utilizzo di llm/transformers in ambito medico
- focus specifico sull’ambito pediatrico e sull'elaborazione del linguaggio clinico
- analisi di modelli pre-addestrati rilevanti (es. biobert, clinicalbert, gatortron, med-palm, deepseek, ecc.)

## 3. raccoglimento e preparazione dei dati

- studio della struttura delle cartelle cliniche pedianet
- parsing e pulizia dei dati (preprocessing testuale, gestione dei valori mancanti)
- tokenizzazione, normalizzazione e anonimizzazione

## 4. analisi statistica esplorativa del dataset

- statistiche descrittive (numero pazienti, età, distribuzione diagnosi)
- frequenze delle condizioni cliniche principali
- lunghezza media dei testi
- visualizzazioni (grafici, distribuzioni, wordclouds)

## 5. modellazione con transformer

### 5.1 estrazione e pre-processing dei dati

- sviluppo di script per estrazione da database/file raw
- output strutturato in formato json

### 5.2 named entity recognition (ner) clinica

- applicazione di ner per identificare entità mediche (sintomi, farmaci, diagnosi, procedure)
- supporto all’analisi strutturata del testo clinico
- potenziale utilizzo come feature nei modelli successivi

### 5.3 classificazione delle anamnesi

- predizione automatica di categorie di rischio o patologie potenziali

### 5.4 classificazione delle diagnosi

- raggruppamento e categorizzazione automatica delle diagnosi a partire da dati clinici grezzi

### 5.5 domande esplorative

- quali correlazioni emergono tra anamnesi e diagnosi?
- è possibile identificare cluster di pazienti con pattern simili?
- la relazione anamnesi-diagnosi è univoca, biunivoca o ambigua?
- esistono segnali precoci che anticipano determinate diagnosi?

## 6. fine-tuning di un modello linguistico (llm)

### 6.1 scelta e preparazione del modello

- selezione di un llm fondazionale (es. deepseek, med-palm, biogpt)

### 6.2 fine-tuning supervisionato

- addestramento supervisionato su coppie (anamnesi, diagnosi)
- valutazione delle prestazioni (accuracy, precision, recall, f1-score)

### 6.3 sviluppo di un prototipo

- input: json con anamnesi
- output: diagnosi possibili con probabilità associate
- possibile interfaccia ui o api rest per test del sistema

## 7. estensioni future

- sviluppo e approfondimento di moduli per named entity recognition clinica
- collaborazione con pediatri per validazione qualitativa e clinica dei risultati
- integrazione con strumenti di supporto alla decisione clinica


---



