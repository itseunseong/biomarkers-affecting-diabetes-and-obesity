# NHANES Exposome Project: Predicting Obesity through Blood Chemistry

### Project Overview
This project explores the **"Exposome"** which is the measure of all the environmental exposures of an individual using the NHANES (National Health and Nutrition Examination Survey) dataset. 

The goal was to see if we could predict a person's clinical status (like Obesity) purely by looking at biomarkers in the blood rather than just demographic data or lifestyle surveys.

### Why the Pivot from Diabetes to Obesity?
Initially, I set out to predict Diabetes. However, I encountered two major scientific hurdles:
1. **Data Leakage:** Standard models achieved 99% accuracy because they were "cheating" as they were looking at Glucose and HbA1c levels, which are the very things doctors use to diagnose diabetes in the first place.
2. **Class Imbalance:** The number of confirmed diabetes cases in the dataset was quite small compared to healthy individuals, making the model's results less reliable.

I moved the focus to **Obesity** (defined as BMI ≥ 30) because it provided a much larger, more balanced dataset.

### What We Learnt
* **The Inflammatory Signal:** Our model (using **Random Forest** and **Hist-Gradient Boosting**) identified **C-Reactive Protein (CRP)** and **Triglycerides** as top predictors. This confirms the scientific theory that obesity is a state of chronic systemic inflammation.
* **Algorithm Performance:** I achieved a stable **~93% accuracy** with Random Forest. I also implemented Histogram-based Gradient Boosting to handle missing data naturally, which is a common issue in real-world clinical datasets.
* **Feature Importance:** By excluding "obvious" features like BMI from the training set, I proved that blood chemistry alone can identify a person's metabolic health with high precision.

### How to Use
1. Clone the repo.
2. Run the Jupyter Notebook.
3. The notebook will automatically download the cleaned NHANES data from Hugging Face and run the analysis.

### Tech Stack
* **Python** (Pandas, NumPy)
* **Scikit-Learn** (Random Forest, HistGradientBoosting)
* **Matplotlib & Seaborn** (Data Visualisation)
* **NHANES Open Data** (via Hugging Face)
