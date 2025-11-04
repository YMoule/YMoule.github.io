## Pokémon Battle Prediction

**Project description:** This is a Machine Learning group project completed for ECS 171 at UC Davis. The goal of this project was to create a machine learning model to predict the winner between two pokémon in a battle. To do this, a suitable dataset was found on Kaggle. Then a logisitic regression, a support vector classifier, and a multi-layer perceptron model were created and compared to find the best performing model. Finally, a UI application was created to easily predict pokémon battle winners. 

### 1. Choice of Dataset

As many different pokémon games exist, there are many different types of data. In addition, each individual pokémon has its own strengths (such as CP and HP) within its species. My team wanted to focus on general pokémon properties rather than individual properties. Thus, we joined a dataset with a list of pokémon names, IDs, and general properties (such as base CP, base HP, and type) with a simulated dataset of pokémon battles and their outcomes using ID as the joining column. The datasets were found on Kaggle. 

The dataset was analyzed to find relationships between features and missing data. As correlation was weak between features, all features were used to train the models. It is important to note that since pokémon type was One-Hot encoded, the data has very high dimensionality. Thus certain types (like Ice) and special pokémon (like MewTwo) are underrepresented in the data. 

### 2. Creating the Support Vector Classification Model

I personally worked on the Support Vector Classification (SVC) Model. It was chosen because SVC models are very good at handeling high dimensional data. The model was created using sci-kit learn and optimized using Grid Search.

We found that the best results were using a subset of features (leaving out Type 2 and Generation data) and using an 'rbf' kernel. The confusion matrix for the SVC model can be seen below. 

<img src="images/SVM_Confusion_Matrix.png?raw=true"/>

### 3. Evaluation of Models

We found that overall the Multilayer Perceptron (MLP) Model performed the best on testing data. This can be seen through the metrics of Precision Score, Recall, F1 Score, and Accuracy. MLP was the highest performing in all measures, and was thus used for the following analysis. 

<img src="images/Precision Scores for Models.png?raw=true" width="200"/> <img src="images/Recall Scores.png?raw=true" width="200"/>
<img src="images/F1 Scores.png?raw=true" width="200"/> <img src="images/Accuracy Scores.png?raw=true" width="200"/>

### 4. User Interface (UI) Application

I created the UI using Render and html. You can access the website at the following link: [Pokémon Website](\https://pokemonwebsite-rso8.onrender.com). Note that it may take up to five minutes to render before use. 
The performance of the website was assessed using well known pokémon such as Squirtle, Charmander, Charizard, and Mewtwo. The image below shows the User Interface. 

We found that although the website works well for pokémon of the same evolution (i.e. Squirtle beats Charmander). However, it performs poorly for pokémon of different evolutions. For example, Charmander's evolution Charizard beats Charmander. In addition, legendary pokémon like Mewtwo, do not consistently beat every other pokémon in a fight, unlike the Pokémon Universe. 
Most likely, these failures are not a failure of the model, but rather a lack of representation of this type of fight in the underlying data. Using a different dataset could lead to much better performance. 

<img src="images/Pokemon_Website.png?raw=true"/>
