# 🎾 Tennis Match Prediction with Machine Learning & Optuna

This project aims to **predict the outcome of professional ATP tennis matches** using supervised machine learning models such as `RandomForest`, `SVM`, `Logistic Regression`, and `Decision Trees`. It leverages **Optuna** for intelligent hyperparameter tuning and evaluates models using **ROC AUC** and **Accuracy**.

---

## 🚀 Project Overview

- 🧠 **Goal**: Predict the probability of victory for each player in a match.
- 📊 **Data**: Real ATP match data including player rankings, points, odds, surface, round, etc.
- 🛠️ **Models**: Logistic Regression, Decision Tree, SVM, Random Forest
- 🔍 **Hyperparameter Optimization**: Using `Optuna` for smarter and faster tuning
- 🧪 **Evaluation Metrics**: `Accuracy`, `ROC AUC`, Cross-validation

---

## 📂 Dataset Structure

The model expects a CSV file structured like this:

| Column       | Description                             |
|--------------|-----------------------------------------|
| `Player_1`   | Name of first player                    |
| `Player_2`   | Name of second player                   |
| `Winner`     | Name of winner (matches one of the two)|
| `Rank_1`     | ATP rank of Player_1                    |
| `Rank_2`     | ATP rank of Player_2                    |
| `Pts_1`      | ATP points of Player_1                  |
| `Pts_2`      | ATP points of Player_2                  |
| `Odd_1`      | Betting odds for Player_1               |
| `Odd_2`      | Betting odds for Player_2               |
| `Surface`    | Court surface (Hard, Clay, Grass)       |
| `Round`      | Round of the tournament (e.g. 1st Round)|
| `Best of`    | Sets to win (3 or 5)                    |
| `Court`      | Indoor / Outdoor                        |

---

## ⚙️ Setup

1. Clone the repo  
2. Install dependencies:

```bash
pip install -r requirements.txt


## 🏗️ How It Works
1. Train and evaluate multiple models:
 * Uses GridSearchCV for classic hyperparameter tuning
 * Compares Accuracy & ROC AUC
 * Stores and visualizes model performance
2. Tune the best model (RandomForest) using Optuna:
 * Runs 30+ trials automatically
 * Searches optimal hyperparameters intelligently
 * Retrains and saves the best model
3. Predict a new match:

```bash
exemple_match = {
    "Rank_1": 15,
    "Rank_2": 441,
    "Pts_1": 2745,
    "Pts_2": 105,
    "Odd_1": 1.10,
    "Odd_2": 6.75,
    "Surface": "Hard",
    "Round": "2nd Round",
    "Best of": 3,
    "Court": "Outdoor"
}



probas = predict_match_proba(exemple_match)
print(probas)
```

## 🔮 Output Example

```yaml
🎯 Prediction:
Probabilité victoire Player_1 : 91.45%
Probabilité victoire Player_2 : 8.55%
```

## 📊 Next Steps
* Integrate head-to-head (H2H) player history
* Simulate full tournament brackets
* Evaluate ROI with real betting strategies
* Export model to web app or API


## 📄 License
MIT License – feel free to use, improve, and share!

## 🙌 Acknowledgements

Inspired by:
* Ghosh et al. (2019)
* Lund University Master's Thesis – Pham & Bufi (2023)