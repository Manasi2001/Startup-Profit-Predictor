# STARTUP PROFIT PREDICTOR

## 📌Aim

The aim is to predict profit that a startup will make on the basis of their R&D, Administration, Marketing Spend and State where they are based in the US.

## ⚙ A.   Acquiring Data and Preprocessing Data
The dataset consisted of 4 attributes on the basis of which the profit was predicted. Those were: R&D Spend, Administration Spend, Marketing Spend and the State where they are based in the U.S., namely New York, California and Florida. The R&D Spend, Administration and Marketing Spend attributes had data which was of float datatype so they didn’t require any encoding. On the other hand, the State attribute needed coding, so I label encoding it. No null values were present. Then I proceeded further and checked the variance inflation factor. On checking, the variance inflation factor for ‘R&D Spend’, ‘Administration’, ‘Marketing Spend’ and ‘State’ attributes was found to be 8.386322, 4.815916, 7.674608 and 2.382637 respectively. As all of the attributes had variance inflation factor less than 10, so I didn’t drop any of them. Moving on, I checked for outliners in the data. I used the seaborn library for plotting box plots for each and every attribute, but I found no outliners. With this, the preprocessing of the data was complete. The dataset was clean and predictions could be accurately made.

## 🛠 B.   Building the Model 
   Before creating the model, it is essential to split the data for training and testing. I used the train_test_split method from model_selection in ‘sklearn’ library to perform the splitting. I split the data in the ratio of 80:20. 80% for training the model and 20% for validation. I set the random_state parameter to 0 so that I get the same results every time. This makes it easy to debug the code if required in future. With this, the splitting was efficiently done. Next, I started making the model.
   I initialized the Random Forest Regressor model with parameter random_state set to 0. Then, I fit the model on training set which had X_train and y_test as features. The model was successfully built and now it was the time for making the predictions on the test set and checking the accuracy. At first, I predicted results for X_test, then used the ‘score’ function for obtaining the accuracy. The score came out to be 0.9691314428968053. Hence, it means that the predictions were approximately 96.91% accurate.

## 🖥 C.   Creating the GUI
   I saved the model that I created in a pickle file using ‘pickle’ library. Now, in a new file, a loaded that model using ‘joblib’ library. This model will further be used to predict the ‘profit’ according to the details entered by the user.
   For the GUI, I imported the ‘tkinter’ library and initialized the root. Then, initialized the main canvas and wrote code to print the name of the project on the top. After this, I created labels and windows for the user to enter all the details for the attributes ‘R&D Spend’, ‘Administration’, ‘Marketing Spend’ and ‘State’. Once I had all these details ready, I called the model and added functionality for printing the results according to the entered quantities. The GUI was also ready after this and the project was complete.

## Dataset Source

Find the source [here](https://www.kaggle.com/sonalisingh1411/startup50).

[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com) [![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)
