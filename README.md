# Costruiamo un Sistema di Raccomandazione con Python

Benvenuti al repository del Beginners'Day, l'evento di apertura del [Pycon Italia 2025](https://2025.pycon.it/it) curato da [Datamasters](https://datamasters.it/)!
Questo workshop è progettato per guidarvi attraverso la creazione di un sistema di raccomandazione per film e serie TV, partendo da approcci semplici fino a tecniche più avanzate, il tutto utilizzando Python .

## 🎯 Obiettivo del Workshop

L'obiettivo principale di questo workshop è fornire una comprensione pratica di:
* Come pre-processare e pulire i dati per un sistema di raccomandazione.
* Diverse tecniche di *Content-Based Filtering*:
    * Filtraggio semplice basato su attributi (es. genere).
    * Calcolo della similarità utilizzando One-Hot Encoding e **Similarità del Coseno**.
    * Estrazione di feature testuali con **TF-IDF**.
    * Utilizzo di **Sentence Embeddings** per una comprensione semantica più profonda del testo.
    * Creazione di sistemi di raccomandazione **ibridi** che combinano diverse fonti di informazione.
    * Personalizzazione delle raccomandazioni basate su un **profilo utente**.

Il focus è sull'apprendimento pratico, con spiegazioni chiare dei concetti teorici man mano che vengono introdotti.

## 🚀 Contenuto del Notebook (`Full.ipynb`)

Il notebook `Full.ipynb` è strutturato in passaggi progressivi:

1.  **Step 0: Caricamento e Preprocessing dei Dati**
    * Lettura del dataset `netflix_titles.csv`.
    * Pulizia dei dati: gestione di stringhe, liste, valori numerici e mancanti.
2.  **Step 1: Raccomandazioni Semplici per Genere**
    * Filtraggio diretto basato sui generi dei film.
3.  **Step 2: Raccomandazioni con Similarità Coseno (Generi)**
    * Introduzione ai concetti di Feature Space, One-Hot Encoding e Similarità del Coseno.
    * Implementazione di un sistema di raccomandazione basato sulla similarità dei generi.
4.  **Step 3 & 4: Arricchimento delle Caratteristiche e Raccomandazioni Estese**
    * Inclusione di `rating`, `type` e `director` nel calcolo della similarità.
5.  **Step 5: Raccomandazioni Basate su Descrizione (TF-IDF)**
    * Introduzione a TF-IDF (Term Frequency-Inverse Document Frequency).
    * Implementazione di raccomandazioni basate sulla similarità testuale delle descrizioni.
6.  **Step 6: Raccomandazioni Ibride (TF-IDF + Categorie)**
    * Combinazione della similarità testuale (TF-IDF) con quella delle categorie strutturate.
7.  **Step 7 & 8: Raccomandazioni con Embedding Semantici (Avanzato)**
    * Introduzione agli Sentence Embeddings (con `sentence-transformers`).
    * Generazione di embedding per le descrizioni e calcolo della similarità.
    * Creazione di un sistema ibrido che usa embedding e categorie strutturate.
8.  **Step 9: Raccomandazioni Personalizzate per Profilo Utente**
    * Creazione di un profilo utente basato sui film preferiti.
    * Generazione di raccomandazioni personalizzate basate su questo profilo ibrido.

## 🛠️ Come Utilizzare il Notebook

Per seguire il workshop e utilizzare il notebook, segui questi passaggi:

### 1. Prerequisiti
* **Python**: Assicurati di avere Python installato (versione 3.7 o successiva raccomandata). Puoi scaricarlo da [python.org](https://www.python.org/).
* **Jupyter Notebook/JupyterLab**: Il notebook è progettato per essere eseguito in un ambiente Jupyter. Se non lo hai, puoi installarlo con pip:
    ```bash
    pip install notebook
    # oppure
    pip install jupyterlab
    ```

### 2. Dataset e File del Progetto

* Clona o scarica questa repository per ottenere il file `Full.ipynb` e il dataset necessari per seguire il workshop.
* Il file `netflix_titles.csv` è già incluso nella repository, all'interno della directory `data/`, che si trova nella stessa directory del  notebook `Full.ipynb`.
* Il dataset originale è disponibile a questo URL: [https://www.kaggle.com/datasets/inegan/netflix-dataset](https://www.kaggle.com/datasets/inegan/netflix-dataset)


### 3. Installazione delle Librerie
Il notebook utilizza diverse librerie Python. Le librerie standard come `csv`, `json`, `math`, `collections` sono incluse con Python.
Per le librerie esterne, principalmente `sentence-transformers` (e le sue dipendenze come `numpy` e `torch`), puoi installarle tramite pip. È consigliabile creare un ambiente virtuale:

```bash
# (Opzionale ma raccomandato) Crea e attiva un ambiente virtuale
python -m venv venv_workshop
source venv_workshop/bin/activate  # Su Linux/macOS
# venv_workshop\Scripts\activate  # Su Windows

# Installa le librerie necessarie
pip install sentence-transformers