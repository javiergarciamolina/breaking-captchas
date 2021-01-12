# Breaking Captchas

## Objective:
In this project I downloaded a dataset of captcha images and went through the whole process of splitting it into training, validation and test sets, extracting the digits from the images, labelling the ones from the training set so that I could feed them to a neural network, training a model that could successfully learn to identify the digits, and then using this model for labelling the whole captcha images of the test set. We had 45 classes and 1236 training images.

## Result:
Our algorithm ended up being able to, given the original images, label them like these:
![captcha_image1](https://user-images.githubusercontent.com/70718425/104241021-4f0ee500-545d-11eb-8a14-bcd5dd128762.png)
![captcha_image2](https://user-images.githubusercontent.com/70718425/104241064-5cc46a80-545d-11eb-9b2c-aef2a6ab581c.png)
![captcha_image3](https://user-images.githubusercontent.com/70718425/104241067-5e8e2e00-545d-11eb-8b15-1a65c996b2de.png)
![captcha_image4](https://user-images.githubusercontent.com/70718425/104241071-6057f180-545d-11eb-9cbf-dace772dec32.png)
![captcha_image5](https://user-images.githubusercontent.com/70718425/104241077-62ba4b80-545d-11eb-9c28-9d09d27b464e.png)


Out of 36 testing images (i.e. 144 digits), our algorithm failed to recognize 4 digits, which was probably due to the digit extraction algorithm. It didn't missclassify any digit.

## Main technologies used:

* Tensorflow
* Keras
* OpenCV
* Matplotlib

## Main techniques used:

* Deep Learning
* Classic Computer Vision
* Modern Computer Vision
* Data Augmentation
* Ensemble Learning

## Model:

The final model used was the regularized MiniVGG network that follows:

![descarga (5)](https://user-images.githubusercontent.com/70718425/104295439-c033b400-54c0-11eb-9f96-b9a47f93926d.png)

        
