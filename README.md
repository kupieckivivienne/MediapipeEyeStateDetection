# MediapipeEyeStateDetection
This Mediapipe implementation aims to detect human eye states and compare different methods to ground truth labels. This code was made in Google Colab.


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
This will depend on the data that you use. The path for your data images will be different, so make sure you adjust accodingly. 

```img = cv2.imread("/content/gdrive/MyDrive/final_project/images/sample/01000.jpg")
print(img.shape)
cv2_imshow(img)```
