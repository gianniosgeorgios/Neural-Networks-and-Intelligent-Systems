# Deep Learning on CIFAR-100, using Convolutional Neural Networks and Transfer Learning techinques

## Dataset:

![21](https://user-images.githubusercontent.com/50829499/111316833-4492e680-866c-11eb-8247-010e756a2fcd.png)

The working dataset was [CIFAR-100](https://www.cs.toronto.edu/~kriz/cifar.html).  It consists of 60000 32x32 colour images in 100 classes (such as vehicles, flowers, household electrical devices, people ...). In this excerisce, our goal was to improre predictions' accuracy on 80 classes

## Description

Using TFRecord files, for proper memory managment, we follow some steps to optimize accuracy 

### Comparing Different Models 

First of all we compare different model architectures about memory usage, total parameters, training time and accuarcy <br/>

These architectures were:<br/> ***VGG-16, EfficientNetB7, ResNet, DenseNet121, Xception, MobileNetV2, InceptionV3***. <br/>

### Choosing best model 

We come to the conclution that **DenseNet** model is the best choice . It needs less training time and memory sources and it succeeds high accuracy (~ 77 %).

### Optimizing best model 

For opotimizing DenseNet model we follow some steps:

1. *Resize input images' shape*: For bigger imput shape accuracy is improving, but RAM usage is increased.
2. *Data augmentation*:  We increase the amount of data by adding slightly modified copies of already existing data so as to avoid overfiting.
3. *Fine tuning*: Since we have a large dataset, there is no reason to train only the head of the network. 
4. *Adding dropout layers*: It was neccesary since some paths in our network represent noise. So we cancel them using dropout layers.
5. *Early stopping techinques*: During the learning proccess, if the validation accuracy does not improve, we stop learning.
6. Experimentation with learning rate, batch size and different opotimizers


### Final Results

After all, we succeeded 92 % accuracy on 20 classes of CIFAR-100, 88% on 40 and 84% on 80 classes. 

