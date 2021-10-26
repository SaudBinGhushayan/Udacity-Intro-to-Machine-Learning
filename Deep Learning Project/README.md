### Introduction:
--------------------------------------

in this project I created a classifier to classify images in the `CIFAR-10` dataset.



### Data Augmentation:
--------------------------------------

I created three data loaders training and validating and testing the data , in the training dataset I transformed the data with RandomFlip and RandomRotation this helps the model
learn fast , for the validation and test datasets I just normalized the images with means and standard deviations of 0.5 , the batch size of the dataloaders are 64 batch which means that
each 64 images will passed to the model at once . 


### Exploring the datasets
--------------------------------------

the images in the dataset comes with 32x32 pixel and RGB colors , with 64 batch size we will have 782 observation in each of the dataloaders.


### Building the Neural Network:
--------------------------------------

I Built the Neural Network with three Convoulotional layers and three Fully Connected layers , the convoulotional layers will extract the features of the the images and maps it into the feature map
after that each convoulotional was set with an activation layer which in my case was a ReLU activation function , after mapping to the feature map a pooling layer will reduce the size of the output
of each convoulotional layer , images have 32x32 x 3 inputs after applying the first convoulotional layer we will get 16x16 x 9 inputs after applying the second convoulotional  layer we will get
8x8 x 27 inputs after applying the third convoulotional layer we will get 4x4 x 64 inputs after that we will pass it into the fully connected layers to produce the output .

I used an activation function on the last layer `log_sogtmax` with `NLLLoss` loss function , and `Adam` optimizer to optimize the gradients .


### Training the Neural Network:
--------------------------------------

with the first epoch I got train loss of `0.5895` and validation loss of `1.5878` and validation accuracy of `0.3976` , it increased over the number of epochs the below image will demonstrate more
![image](https://user-images.githubusercontent.com/82407781/135081467-1a9bd9d2-7e5f-4218-b864-9c6720c3fd8c.png)


### Testing the model:
--------------------------------------

After training on the training and validation dataloaders I applied the model on the testing dataloader which got 74% Accuracy and 76% test loss .
