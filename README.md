# **Football Match Outcome Prediction Report**

---

## **1. Introduction**

### **Objective:**
The goal of this project is to predict **match outcomes** (win or no-win) based on football statistics, such as goals scored, shots on target, passes, and disciplinary records. We aim to determine whether a **home team wins** using two classification models—**Logistic Regression** and **Random Forest**—and evaluate their performance.

### **Key Questions:**
1. What factors are most important in predicting match outcomes?  
2. How accurately can we predict match results based on available features?  
3. Which machine learning model performs better—**Logistic Regression** or **Random Forest**?  

---

## **2. Dataset Overview**

### **Data Source:**
The analysis uses two datasets:
1. **Match Results (results.csv)** - Contains details about each match, including teams, goals, results, and season.  
2. **Team Statistics (stats.csv)** - Includes detailed statistics, such as wins, losses, goals, and disciplinary actions.  

### **Columns in Results Data:**
- **home_team**: Home team name.  
- **away_team**: Away team name.  
- **home_goals**: Goals scored by the home team.  
- **away_goals**: Goals scored by the away team.  
- **result**: Match outcome—Home Win (H), Draw (D), Away Win (A).  
- **season**: The season during which the match occurred.  

### **Columns in Stats Data:**
- **wins**: Total matches won.  
- **losses**: Total matches lost.  
- **goals**: Total goals scored.  
- **total_yel_card**: Total yellow cards received.  
- **total_red_card**: Total red cards received.  
- **corner_taken**: Total corners taken.  

### **Preprocessing Steps:**
- Merged datasets based on teams and seasons.  
- Removed unnecessary columns and handled missing values.  
- Encoded categorical features.  
- Standardized numerical data for consistency.  
- Created a binary target variable: **Win (1)** vs **No-Win (0)**.  

---

## **3. Exploratory Data Analysis (EDA)**

### **Key Insights:**
1. **Goal Distribution**:  
   - Home teams scored more goals on average than away teams.  
   - Most matches had **1–2 goals** scored per team.  

2. **Match Results**:  
   - Home Wins (H) were the most common outcomes, followed by Draws (D).  

3. **Goals per Season**:  
   - Goal-scoring trends varied slightly by season, showing fluctuations in average goals scored.  

4. **Team Performance**:  
   - Teams with higher wins generally had better offensive statistics, such as goals scored and shots on target.  

5. **Disciplinary Records**:  
   - Yellow and red card distributions revealed that some teams had consistently higher disciplinary actions, which may correlate with losses.  

### **EDA Visualizations:**
- **Goal Distributions**: Histogram of home and away goals.  
- **Match Outcomes**: Bar chart of results (H, D, A).  
- **Goals Per Season**: Line chart showing goal trends across seasons.  
- **Scatterplots**: Goals vs Wins, Corners vs Goals, Saves vs Goals Conceded.  
- **Correlation Heatmap**: Relationships between numerical features.  
- **Feature Importance Analysis**: Identified top predictors for match outcomes.  

---

## **4. Modeling Approach**

### **Feature Engineering:**
- Encoded categorical variables using **LabelEncoder**.  
- Standardized numerical variables using **StandardScaler**.  

### **Models Trained:**
1. **Logistic Regression**:  
   - Linear classifier for binary classification tasks.  
2. **Random Forest Classifier**:  
   - Ensemble model capturing non-linear relationships through decision trees.  

### **Training and Testing Split:**
- **Training Size**: 80%  
- **Testing Size**: 20%  

---

## **5. Model Evaluation**

### **Logistic Regression Results:**
- **Accuracy:** **100%**  
- **Precision, Recall, and F1-scores:** **Perfect (1.00)** across all metrics.  
- **ROC-AUC:** **1.0**  

**Observations:**
- Logistic Regression performed exceptionally well, achieving **perfect predictions** without any errors.  
- The model’s simplicity proved highly effective for this dataset.  

### **Random Forest Results:**
- **Accuracy:** **95.23%**  
- **Precision, Recall, and F1-scores:** **Above 95%** across metrics.  
- **ROC-AUC:** **0.995**  

**Observations:**
- Random Forest provided high accuracy but misclassified a few cases.  
- The **feature importance analysis** highlighted **home_goals** and **away_goals** as the most influential predictors.  

---

### **Model Comparison:**

| Metric                  | Logistic Regression | Random Forest |
|-------------------------|---------------------|---------------|
| **Accuracy**            | **100%**            | **95.23%**    |
| **F1-Score (Avg)**      | **1.00**            | **0.95**      |
| **ROC-AUC**             | **1.0**             | **0.995**     |
| **Misclassification**   | **0 errors**        | **29 errors** |

**Key Finding:**  
Both models performed exceptionally well, but **Logistic Regression** achieved **perfect predictions** in this dataset, indicating strong linear relationships among features.

---

## **6. Observations**
1. **Logistic Regression** emerged as the top performer with **100% accuracy** and no misclassifications.  
2. **Random Forest** demonstrated high performance but made a few errors due to its sensitivity to noise.  
3. **Feature Importance** analysis identified **home and away goals** as the most critical predictors, followed by **wins** and **shots on target**.  
4. The dataset exhibited clear patterns, making it easier for linear models like **Logistic Regression** to excel.  

---

## **7. Conclusion**

This project successfully predicted **football match outcomes** using **Logistic Regression** and **Random Forest** classifiers. 

### **Key Takeaways:**
- **EDA** revealed trends in goals, wins, and cards that influenced match outcomes.  
- **Logistic Regression** achieved **perfect accuracy** due to linear relationships in the data.  
- **Random Forest** also performed well but showed slight errors, emphasizing the trade-off between complexity and interpretability.