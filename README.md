---

A SIMPLE GUIDE TO BUILDING AN IMAGE CLASSIFIER WITH CNN (using google colab)
Today we are going to build an image classifier using CNN. For this project we would train our model to classify two fruits, the african cherry (locally known as agbalumo) and the soursop (locally known as local ebo). We would be working with google colab for this project and we would connect our google drive to it. Below is what would be covered.
Image acquisition
Dataset formation
Model development


You can check this project (with pictures and a video) on medium at https://medium.com/@usman.a1282/a-simple-guide-to-building-an-image-classifier-with-cnn-from-data-set-to-deployment-deecde4480dc 

---

IMAGE ACQUISITION
The images used in this project are gotten from google and we would first have to download a google chrome plug-in for batch download.
Just go on google and search for "fatkun", click on the first result that shows up and download.

2. The next step is to go on google and type "google images", click on the first result that shows up and you should be directed to the google image homepage.
3. Type in the name of the image you would like to download ad search.
4. Click on the icon for google chrome extensions on the top right corner of your chrome browser and select fatkun batch downloader.
5. Do some data cleaning by deselecting the images you do not require and click download. A folder is automatically created in your download folder containing the downloaded images.
6. Repeat steps 3 to 5 while searching for soursop instead.
steps 2 to 5 can be seen in the video below

---

The next step is to make a dataset out of the images we downloaded, to do so we would be making use of google colab as our IDE. This means we are going to upload the images we downloaded to google drive for easy accessibility. Below are the steps to follow
Log into your google drive account, create a folder (mine is 'fruits classifier' which is inside an 'AI projects' folder) and upload the two folders for the fruits we downloaded.
Open a new tab on your browser and search for 'google colab'. Click on the first result.
Select file and click on new notebook as in the image below.

4. Mount google drive onto the google colab notebook using the codes in the image below. You would be redirected to a page where you grant your notebook access to tour google drive, just copy the key provided and paste it in the field on your notebook.
5. Next is to place the path to our images on our google drive, it should follow the format "gdrive/Mydrive/your folder name"
6. Import all neccesary libraries.
7. Make a list containing the two categories of fruits we will be classifying
8. Create a function that gives a file path to each image in each of the two folders containing our downloaded images. This is going to take the format "gdrive/MyDrive/Ai_projects/fruit classifier/African cherry (Agbalumo)/image name" for all the images in the African cherry folder and "gdrive/MyDrive/Ai_projects/fruit classifier/Soursop (Local Ebo)/image name" for images in the soursop folder. Each image will be resized to a 200 x 200 image and appended to a list followed by a class number which is based on the index of the fruit class in the categories list created in step 7(0 for african cherry and 1 for soursop). Training list will be
training = [["gdrive/MyDrive/Ai_projects/fruit classifier/African cherry (Agbalumo)/002",0] , ["gdrive/MyDrive/Ai_projects/fruit classifier/Soursop (Local Ebo)/image(01) , 1]…]
9. Shuffle the contents of the training list and split the list into our images (X) which are then reshaped and their categories (y). X contains matrixes containing pixel values for our images while y contains 0's and 1's representing the category of each image.

---

This section is where we develop and train our model, below are the steps to follow.
Convert the contents of X to float32 data type and normalize them. The contents of y are also converted to a categorical data type before they are being split to test and training datasets.

2. Create, compile and fit our CNN model. You can try different values for your layers (the first value in the conv2D layer)and see if you can achieve better results.
3. Evaluate the model. what we want to achieve is a low value for loss (close to 0) and a high value for accuracy (close to 1).
4. Now that we have trained our model, its time to test it on our training data.
5. We can check if the predicted classes for the fruits match the actual classes of the fruits with the function below.
Below are the output of the functions above
Only on of the image was misclassified, that number 41 on the index, an african cherry fruit was misclassified as a soursop fruit. This is a good result.
6. Save the model.
That brings us to the end of this part, feel free to drop any questions in the comments section, below is the link to my google colab notebook for this project and watch out for the next part of this series.
Google Colaboratory
Edit descriptioncolab.research.google.com (https://medium.com/r/?url=https%3A%2F%2Fcolab.research.google.com%2Fdrive%2F1EY1ifUPPKE-1zbcRL-XoWbRMHmewgAJz%3Fusp%3Dsharing)

You can check this project ((with pictures and a video)) on medium at https://medium.com/@usman.a1282/a-simple-guide-to-building-an-image-classifier-with-cnn-from-data-set-to-deployment-deecde4480dc 

Reference
Image Classification Using Convolutional Neural Networks: A step by step guide by Devansh
