# Disaster Response Project

## Table of Contents
 * [Project Motivation](#project-motivation)
 * [File Descriptions](#file-descriptions)
 * [Components](#components)
 * [Instructions of How to Interact With Project](#instructions-of-how-to-interact-with-project)
 * [Licensing, Authors, Acknowledgements, etc.](#licensing-authors-acknowledgements-etc)
 
### Project Motivation
This project involved analysing disaster data from Appen to build a model that classifies disaster messages. Natural Language Processing and Machine Learning was used to build a pipeline that catogerises messages in a disaster to identify the correct response team required. A web app was created where disaster messages could be inputted and the output would catogerize them into areas where they require attention. 

### File Descriptions
app    

| - template    
| |- master.html # main page of web app    
| |- go.html # classification result page of web app    
|- run.py # Flask file that runs app    


data    

|- disaster_categories.csv # data to process    
|- disaster_messages.csv # data to process    
|- process_data.py # data cleaning pipeline    
|- DisasterResponse.db # database to save clean data to     


models   

|- train_classifier.py # machine learning pipeline     
|- classifier.pkl # saved model     


README.md  

### Components
#### 1. ETL Pipeline
A Python script, `process_data.py`, writes a data cleaning pipeline that:

 - Loads the messages and categories datasets
 - Merges the two datasets
 - Cleans the data
 - Stores data in a SQLite database
 
A jupyter notebook `ETL Pipeline Preparation` was used to do EDA to prepare the process_data.py python script. 
 
#### 2. ML Pipeline
A Python script, `train_classifier.py`, writes a machine learning pipeline that:

 - Loads data from the SQLite database
 - Splits the dataset into training and test sets
 - Builds a text processing and machine learning pipeline
 - Trains and tunes a model using GridSearchCV
 - Outputs results on the test set
 - Exports the final model as a pickle file
 
A jupyter notebook `ML Pipeline Preparation` was used to prepare the train_classifier.py python script. 

#### 3. Flask Web App
A web app was developed where emergency workers can input new disaster messages and recieve classification results, as shown below:

![Capture](https://user-images.githubusercontent.com/123730023/220874070-1feca682-4dbc-4f43-ba2b-052e4fa860ab.PNG)

![Capture2](https://user-images.githubusercontent.com/123730023/220873950-c65dba65-5826-4230-969d-05db15a7dc7d.PNG)

![newplot](https://user-images.githubusercontent.com/123730023/220877848-76e699a8-d0d0-4cdd-bf75-6321a6c36944.png)

![newplot (1)](https://user-images.githubusercontent.com/123730023/220896335-9b2dccc1-bf1d-450d-96c5-5d0f4456fe6b.png)


### Instructions of How to Interact With Project:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Go to `app` directory: `cd app`

3. Run your web app: `python run.py`

4. Go to http://0.0.0.0:3000/

### Licensing, Authors, Acknowledgements, etc.
Thank you to Udacity for starter code for the web app. 
