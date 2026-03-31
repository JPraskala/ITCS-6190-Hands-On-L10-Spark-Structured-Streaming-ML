# Handson-L10-Spark-Streaming-MachineLearning-MLlib

## Task 4

### Explanations

#### Part 1

In part 1 of Task 4, we are training an offline model using PySpark using a dataset titled “training-dataset.csv”. The dataset consists of 5 features and 58 samples. The purpose of the offline model training is for the program to learn the relationship between “distance_km” and “fare_amount”. In the offline model training, we first convert “distance_km” and “fare_amount” from integers to doubles to prevent any precision issues later on.  After that, a VectorAssembler object is created, which allows us to combine the feature columns into one single ‘features’ vector. Using this vector, the training set is transformed and then fit to the model, which then produces an output that is saved into a parquet file.

#### Part 2

In Part 2 of Task 4, we implement data streaming to predict fare times in real-time on port 9999. The purpose of the data streaming is to predict the fare based on the trip’s distance. To begin, the output that was produced from part 1 is loaded into the program, which will be used for the streaming analysis. Once the data is loaded, we create another VectorAssembler, transform the training dataset, and calculate the deviation (absolute difference) between the “fare_amount” and the “predictions”. By calculating the deviation, it tells us what the fare will be based on the distance provided.

### Approaches

#### Parts 1 and 2

For Task 4, my approach was to look back at the lecture notes as well as ask the TA’s for any help if I had any questions. I found myself getting stuck in some parts such as on lines 35 and 79, but after consulting with one of the TA’s, I was able to figure it out. If I still could not figure it out, I used external resources such as Google to look at the PySpark documentation to see if that could help clear some things up. As mentioned, the lecture slides did provide some guidance in helping me solve the problems.

### Results Screenshot

<img width="1327" height="643" alt="task4_screenshot" src="https://github.com/user-attachments/assets/e41aec8d-0c0d-47e8-8c75-255aa8cff30b" />


