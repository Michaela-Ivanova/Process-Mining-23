# Process-Mining-23

Tool(s) predicting the next event & timestamp in a business process 

Authors: Théophile Guillet, Rares Ioan, Michaela Ivanova, Krasimira Kamenska, Milou der Kinderen, Kalina Kostova

Group: 23

Course: DBL Process Mining, Faculty of Mathematics and Computer Science, Eindhoven University of Technology

**General Introduction**

This tool is trained and evaluated on the Italian Road Fines Management dataset, 
aiming to predict the next event in a trace. Additionally, it contains a model 
capable of predicting the suffix of a running process.

**Installation**

To use this project, you'll need to have Python installed. 
It is recommended to use Jupyter Notebook for running the project. 
You can download and install Python from the official Python website
(https://www.python.org/). The tool has been compiled and tested
on Python 3.11.4. 
For instructions on installing Jupyter Notebook, see the official
Jupyter website (https://jupyter.org/install). 


**Dependencies**

Ensure you have the following Python packages installed. 
pandas
pm4py
scikit-learn
xgboost
tensorflow
numpy

You can install them separately or using pip and the provided requirements.txt file:
pip install -r requirements.txt
inside of the attached Jupyter Notebook. 

**Overview**

Running the notebook in Jupyter will convert an .xes file into 
a dataframe and train and evaluate several prediction models on it.
Furthermore, it will train an LSTM model to make a prediction about 
the next event based on a given prefix of variable length. The LSTM
is then used to generate the entire suffix of a running activity,
including the types of events and their (relative) timestamps. 
The preset training and evaluation set is the RTFM dataset. 

To download the dataset go to https://doi.org/10.4121/uuid:270fd440-1057-4fb9-89a9-b699b47990f5Links
Make sure you have the dataset in the same folder as the tool file. 

**If running on a different dataset**
- ensure that it has the necessary column names ("case:concept:name", "concept:name", "time:timestamp")
- comment out the part specified as "Dataset specific features below" in the addFeatures() function 
- the function will now generate 5 generic features that should be applicable for most 
business process datasets (provided that they have the abovementioned columns) 
- update the event_features and time_features lists where specified in the notebook by removing
the 'dismissal_encoded' and 'in_debt' features where present, and optionally adding new dataset-specific
ones 

**Running on Different Operating Systems**

MacOS and Linux: Open Terminal and run jupyter notebook by typing by typing 'jupyter notebook'. 
Navigate to the file directory and open the file 'FinalToolGroup23.ipynb'. Please ensure that
the dataset provided is in the same directory as the notebook. 
