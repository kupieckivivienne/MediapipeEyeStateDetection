# MediapipeEyeStateDetection
This Mediapipe implementation aims to detect human eye states and compare different methods to ground truth labels. This code was made in Google Colab.

## Running Our Data 
We focused on the implementation of several different datasets. Click the Link to download the folders. Make sure to upload them to your Google Drive when using Google Colab: 

### Flickr-Faces-HQ Dataset (FFHQ) 
We used 50 images from the Flickr Faces HQ Dataset, which are 1024 x 1024 px. Please redirect any changes or additions to this Dataset here: 
https://github.com/NVlabs/ffhq-dataset 

### Open: Closed 
Diverse data set with 26 open-eyed images and 26 closed-eyed images. We changed the ground truth to match this accordingly to run with our code. 

## Running Packages
In order to use Mediapipe, please run the command below at the top of your code: 

`! pip install mediapipe`

To see more documentation on how to run Mediapipe, please follow the instructions on Mediapie's getting started page: 
https://google.github.io/mediapipe/getting_started/python.html

In addition, we used cv2.utils package: 

`! pip install cv2-utils`

## Mounting your Google Drive

`from google.colab import drive
drive.mount("/content/gdrive")`

## Test that your Google Drive Successfully Mounted 
This will depend on the data that you use. The path for your data images will be different, so make sure you adjust accordingly. 
If you use Google Drive, all file paths will start with "/content/gdrive/MyDrive/...."

```
img = cv2.imread("/content/gdrive/MyDrive/final_project/images/sample/01000.jpg")
print(img.shape)
cv2_imshow(img)
```
## Functions
The functions used to compute the key blink point ratio were adapted from https://medium.com/@asadullah92c/eyes-blink-detector-and-counter-mediapipe-a66254eb002c

## Understanding Right and Left Eye Key points
The numbers in r_eye and l_eye variables are appointed from Medipipe's face mesh. Those key points, are universal, and are adapted to every image run through the system. They are used as landmarks and key points, to then calculate ratios for the open, closed, and squinted eye states. 
```
if idx in (7, 33, 133, 144, 145, 153, 154, 155, 157, 158, 159, 160, 161, 163, 173, 246, 469, 470, 471, 472):
            r_eye_landmarks.append((-1, -1))
elif idx in (249, 263, 362, 373, 374, 380, 381, 382, 384, 385, 386, 387, 388, 390, 398, 466, 474, 475, 476, 477):
            l_eye_landmarks.append((-1, -1))
```
If you are curious about the key points, please download the Face Mesh image here: 
https://github.com/kupieckivivienne/MediapipeEyeStateDetection/tree/main/Face%20Mesh 

## Saving Eye Aspect Ratios in a CSV File 
Again, save your files into the respective Google Drive Folders. For example, you can find the EAR for all 50 images of the FFHQ Dataset sample here: https://github.com/kupieckivivienne/MediapipeEyeStateDetection/tree/main/Data/FFHQ%20(50%20Images) 

``` 
from pathlib import Path  
filepath_l = Path('gdrive/MyDrive/images/left.csv')
filepath_r = Path('gdrive/MyDrive/images/right.csv')  
filepath_r.parent.mkdir(parents=True, exist_ok=True)  
df_l.to_csv(filepath_l) 
df_r.to_csv(filepath_r) 
```  

## Contribution 

### Below we added respective contributions for our code: 

### Akanksha: 
- Met with Nerea Aranjuelo initially and adpated sections of the gaze-capture project's code to 
  fit the tasks needed to be accomplished by our project
- Mounted Drive on Google Colab and debugging
- Explored different options for EAR ratio code
- Adjusted threshold code which improved accuracy up to 93 percent
- Explored and tested diverse datasets  

### Vivienne: 
- Edited EAR functions and applied them to the data 
- Drew eye lines on preexisting Mesh Face on all images 
- Wrote threshold function and compared predicted versus ground truth labels 
- T- Test for different datasets and comparing error
-
### Alex: 
- Mounted Drive on Google Colab and debugging 
- Adjusted threshold code which improved accuracy up to 93 percent 
- Plotted accuracies for both right and left eye ratios 
- Explored and tested diverse datasets 

Thank you for viewing our project, and if you have any questions, please email @kupiecki@bc.edu 

