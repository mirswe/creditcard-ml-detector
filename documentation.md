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
## Notes
    - used shape to get the rows and cols which the rows corresponds to each transaction made and theres 31 cols describing each transaction
        - the columns include:
            Time: The time elapsed since the first transaction
            Amount: The transaction amount
            PCA-transformed features: V1 through V28
                - reduction technique used to simplify data
            Class: The target variable, where 0 represents a non-fraudulent transaction, and 1 represents a fraudulent transaction