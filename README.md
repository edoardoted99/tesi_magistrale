# Wikipedia Graph + Transformer Analysis (Italiano)

Questo progetto ha l'obiettivo di costruire un grafo orientato delle pagine di Wikipedia in italiano, utilizzando i dump ufficiali rilasciati da Wikimedia. In seguito, si intende applicare un modello Transformer sul contenuto testuale di ciascuna pagina per condurre analisi avanzate.

## Contenuti

- Download e parsing dei dump SQL di Wikipedia (itwiki)
- Importazione in un database MySQL
- Costruzione di un grafo delle pagine e dei link interni
- Estrazione e pre-processing dei testi
- Applicazione di un Transformer a ciascun nodo del grafo (pagina)
- Analisi e interpretazione dei risultati

## Dump utilizzati

Scaricati da https://dumps.wikimedia.org/itwiki/latest/:

- `itwiki-latest-page.sql.gz`: contiene i metadati delle pagine (nodi del grafo)
- `itwiki-latest-pagelinks.sql.gz`: contiene i collegamenti tra pagine (archi del grafo)
- `itwiki-latest-pages-articles.xml.bz2`: contiene il testo completo delle voci

## Setup ambiente

### 1. Installazione MySQL

```bash
sudo apt update
sudo apt install mysql-server
sudo systemctl start mysql
```

### 2. Creazione del database

```sql
CREATE DATABASE itwiki;
```

### 3. Import dei dump

```bash
gunzip itwiki-latest-page.sql.gz
gunzip itwiki-latest-pagelinks.sql.gz

mysql -u root -p itwiki < itwiki-latest-page.sql
mysql -u root -p itwiki < itwiki-latest-pagelinks.sql
```

## Struttura dati

- `page`: contiene `page_id`, `page_title`, `page_namespace`
- `pagelinks`: contiene `pl_from` (ID sorgente) e `pl_title` (titolo destinazione)

## Roadmap

### Fase 1: Importazione e costruzione del grafo
- [x] Scaricamento dei dump
- [x] Importazione dei dati in MySQL
- [x] Estrazione dei nodi e archi
- [ ] Costruzione del grafo con `networkx`

### Fase 2: Estrazione e pre-processing del testo
- [ ] Parsing di `itwiki-latest-pages-articles.xml.bz2`
- [ ] Normalizzazione e pulizia del contenuto testuale

### Fase 3: Integrazione con modello Transformer
- [ ] Integrazione di un modello pre-addestrato (es. BERT, DistilBERT)
- [ ] Generazione delle embedding per ogni nodo del grafo
- [ ] Salvataggio e gestione delle rappresentazioni

### Fase 4: Analisi
- [ ] Analisi di similarità semantica tra nodi
- [ ] Clustering semantico
- [ ] Classificazione/annotazione delle pagine
- [ ] Visualizzazione con embedding 2D (es. t-SNE, UMAP)

## Idee per analisi future

- Individuare comunità semantiche di pagine (community detection su embedding)
- Trovare "outlier" semantici: pagine che parlano di argomenti insoliti rispetto ai link
- Costruire un sistema di raccomandazione tra pagine
- Valutare la correlazione tra struttura del grafo e similarità semantica del contenuto
- Usare il grafo come supporto per task NLP supervisionati (es. classificazione, QA)

## Librerie Python usate

- `mysql-connector-python`
- `networkx`
- `pandas`
- `transformers`
- `scikit-learn`
- `matplotlib`

## Licenza

MIT — libero uso per fini di studio e ricerca.  
I dati provengono da Wikipedia e sono distribuiti secondo la licenza CC BY-SA 3.0.

## Contatti

tedesco@system-product-name.local  
GitHub: [inserisci tuo username]

