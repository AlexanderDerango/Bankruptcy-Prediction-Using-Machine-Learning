# Bankruptcy Prediction Model

A machine learning application that predicts whether a company is likely to be classified as bankrupt or healthy based on 18 financial indicators. The project combines a Gradient Boosting classification model with a React frontend and Flask backend to create an interactive prediction application.

## About

This project was developed as part of Machine Learning Student Network (MLSN) during Fall 2025. The goal was to explore how financial data and machine learning can be used to identify patterns associated with corporate bankruptcy.

The model uses 18 financial indicators as inputs and performs a binary classification:

* **Healthy**
* **Bankrupt**

We also built a web application around the model so users can enter financial information and receive a prediction and probability estimate.

## Repository Structure

## Repository Structure

```text
MLSN_Project_Fall_2025/
│
├── Backend (Python/Flask)
│   ├── app.py              # Main Flask application
│   ├── config.py           # Configuration management
│   ├── train_model.py      # Model training script
│   ├── requirements.txt    # Python dependencies
│   └── model.pkl           # Trained model (generated)
│
├── Frontend (React/JavaScript)
│   ├── public/
│   │   └── index.html      # HTML template
│   ├── src/
│   │   ├── index.js        # React entry point
│   │   ├── index.css       # Global styles
│   │   ├── App.js          # Root component
│   │   ├── App.css         # App styles
│   │   └── components/
│   │       ├── PredictionForm.js
│   │       ├── PredictionForm.css
│   │       ├── ResultsDisplay.js
│   │       └── ResultsDisplay.css
│   ├── package.json        # NPM dependencies
│   └── .env                # Environment variables (optional)
│
└── Documentation
    ├── README.md           # Main documentation
    ├── QUICK_START.md      # Quick setup guide
    ├── DEPLOYMENT.md       # Deployment guide
    ├── PROJECT_COMPLETION.md  # Completion summary
    └── DEVELOPER_GUIDE.md  # Developer documentation

## Features

* Machine learning bankruptcy classification
* 18 financial input parameters
* Interactive React frontend
* Flask REST API for model predictions
* Probability estimates for each prediction
* Risk-level classification
* Input validation and error handling
* Responsive interface for desktop and mobile

## Model

The project uses a **Gradient Boosting Classifier** trained on financial data.

**Model:** Gradient Boosting Classifier
**Features:** 18 financial indicators
**Task:** Binary classification
**Accuracy:** 93%

> Accuracy alone does not fully describe the performance of a bankruptcy classifier, particularly when the classes are imbalanced. Additional evaluation metrics should be considered when interpreting the model.

### Financial Features

The model uses the following 18 variables:

| Code | Financial Indicator         |
| ---- | --------------------------- |
| X1   | Current Assets              |
| X2   | Cost of Goods Sold          |
| X3   | Depreciation & Amortization |
| X4   | EBITDA                      |
| X5   | Inventory                   |
| X6   | Net Income                  |
| X7   | Total Receivables           |
| X8   | Market Value                |
| X9   | Net Sales                   |
| X10  | Total Assets                |
| X11  | Total Long-term Debt        |
| X12  | EBIT                        |
| X13  | Gross Profit                |
| X14  | Total Current Liabilities   |
| X15  | Retained Earnings           |
| X16  | Total Revenue               |
| X17  | Total Liabilities           |
| X18  | Total Operating Expenses    |

## Technology Stack

### Machine Learning / Backend

* Python
* Pandas
* NumPy
* Scikit-learn
* Joblib
* Flask

### Frontend

* React
* JavaScript
* Axios
* CSS3

## Application Architecture

The application consists of three main components:

```text
User
  ↓
React Frontend
  ↓
Flask REST API
  ↓
Gradient Boosting Model
  ↓
Prediction + Probability
  ↓
Results Display
```

The React frontend collects the 18 financial indicators and sends them to the Flask API. The backend loads the trained model, generates a prediction, and returns the prediction probabilities to the frontend.

## Running the Application

### 1. Install Backend Dependencies

```bash
cd Backend
pip install -r requirements.txt
```

### 2. Install Frontend Dependencies

```bash
cd Frontend
npm install
```

### 3. Start the Backend

```bash
python app.py
```

The Flask API will run on:

```text
http://localhost:5000
```

### 4. Start the Frontend

In a separate terminal:

```bash
cd Frontend
npm start
```

The React application will run on:

```text
http://localhost:3000
```

Once both servers are running, the application can be accessed through the React frontend.

## Results

The initial model achieved approximately **93% accuracy** on the evaluated dataset.

However, bankruptcy prediction presents a significant class-imbalance challenge. Because a much larger proportion of companies in the dataset are classified as healthy, accuracy alone may not provide a complete picture of how well the model identifies bankrupt companies.

Future evaluations should include metrics such as:

* Precision
* Recall
* F1-score
* ROC-AUC
* Confusion matrix

## Takeaways

This project gave us experience working across the full machine learning pipeline, from preparing financial data and training a classification model to deploying that model through a web application.

One of the biggest lessons was that model performance needs to be evaluated in context. A high accuracy score does not necessarily mean a model is effective at identifying the minority class, especially in an imbalanced dataset.

Building the React and Flask application also gave us experience connecting a machine learning model to a user-facing application rather than keeping the model entirely within a notebook.

## Future Improvements

* Evaluate the model using additional classification metrics
* Address class imbalance through resampling or class weighting
* Compare Gradient Boosting with other classification models
* Improve probability calibration
* Add model explainability to show which financial indicators influenced predictions
* Deploy the application online
