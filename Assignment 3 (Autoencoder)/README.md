# Assignment 3: Credit Card Customer Risk Management Using Autoencoder

## Project Overview

This project investigates how unsupervised learning methods can improve customer risk management in the credit card industry. Using the "German Credit Card Case" dataset, we explore the effectiveness of unsupervised learning, particularly autoencoders, in enhancing credit risk classification. The dataset consists of 1,000 observations and 22 variables, including features such as credit history, credit amount, employment status, and the purpose of credit. Our analysis compares a baseline logistic regression model with an autoencoder-pretrained logistic regression model to determine the optimal approach for customer classification.

## Methodology

The project begins with data preprocessing steps to ensure the dataset is ready for model training. Key steps include:

- **Handling missing categories:** The `personal_status` variable was converted into a factor, excluding the "female single" category as it had no observations.
- **Consolidating low-frequency categories:** The `purpose` variable was recoded to combine infrequent categories into an "other" group.
- **Log transformation:** A log transformation was applied to the highly skewed `credit_amount` variable to reduce skewness.

A **baseline logistic regression model** was then fitted using cross-validation. The dataset was divided into five folds, with precision, recall, F1-score, and total cost calculated using two cutoff values—0.5 (standard) and 0.086 (based on the company’s risk tolerance). These metrics allowed us to evaluate model performance in predicting whether credit card applicants are classified as "good" or "bad" risks.

Next, **unsupervised pre-training** was performed using autoencoders. The data was normalized and converted into a design matrix via one-hot encoding. Three autoencoder models were trained with different configurations:

- **Model 1:** Used a sigmoid activation function.
- **Model 2:** Used a ReLU activation function.
- **Model 3:** Used ReLU activation with a dropout regularization layer to prevent overfitting.

The autoencoder models were trained using 100 epochs and a batch size of 32. Model 2, which had the lowest loss and highest accuracy, was selected to pretrain the dataset before retraining the logistic regression model.

## Results

The results of the analysis reveal that the **baseline logistic regression model** outperformed the autoencoder-pretrained model in terms of precision, F1-score, and total cost:

- **Baseline Logistic Regression:**
  - Precision: 0.374
  - Recall: 0.923
  - F1-Score: 0.532
  - Total Cost: 116

- **Autoencoder-Pretrained Logistic Regression:**
  - Precision: 0.303
  - Recall: 0.986
  - F1-Score: 0.464
  - Total Cost: 140

While the autoencoder-pretrained model demonstrated higher recall, the baseline logistic regression model performed better overall in key metrics such as precision, F1-score, and cost. The baseline model’s simplicity also makes it easier to interpret, which is an important factor in credit risk management. Although unsupervised learning methods like autoencoders can sometimes enhance model performance, in this case, the more simplistic logistic regression model without pretraining was the optimal choice.

## Conclusion

This study tested the hypothesis that unsupervised learning, specifically auto-encoding, would improve logistic regression for customer segmentation. While the autoencoder-pretrained model delivered similar results, the baseline logistic regression model outperformed it in key metrics. Ultimately, the simplicity and interpretability of the logistic regression model make it the better choice for this problem, demonstrating that sometimes simpler models are more effective, even when advanced techniques are available.

### Contributors

This project was a collaborative effort by the following team members:

- David Caban
- Bronsin Jabraeili
- Scott Jue
