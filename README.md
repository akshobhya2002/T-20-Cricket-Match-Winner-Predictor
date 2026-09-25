# 🏏 American Express Campus Challenge 2024 – Team *The Data Disruptors*  

Pulkit Agrawal | Aditya Singh | Pratham Malviya  
Indian Institute of Technology, Kharagpur  

---

## 📌 1. Project Title  
**Cricket Match Winner Prediction using Machine Learning**  

---

## ✅ 2. Objectives  
- Predict the outcome of cricket matches (whether **Team 1 wins**) using ML models.  
- Apply **feature engineering** to capture cricket-specific insights (batting, bowling, toss, ground).  
- Experiment with **different modeling techniques** including boosting, ensembles, and calibrated models.  
- Evaluate models on **balanced sampling strategies** for reliable results.  
- Provide a **decision-science based predictive solution** with high interpretability.  

---

## 🛠 3. Tools & Technologies  
- **Programming Language**: Python  
- **Libraries**: pandas, numpy, scikit-learn, catboost, xgboost, lightgbm, matplotlib, seaborn  
- **Techniques**:  
  - Standalone Boosting Models (XGBoost, LightGBM, CatBoost)  
  - Ensemble Methods (Voting, Stacking)  
  - Sampling (Simple, Systematic, Stratified Shuffle Split)  
  - Feature Engineering (batting, bowling, ground, toss features)  

---

## 🔍 4. Process  

### **Step 1: Problem Framing**  
- Original dependent variable `Match Winner Prediction` reframed as **binary classification** → `is_team1_winner`.  

### **Step 2: Data Sampling**  
- Used **Stratified Shuffle Split Sampling** to maintain class distribution.  
- Ensured balanced train-test splits to avoid bias.  

### **Step 3: Feature Engineering**  
Crafted interpretable cricket-specific features:  
- **Ground Features** → team’s historical win percentage at ground.  
- **Batting Features** → average runs in last 15 overs, run rates.  
- **Bowling Features** → average wickets, economy in last 5 overs.  
- **Toss Features** → toss winner and decision impact.  

Top important features included:  
1. `team2_winp_at_ground` – 5.35%  
2. `team2_avg_runs_last15` – 5.03%  
3. `opposite_bowler_count_team2` – 3.98%  
4. `team1_avg_bat_last15` – 3.13%  
5. `team1_avg_wickets_last15` – 3.06%  

### **Step 4: Model Development**  
- **Standalone Boosting Models**: Achieved ~55% accuracy.  
- **Ensemble Methods**: Voting & stacking improved accuracy to ~62%.  
- **Boosting + Feature Engineering + Stratified Sampling**:  
  - CatBoost selected as **final model**.  
  - Accuracy improved to **68%**.  

### **Step 5: Model Tuning**  
- **Hyperparameter tuning** via grid search.  
- Used CatBoost classifier with:  
  - Handling categorical features via ordered target statistics.  
  - Oblivious symmetric trees for efficiency.  
  - GPU acceleration for large-scale runs.  

---

## 🌟 5. Key Features of the Solution  
- **Stratified sampling** → ensures balanced evaluation.  
- **Domain-driven feature engineering** → interpretable cricket insights.  
- **Boosting & Ensembles** → captured non-linear relationships.  
- **CatBoost Classifier** → final choice for best accuracy and interpretability.  
- **Backward Feature Elimination** → refined features using adjusted R² and 5% significance.  

---

## 📊 6. Model Performance Summary  

| Technique                                   | Accuracy |
|---------------------------------------------|----------|
| Standalone Boosting (XGBoost/LightGBM)      | ~55%     |
| Ensemble (Voting & Stacking)                | ~62%     |
| CatBoost + Feature Engineering + Stratified | **68%**  |

---

## 🔍 7. Advanced Enhancements Suggested  
- **Model Variety**: Neural networks, deeper ensemble methods.  
- **Feature Transformations**: Logarithmic, polynomial features.  
- **Variable Discretization**: Bin continuous features to capture nonlinearities.  
- **Model Calibration**: Apply Platt scaling / isotonic regression for probability tuning.  

---

## ✅ 8. Outcomes  
- Developed a robust ML pipeline for **cricket match outcome prediction**.  
- Accuracy improved from **55% → 68%** with CatBoost + feature engineering.  
- Identified **key cricket features** that strongly influence match results.  
- Created a solution balancing **predictive performance and interpretability**.  