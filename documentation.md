# Day One
    Imported libraries
## Notes
    - for now i don't remember different techniques like oversampling or undersampling and much more methods like random forest and logistic regression
    - just setup imports and set up the things needed to do
    - since im not trying to dive too much into the ml space just to learn the basics and some cybersec methods on the side
    im not going to go too much into the theory, just implementation and flying through the project
    - also looking forward to figuring out if i want to implement/deploy this or just keep it practical and something i could jot down as a project for my resuem
    - always document so i can learn (will help me in the long run)

# Day Two
    Checked and went through the csv(data)
    Scaled and Fit the data
    Trained the imbalanced set
## Notes
    - used shape to get the rows and cols which the rows corresponds to each transaction made and theres 31 cols describing each transaction
        - the columns include:
            Time: The time elapsed since the first transaction
            Amount: The transaction amount
            PCA-transformed features: V1 through V28
                - reduction technique used to simplify data
            Class: The target variable, where 0 represents a non-fraudulent transaction, and 1 represents a fraudulent transaction
    - first trained on an imbalanced set
        - scaled then used linear regression then fit the model
        - ran the confusion matrix then got 56837 true negatives, 27 false positives, 41 flase negatives, and 57 true positives
        - ran the classification report and here's what I got:
            predicted 100% of the non fraud cases
            predicted 68% with precision, and 58% with recall, missing 42% of them
            it struggles to detect fruad effectively
        - bro first try on imbalanced set i got an roc-auc score of 94, i didn't expect this, the model is doing pretty good before applying smote
        - but the downside to this is that the recall to fraud cases is pretty terrible

## What I learned
    Learned how to read data and view the columns and rows to check the data
    Also learned how to what PCA transformed features are and how they work as far as in reducing and simplifying data
    Learned what target variables (or in this case class columns) are and how they represent the output the model is trained to predict
    Learned how to train, first trained on an imbalanced set and learned the following
        - learned what scaling does and how it helps
        - used linear regression to fit the model
        - learned how to run and read the confusion matrix
        - learned how to read and run the classification report
        - and also learned the importance behind running an roc-auc score
    Learned the difference between classification tasks and regression problems
# Day Three
    Appling SMOTE
    Train on balanced training data
    Train using Log Regression
    Train using Random Forest

## Notes
    Applied SMOTE and trained using Logistic Regression and Random Forest Classifier
    Logistic Regression
        Logistic regression got 88 True Positives, 10 False Negatives, 570 False Positives
        Logistic Regression also got a ROC AUC score of 98%, however it sacrificed having a low precision (13%) and f1 score (23%) for a very high recall score (89%)
    Random Forest Classifier
        Random Forest got 81 True Positives, 17 False Negatives, 17 False Positives
        Random Forest also got a ROC AUC score of 96% which was lower, high precision (83%) meaning most flagged fraud cases was truly fraud, slightly lower recall than lg recall but its still (83%), and f1 score is a strong balance between precision and recall for fraud detection (83%)
    Summary
        Even though the ROC AUC score was slightly lower for Random Forest, I'd rather choose rf since its beneficial for fraud detection to avoid unnecessary alerts.
        If catching the most fraud cases (higher recall) is more critical, you might prefer Logistic Regression. If avoiding false positives is a priority (e.g., reducing manual checks), Random   Forest is the better choice. (which is mine)
## What I learned
    Learned what SMOTE is and how it works
        learned how it balances the minority out by balancing the class distribution by generating synthetic samples (which was class 1 or fraud cases)
    Learned how to train using Logistic Regression
        learned its benefits and weaknesses, i got more catches for fraud using this, however, the downside to this is that I alot of false positives
    Learned how to train using Random Forest
        also learned that its the most optimal way, even though the recall was lower, meaning catching slightly fewer fraud cases, it was more balanced and avoiding false positives 
# How I could pursue this
    I could apply this to a real world project like a future website that has a payment service option
    Could fine tune Random Forest, or even try out other models