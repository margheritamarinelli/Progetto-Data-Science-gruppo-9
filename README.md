# Previsione dell'abbandono dei dipendenti
## Progetto del corso di Introduzione al Pensiero Computazionale e alla Data Science
## A.A. 2025/2026 — Alma Mater Studiorum, Università di Bologna
## Docente: Francesco Poggi 

## Indice
1. Descrizione del progetto
2. Descrizione del dataset
3. Obiettivo
4. Struttura del repository
5. Modelli utilizzati
6. Istruzioni per l'esecuzione
7. Membri del gruppo
8. Report
9. Uso di assistenti LLM

## 1. Descrizione del progetto
Il progetto analizza il dataset _Employee Attrition_ con l'obiettivo di prevedere se un dipendente abbandonerà l'azienda, a partire da alcune caratteristiche demografiche, contrattuali e lavorative. Il lavoro segue le seguenti fasi: comprensione del dataset, analisi esplorativa e visualizzazione, modellazione, valutazione critica dei risultati e stesura di un report scientifico in LaTeX.

## Descrizione del dataset
| **Caratteristica** | **Valore**|
|----------------|--------|
| Osservazioni | 1.470 dipendenti |
| Variabili totali | 35 (26 numeriche, 9 categoriche) |
| Variabile target | Attrition (Yes / No) |
| Distribuzione target | 83,88% No — 16,12% Yes (sbilanciamento di classe) |
| Valori nulli | Nessuno |
| Outlier rilevanti | Nessuno |

Le variabili _EmployeeCount_, _StandardHours_, _Over18_, ed _EmployeeNumber_ - costanti o puramente identificative - sono state rimosse prima della fase di modellazione.

## Obiettivo
Prevedere se un dipendente abbandonerà l'azienda (classificazione binaria) e individuare quali fattori (es. età, reddito mensile, anzianità, straordinari) sono più associati a questo comportamento attraverso la costruzione di modelli di classificazione.

## Modelli utilizzati
| **Modello** | **Tipo** | **Note** |
|----------------|--------| -------- |
| Regressione Logistica | Lineare |class_weight='balanced', standardizzazione delle feature |
| k-Nearest Neighbors | Non lineare | testati k=5 e k=3 |
| Random Forest | Non lineare | 100 alberi |

Tutti i modelli sono stati valutati con le seguenti metriche: accuracy, precision, recall, F1-score e confusion matrix. Il confronto finale è stato effettuato tramite 10-fold cross-validation stratificata.

## Struttura del repository
```text
.
├── data/
├── figures/
├── notebook/
├── report/
├── LICENSE
└── README.md
```

- **data/**: dataset originale e versioni pre-processate.
- **figures/**: grafici esportati (heatmap, confusion matrix, ROC curve, ecc.).
- **notebook/**: notebook Colab con l'intera analisi.
- **report/**: sorgenti LaTeX/Overleaf e PDF finale della relazione.
- **license** – contiene la licenza del progetto e le informazioni relative ai termini di utilizzo, modifica e distribuzione.

## Istruzioni per l'esecuzione
1. Apire il notebook “notebooks/Progetto_Data_Science_gruppo9.ipynb” in Google Colab;
2. Caricare il dataset (Employee_Attrition.csv) nella cartella “sample_data”;
3. Eseguire la prima cella di importazione delle librerie;
4. Eseguire tutte le altre celle.

Il notebook è stato sviluppato su Google Colab e utilizza librerie già disponibili nell'ambiente standard:
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Scikit-learn

## Membri del gruppo
* Margherita Marinelli: matricola 1216632, margherita.marinell5@studio.unibo.it
* Valeria Di Stefano: matricola 1216919, valeria.distefano4@studio.unibo.it
* Edoardo Moretti: matricola 1216449, edoardo.moretti5@studio.unibo.it

## Report 
Il report scientifico completo, con discussione metodologica e interpretazione critica dei risultati, è disponibile nella cartella report/ che contiene sia il PDF finale che i file sorgenti Overleaf.

## Uso di assistenti LLM
Sono stati utilizzati principalmente per:
- Interpretare grafici e valori di parametri;
- Supporto nella scrittura del codice;
- Supporto nella scrittura del report in LateX, attraverso pacchetti e comandi non conosciuti precedentemente. 
