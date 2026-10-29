Heart Disease Prediction Using Machine Learning


About the Project:


This project applies machine learning classification techniques to the Cleveland Heart Disease dataset from the UCI Machine Learning Repository. It compares Random Forest, Gradient Boosting, K-Nearest Neighbors (KNN), and a hybrid Stacking Classifier to classify whether a patient has an indication of heart disease based on clinical attributes. Model performance is evaluated using multiple classification metrics and visualizations.



Objectives:


- Analyze clinical attributes associated with heart disease.


- Clean and preprocess the dataset, including handling missing values.


- Engineer an additional risk-related feature.


- Train and compare multiple machine learning classifiers.


- Evaluate model performance using classification metrics.


- Visualize confusion matrices, ROC curves, precision-recall curves, and model comparisons.


Dataset:

The project uses the Cleveland Heart Disease dataset from the UCI Machine Learning Repository.

Dataset URL:

https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/processed.cleveland.data


The dataset contains clinical attributes such as:

[Feature | Description]

 `age` | Age in years 

`sex` | Sex code 

 `cp` | Chest pain type 

 `trestbps` | Resting blood pressure 
 
 `chol` | Serum cholesterol 
 `fbs` | Fasting blood sugar indicator 
 `restecg` | Resting electrocardiographic results 
 `thalach` | Maximum heart rate achieved 
 `exang` | Exercise-induced angina indicator 
 `oldpeak` | ST depression induced by exercise 
 `slope` | Slope of the peak exercise ST segment 
 `ca` | Number of major vessels visualized 
 `thal` | Thalassemia-related coded value 
 `target` | Original heart disease severity value, converted to binary 


The original target values are converted into two classes:


- `0`: No heart disease indicated by the original target coding.

- 
- `1`: Heart disease indicated by the original target coding.



This binary classification is created by converting all original target values greater than zero to `1`.



Technologies Used:

- Python 3


- Pandas


- NumPy


- Matplotlib


- Seaborn


- Scikit-learn


- Jupyter Notebook



Machine Learning Models:


1. Random Forest Classifier


Uses an ensemble of decision trees to classify the target. The model is configured with 200 estimators and a maximum depth of 8.



2. Gradient Boosting Classifier


Builds an ensemble of trees sequentially, with each stage improving on the previous model's errors. The configuration uses 150 estimators and a learning rate of 0.05.



3. K-Nearest Neighbors (KNN)


Classifies samples based on the nearest observations in the feature space. The model uses 7 neighbors.


4. Hybrid Stacking Classifier


Combines Random Forest, Gradient Boosting, and KNN predictions using Logistic Regression as the final estimator. The stacking model uses 10-fold cross-validation for its internal training procedure.



Project Workflow:

1. Import Libraries: Load the data analysis, visualization, and machine learning libraries.


2. Load Dataset: Read the Cleveland dataset directly from the UCI repository.


3. Handle Missing Values: Replace missing values represented by `?` with column medians.


4. Binary Target Conversion: Convert the original target into a binary classification label.


5. Feature Engineering: Create a `risk_multiplier` feature using `oldpeak`, `ca`, `age`, and `thalach`.


6. Prepare Features: Separate the input features from the target variable.


7. Train-Test Split: Split the data into 80% training and 20% testing sets using `random_state=42`.


8. Feature Scaling: Standardize the features using `StandardScaler`, fitted on the training data.


9. Model Training: Train the four classification models.


10. Evaluation: Calculate performance metrics and generate comparison visualizations.



Evaluation Metrics:


The project evaluates each model using the following metrics:


- Accuracy: Proportion of predictions that are correct.


- Precision: Proportion of positive predictions that are correct.


- Recall: Proportion of actual positive cases identified by the model.


- F1 Score: Harmonic mean of precision and recall.


- ROC-AUC: Measures how well the model distinguishes between the two classes across classification thresholds.


The notebook also generates classification reports and confusion matrices to provide additional details about model predictions.



Visualizations:


The notebook produces the following visualizations:

- Feature Correlation Matrix: Displays correlations among dataset features.


- Confusion Matrices: Shows actual versus predicted classifications for each model.


- Model Performance Comparison: Compares accuracy, precision, recall, F1 score, and AUC.


- ROC Curve Comparison: Compares the models' true positive and false positive rates.


- Precision-Recall Curves: Illustrates the relationship between precision and recall at different thresholds.



Project Structure:



```text
Heart-Disease-Prediction/
|
|-- HeartDisease.ipynb
|-- README.md
```


The dataset is loaded directly from the UCI repository, so an internet connection is required when executing the notebook. A separate CSV file is not required unless you choose to download and store the dataset locally.


Installation and Setup:


1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<your-repository>.git
cd <your-repository>
```

Replace the placeholders with your GitHub username and repository name.

Alternatively, download the repository and open it in Visual Studio Code.


2. Install Dependencies

Install the required Python libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```


3. Run the Notebook

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `HeartDisease.ipynb` and run the cells in order.

One can also open the notebook directly in VS Code if you have installed the Python and Jupyter extensions.



Results:

The notebook prints the evaluation results for all four models and displays visual comparisons of their performance.

The best-performing model should be identified from the actual evaluation results after running the notebook. No fixed accuracy or performance score is assumed in this README.


Limitations:

- The project uses a relatively small, historical dataset.


- Median imputation may not accurately represent missing clinical values.


- The engineered `risk_multiplier` is a mathematical feature and is not a clinically validated risk score.


- A single random train-test split may not provide a complete estimate of model generalization.


- High classification performance does not establish clinical reliability or prove that a feature causes heart disease.



Future Enhancements:

- Apply cross-validation to compare models more robustly.


- Tune hyperparameters using GridSearchCV or RandomizedSearchCV.


- Add feature importance and model explainability techniques.


- Develop an interactive web interface for educational predictions.


- Validate the models on additional datasets.


- Save trained models for reuse without retraining.



Disclaimer:

This project is intended for educational and research purposes only. It is not a medical diagnostic tool and must not be used to make clinical decisions. Predictions require validation by qualified healthcare professionals and appropriate clinical evidence.


License:

No license is currently specified.
