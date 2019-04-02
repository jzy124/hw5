# Project 5：频域滤波器

姓名：江朝昀

班级：自动化少61

学号：2140506069

提交日期：2019.4.2

## 摘要

本次实验内容为使用频域低通滤波器Butterworth and Gaussian对图像进行平滑测试，使用频域高通滤波器Butterworth and Gaussian对图像进行边缘增强，使用拉普拉斯和Unmask测试图像。根据实验结果分析各滤波器的优缺点，再对比Project 3中的空域低通、高通滤波器，分析空域滤波器与频域滤波器之间的关系。

##  一. 频域低通滤波器（Butterworth and Gaussian）

题目要求：设计低通滤波器包括 Butterworth and Gaussian (选择合适的半径，计算功率谱比),平滑测试图像test 1和2;分析各自优缺点。

Butterworth频域低通滤波器表达式为：

![](<https://github.com/jzy124/hw5/raw/master/0/1.png>)

其中D(u,v)是频率域中点(u,v)频率矩形中心的距离。

Gaussian频域低通滤波器表达式为：

![](<https://github.com/jzy124/hw5/raw/master/0/8.png>)

其中D0是截止频率。

+ test 1

butterworth:

![](<https://github.com/jzy124/hw5/raw/master/1/test1-butterworth.png>)

gaussian:

![](<https://github.com/jzy124/hw5/raw/master/1/test1-gaussian.png>)

| 滤波器      | 半径 | 功率谱比           |
| :---------- | ---- | ------------------ |
| Butterworth | 25   | 0.9323223707489666 |
| Butterworth | 50   | 0.9695872944250473 |
| Butterworth | 75   | 0.9823906666912847 |
| Gaussian    | 25   | 0.9227772995992531 |
| Gaussian    | 50   | 0.9622021014322818 |
| Gaussian    | 75   | 0.9766376098870712 |

+ test 2

butterworth:

![](<https://github.com/jzy124/hw5/raw/master/1/test2-butterworth.png>)

gaussian:

![](<https://github.com/jzy124/hw5/raw/master/1/test2-gaussian.png>)

| 滤波器      | 半径 | 功率谱比           |
| ----------- | ---- | ------------------ |
| Butterworth | 25   | 0.9537087858280694 |
| Butterworth | 50   | 0.9747273087505853 |
| Butterworth | 75   | 0.9824205286083455 |
| Gaussian    | 25   | 0.9481346629832537 |
| Gaussian    | 50   | 0.9706925041059914 |
| Gaussian    | 75   | 0.9792909414000763 |

+ 优缺点分析
  1. 对于同一张图片，相同半径的Butterworth低通滤波器处理得到的功率谱比要大于Gaussian低通滤波得到的功率谱比。
  2. 在相同的半径下，Butterworth的平滑效果要比Gaussian好，这是因为Gaussian滤波器的频域过渡更加平缓。
  3. Butterworth低通滤波器在某些时候会产生振铃（本实验中未出现），Gaussian滤波器不会出现振铃。

##  二. 频域高通滤波器（Butterworth and Gaussian）

题目要求：设计高通滤波器包括butterworth and Gaussian，在频域增强边缘。选择半径和计算功率谱比，测试图像test 3和4；分析各自优缺点。

Butterworth频域高通滤波器表达式为：

![](<https://github.com/jzy124/hw5/raw/master/0/3.png>)

Gaussian频域高通滤波器表达式为：

![](<https://github.com/jzy124/hw5/raw/master/0/4.png>)

+ test 3

butterworth：

![](<https://github.com/jzy124/hw5/raw/master/2/test3-butterworth.png>)

gaussian：

![](<https://github.com/jzy124/hw5/raw/master/2/test3-gaussian.png>)

| 滤波器      | 半径 | 功率比                |
| ----------- | ---- | --------------------- |
| Butterworth | 25   | 0.01697496283186647   |
| Butterworth | 50   | 0.0033361609147567937 |
| Butterworth | 75   | 0.0010501478718664885 |
| Gaussian    | 25   | 0.01357254694962474   |
| Gaussian    | 50   | 0.0028334164461205507 |
| Gaussian    | 75   | 0.0009533473337376779 |



+ test 4

butterworth:

![](<https://github.com/jzy124/hw5/raw/master/2/test4-butterworth.png>)

gaussian:

![](<https://github.com/jzy124/hw5/raw/master/2/test4-gaussian.png>)

| 滤波器      | 半径 | 功率比               |
| ----------- | ---- | -------------------- |
| Butterworth | 25   | 0.03348535770906169  |
| Butterworth | 50   | 0.014056980936922574 |
| Butterworth | 75   | 0.007964754148220227 |
| Gaussian    | 25   | 0.028474288782775022 |
| Gaussian    | 50   | 0.011861406357934461 |
| Gaussian    | 75   | 0.00674285098933673  |

+ 优缺点分析
  1. 对于同一张图片，相同半径的Butterworth高通滤波器处理得到的功率谱比要大于Gaussian高通滤波得到的功率谱比。
  2. 就实验结果来看，在相同的半径下，Gaussian高通滤波器的边缘提取效果要优于Butterworth滤波器。Butterworth高通滤波器提取的边缘会包含更多的虚假边缘，这是因为滤波器频域变化平缓导致通过了更多的高频信息。

##  三. 其他高通滤波器（Laplace and Unmask）

题目要求：设计拉普拉斯和Unmask，对测试图像test 3,4滤波；分析各自优缺点。

Laplace频域高通滤波器表达式为：

![](<https://github.com/jzy124/hw5/raw/master/0/5.png>)

![](<https://github.com/jzy124/hw5/raw/master/0/6.png>)

![](<https://github.com/jzy124/hw5/raw/master/3/test3-Laplace.png>)

![](<https://github.com/jzy124/hw5/raw/master/3/test4-Laplace.png>)

Umask频域滤波器表达式为：

![](<https://github.com/jzy124/hw5/raw/master/0/7.png>)

![](<https://github.com/jzy124/hw5/raw/master/3/test3-unmask.png>)

![](<https://github.com/jzy124/hw5/raw/master/3/test4-unmask.png>)

+ 优缺点分析

  laplace算子提取的边缘有较多噪声，而且根据test4的结果来看，提取出来的边缘信息非常弱，非锐化掩蔽提高了图像的对比度，但是使灰度信息发生了改变。

##  四. 频率滤波器与空域滤波器

滤波的概念在频域更加直观，频域滤波器越窄，其衰减的低频越多，引起的模糊越大，在空间域，这意味着必须使用更大的模板来增加效果。

在低通滤波中，频域滤波器对于噪声的抑制效果更好，而空域滤波器算法简单，处理速度快。

频域高斯低通滤波器：

![](<https://github.com/jzy124/hw5/raw/master/1/test1-gaussian.png>)

空域高斯低通滤波器：

![](<https://github.com/jzy124/hw4/raw/master/pictures/1/test1-gaussian-3.png>)

在高通滤波提取边缘时，空域滤波器锐化更加明显，频域滤波器算法复杂，计算速度慢，非锐化掩蔽效果好，但是laplace算子效果欠佳，提取的边缘非常弱；且有可能会发生振铃效果。

空域laplace算子：

![](<https://github.com/jzy124/hw4/raw/master/pictures/2/test4-Laplace.png>)

频域laplace算子：

![](<https://github.com/jzy124/hw5/raw/master/3/test4-Laplace.png>)

空域非锐化掩蔽：

![](<https://github.com/jzy124/hw4/raw/master/pictures/2/test3-unsharpMasking.png>)

频域非锐化掩蔽：

![](<https://github.com/jzy124/hw5/raw/master/3/test3-unmask.png>)

### 参考资料

+ Digital Image Processing, Third Edition, Rafael C.Gonzalez, Richard E.Woods