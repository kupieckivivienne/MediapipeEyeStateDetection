# MediapipeEyeStateDetection
This Mediapipe implementation aims to detect human eye states and compare different methods to ground truth labels. This code was made in Google Colab.

## Running Our Data 
We focused on the implementation of several different datasets. Click the Link to download the folders. Make sure to upload them to your Google Drive when using Google Colab: 

### Flickr-Faces-HQ Dataset (FFHQ) 
We used 50 images from the Flickr Faces HQ Dataset, which are 1024 x 1024 px. Please redirect any changes or additions to this Dataset here: 
https://github.com/NVlabs/ffhq-dataset 

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
