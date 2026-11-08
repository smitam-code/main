

# Multiple Classification Models Using Machine Learning



## 1. Problem Statement



The objective of this project is to develop and compare five machine learning classification algorithms using a common dataset.



The project uses the Wisconsin Breast Cancer Diagnostic Dataset to classify breast cancer observations into two categories:



- Malignant (0)

- Benign (1)



The following five classification algorithms are implemented:



1. Logistic Regression

2. Decision Tree Classifier

3. K-Nearest Neighbor (KNN) Classifier

4. Gaussian Naive Bayes Classifier

5. Support Vector Machine (SVM)



The performance of each algorithm is evaluated using six evaluation metrics:



- Accuracy

- Area Under the ROC Curve (AUC)

- Precision

- Recall

- F1 Score

- Matthews Correlation Coefficient (MCC)



An interactive Streamlit application is developed to allow users to upload test datasets, select classification models, visualize evaluation results and compare model performance.



The application uses previously trained models and does not retrain them on uploaded test data.



---



## 2. Dataset Description



**Dataset Name:** Wisconsin Breast Cancer Diagnostic Dataset



**Dataset Source:** UCI Machine Learning Repository



**Dataset URL:** https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic



### Dataset Characteristics



| Property | Description |

|---|---|

| Dataset type | Classification |

| Total instances | 569 |

| Number of input features | 30 |

| Number of target classes | 2 |

| Target column | target |

| Class 0 | Malignant |

| Class 1 | Benign |

| Training percentage | 80% |

| Testing percentage | 20% |

| Random state | 42 |



### Feature Description



The dataset contains 30 numerical features calculated from digitized images of breast cell nuclei.



These features describe:



- Radius

- Texture

- Perimeter

- Area

- Smoothness

- Compactness

- Concavity

- Concave points

- Symmetry

- Fractal dimension



Each characteristic is represented by mean, standard error or worst-value measurements.



The target variable represents whether the observation is malignant or benign.



### Dataset Preprocessing



1. Load the dataset.

2. Separate input features and target.

3. Split the dataset using an 80:20 stratified split.

4. Apply StandardScaler to models requiring feature scaling.

5. Fit preprocessing and classification models using training data only.

6. Save the fitted pipelines.

7. Export the independent test dataset as `test_data.csv`.



The Decision Tree model is used without feature scaling because tree-based algorithms generally do not require standardized input.



---



## 3. GitHub Repository Link



**GitHub Repository:** [INSERT YOUR GITHUB REPOSITORY URL HERE]



The repository contains the following files:



```text

multiple_classification_project/

│

├── app.py

├── train_models.py

├── requirements.txt

├── README.md

├── test_data.csv

│

├── model/

│   ├── logistic_regression.joblib

│   ├── decision_tree.joblib

│   ├── knn.joblib

│   ├── naive_bayes.joblib

│   └── svm.joblib

│

└── results/

&#x20;   ├── metrics.json

&#x20;   └── model_comparison.csv

```



All five trained models and their preprocessing pipelines are stored in the model directory.



The `test_data.csv` file contains the independent test records and target column.



---



## 4. Models Used



All five machine learning algorithms are trained using the same training dataset and evaluated using the same independent test dataset.



### 4.1 Logistic Regression



Logistic Regression is a supervised classification algorithm that estimates the probability of an observation belonging to a particular class.



It is used as a baseline classification model.



A StandardScaler preprocessing step is applied before training.



### 4.2 Decision Tree Classifier



Decision Tree is a supervised learning algorithm that makes classification decisions using a tree-like structure.



It divides observations based on feature values and selects decision rules to classify the input data.



The maximum tree depth is limited to five to help control model complexity.



### 4.3 K-Nearest Neighbor Classifier



KNN is a distance-based classification algorithm.



It identifies the nearest observations in the training dataset and assigns a class based on the majority class among the nearest neighbors.



The implementation uses five nearest neighbors.



StandardScaler is applied because KNN is sensitive to differences in feature scales.



### 4.4 Gaussian Naive Bayes



Gaussian Naive Bayes is a probabilistic classification algorithm based on Bayes' theorem.



It assumes that the numerical input features follow a Gaussian distribution within each class.



It calculates class probabilities and predicts the most probable class.



### 4.5 Support Vector Machine



Support Vector Machine is a supervised learning algorithm that identifies an optimal decision boundary between classes.



The implementation uses an RBF kernel to support nonlinear classification boundaries.



Probability estimation is enabled to calculate the AUC score.



StandardScaler is applied before model training.



---



## 5. Model Evaluation Metrics



The following six metrics are calculated for every model.



| Metric | Description |

|---|---|

| Accuracy | Proportion of correctly classified observations |

| AUC | Measures the ability to distinguish between classes |

| Precision | Proportion of positive predictions that are correct |

| Recall | Proportion of actual positive observations correctly identified |

| F1 Score | Harmonic mean of precision and recall |

| MCC | Measures the correlation between actual and predicted classifications |



For this binary classification problem, class 1 (Benign) is treated as the positive class for precision, recall and F1 calculations.



The AUC is calculated using predicted class probabilities.



MCC ranges from -1 to +1:



- +1 indicates perfect classification.

- 0 indicates performance equivalent to random correlation.

- -1 indicates complete disagreement.



---



## 6. Comparison of All Five Classification Models



The following table presents the required evaluation metrics.



