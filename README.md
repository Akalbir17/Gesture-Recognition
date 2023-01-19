# Gesture-Recognition

## Problem Statement: - 
Imagine you are working as a data scientist at a home electronics company which manufactures state of the art smart televisions. You want to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote. The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

1. Thumbs up:  Increase the volume <br>
2. Thumbs down: Decrease the volume <br>
3. Left swipe: 'Jump' backwards 10 seconds <br>
4. Right swipe: 'Jump' forward 10 seconds  
5. Stop: Pause the movie
 

Each video is a sequence of 30 frames (or images). In the next couple of lectures, our subject matter expert Snehansu will walk you through the structure of the dataset.

## Understanding the Dataset
The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use. 

 The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each subfolder, i.e. a video, contains 30 frames (or images). Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). Hence, you will need to do some pre-processing to standardise the videos. 

 

Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

 

Your task is to train a model on the 'train' folder which performs well on the 'val' folder as well (as usually done in ML projects). We have withheld the test folder for evaluation purposes - your final model's performance will be tested on the 'test' set.

## Experimentation 
![2023-01-19 (1)](https://user-images.githubusercontent.com/69676151/213457194-d8f8e36a-a0f3-4ecd-bf63-5dc2ae3e1ba6.png)
![2023-01-19 (2)](https://user-images.githubusercontent.com/69676151/213457488-eee93451-62d5-4eb2-8c4a-6e45c78952b3.png)
![2023-01-19 (3)](https://user-images.githubusercontent.com/69676151/213457717-e8e537fe-856c-4006-8b02-28bbd6ae6cd7.png)

## Final Models Selected
![2023-01-19 (4)](https://user-images.githubusercontent.com/69676151/213458092-dcffac58-26ef-4966-8ad6-fd7b4f719deb.png)

## Final Model Performance
![2023-01-19 (5)](https://user-images.githubusercontent.com/69676151/213458557-0cae430a-2453-4cff-9818-309353c46d49.png)
![2023-01-19 (6)](https://user-images.githubusercontent.com/69676151/213458717-bf7506dd-3928-4c57-9049-35d706c789b8.png)

## Conclusion
## Conclusion
Hence I was sucesssfully able to design a gesture recognition model using two different approaches viz. Conv3D approach and Conv2D+RNN approach. For Conv2D I used transfer learning with mobilenet model.Both the approaches performed very well with training accuracy of 
`95.32 %` and `99.85 %` respectively. It also performed well on the validation data with accuracy of `88.00 %` and `97.00 %` 
