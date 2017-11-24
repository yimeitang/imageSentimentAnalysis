# imageSentimentAnalysis


In this project, I want to explore whether it is practical to using images alone to perform sentiment analysis.
In particular, I want to analyze whether we could predict the rating given by the guest to a hotel by only using the image as input data. The target variable will be 1,2,3,4,5 so it is a supervised learning.



## Step 1 : Get the Data
I start with one hotel in Chicago by downloading 1000 images from the hotel on TripAdvisor(using Image Downloader – a Chrome extension), then filtering out photos taken by Experts and hotel management, then hand labelling them with ratings.
I can’t match all pictures with the ratings on the website, therefore, I eventually have 400 pictures with ratings.

Data Distribution: 

![data_distribution](https://user-images.githubusercontent.com/27776652/33224666-8de1796c-d131-11e7-91c7-53fc56efa6b0.png)

## Step 2 : Preprocess the data
After getting the data labeled, I converted each image to 3-d numpy array of their RGB values.However, since each
picture has different size, after exploring some classic CNN models, most of the input pic size is no larger than 227\*227.
Therefore, I re-sized all the images to 227\*227. Now each image is represented by a numpy array, shape of (227,227,3).
Since I only have 400 data set, I will not use validation set butonly use 10% as the test set and the remaining 360 images as
training set. I randomly shuffled the 400 images before splitting into training set and test set.

Images of Rating 1:
![6picsofrating1](https://user-images.githubusercontent.com/27776652/33224704-fb8b5104-d131-11e7-922c-b6022ee9b18a.PNG)

Images of Rating 2:
![6picsofrating2](https://user-images.githubusercontent.com/27776652/33224705-fb9b2ad4-d131-11e7-9bf3-1f7ae0e972fe.PNG)

Images of Rating 3:
![6picsofrating3](https://user-images.githubusercontent.com/27776652/33224706-fba8c1bc-d131-11e7-84d5-1dab15625c84.PNG)

Images of Rating 4:
![6picsofrating4](https://user-images.githubusercontent.com/27776652/33224707-fbb568b8-d131-11e7-909b-e9c03a6679be.PNG)

Images of Rating 5:
![6picsofrating5](https://user-images.githubusercontent.com/27776652/33224708-fbc719dc-d131-11e7-88da-079f19917df7.PNG)
