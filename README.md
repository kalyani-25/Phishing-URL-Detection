# 🛡️ Phishing URL Detection using Machine Learning

Phishing remains a top cyber threat, targeting users through deceptive websites that mimic legitimate ones to steal sensitive information. This project presents a **machine learning-based phishing URL detection system** built with Python, capable of analyzing and classifying URLs in real-time using engineered features and neural networks.

## 📌 Overview
- 🔍 **Objective**: Detect phishing URLs using machine learning.
- 📊 **Dataset**: 1.17M URLs (phishing & legitimate), balanced down to 347,774 for training.
- 🧠 **Models**: GRU-based RNN and Fully Connected Neural Network (FCNN).
- 🔄 **Data Sources**: https://urlscan.io, https://www.hybrid-analysis.com

## 📂 Project Structure
phishing-url-detector/
├── data/
│   ├── malicious_data.csv
│   ├── legitimate_data.csv
│   └── balanced_dataset.csv
├── models/
│   ├── train_gru.py
│   ├── train_fcnn.py
├── utils/
│   └── preprocessing.py
├── predict.py
├── requirements.txt
└── README.md


## 🧠 Model Architectures
1. GRU:
   - Sequential RNN model for URL sequences
   - High validation accuracy (99.93%) but overfit

2. FCNN:
   - Dense layers with ReLU and Dropout
   - Generalizes better, 82% accuracy on real test data

## 📊 Results & Evaluation
| Metric         | GRU Model | FCNN Model |
|----------------|-----------|------------|
| Accuracy       | 99.96%    | 82%        |
| Precision (1)  | 100%      | 76%        |
| Recall (1)     | 100%      | 92%        |
| F1-Score (1)   | 0.9996    | 83%        |
| Status         | Overfit   | ✅ Final   |

## ⚙️ Feature Engineering
- URL_Length
- Num_Subdomains
- Suspicious_Chars
- Phishing_Patterns
- Has_IP, Has_Port
- digit_letter_ratio

## 🔐 Real-Time Integration
- Live feeds via URLScan.io & Hybrid Analysis
- Keeps model updated with latest phishing patterns

## 🧪 Example
python predict.py --url "http://secure-login-paypal.com"
Result: 🚨 Phishing Detected! (Probability: 0.87)

## 🧭 Future Work
- API deployment (Flask/FastAPI)
- Add domain reputation & WHOIS lookup
- Browser plugin integration

## 📚 References
- https://urlscan.io
- https://www.hybrid-analysis.com
- PhishNet, PhishZoo, CANTINA+, PhishPedia (academic works)
