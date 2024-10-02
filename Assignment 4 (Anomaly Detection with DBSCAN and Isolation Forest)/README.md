# Assignment 4: Fraud Detection in Sales Transactions using DBSCAN and Isolation Forest

## Project Overview

This project investigates the use of unsupervised learning techniques to detect fraudulent activities in sales transactions. Fraud in sales can lead to significant financial and reputational damage for businesses. To address this issue, we compare two widely used anomaly detection methods: Density-Based Spatial Clustering of Applications with Noise (DBSCAN) and Isolation Forest.

The analysis was conducted on a comprehensive dataset consisting of 133,371 unlabeled sales transactions across 798 products for training, and a testing dataset of 15,372 transactions, including 1,270 manually identified fraudulent transactions. The goal was to identify which method more effectively detects fraudulent sales transactions by labeling transactions as either normal or fraudulent. Given the imbalanced nature of the dataset, the F1 score was selected as the primary evaluation metric due to its ability to balance precision and recall.

The results of the analysis demonstrated that DBSCAN outperformed Isolation Forest in detecting fraudulent transactions, achieving higher accuracy, precision, recall, and F1 score. DBSCAN was also more effective in identifying true positives and true negatives, making it the superior method for fraud detection in this dataset. Precision-Recall curves and Area Under the Curve (AUC) analysis further validated the efficacy of DBSCAN.

## Methodology

Before applying the models, several preprocessing steps were conducted:
- **Handling Missing Data**: Null values in the ‘Quant’ and ‘Val’ variables were filled with zeros using the `fillna()` method, based on the decision to retain these observations.
- **Encoding Categorical Variables**: The ‘Prod’ variable was converted to numerical values using one-hot encoding, while the ‘ID’ and ‘Insp’ columns were dropped as they were not relevant for model training.
  
### Model Training

1. **Isolation Forest**:
   - The training data was used to fit an Isolation Forest model with a contamination level of 0.08, based on the prior knowledge that 1,270 out of the 15,732 transactions in the test set were fraudulent.
   
2. **DBSCAN**:
   - The DBSCAN model was trained using normalized data to account for scale differences across variables. Epsilon and minimum points for clustering were determined using the nearest neighbors algorithm and iterative testing.

Both models' predictions were compared to true labels (encoded as 0 for non-fraud and 1 for fraud) using accuracy, precision, recall, and F1-score to evaluate their effectiveness in detecting fraudulent transactions.

## Results

The comparison of DBSCAN and Isolation Forest yielded the following results:
- DBSCAN outperformed Isolation Forest across nearly all evaluation metrics:
  - Accuracy: 0.891 (DBSCAN) vs. 0.833 (Isolation Forest)
  - Precision: 0.331 (DBSCAN) vs. 0.050 (Isolation Forest)
  - Recall: 0.333 (DBSCAN) vs. 0.055 (Isolation Forest)
  - F1-Score: 0.332 (DBSCAN) vs. 0.055 (Isolation Forest)

DBSCAN also achieved a better **Area Under the Curve (AUC)** score (0.64 vs. 0.48 for Isolation Forest) and produced stronger results in the **Precision-Recall Curves**. Additionally, DBSCAN correctly classified 425 out of the 1,270 fraud transactions, while Isolation Forest only identified 48 correctly. DBSCAN's confusion matrix further highlights its superior performance in detecting both true positives and true negatives.

## Conclusion

The comparative analysis clearly indicates that DBSCAN is the recommended method for fraud detection in sales transactions. It consistently outperformed Isolation Forest across key metrics, particularly in terms of F1-Score, precision, and recall. DBSCAN's superior performance demonstrates its effectiveness in minimizing the risks associated with fraud, offering businesses a powerful tool to protect financial integrity and customer trust. The reliability and flexibility of these algorithms can be applied not only in fraud detection but also in various fields requiring anomaly detection.