**Note:** Populate the table using actual results generated by executing `train_models.py`. Do not use assumed or fabricated evaluation scores.



| ML Model Name | Accuracy | AUC | Precision | Recall | F1 | MCC |

|---|---:|---:|---:|---:|---:|---:|

| Logistic Regression | TBD | TBD | TBD | TBD | TBD | TBD |

| Decision Tree | TBD | TBD | TBD | TBD | TBD | TBD |

| KNN | TBD | TBD | TBD | TBD | TBD | TBD |

| Naive Bayes | TBD | TBD | TBD | TBD | TBD | TBD |

| Support Vector Machine | TBD | TBD | TBD | TBD | TBD | TBD |



The actual values are automatically calculated and saved in:



`results/model_comparison.csv`



---



## 7. Observations About Model Performance



The following observations should be finalized using the actual evaluation results generated by the project.



### 7.1 Logistic Regression



Logistic Regression provides a baseline for evaluating the classification problem.



Its performance indicates how effectively a linear decision boundary separates malignant and benign observations.



The Accuracy, AUC, Precision, Recall, F1 and MCC values should be considered when assessing its performance.



### 7.2 Decision Tree



Decision Tree identifies classification rules based on feature values.



Its performance indicates how effectively a tree-based model classifies the observations.



The model can capture nonlinear relationships but may be affected by overfitting.



### 7.3 K-Nearest Neighbor



KNN classifies observations based on similarities with neighboring training records.



Its performance depends on the selected number of neighbors and the scaling of input features.



The results indicate how effectively distance-based classification works on this dataset.



### 7.4 Naive Bayes



Gaussian Naive Bayes uses probability distributions to estimate class membership.



Its performance depends partly on how well the Gaussian distribution and feature-independence assumptions represent the dataset.



### 7.5 Support Vector Machine



SVM attempts to identify a decision boundary that separates the two classes.



The RBF kernel allows the model to capture nonlinear classification patterns.



Its performance should be evaluated using all six metrics.



### 7.6 Overall Winner for the Dataset



The overall winning model is selected using the highest F1 Score on the independent test dataset.



The winner should also be examined using AUC, Recall, MCC and Accuracy.



The application automatically identifies the model with the highest F1 Score and displays the result in the Model Comparison section.



**Final winning model:** To be filled using the actual output of `results/model_comparison.csv`.



**Reason:** The winning model achieves the highest measured F1 Score on the held-out test dataset. Its other metrics should also be considered before concluding that it is the most suitable classifier.



---



## 8. Streamlit Application



The project provides an interactive Streamlit application with the following functionality.



### 8.1 Dataset Information



Displays the dataset source, number of records, feature count and target classes.



### 8.2 Dataset Upload



Allows users to upload a CSV test dataset.



The uploaded file must contain:



- All 30 required input features.

- The target column named `target`.



Additional columns are ignored.



### 8.3 Model Selection



Users can select any of the following algorithms:



- Logistic Regression

- Decision Tree

- KNN

- Naive Bayes

- Support Vector Machine



### 8.4 Evaluation Metrics



Displays the six evaluation metrics for the selected classifier.



### 8.5 Confusion Matrix



Displays the relationship between actual and predicted class labels.



### 8.6 Classification Report



Displays class-wise precision, recall, F1 Score and support.



### 8.7 Model Comparison



Displays the performance of all five classifiers in a comparison table.



A chart allows users to compare the models based on a selected metric.



The application also provides a downloadable CSV containing the comparison results.



---



## 9. Installation and Execution Instructions



### Step 1: Clone the GitHub Repository



```bash

git clone YOUR_GITHUB_REPOSITORY_URL

```



### Step 2: Navigate to the Project Folder



```bash

cd multiple_classification_project

```



### Step 3: Install the Required Libraries



```bash

pip install -r requirements.txt

```



### Step 4: Generate Trained Models and Test Dataset



```bash

python train_models.py

```



This command generates:



- Five saved classification models.

- `test_data.csv`.

- `results/metrics.json`.

- `results/model_comparison.csv`.



### Step 5: Run the Streamlit Application



```bash

streamlit run app.py

```



The application will open in the browser.



### Step 6: Upload Test Data



Upload the generated `test_data.csv` using the sidebar.



### Step 7: Evaluate the Models



Select Model Evaluation to examine individual model performance.



Select Model Comparison to compare all five algorithms.



---



## 10. Deployment



The application can be deployed using Streamlit Community Cloud.



Deployment procedure:



1. Push all project files to GitHub.

2. Open https://share.streamlit.io/.

3. Sign in using GitHub.

4. Select the project repository.

5. Select `app.py` as the main application file.

6. Deploy the application.



Ensure that all five trained models are committed to the repository so the deployed application can load them without running the training script.



---



## 11. Conclusion



This project implements and compares five supervised machine learning classification algorithms using the Wisconsin Breast Cancer Diagnostic Dataset.



The models are evaluated using Accuracy, AUC, Precision, Recall, F1 Score and Matthews Correlation Coefficient.



The Streamlit application provides an interactive interface for uploading test data, selecting models, displaying evaluation metrics, visualizing confusion matrices and comparing all five classifiers.



The project demonstrates the complete machine learning workflow, including dataset selection, preprocessing, model training, model persistence, evaluation, visualization and web application deployment.



The final winning classifier is determined from the actual evaluation results rather than assuming that one algorithm will always perform best.



