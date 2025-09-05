🍄 Mushroom Classification with PCA & Logistic Regression
📌 Project Overview

This project applies Dimensionality Reduction (PCA) and Logistic Regression to the Mushroom Dataset.
The dataset consists entirely of categorical features, with the target variable being the class of mushroom:

e → Edible

p → Poisonous

The objectives of this project are:

Perform Exploratory Data Analysis (EDA) and preprocessing.

Apply Principal Component Analysis (PCA) to reduce dimensionality.

Visualize variance explained and class separability.

Train Logistic Regression models before and after PCA.

Compare performance to evaluate the impact of PCA.

📂 Dataset

Source: UCI Mushroom Dataset

Rows: 8124 samples

Features: 22 categorical attributes + target (class)

Target Variable:

e → Edible

p → Poisonous

⚙️ Steps Performed
Part A – EDA & Preprocessing

Load dataset → Checked structure and target column (class).

One-hot encoding → Converted categorical features into numerical binary columns.

Necessary because PCA only works on numerical data.

Separation → Split into X (features) and y (target).

Initial Analysis → Observed feature expansion after encoding:

Before encoding: (8124, 23)

After encoding: (8124, 117)

Standardization → Applied StandardScaler to scale binary features.

Ensures equal contribution of all features.

Part B – Principal Component Analysis (PCA)

Applied PCA without fixing component number.

Scree Plot:

Plotted explained variance ratio and cumulative explained variance ratio.

Identified the number of components required to retain 95% variance (~60 PCs).

Visualization:

Projected dataset on first two PCs.

Edible and poisonous mushrooms formed partially separable clusters.

Part C – Logistic Regression Performance

Baseline Model (without PCA):

Trained Logistic Regression on full standardized dataset.

Achieved very high accuracy (>95%).

Confusion Matrix shows excellent class separation.

PCA Model:

Transformed dataset using optimal number of PCs (~95% variance retained).

Trained Logistic Regression again.

Accuracy was almost the same, confirming PCA preserved most useful variance.

Comparison:

Baseline and PCA models had similar performance.

PCA reduced dimensionality, removed collinearity, and improved efficiency.

📊 Key Visualizations

Scree Plot – Explained variance vs. number of components.

2D Scatter Plot (PC1 vs PC2) – Partial separability between edible & poisonous mushrooms.

Confusion Matrices – Before and after PCA, showing classification performance.

🔍 Findings

One-hot encoding was necessary to convert categorical features for PCA.

Standardization ensured fair contribution of features.

PCA successfully reduced 117 features → ~60 PCs, while retaining 95% variance.

Logistic Regression performed almost equally well before and after PCA, proving PCA preserved information while reducing redundancy.

PCA is beneficial for:

Handling collinearity

Improving computational efficiency

Enabling better visualization of high-dimensional data

🚀 How to Run

Clone this repo or download the notebook and dataset.

Install dependencies:

pip install pandas numpy matplotlib seaborn scikit-learn


Place the dataset file (mushrooms.csv) in the same folder as the notebook.

Run the notebook cell by cell in Jupyter Notebook or Google Colab.

✅ Conclusion

PCA is a powerful tool for reducing high-dimensional categorical data after one-hot encoding.

Even though the accuracy difference was minimal, PCA improved efficiency and provided clearer insights into class separability.

Logistic Regression proved to be a reliable surrogate for evaluating PCA effectiveness.

✍️ Prepared By: Your Name – DA5401 Assignment A2
