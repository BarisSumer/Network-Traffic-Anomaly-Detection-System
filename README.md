# 🛡️ Network Traffic Anomaly Detection System

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Flask](https://img.shields.io/badge/Framework-Flask-green)
![ML](https://img.shields.io/badge/AI-Scikit--Learn%20%7C%20XGBoost-orange)
![Analysis](https://img.shields.io/badge/Network-PyShark%20(Wireshark)-red)

A comprehensive cybersecurity project designed to detect network anomalies and potential intrusions using Machine Learning. This system compares supervised and unsupervised algorithms on standard datasets (CICIDS2017, KDD99, UNSW-NB15) and includes a **Flask Web Interface** to analyze real-world traffic (PCAP files) in real-time.

## 🌟 Features

* **Multi-Dataset Training:** Models trained and tested on three major cybersecurity datasets:
    * **CICIDS2017**
    * **KDD99**
    * **UNSW-NB15**
* **Machine Learning Models:**
    * *Supervised:* Random Forest, XGBoost, Decision Tree, SVM.
    * *Unsupervised:* Isolation Forest, One-Class SVM (for zero-day anomaly detection).
* **Live Traffic Analysis:** Uses `PyShark` to parse `.pcap` files, extract features (IPs, Ports, Protocols, Length), and detect anomalies using Isolation Forest.
* **Web Dashboard:** A Flask-based UI to upload traffic files, view visualizations (Confusion Matrices, ROC Curves), and generate **PDF Reports**.
* **Visualization:** Automatically generates Heatmaps, ROC Curves, and Feature Importance charts.

## 🏗️ Architecture

The project consists of three main modules:

1.  **Model Training (`main.py`):** Preprocesses datasets, trains models, evaluates performance (Accuracy, F1-Score), and saves performance graphs.
2.  **Traffic Analyzer (`MyOwnNetwork.py`):** Captures or reads network packets using Wireshark's engine (TShark), anonymizes IPs, and flags anomalous packets.
3.  **Web Dashboard (`app.py`):** Serves the results and allows users to upload their own traffic files for analysis.

## 📊 Model Performance

Based on the generated reports, the system achieves high accuracy across different datasets. **Random Forest** and **XGBoost** generally yielded the best results.

| Dataset | Best Model | Accuracy | F1 Score |
| :--- | :--- | :--- | :--- |
| **CICIDS2017** | Random Forest | ~99.7% | 0.96 |
| **KDD99** | XGBoost | ~99.9% | 0.99 |
| **UNSW-NB15** | Random Forest | ~97.5% | 0.96 |

*> Note: Unsupervised models (Isolation Forest) had lower accuracy but are essential for detecting unknown attack patterns.*

## 🛠️ Installation

### Prerequisites
* Python 3.x
* **Wireshark (TShark):** Required for `pyshark` to parse PCAP files.
    * *Windows:* Install Wireshark and ensure `tshark.exe` is in your PATH.
    * *Mac/Linux:* `brew install wireshark` or `sudo apt install tshark`.

### Dependencies
Install the required Python libraries:

```bash
pip install flask pandas numpy scikit-learn xgboost matplotlib seaborn pyshark xhtml2pdf openpyxl

Based on the code files (main.py, MyOwnNetwork.py, app.py) and the analysis report you provided, here is a professional README.md for your Network Traffic Anomaly Detection System.

This README highlights the machine learning models used, the Flask web interface, and the capability to analyze real-world PCAP files.

Markdown

# 🛡️ Network Traffic Anomaly Detection System

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Flask](https://img.shields.io/badge/Framework-Flask-green)
![ML](https://img.shields.io/badge/AI-Scikit--Learn%20%7C%20XGBoost-orange)
![Analysis](https://img.shields.io/badge/Network-PyShark%20(Wireshark)-red)

A comprehensive cybersecurity project designed to detect network anomalies and potential intrusions using Machine Learning. This system compares supervised and unsupervised algorithms on standard datasets (CICIDS2017, KDD99, UNSW-NB15) and includes a **Flask Web Interface** to analyze real-world traffic (PCAP files) in real-time.

## 🌟 Features

* **Multi-Dataset Training:** Models trained and tested on three major cybersecurity datasets:
    * **CICIDS2017**
    * **KDD99**
    * **UNSW-NB15**
* **Machine Learning Models:**
    * *Supervised:* Random Forest, XGBoost, Decision Tree, SVM.
    * *Unsupervised:* Isolation Forest, One-Class SVM (for zero-day anomaly detection).
* **Live Traffic Analysis:** Uses `PyShark` to parse `.pcap` files, extract features (IPs, Ports, Protocols, Length), and detect anomalies using Isolation Forest.
* **Web Dashboard:** A Flask-based UI to upload traffic files, view visualizations (Confusion Matrices, ROC Curves), and generate **PDF Reports**.
* **Visualization:** Automatically generates Heatmaps, ROC Curves, and Feature Importance charts.

## 🏗️ Architecture

The project consists of three main modules:

1.  **Model Training (`main.py`):** Preprocesses datasets, trains models, evaluates performance (Accuracy, F1-Score), and saves performance graphs.
2.  **Traffic Analyzer (`MyOwnNetwork.py`):** Captures or reads network packets using Wireshark's engine (TShark), anonymizes IPs, and flags anomalous packets.
3.  **Web Dashboard (`app.py`):** Serves the results and allows users to upload their own traffic files for analysis.

## 📊 Model Performance

Based on the generated reports, the system achieves high accuracy across different datasets. **Random Forest** and **XGBoost** generally yielded the best results.

| Dataset | Best Model | Accuracy | F1 Score |
| :--- | :--- | :--- | :--- |
| **CICIDS2017** | Random Forest | ~99.7% | 0.96 |
| **KDD99** | XGBoost | ~99.9% | 0.99 |
| **UNSW-NB15** | Random Forest | ~97.5% | 0.96 |

*> Note: Unsupervised models (Isolation Forest) had lower accuracy but are essential for detecting unknown attack patterns.*

## 🛠️ Installation

### Prerequisites
* Python 3.x
* **Wireshark (TShark):** Required for `pyshark` to parse PCAP files.
    * *Windows:* Install Wireshark and ensure `tshark.exe` is in your PATH.
    * *Mac/Linux:* `brew install wireshark` or `sudo apt install tshark`.

### Dependencies
Install the required Python libraries:

```bash
pip install flask pandas numpy scikit-learn xgboost matplotlib seaborn pyshark xhtml2pdf openpyxl
🚀 Usage
1. Training the Models
To retrain models on the datasets and generate static reports:

Bash

python main.py
Make sure to update the CSV file paths in main.py to point to your local datasets.

2. Analyzing Custom Traffic (CLI)
To analyze a specific .pcap file in the terminal:

Bash

python MyOwnNetwork.py
3. Launching the Web Dashboard
To start the web interface and generate PDF reports:

Bash

python app.py
Open your browser at http://127.0.0.1:5000.

Go to "Upload Traffic" to analyze a .pcap or .csv file.

Download the analysis as a PDF.

📂 File Structure
Plaintext

├── main.py              # ML Training & Evaluation (CICIDS, KDD, UNSW)
├── MyOwnNetwork.py      # Script for parsing and analyzing PCAP files
├── app.py               # Flask Web Server & PDF Generation
├── static/
│   └── plots/           # Generated graphs (ROC, Confusion Matrix, etc.)
├── templates/
│   ├── index.html       # Dashboard Home
│   ├── results.html     # Model Comparison Results
│   └── ...              # Other HTML templates
└── uploads/             # Temp folder for user uploaded traffic files
⚠️ Disclaimer
This project handles network packet data. Ensure you have authorization before capturing or analyzing traffic on any network. The provided datasets (CICIDS, KDD) are for educational and research purposes.
