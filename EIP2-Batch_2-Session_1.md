# EIP2 Batch 2 Session 1

# URL #

**Delete this before submission**

for kernel.

https://blog.xrds.acm.org/2016/06/convolutional-neural-networks-cnns-illustrated-explanation/

**Delete this before submission**

## Convolution

**Convolution** is a process of extracting feature form an image. Rather than looking into whole image, we look into a smaller area to extract feature. It's like having a small window over a image which moves right and  then down. The importance of this feature will be decided during learning process. Once a feature is found, it will be reported to the **feature map**, which is the output of one round of convolution. The window we are talking about here is known as **kernel** or **filter**.

![](/home/sahade/Desktop/DeepinScreenshot_select-area_20180930093607.png)

In the above image the kernel is current on the area marked in Green and the output of the operation is stored in the orange shaded area of the feature map. The output will sit roughly the same location as of the input data.

## Kernel

**Kernel** is a small matrix of data.  The weights of the kernel determine what specific features we are trying to detect. This value changes with every iteration over the input data, indicating that network is learning to identify significance of a area for extracting features from the data. Kernel has the power to reduce size of the input. Size of the kernel plays an import role in finding important feature. Bigger kernel can over look a essential feature where as a smaller one could generate more information. This it is essential to generate a suitable size of the kernel.
$$
\begin{vmatrix} 
\mathbf{1} & \mathbf{0} & \mathbf{1} \\
\mathbf{0} & \mathbf{1} & \mathbf{0} \\
\mathbf{1} & \mathbf{0} & \mathbf{1}\\
\end{vmatrix}
$$
if we look at the kernel shown above the feature we are are trying to detect is a diagonal line on either direction.



> ## Filters (Convolution Kernels)
>
> A filter (or kernel) is an integral component of the layered architecture.
>
> Generally, it refers to an operator applied to the entirety of the image such that it transforms the information encoded in the pixels. In practice, however, a kernel is a smaller-sized matrix in comparison to the input dimensions of the image, that consists of real valued entries.
>
> The kernels are then convolved with the input volume to obtain so-called ‘activation maps’. Activation maps indicate ‘activated’ regions, i.e. regions where features specific to the kernel have been detected in the input. The real values of the kernel matrix change with each learning iteration over the training set, indicating that the network is learning to identify which regions are of significance for extracting features from the data.

## Feature Map

**Feature** is said to be an attribute or a property common to all the data unit. during convolution process , we look for feature through small window called kernel, which will focus on a small portion of the data. When ever we find a feature we will put the feature into a **Feature Map**. 

**Feature Map** is the output of a single convolution process on a input matrix. The kernel would be moving on top of input matrix doing mathematical operation and the output will be another matrix which is known as feature map. 

![](/home/sahade/Desktop/DeepinScreenshot_select-area_20180930093607.png)

Consider the above scenario, we have a 7x7 input matrix and 3x3 Kernel. This kernel is moving on top of the input matrix, and generating a feature map of size 5x5.  



## 3x3 Convolution

**3x3 convolution** uses a 3x3 kernel. The size of the kernel is very important, while a small kernel will generate huge volume of information and a large one will overlook features. it is very essential to have a suitable kernel size. so it is general consensus to use a 3x3 kernel. 



> "Note: I'm excluding 1x1 since that's a special case with its own special use case.
>
> The general consensus appears to be that you should use 3x3 filters and stack them in order to get a larger receptive field (ie two 3x3s give a 5x5 receptive field).
>
> There are a multitude of reasons why. The primary reason is because two layers with a nonlinearity have more expressive power than a single 5x5 layer and so forth for 7x7 and larger. It's also more parametrically efficient, and thanks to winograd filtering, computationally efficient.
>
> Also note that I'm a big fan of dilated convolution, it allows a larger receptive field size for the same amount of parameters and actually results in less overall computation. And empirically, it performs better as well.
>
> https://towardsdatascience.com/types-of-convolutions-in-deep-learning-717013397f4d





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
|  0   |      8:30       | Delayed |
|  1   |      06:30      | On Time |
|  2   |      8:30       | Delayed |
|  3   |      08:30      | On Time |
|  4   |      07:30      | On Time |