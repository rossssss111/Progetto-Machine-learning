# Progetto Machine Learning — Water Potability

Classificatore binario per la previsione della **potabilità dell'acqua** basato su **Random Forest**, sviluppato come progetto universitario in Python con Jupyter Notebook.

---

## Cosa fa

Il progetto analizza un dataset di campioni d'acqua con 9 parametri chimico-fisici e allena un modello di classificazione per determinare se un campione è **potabile (1)** o **non potabile (0)**.

Il flusso di lavoro completo è contenuto nel notebook `ProgettoML.ipynb` e si articola in:

1. **Caricamento e analisi esplorativa (EDA)**
   - Visualizzazione delle prime righe e statistiche descrittive
   - Heatmap dei valori mancanti (missing values)
   - Distribuzione delle classi (bilanciamento del dataset)
   - Matrice di correlazione tra le feature

2. **Preprocessing**
   - Imputazione dei valori mancanti con la **mediana** per le colonne `ph`, `Sulfate` e `Trihalomethanes`

3. **Training del modello**
   - Divisione train/test: **80% / 20%** con stratificazione
   - Modello: `RandomForestClassifier` con 100 estimatori

4. **Valutazione**
   - Classification report (precision, recall, F1-score)
   - Matrice di confusione visualizzata graficamente

---

## Dataset

**File:** `water_potability.csv`  
**Righe:** 3.276 campioni  
**Target:** `Potability` (0 = non potabile, 1 = potabile)

| Feature | Descrizione |
|---|---|
| `ph` | Valore di pH dell'acqua |
| `Hardness` | Durezza (mg/L) |
| `Solids` | Solidi disciolti totali (ppm) |
| `Chloramines` | Clorammine (ppm) |
| `Sulfate` | Solfati (mg/L) |
| `Conductivity` | Conducibilità elettrica (μS/cm) |
| `Organic_carbon` | Carbonio organico totale (ppm) |
| `Trihalomethanes` | Trialometani (μg/L) |
| `Turbidity` | Torbidità (NTU) |

> Le colonne `ph`, `Sulfate` e `Trihalomethanes` contengono valori mancanti, gestiti nel preprocessing.

---

## Struttura del progetto

```
Progetto-Machine-learning-main/
├── ProgettoML.ipynb          # Notebook principale (EDA + training + valutazione)
├── water_potability.csv      # Dataset
└── Water Potability.pptx     # Presentazione del progetto
```

---

## Requisiti

- Python 3.8+
- Jupyter Notebook o JupyterLab

### Librerie Python

```
pandas
seaborn
matplotlib
scikit-learn
```

---

## Installazione e avvio

### 1. Clonare il repository

```bash
git clone https://github.com/utente/Progetto-Machine-learning.git
cd Progetto-Machine-learning
```

### 2. Creare un ambiente virtuale (consigliato)

```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows
```

### 3. Installare le dipendenze

```bash
pip install pandas seaborn matplotlib scikit-learn notebook
```

### 4. Avviare Jupyter

```bash
jupyter notebook ProgettoML.ipynb
```

Aprire il browser su `http://localhost:8888` e eseguire le celle in ordine.

---

## Risultati

Il modello `RandomForestClassifier` con 100 alberi produce una **matrice di confusione** e un **classification report** con metriche di precision, recall e F1-score separate per le due classi (potabile / non potabile).

---

## Possibili miglioramenti

- Hyperparameter tuning (GridSearchCV / RandomizedSearchCV)
- Confronto con altri modelli (SVM, XGBoost, regressione logistica)
- Gestione dello sbilanciamento delle classi (SMOTE, class_weight)
- Cross-validation k-fold per una valutazione più robusta
- Pipeline scikit-learn per unire preprocessing e modello

---

## Autore

Progetto universitario sviluppato per finalità didattiche.
