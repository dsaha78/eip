# EIP2 Batch 2 Session 1



## Convolution

**Convolution** is a process of extracting feature form an image. In this process we look into a smaller area to extract feature rather than looking into whole image. It's like having a small window over a image which moves right and  then down. The importance of this feature will be decided during learning process. Once a feature is found, it will be reported to the **feature map**, which is the output of one round of convolution. The window we are talking about here is known as **kernel** or **filter**.

![](https://github.com/dsaha78/eip/raw/master/image1.jpg)

In the above image the kernel is sitting in the middle and the output of the operation is stored in the blue shaded area of the feature map. The output will sit roughly the same location as of the input data.



## Kernel

**Kernel** is a small matrix of data.  The weights of the kernel determine what specific features we are trying to detect. This value changes with every iteration over the input data, indicating that network is learning to identify significance of a area for extracting features from the data. Kernel has the power to reduce size of the input. Size of the kernel plays an import role in finding important feature. Bigger kernel can over look a essential feature where as a smaller one could generate more information. This it is essential to generate a suitable size of the kernel.



## Feature Map

**Feature** is said to be an attribute or a property common to all the data unit. During convolution process , we look for feature through small window called kernel, which will focus on a small portion of the data. When ever we find a feature we will put the feature into a **Feature Map**. 

**Feature Map** is the output of a single convolution process on a input matrix. The kernel would be moving on top of input matrix doing mathematical operation and the output will be another matrix which is known as feature map. 

![](https://github.com/dsaha78/eip/raw/master/image1.jpg)

Consider the above scenario, we have a 7x7 input matrix and 3x3 Kernel. This kernel is moving on top of the input matrix, and generating a feature map of size 5x5.  



## 3x3 Convolution

**3x3 convolution** uses a 3x3 kernel. The size of the kernel is very important, while a small kernel will generate huge volume of information and a large one will overlook features. it is very essential to have a suitable kernel size. so it is general consensus to use a 3x3 kernel. We stack them together to get a large receptive field.



## 1x1 Convolution

For **1x1 Convolution** we use a matrix a single number as kernel/filter. In this scenario we will be considering a single point rather than considering the other points around it. this method of convolution is used to reduce the number of depth channels.  for example lets consider we have a matrix of 200x200 with 64 depth channels. when we run  convolution  20 channels  1x1 matrix kernel, the output channels will be reduced to 20 channels.



## Epoch

**Epoch** is the number of times the machine has run through the entire data set. Once the machine completes running through  the entire data set it is said to be on epoch has been completed. For example let us consider we have 100 data set. once the machine has completed reading all the 100 data set, it is said that one epoch is completed. 



## FEATURE ENGINEERING

**Feature** is said to be an attribute or a property common to all the data unit. Now we will use the domain knowledge of the data to create features that would make machine learning algorithm works. This process is creating feature is called **Feature Engineering**. A good feature engineering could be the major differentiator between a good and bad model.

Look at this data shown below, **Time of the Day** is the  deciding factor for a flight to be on time or delayed not the date.  

|      | Date_Time_combined | Status  |
| :--: | :----------------: | :-----: |
|  0   |  2018-02-18 18:30  | Delayed |
|  1   |  2018-02-18 06:30  | On Time |
|  2   |  2018-02-16 18:30  | Delayed |
|  3   |  2018-02-16 08:30  | On Time |
|  4   |  2018-02-15 07:30  | On Time |

With **Time of the Day** machine learning algorithm will be able to decide better whether a flight will be delayed or on time. the creation of this new feature called **Time of the Day** is feature engineering.   

|      | Time of the Day | Status  |
| :--: | :-------------: | :-----: |
|  0   |      18:30      | Delayed |
|  1   |      06:30      | On Time |
|  2   |      18:30      | Delayed |
|  3   |      08:30      | On Time |
|  4   |      07:30      | On Time |



## Activation Function ##

The **Activation Function** is a transformation we do on a output data of a neuron. This would decide whether the next neuron will get activated or not.  lets say the out put could be anything between 0 to 1, and our next neuron is expecting either a 0 or 1. 1 means next neuron will get activated. 

Now consider a scenario, the the output of the previous neuron is 0.85. our activation function will convert anything greater than .7 to1 else 0. Once this activation function is applied the output will be 1 in this scenario thus activating the next neuron.  If we receive a value say 0.63 then the next neuron will not get activated.



## Receptive Field ##

In a Convolution Neural Network the **Receptive Filed** is the part of the image that is visible to the kernel at any given point of time. We do not connect all the data of the input , which will create a lot of data and also a high computational complexity. So we concentrate a smaller area which would be size of the kernel. In the image below red shaded region is the receptive field.



![](https://github.com/dsaha78/eip/raw/master/image1.jpg)