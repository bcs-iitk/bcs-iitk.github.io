---
layout: project-completed
title: Facial Expression Recognition
abstract: Computer Vision , a well-known problem of every ML enthusiast , is leveraging the computer/machine with the ability to see and classify objects much like human beings. This project was based on exploring Computer vision to a little extent. The aim was to develop a Machine learning model which is able to classify some basic emotions (Happy , Sad, Angry, Disgust, Fear, Surprise and Contempt) using facial expressions of humans .We had chosen the CK+ dataset for implementation. Overall, the project had three phases; Preprocessing , Model , Evaluation.
stat: completed

---
**Mentor:** Avisha Gaur <br>
**Poster :** <a href="https://drive.google.com/file/d/16-eVFhDVKEf58gj0dlAS7SRuXL24Nvd9/view?usp=sharing" target="_blank">Link</a><br>
**Documentation :** <a href="https://drive.google.com/file/d/1A-Lygswq49kQd_QBPK6TUQI169W5QoRH/view?usp=sharing" target="_blank">Link</a><br>
### Team 1
**Team Members:** Shashi Kumar, Aman Agarwal, Arpit Verma, Gaurav Sharma, Himanshu shetty, Anumam Yadav, and Shakshi. <br><br>
**Abstract:**<br>
* Preprocessing : This was the start of the project, basically  we aligned, face - cropped, normalized the images of our dataset and also augmented (flipped and randomly rotated) them to ensure good results.
* CNN model : We implemented a CNN model structure with two convolutional layers and two subsampling layers along with dropouts of 0.5 followed by output dense layer of seven units and softmax activation function.
* Evaluation : We evaluated our model on three cropping methods viz. Cropping with background, Cropping without background, Cropping without forehead. We also made variation in the neuron number of hidden dense layer prior to the output layer as 0, 256, 512, 1024. Further, we performed a ten- fold cross validation on our dataset.
* Results : Finally, We got an average accuracy of 97.49 after performing all above mentioned evaluation statistics.
<br><br>

### Team 2
**Team Members:** Falguni Yadav, Prachi Singh, Pranav Kumar, Saksham Pruthi, Samriddhi Gupta, Tanisha Agrawal, Videeta Sharma, Yatharth Gupta <br><br>
**Abstract:**<br>
With the recent development and application of human–computer interaction systems, facial expression recognition (FER) has become a popular research area. The recognition of facial expression is a difficult problem for existing machine learningand deep learning models because that the images can vary in brightness, background, pose, etc. Feature extraction is very important for FER, even a simple algorithm can be very effective if the extracted features are sufficient to be separable. However, deep learning methods automatically extract features so that some useless features can interfere with useful features. For these reasons, FER is still a challenging problem in computer vision.

Facial expressions are one of the most important features to reflect the human emotional state because they convey useful information to the observer. Several deep learning approaches for facial expression recognition were developed in the last decades, particularly the method of CNN.
This project aims to to detect involuntary emotional response occurring simultaneously with conflicting voluntary emotional response and identifying true emotions by building classifiers that categorise facial expressions into 6 universal emotion categories (+1 neutral). We start off by implementing various pre-processing techniques for the images and use a customised face-cropping method. We also implement Linear Binary Patterns for Feature Extraction and then test these on 2 customised CNN models while measuring their performance.
<br><br>

### Team 3
**Team Members:** Aditya Prakash, Ananya Gupta, Bhavesh Jain, Shivanshu Tyagi, Urbi Ghosh <br><br>
**Abstract:**<br>
Facial expression recognition has gained a lot of attention in the past few years due to its wide applications. FER can be classified into two categories: Macro Expressions and Micro expressions recognition. We focused on macro expression recognition. Methods for emotion recognition  often involve the Facial Action Coding System (FACS) which describes the facial expression using Action Units (AU). An Action Unit is a facial action like ”raising the Inner Brow”. Detecting such landmarks can be hard, as the distance between them differs depending on the person .

The presented approach uses Convolutional Neural Networks special type of Artificial Neural Networks(ANNs).The proposed network has been trained on the FER-2103 Dataset  and evaluated on the CK+ dataset and achieved an accuracy of 95.6%.
After training on image dataset, the problem statement was expanded to video dataset. Approach for the second problem was  changed: a hybrid of C3D and CNN+LSTM network was used. LSTM has memory ability and suits for processing sequences with contexts well. In the end, real time emotion classification using webcam input was incorporated. 
<br><br>

### Team 4
**Team Members:** Kusum Bunkar, Deepika Meena, Lakshita Mohanty, Pranay Vandanapu, Rishi Dhakar, Bhavy Gandhi, Mukulesh Shinde <br><br>
**Abstract:**<br>
Facial expressions are one of the most important features to reflect the human emotional state and they convey 55% of a communicated message which is more than the part conveyed by the combination of voice and language. FER technique can be used for the development of human–computer interaction systems, such as social robots, visual interactive games, and data-driven animation.<br> 
We used a new face cropping and image rotation strategy to improve the accuracy and simplify the CNN structure. By facial cropping we removed the emotionally inactive part of the region and random rotations to cope up with data scarcity. Also Histogram equalization, Z-score normalization, and down-sampling were applied to standardize the image data.The expanded training data thus obtained is used to train the CNN, and we got our best CNN model by ten-fold cross validation. During the validation or testing phase, the normalized testing images (without expansion) were sent to the CNN model from the training phase for prediction. Further we have used the combined datasets to train a model for detecting single and multiple faces and their six different expressions in a realtime environment.
<br><br>

### Team 5
**Team Members:** Aditya Jindal, Mrigya Gupta, Sampada Sinha, Shruthi Sureshkumar <br><br>
**Abstract:**<br>
Emotions play a hugely important role in our interpersonal communications. Recognizing emotions accurately has wide ranging applications - from marketing to psychology to gaming. In this project we aimed to recognize facial expressions from input image data. We began with a review of existing literature to understand the problem of facial expression recognition. We ended up implementing 3 different papers to obtain better accuracies, and obtained the highest accuracy on the final paper implemented. We were introduced to machine learning, and deep learning techniques. We tested and trained the model on existing standard datasets, and also tested the model with a live webcam feed.<br>
