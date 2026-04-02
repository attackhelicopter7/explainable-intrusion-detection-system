# explainable-intrusion-detection-system
Explainable intrusion detection system using ML and counterfactual explanations (DiCE) to improve trust in cybersecurity models.

# Explainable Intrusion Detection System

This project focuses on building a behavior-based intrusion detection system using machine learning, with an emphasis on making model decisions interpretable through counterfactual explanations.

## Problem

Most machine learning-based intrusion detection systems operate as black boxes. While they can achieve high accuracy, they provide little insight into why a particular network flow is classified as malicious. This lack of transparency makes it difficult for security analysts to trust or validate the system in real-world environments.

## Approach

The project builds a complete pipeline starting from raw network activity to explainable predictions.

- Network binaries were executed in a sandbox environment to simulate real malware behavior and generate traffic.
- PCAP data was processed using CIC Flow Meter to extract flow-level features such as packet statistics, inter-arrival times, and flag counts.
- The dataset was cleaned, normalized, and prepared for training.

Multiple models were implemented and compared, including KNN, Random Forest, Gradient Boosting, and neural networks. Performance was evaluated using metrics such as TPR, FPR, TNR, FNR, and ROC curves.

## Explainability

The main focus of the project is on interpretability.

Counterfactual explanations were generated using DiCE (Diverse Counterfactual Explanations). For a given prediction, the system identifies the smallest changes in feature values that would alter the classification.

This helps answer questions like:
- Which features are actually driving the prediction?
- How sensitive is the model to specific behavioral patterns?
- Are the decisions consistent with expected network behavior?


## Key Contribution

Instead of treating explainability as an add-on, it is integrated directly into the pipeline.

Counterfactual samples were also used to augment the dataset and retrain the model, improving both robustness and reliability.


## Results

Among the tested models, Gradient Boosting performed best in terms of overall metrics. Counterfactual analysis provided clear insight into decision boundaries and highlighted the features most influential in classification.


## Why This Matters

In practical cybersecurity settings, predictions alone are not sufficient. Analysts need to understand why a system flags traffic as malicious. This project addresses that gap by combining detection with explanation, making the system more transparent and usable in real scenarios.


## Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- TensorFlow  
- XGBoost  
- DiCE  
- Matplotlib  

## Dataset

Only a sample dataset is included due to size constraints. The full dataset was generated through sandboxed execution of binaries and network traffic capture.

## Future Work

- Real-time deployment  
- Integration with security monitoring systems  
- Further exploration of deep learning models  
- Automated explainability analysis  

## Author

Devyansh Tiwari
