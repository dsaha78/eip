# EIP2 Batch 2 Session 1

## Convolution

**Convolution** is process for combining two sets of data. On the input matrix we will apply a **Filter/Kernel** to produce output matrix known as **Feature Map**.  The **Kernel** will move over the input matrix, performing element wise mathematical operation on the data it is currently on and result out a single data point. This process is repeated until the complete matrix is covered. 

![](/home/sahade/Desktop/DeepinScreenshot_select-area_20180930093607.png)

In the above image the kernel is current on the area marked in Green and the output of the operation is stored in the orange shaded area of the feature map. the output will sit roughly the same location as of the input data.

## DATA FROM INTERNET

> In convolutional networks, you look at an image through a smaller window and move that window to the right and down. That way you can find features in that window, for example a horizontal line or a vertical line or a curve etc… What exactly a convolutional neural network considers an important feature is defined while learning.
>
> Wherever you find those features, you report that in the feature maps. A certain combination of features in a certain area can signal a larger, more complex feature exists there.
>
> For example, your first feature map could for example looks for curves. The next feature map could look at a combination of curves that build circles. The next feature map could detect a bicycle from lines and circle features.

## DATA FROM INTERNET



## Kernel

**Kernel** is a small matrix of data.  The weights of the kernel determine what specific features we are trying to detect.
$$
\begin{vmatrix} 
\mathbf{1} & \mathbf{0} & \mathbf{1} \\
\mathbf{0} & \mathbf{1} & \mathbf{0} \\
\mathbf{1} & \mathbf{0} & \mathbf{1}\\
\end{vmatrix}
$$
if we look at the kernel shown above the feature we are are trying to detect is a diagonal line on either direction.



## Feature Map

**Feature** is said to be an attribute or a property common to all the data unit. during convolution process , we look for feature through small window called kernel, which will focus on a small portion of the data. When ever we find a feature we will put the feature into a **Feature Map**. 

**Feature Map** is the output of a single convolution process on a input matrix. The kernel would be moving on top of input matrix doing mathematical operation and the output will be another matrix which is known as feature map. 

![](/home/sahade/Desktop/DeepinScreenshot_select-area_20180930093607.png)

Consider the above scenario, we have a 7x7 input matrix and 3x3 Kernel. This kernel is moving on top of the input matrix, and generating a feature map of size 5x5.  



## 3x3 Convolution

When we use a kernel of 3x3 on input matrix , this convolution is known as 3x3 convolution.eeeee



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