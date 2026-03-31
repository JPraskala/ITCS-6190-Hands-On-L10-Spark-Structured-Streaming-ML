# Handson-L10-Spark-Streaming-MachineLearning-MLlib

## Task 4

### Explanations

#### Part 1

In part 1 of Task 4, we are training an offline model using **PySpark** using a dataset titled “training-dataset.csv”. The dataset consists of 5 features and 58 samples. The purpose of the offline model training is for the program to learn the relationship between `distance_km` and `fare_amount`. In the offline model training, we first convert `distance_km` and `fare_amount` to the DoubleType provided by spark.  After that, a `VectorAssembler` object is created, which allows us to combine the feature columns into one single `features` vector. Using this vector, the training set is transformed and then fit to the model, which then produces an output that is saved so it can be used for the streaming process.

#### Part 2

In Part 2 of Task 4, we implement data streaming to predict fare amounts in real time on port 9999. The purpose of the data streaming is to predict the fare based on the trip’s distance. To begin, the output that was produced from part 1 is loaded into the program, which will be used for the streaming analysis. Once the model is loaded, another `VectorAssembler` object is created so the streaming data can be transformed into the same feature format used during the training session in part 1. The absolute difference between the `fare_amount` and the `predictions` is then calculated to see how accurate the model is.

### Approaches

#### Parts 1 and 2

For Task 4, my approach was to look back at the lecture notes as well as ask the TA’s for any help if I had any questions. I found myself getting stuck in some parts such as on lines 35 and 79, but after consulting with one of the TA’s, I was able to figure it out. If I still could not figure it out, I used external resources such as Google to look at the PySpark documentation to see if that could help clear some things up. As mentioned, the lecture slides did provide some guidance in helping me solve the problems.

### Results Screenshot

<img width="1327" height="643" alt="task4_screenshot" src="https://github.com/user-attachments/assets/e41aec8d-0c0d-47e8-8c75-255aa8cff30b" />


## Task 5

### Explanations

#### Part 1

In part 1 of Task 5, we are training an offline model aggregated into 5-minute windows, calculating the average fare for each window. The purpose of the window is to perform **feature engineering**; instead of using a raw timestamp, the hour and minute are extracted and used as features for the model. Once the window is setup, a `VectorAssembler` object is created which takes `hour_of_day` and `minute_of_hour` as the input columns and `features` as the output column. The object then transforms the dataset, and the transformed data is run through the Linear Regression model; in the end, the data that is produced is saved so it can be used for the streaming process.

#### Part 2

In part 2 of Task 5, we are live streaming the data using the same aggregated 5-minute window from before. The purpose of the streaming is to predict the average fare for a given time window. After creating the window feature in the dataset, another `VectorAssembler` object is created which takes in `hour_of_day` and `minute_of_hour` as the input columns and `features` as the output column. Once the object transforms the training dataset, the training model from part 1 is loaded to the transformed features dataset. The predictions that are calculated are then written to the console so the predicted average fare can be easily observed.

### Approaches 

#### Parts 1 and 2

For Task 5, since I did not have the TA's to ask for help as I did this task away from the classroom, I still looked at the lecture notes and spark documentation to help solve the problems. Overall, my approach is very similar to how it was in Task 4; I used whatever resources were available to me to solve the TODOs that were required for me to fill out.

### Results Screenshot


<img width="848" height="536" alt="task5_screenshot" src="https://github.com/user-attachments/assets/6dad35fe-7bdc-4186-9be7-aa3f44dd376a" />

