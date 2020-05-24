# Capstone-Sparkify-Project

## Table of Contents

1. [Dependencies](#dependencies)
2. [Project Motivation](#motivation)
3. [Files Description](#description)
4. [Results](#results)
5. [Acknowledgements](#acknowledgements)


### Dependencies <a name = "dependencies"></a>

All the following libraries are needed to implement this project:

**Python**<br>
**Pandas**<br>
**Matplotlib**<br>
**Seaborn**<br>
**PySpark**<br>
**Spark**<br>
### Project Motivation <a name = "motivation"></a>

This project is a part of the Udacity's Data Scientist Nanodegree program analyzing the behaviour of users for an app called Sparkify to predict user churn. Sparkify is an app similar to Spotify and the dataset contains user behaviour log for the past few months. It contains some basic information about the users as well as information about a particular action they have taken.
A user can have multiple actions which leads to multiple entries for a user, we can identify when a user churned through the action of account cancellation.

### Files Description <a name = "description"></a>

### Project overview
This is the final project of the datascience nanodegree (DSND). We have an example of a virtual company called 'Sparkify' who offers paid and free listening service, the customers can switch between either service, and they can cancel their subscription at any time.
The given customers dataset is huge (12GB), thus the standard tools for analysis and machine learning will not be useful here as it will not fit in the computer's memory (even the data can fit in the memory of a 32GB computer, the analysis, and computations require way more than that amount, and the analysis will crash the system). The safe way to perform such analysis is to do it using Big Data tools like Apache Spark which is one of the fastest big data tools.
> For this tutorial, we worked with only a 128MB slice of the original dataset.

**The problem** is to create a machine learning model to predict the user intent to unsubscribe (Called customers' churn) before this happens.

* **Files**
  * [Sparkify.ipynb](https://github.com/shahil04/Capstone-Sparkify-Project/blob/master/Sparkify.ipynb): The main coding file in jypyter notebook format to work in Udacity workspace.
   * [Sparkify.html](https://github.com/shahil04/Capstone-Sparkify-Project/blob/master/Sparkify.html): an HTML file for the jupyter workbook
  * [README.md](https://github.com/shahil04/Capstone-Sparkify-Project/blob/master/README.md): This file.
  
  ### Files NOT in this repo
* mini_sparkify_event_data.json: A 128MB json file contains the main data (exceeds GitHub limit)

### Used resources
- Python 3.6.x (The programing language)
- pySpark 2.4.x (Machine learning library for big data)
- matplotlib 3.03 (A plotting library)
- pandas 0.23 (numerical calculations library)
- jupyter (The programming notebook interface)

### Results <a name = "results"></a>
## Expected Results
At the end of this project, a model for churn prediction should have been created and evaluated. The model should have been trained and tested on a subset of the 12GB of data, and the final testing should happen on completely separate validation set. An accuracy, F1-Score confusion matrix will be used to evaluate the performance and feasibility of the model.

### Actual Results
At the end of this project, two main iterations on a churn-prediction model were implemented and evaluated. The first model used a simple pivot of the event that seemed to contain the most relevant difference between churning and non-churning users.

Three models were trained with this data, given the following F1 Values:

Gradient Boosted Trees -81.818%

Random Forest - 77.0%

 Decision Tree Classifier - 73.5%

While the values look promising, inspection of the confusion matrices revealed that Decision Tree Classifier and Random Forest classified all users as non-churning, but because of the relative low number of churned users, the F1 score was still fairly high.

The best performing model for the first iteration was Gradient Boosted Trees, which managed to predict 17 churners correctly.

For the second iteration, two new features were introduced. Number of sessions and days from first to last recorded event.

Using these features, the Gradient Boosted Trees algorithm was once again trained.

The results were much better than the initial attempt. With a F1-score of 81.81% for validation data, and 294 correctly identified churners, the second iteration of the model is a great first model which could be fine-tuned and improved even more.


Check out my blog post by clicking this [link](https://medium.com/@shahilansari/customer-churn-prediction-for-subscription-using-spark-2afef134e66a) for more detailed analysis.

### Acknowledgements <a name = "acknowledgements"></a>

Udacity has to be acknowledged for giving me this wonderful project.
