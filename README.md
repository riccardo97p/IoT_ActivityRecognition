# Activity Recognition
This is the official documentation page of the Activity Recognition IoT project.

## Who we are
We are [Andrea Napoletani](https://www.linkedin.com/in/andrea-napoletani-aa0b87166/), [Alessandro Giannetti](https://www.linkedin.com/in/alessandro-giannetti-2b1864b4/) and [Riccardo Pattuglia](https://www.linkedin.com/in/alessandro-giannetti-2b1864b4/) three friends and students at "La Sapienza" University of Rome.

## The Project
Activity Recognition is a project that aims to recognize your activities like standing, sitting, walking and running in order to 
keep track of your daily trends.

We use the [Intel® Curie™](https://www.intel.com/content/dam/support/us/en/documents/boardsandkits/curie/intel-curie-module-datasheet.pdf) module of Genuino 101 board to train activity patterns and his Pattern Matching Engine to classify new patterns exploiting data from accelerometer and gyroscope.
All the classified activities are sent to an Android application through [Bluetooth Low Energy (BLE)](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy) and stored on Amazon Web Services (AWS IoT and AWS DynamoDB); finally, everything is plotted on Redash.

### Technologies
* [Genuino 101 Board](https://store.arduino.cc/genuino-101)
* [Android Studio](https://developer.android.com/studio)
* [Amazon Web Services IoT](https://aws.amazon.com/iot/?nc1=f_ls)
* [Amazon Web Services DynamoDB](https://aws.amazon.com/dynamodb/?nc1=f_ls)
* [Redash](https://redash.io/)

Be careful: for this project we have used free trial periods (30 days for Redash and 12 months for AWS IoT/DynamoDB), after that period you have to pay for them. 

### Project overview
* Train Genuino 101 Board on some regular patterns (referred to each activity) in order to allow it to classify new patterns captured by accelerometer and gyroscope.
* Send data from Genuino 101 to the Android App through Bluetooth Low Energy (BLE) technology.
* Connect the Android App to AWS IoT service and send data exploiting MQTT protocol.
* Connect and store data from AWS IoT to AWS DynamoDB.
* Query the AWS DynamoDB from Redash to plot the activity overview.

For the details about each step see our [Hackster.io](https://www.hackster.io/andreanapoletani/activity-recognition-using-genuino-101-and-aws-iot-fbeea2) post!

## How to use
Follow these steps to try the project:
* Import and upload the [sketch](https://github.com/riccardo97p/IoT_ActivityRecognition/tree/master/IoT_Arduino) on Genuino 101.
* Import the [Android app](https://github.com/riccardo97p/BLE_to_DynamoDB.git) on Android Studio.
* Change ```private static final String CUSTOMER_SPECIFIC_IOT_ENDPOINT = "YOUR_ENDPOINT";``` in the `AWSServiceClient.java` file with your AWS IoT Endpoint.
* Change
```  
    "PoolId": "YOUR_POOLID",
    "Region": "YOUR_REGION"
```
in the `res/raw/awsconfiguration.json` file with your PoolID and Region values.
* Build and Run the app.

# Useful Links
* [Project presentation](https://www.slideshare.net/AndreaNapoletani/activity-recognition-137479240) (one technology is changed due to compatibility problems)
* [Proof of Concept](link)
* [Hackster post](https://www.hackster.io/andreanapoletani/activity-recognition-using-genuino-101-and-aws-iot-fbeea2)

Feel free to contact us for further information!
