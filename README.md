# Coursera-Churn-Prediction-Challenge

🔹 Step 1: Understanding the Data
Train Dataset (train.csv): Contains 243,787 subscriptions, including the target variable Churn (1 = churned, 0 = retained).
Test Dataset (test.csv): Contains 104,480 subscriptions without the Churn label. We need to predict the probability of churn for these subscriptions.
Features: Customer demographics, streaming preferences, and activity-related data.
🔹 Step 2: Data Preprocessing
Handling Categorical Variables
Used Label Encoding to convert categorical features into numerical values.
Applied LabelEncoder() on categorical columns (except CustomerID).
Handling Missing Data
Filled missing values using fillna(), replacing NaNs with 0 (or another appropriate strategy if needed).
Feature Scaling
Used MinMaxScaler to scale numerical features to a range between 0 and 1.
Ensured all feature values were numeric to avoid ValueError: could not convert string to float.
🔹 Step 3: Model Selection & Training
Logistic Regression was chosen as the classifier because:
It is a simple, interpretable model for binary classification.
It outputs probabilities (needed for ROC-AUC scoring).
It performs well when features are properly scaled.
Training Steps
Split the data into X_train (features) and y_train (target).
Fit the logistic regression model to the training data.
Make probability predictions on the test set.
🔹 Step 4: Making Predictions
The trained model outputs probabilities instead of hard labels (0/1).
The final output is a DataFrame (prediction_df) with:
CustomerID
predicted_probability (probability of churn)
🔹 Step 5: Submission Format & Validation
The final DataFrame must match Coursera’s required format:
CustomerID (unique customer ID)
predicted_probability (churn probability, between 0 and 1)
Several assertion tests were used to:
Check for the correct number of rows and columns.
Ensure column names match the expected format.
🔹 Step 6: Model Evaluation
Since we don’t have the ground truth for the test dataset, we used:
ROC-AUC score on the training set to evaluate model performance.
This metric assesses the model’s ability to distinguish churned vs. retained customers.
🔹 Possible Improvements
To improve the model’s performance, we could: ✅ Try other machine learning models (e.g., Random Forest, Gradient Boosting).
✅ Perform feature engineering (create new features from existing ones).
✅ Tune hyperparameters (optimize the model for better predictions).
✅ Handle missing values in a more sophisticated way (e.g., imputing with median).
✅ Try different encoding methods (e.g., One-Hot Encoding instead of Label Encoding).

🔹 Summary of the Approach
1️⃣ Data Cleaning & Preprocessing (encoding categorical variables, handling NaNs, scaling features).
2️⃣ Train a Logistic Regression model using train.csv.
3️⃣ Make predictions on test.csv.
4️⃣ Format predictions correctly for submission.
5️⃣ Validate the submission with assertion tests.

This structured approach ensures the model works effectively while following the competition guidelines. 🚀 Let me know if you need further improvements! 😊





