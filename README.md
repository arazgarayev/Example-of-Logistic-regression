# arazgara
[Power Bi example over Reservations](https://github.com/arazgarayev/arazgara/blob/5f98be864f4e754b6e0bae85a13a84ae1cddd879/README.md#L1-L19)
# arazgara
Example of logistic regression for classification in R
# Load the required library
library(caret)

# Load the dataset
data <- read.csv("your_dataset.csv")  # Replace "your_dataset.csv" with your actual dataset file name

# Split the data into training and testing sets
set.seed(123)  # Set a seed for reproducibility
trainIndex <- createDataPartition(data$target_variable, p = 0.7, list = FALSE)  # Replace "target_variable" with the name of your target variable
trainData <- data[trainIndex, ]
testData <- data[-trainIndex, ]

# Train the logistic regression model
model <- train(target_variable ~ ., data = trainData, method = "glm", family = "binomial")

# Make predictions on the testing set
predictions <- predict(model, newdata = testData)
