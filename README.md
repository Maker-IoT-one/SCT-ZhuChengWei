# SCT-ZhuChengWei
## 20231214-SCT-朱成伟-算法

**处理异常图片**
    dir_lit = os.listdir('./work/cat_12_train/')for list in dir_lit:    img_path=os.path.join('./work/cat_12_train/',list)    img=Image.open(img_path)    if img.mode != 'RGB':        img = img.convert('RGB')        img.save(img_path)        print(img_path)dir_lit = os.listdir('./work/cat_12_test/')for list in dir_lit:    img_path=os.path.join('./work/cat_12_test/',list)    img=Image.open(img_path)    if img.mode != 'RGB':        img = img.convert('RGB')        img.save(img_path)        print(img_path)

整理成paddlex数据格式
划分训练集验证集
数据增强

##卷积神经网络
CNN，卷积神经网络的基本结构大致包括：卷积层、激活函数、池化层、全连接层、输出层。
卷积神经网络可以处理图像以及一切可以转化成类似图像结构的数据。相比传统算法和其它神经网络，卷积神经网络能够高效处理图片的二维局部信息，提取图片特征，进行图像分类。通过海量带标签数据输入，用梯度下降和误差反向传播的方法训练模型。
卷积层
    这一层就是卷积神经网络最重要的一个层次，也是“卷积神经网络”的名字来源。卷积神经网路中每层卷积层由若干卷积单元组成，每个卷积单元的参数都是通过反向传播算法优化得到的
    在这个卷积层，有两个关键操作：
        局部关联。每个神经元看做一个滤波器(filter)。
        窗口(receptive field)滑动， filter对局部数据计算。

    卷积运算的目的是提取输入的不同特征，某些卷积层可能只能提取一些低级的特征如边缘、线条和角等层级，更多层的网路能从低级特征中迭代提取更复杂的特征。
    卷积层的作用是对输入数据进行卷积操作，也可以理解为滤波过程，一个卷积核就是一个窗口滤波器，在网络训练过程中，使用自定义大小的卷积核作为一个滑动窗口对输入数据进行卷积。
     卷积过程实质上就是两个矩阵做乘法，在卷积过程后，原始输入矩阵会有一定程度的缩小，比如自定义卷积核大小为3*3，步长为1时，矩阵长宽会缩小2，所以在一些应用场合下，为了保持输入矩阵的大小，我们在卷积操作前需要对数据进行扩充，常见的扩充方法为0填充方式。
    卷积层中还有两个重要的参数，分别是偏置和激活（独立层，但一般将激活层和卷积层放在一块）。
     偏置向量的作用是对卷积后的数据进行简单线性的加法，就是卷积后的数据加上偏置向量中的数据，然后为了增加网络的一个非线性能力，需要对数据进行激活操作，在神经元中，就是将没有的数据率除掉，而有用的数据则可以输入神经元，让人做出反应。

