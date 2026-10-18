[README.md](https://github.com/user-attachments/files/33633134/README.md)
# Diabetes Risk Prediction: Data Preprocessing and Exploratory Analysis

**Student:** Binu Thomas  
**Class:** DAF49

## Project overview

This project explores a synthetic diabetes-risk dataset using Python. It covers project definition, data preprocessing, and exploratory data analysis (EDA) with and without visualization. The aim is to understand the data, address data-quality issues, and describe patterns across the supplied Low, Moderate, and High risk labels.

The current submission covers Phases 1–3. It does not train or evaluate a prediction model.

## Dataset

- **Source:** [Diabetes Risk Prediction on Kaggle, by Mansi Aggarwal](https://www.kaggle.com/datasets/mansiaggarwal88/diabetes-risk-prediction)
- **Original file:** `diabetes_risk.csv`
- **Rows:** 15,000
- **Columns:** 19
- **Supplied label:** `diabetes_risk` — Low, Moderate, or High
- **Nature of data:** Synthetic records created for analysis; not an independent sample of real patients.

The source is credited to its Kaggle publisher. This project does not claim ownership of the dataset; consult the source page for its usage terms.

## Feature descriptions

| Column | Description |
|---|---|
| `patient_id` | Synthetic record identifier |
| `age` | Age in years |
| `gender` | Recorded gender category |
| `city` | Simulated city |
| `bmi` | Body mass index |
| `family_history_diabetes` | Recorded family-history category |
| `physical_activity_level` | Physical-activity category |
| `diet_type` | Diet category |
| `smoking_status` | Smoking category |
| `alcohol_consumption` | Alcohol-consumption category |
| `hours_sleep_per_night` | Nightly sleep duration |
| `stress_level` | Recorded stress score |
| `fasting_blood_sugar` | Simulated fasting blood-sugar measurement |
| `hba1c_level` | Simulated HbA1c measurement |
| `blood_pressure_systolic` | Simulated systolic blood-pressure measurement |
| `blood_pressure_diastolic` | Simulated diastolic blood-pressure measurement |
| `waist_circumference_cm` | Waist circumference in centimetres |
| `income_bracket` | Recorded income category |
| `diabetes_risk` | Supplied Low, Moderate, or High label |

## Project files

Keep the following files together in the repository's main folder:

- `Diabetes_Phases_1_2_3_EDA.ipynb` — notebook containing the code, tables, charts, explanations, and insights.
- `diabetes_risk.csv` — original input dataset.
- `README.md` — project description and instructions.

Running the notebook also creates `diabetes_cleaned.csv`. This is an output file; the notebook starts from the original CSV.

## Work completed

### Phase 1: Project definition

Problem definition, project aim, dataset description, source, and feature descriptions.

### Phase 2: Preprocessing

- Inspect dataset dimensions, data types, and summaries.
- Remove extra spaces and identify blank or missing values.
- Fill missing categorical responses with `Unknown`; use numerical medians where required, excluding the identifier and label.
- Check for and remove exact duplicate rows if present.
- Flag unusual values using the 1.5 × IQR rule across eight measurement columns, retaining the original measurements.
- Create age groups and data-quality features.
- Export the cleaned dataset.

### Phase 3: Exploratory data analysis

- **Univariate:** category counts, proportions, numerical summaries, risk-label bars, and histograms.
- **Bivariate:** grouped summaries, cross-tabulations, boxplots, and activity/risk comparisons.
- **Multivariate:** measurements displayed together with risk labels; a correlation heatmap summarizes pairwise relationships across several measurements.
- **Interactive Plotly charts:** risk-label bar chart, BMI boxplot by risk, and fasting-measurement/HbA1c scatter plot coloured by risk.
- English insights appear below every visual, including separate insights for individual chart panels.

## How to run

1. Download the notebook and `diabetes_risk.csv` into the same folder.
2. Install Python and the required packages. In a terminal, run:

   ```bash
   python -m pip install notebook pandas matplotlib plotly
   ```

3. Launch Jupyter from that folder:

   ```bash
   python -m notebook
   ```

4. Open `Diabetes_Phases_1_2_3_EDA.ipynb` directly in Jupyter.
5. Choose **Restart Kernel and Run All Cells**, or restart the kernel and run every cell from top to bottom.
6. Review the outputs and save the notebook.

Do not paste the raw contents of an `.ipynb` file into a Code cell. Loading the CSV and assigning `original_rows, original_columns = df.shape` must happen before printing those variables.

For interactive Plotly charts, open and run the notebook in Jupyter. A static repository preview may not support hover, zoom, or legend selection. If Jupyter marks a notebook untrusted, review its code before trusting and running it.

## Main findings

- The supplied labels contain **9,000 Low (60%)**, **3,750 Moderate (25%)**, and **2,250 High (15%)** records.
- The cleaned dataset retains **15,000 rows** and has **23 columns**, including engineered features.
- No exact duplicate rows were removed.
- The IQR checks flag **1,239 records** for review without deleting their measurements.
- BMI and waist circumference have a positive correlation of approximately **0.936**.
- Fasting blood sugar and HbA1c have a positive correlation of approximately **0.913**.
- Measurement summaries differ across supplied risk labels, with overlap between groups.

## Limitations

The dataset is synthetic, and its generation recipe uses some measurements to construct the labels. The observed relationships therefore do not independently validate diabetes risk prediction. Correlation does not establish causation, and these results must not be used for medical diagnosis. No predictive accuracy is claimed for this EDA submission.
