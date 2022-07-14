# FnB-Delivery-ETA-Prediction
It is very important for ride hailing superapp company to get this right, as it has a big impact on consumer experience. Order lateness / underprediction of delivery time is of particular concern as past experiments suggest that underestimating delivery time is roughly twice as costly as overestimating it. Orders that are very early / late are also much worse than those that are only slightly early / late. In this project, I will build a model to predict the estimated time taken for a delivery.

Problem Statement: We are providing you with data from thousands of restaurants in India regarding the time they take to deliver food for online order. As data scientists, your goal is to predict the online order delivery time based on the given factors. Analytics India Magazine and IMS Proschool bring to you ‘Predicting Predicting Food Delivery Time Hackathon’.

##### FEATURES:

    - Restaurant: A unique ID that represents a restaurant.
    - Location: The location of the restaurant.
    - Cuisines: The cuisines offered by the restaurant.
    - Average_Cost: The average cost for one person/order.
    - Minimum_Order: The minimum order amount.
    - Rating: Customer rating for the restaurant.
    - Votes: The total number of customer votes for the restaurant.
    - Reviews: The number of customer reviews for the restaurant.
    - Delivery_Time: The order delivery time of the restaurant. (Target Classes)
    
# Solution:
I approached the problem in two ways, one using machine learning and one using deep learning.

Steps Taken to arrive at the solution :-

1. Preprocessing : The provided dataset has some missing values and some strings in the numerical fields and all the numerical data was dumped as strings. I started by removing the unwanted values and replaced them with necessary data values.

2. Feature Engineering : The dataset has attributes like restaurant Id, location, etc. which were not related to the delivery time and hence had to be removed. At last 5 parameters were chosen for building the models.

3. Model Selection : I wanted to try both ML and DL to solve the problem hence I chose Gradient Boosting as the ML algorithm and then a 4 Layer Deep Densely connected Neural Network (5,20,20,7,1). 

4. Model building and training : The models were built using Sci-Kit Learn for Gradient boosting and Keras on top of Tensorflow for the DNN model. Then the models were trained on Visual Studio with a GPU back-end for faster training.

5. Model Evaluation and output generation : The model was evaluated using R2 metric measure and the output for the test data was produced, dumped in to an Excel file.

Due to the lack of output variable (Delivery_time) in the test data set, test validation could not be performed and hence had to stop the training once the MSE reached around 0.5-06.

### Data Observations and Processing
- From the above features we dropped the Restaurant and Location columns.
- There were a total of 101 cuisines with mutli-labelled values.
- We noticed that the 8 cuisines was the maximum number used to describe few of the rows, hence we introduced 8 columns to represent the cuisines.
- For rows which which had less than 8 cuisines the remaining values were stored as nan which we labelled as None.
- For newly opened resturants and resturants with blank we converted the value to 0.
- The data was also scaled.
