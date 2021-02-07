# Breaking Captcha Images: Project Overview

* Created an algorithm that successfully labels full captcha images.

## Steps:

* Picked and downloaded a dataset of captcha images from Kaggle.
* Created an algorithm that could extract the digits from each image, i.e. automatically draw bounding boxes around the digits.
* Manually labelled the extracted digit images from the training and validation set.
* Created a couple VGG-like convolutional networks, trained them and tested them on the validation data, eventually achieving a validation accuracy of 0.972 on the best one.
* Built a function that could label the whole captcha images from the test set and evaluated it.

## Main technologies used:

* Tensorflow
* Keras
* OpenCV
* Matplotlib

## Main techniques used:

* Deep Learning
* Classical Computer Vision
* Modern Computer Vision
* Data Augmentation
* Ensemble Learning

## Digit Extraction:

Found an appropiate threshold for the value channel and detected the main contours using the OpenCV function findContours. The algorithm ended up being able to extract the digits of each image as follows:

![descarga (2)](https://user-images.githubusercontent.com/70718425/107143212-136c1b80-6934-11eb-99ec-f11d9144d007.png)

## Manual Labelling:

I built a function that would display each digit image (from the train and validation splits) and save it along with the label that I typed.

## Model Selection:

I tried three models: a reguralized LeNet and two regularized VGG-like architectures, which I will call VGG1 and VGG2. I used data augmentation to improve generalization.
With each model, I increased the complexity and the regularization of the previous one, the results were the following:

|  Model | Validation Accuracy  | 
|---|---| 
| LeNet  |  0.943               |
| VGG1  | 0.968  |
|  VGG2 |  0.972 |

I finally chose the last model, trained and saved it 5 times and used the trained models for ensemble learning.

## Final Algorithm:

I built a function that would extract the digits from the test images, label them using the ensemble of models trained in the last step, and write the label on the full captcha image. 
Here are some results (of the test images):
![captcha_image1](https://user-images.githubusercontent.com/70718425/104241021-4f0ee500-545d-11eb-8a14-bcd5dd128762.png)
![captcha_image2](https://user-images.githubusercontent.com/70718425/104241064-5cc46a80-545d-11eb-9b2c-aef2a6ab581c.png)
![captcha_image3](https://user-images.githubusercontent.com/70718425/104241067-5e8e2e00-545d-11eb-8b15-1a65c996b2de.png)
![captcha_image4](https://user-images.githubusercontent.com/70718425/104241071-6057f180-545d-11eb-9cbf-dace772dec32.png)
![captcha_image5](https://user-images.githubusercontent.com/70718425/104241077-62ba4b80-545d-11eb-9c28-9d09d27b464e.png)


The algorithm failed to recognize 4 digits among all the test images (which was probably due to the digit extraction algorithm), and didn't classify incorrectly any digit.
