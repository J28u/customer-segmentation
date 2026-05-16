# Customer Segmentation

**OpenClassrooms — Data Scientist Path | Project 5** (February – March 2023)

> Note: project deliverables (notebooks, presentation) are in French.

## Sectors
Marketing & Communication · E-commerce & Retail

## Tech Stack
- Jupyter Notebook
- Python: scikit-learn, pandas, numpy, matplotlib, seaborn

## Keywords
unsupervised learning, clustering, PCA, RFM features, model maintenance

## Context
The marketing teams of Olist, a Brazilian e-commerce marketplace, want to optimise their communication campaigns. To do so, they need a clear picture of the different consumer profiles purchasing through the platform.

## Mission
- Build a clustering model that groups customers with similar behaviours into segments that are directly usable by the marketing team.
- Establish a **maintenance contract**: simulate how quickly the segmentation degrades over time and estimate how frequently the model should be retrained to remain relevant.

## Selected Algorithm
**KMeans**

## Deliverables
- `notebook_exploration.ipynb` — exploratory data analysis
- `notebook_modelisation.ipynb` — modelling experiments across different algorithms and feature sets
- `notebook_maintenance.ipynb` — simulation to determine the required model update frequency
- `toolbox.py` — helper functions used across notebooks
- `presentation.pdf` — presentation slides (in French)

## Methodology

1. **Data cleaning**
   - Aggregate multiple relational tables into a single customer-level dataset
   - Impute missing values and handle outliers

2. **Feature engineering & preprocessing**
   - Build RFM features (Recency, Frequency, Monetary value)
   - Apply StandardScaler and log transformations

3. **Modelling**
   - Benchmark three algorithms: DBSCAN, Agglomerative Hierarchical Clustering, KMeans
   - Select the best model based on three criteria:
     - **Business relevance**: segments make sense when compared against domain knowledge (boxplots, radar charts)
     - **Balance**: segments are roughly balanced in size (pie chart)
     - **Cohesion & separation**: measured with the Silhouette coefficient

4. **Maintenance simulation**
   - At each time interval *tᵢ*, compare the clustering of *M₀* on *C₀* vs. *M₀* on *Cᵢ* using the Adjusted Rand Index
   - Define retraining trigger: model should be retrained when the Adjusted Rand Index drops below 0.8

## Skills
- Selecting and tuning unsupervised learning algorithms for a business problem
- Engineering and transforming features for clustering models
- Evaluating clustering quality with relevant metrics
- Simulating model drift to define a maintenance strategy

## Data Source
[Kaggle — Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/olistbr/brazilian-ecommerce)
