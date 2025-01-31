# 🛍️ HomeDepot Product Search Relevance Prediction  

## 📜 Overview  
This project builds a **ranking model** to predict the **relevance score** for **query-product pairs** in HomeDepot’s product search. Using **Learning to Rank (LTR)**, we apply a **Pointwise Approach** to train a regression model based on **text similarity features** between the user query and product information.  

📌 **Note**: 
Product description dataset is very large. Please contact me if you want to use it. 

📌 **Dataset**:  
- **Train Set (`train_new.csv`)** – Query-product pairs with **ground-truth relevance scores**.  
- **Test Set (`test_new.csv`)** – Query-product pairs for **prediction**.  
- **Product Descriptions (`product_descriptions_new.csv`)** – Additional product details.  
- **Product Attributes (`attributes_new.csv`)** – Additional structured product attributes.  

📌 **Goal**:  
1. Compute **text similarity** between `search_term` and:  
   - `product_title`  
   - `product_description`  
   - `product_attributes`  
2. Generate **feature vectors** for training and testing.  
3. Train a **machine learning model** to predict **relevance scores**.  
4. Evaluate performance using **Mean Squared Error (MSE) & R² score**.  

📌 **Programming Language**: `Python 3`  
📌 **Libraries Used**: `pandas`, `scikit-learn`, `nltk`, `numpy`, `scipy`, `XGBoost`  

## 🚀 Approach  

### **1️⃣ Data Preprocessing**  
- **Text Cleaning** (e.g., spelling correction, numerical normalization).  
- **Tokenization & Stopword Removal** using `NLTK`.  
- **TF-IDF Vectorization** for product details.  

### **2️⃣ Feature Engineering**  
- Compute **Cosine Similarity** between `search_term` and:  
  - `product_title`  
  - `product_description`  
  - `product_attributes`  
- Compute **additional similarity measures** (e.g., **Jaccard, Dice Coefficient, Overlap**).  
- Minimum **6 similarity features** for each query-product pair.  

### **3️⃣ Model Training & Evaluation**  
- Train models using **Supervised Learning Algorithms**:  
  - **Linear Regression**  
  - **Support Vector Regressor (SVR)**  
  - **XGBoost Regressor**  
  - **Neural Networks**  
- Evaluate model performance using:  
  - **Mean Squared Error (MSE)**  
  - **R² Score**  

### **4️⃣ Predictions on Test Data**  
- Generate **predicted relevance scores** for `test_new.csv`.  
