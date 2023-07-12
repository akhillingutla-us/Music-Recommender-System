# **Summary**


  The Music-Recommender-System uses decision trees, Sklearn, and pandas to recommend songs/genres to users based on their age, gender, and preferred genres. The dataset used for this project is music.csv, which contains information about the ages, genders, and preferred genres of 20 users.
    
  The system is implemented in Python and is divided into three main parts:
    
  * Data preprocessing: This part of the project involves cleaning the data and preparing it for analysis.
      
  * Model training: This part of the project involves training a decision tree model to predict the preferred genres of users based on their age, gender, and other features.
    
  * Recommendation: This part of the project involves using the trained model to recommend songs to users.



# **Core Features**

  * Support for more genres: The system currently only supports a limited number of genres. In the future, the system could be expanded to support more genres, which would allow it to recommend a wider variety of songs to users.
    
  * Personalization: The system currently predicts preffered genres to users based on their age and gender. The system is personalized to each user
    
  * Collaborative filtering: Collaborative filtering is a technique that can be used to recommend songs to users based on the ratings of other users. The system could be integrated with a collaborative filtering algorithm, which would allow it to recommend songs to users that are similar to the songs that other users have rated highly.
  
  These are the core features that are included/will be included in the music recommender system. The specific features that are included will depend on the goals of the system and the needs of the users.


# **Explanation of the Decision Tree**


      import pandas as pd
      
      from sklearn.tree import DecisionTreeClassifier # Import decision tree algo
      
      from sklearn import tree
      
      
      #TRAINING
      
      
      #Seperate the Data into input and output
      
      
      music_data = pd.read_csv('music.csv')
      
      X = music_data.drop(columns = ['genre'])
      
      y = music_data['genre'] # returns all the values in the genre column
      
      
      #Now we create the model using a ML algo (Decision Trees)
      
      model = DecisionTreeClassifier()
      
      model.fit(X, y) #Takes the input/output set. 
      
      
      tree.export_graphviz(model, out_file='music-recommender.dot', 
                          feature_names=['age', 'gender'], #The rules in our nodes
                          class_names=sorted(y.unique()), #set it to the unique list of genres so they are displayed in the nodes
                          label ='all', #Every node has labels that we can read
                          rounded=True, #Gives boxes rounded corners
                          filled=True) #Each box is filled with a color

                    
# **Libraries**

* pandas
* Sklearn
