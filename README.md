# Occupancy Detection App Powered by AI Backend
I have made and Occupancy detection App which detects the presence of people in a room based on input like Temperature (Celsius), humidity (%), Light (lux), CO2 (ppm). 

This app is a Machine Learning Model-Based app.



About App:-

The app consists of only the main design. The main layout has two sections: the upper half and the lower half. 

Upper half:  It shows reading from the different sensors. Earlier I planned to use real sensors to an Arduino to get actual data, but due to Lockdown and CoronaVirus, I was not able to buy the required equipment. 

But that doesn't mean that I haven't looked for alternatives, I tried tinkercad and proteus to simulate Arduino, wifi module, sensors, but nothing worked out. Then I found that every(almost) smartphone has an in-built Light sensor at the top beside the front camera. So in the app, what you see in the Light sensor Reading area is the real-time reading from your light sensor. I don't have a temperature, humidity, Co2 sensor with my phone. So the user has to give input manually. If your smartphone has any of the sensors, please tell me I will updates the app accordingly.



Lower half: It shows the output "Occupied" or "Vacant" based on the reading given in the upper half with the percentage of chances of being the output to be true.



Working:  Inputs given by the user (Temperature, humidity, co2) are stored locally on the device. But the Light sensor reading is first stored to the Google Firebase, and then it is being retrieved from there. Why? I will tell you later. Once the light sensor reading is changed, all the inputs, Is feed to the neural network, which is being hosted at the Google Firebase. And based on the output from the neural network, the lower half shows the current state of the room with % chances.



About Neural Network: First of all, the data set provided by you consist of 1 training set and two testing set. And given the training set doesn't have enough data. So what I did is that I combined one of the testing set to the training set. This increased the number of input for training. Using Tensorflow2.0, I have made a dense-deep neural network with one input layer, one hidden layer, and one output layer. My hidden layer consist of six nodes. I have used Sigmod Function as my Activation function. Then I trained it. Testing gives me 90.4% of accuracy.



Note:  Make sure you have an active internet connection before you start the app. To get new results after you enter the values, you must hover your hand over the light sensor. It will trigger the model again.



What I have noticed: the model is very sensitive to the light sensor. If you cover the light sensor by your hand model will give output as "Occupied" with a probability of 0.99. Also, the reading of the light sensor should be greater the 150lux for the room to be occupied.



I Have attached my app's ".apk " file install it on your smartphone and let me know the feedback. 

I have also attached my python file have a look on it. In order to run it, you have to go to colab upload the training and test set the run it.

