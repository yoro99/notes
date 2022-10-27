# 基于脑机接口的意识检测系统研究

* EEG：有时间分辨率，但是空间分辨率差，不能定位信号源，数据集较多

  * me：关于通道，一个通道获得一个eeg，可以检测不同位置的信息源（距离越近捕获的波形越明显），得到比较全面的数据

  ![](https://mdgraph-1301162508.cos.ap-shanghai.myqcloud.com/2022/image-20221027155717931.png)

  * 滤波可以获得稳定波形

  * 是不是先前的预调整就相当于定位？

  * **什么是前向问题？**

    假设在大脑和头部模型中有活动来源，以计算将在头皮上测量到的电势的理论值。

    **什么是反问题？**

    在更改信号源模型的参数的同时重复计算，以使头皮上测得的电位数据与通过解决正向问题获得的理论值之间的误差最小

    重复正向问题和逆向问题来计算信号源估计

* MRI（磁共振成像）提供了大脑的图谱 - 它如何在一个固定的时刻观察。静态图，

* MEG在需要时间分辨率时是更优选

* fMRI：如果大脑的一部分与其他部位相比有更多的含氧血液，那么这个大脑区域可能更活跃。这被称为血氧水平依赖性反应（也称为BOLD）
  * 缺点是时间分辨率。由于血流需要几秒钟的变化，并且实际记录受到计算因素的限制，因此数据收集速度变慢；会破坏记录新反应的准确性，但确实提供了全方位的大脑反应
  * **无论脑磁图还是脑电图都来自于高级视觉皮层，而脑磁图还显示了来自低水平视觉皮层的成分**
* **fNIRS（Functional Near-Infrared Spectroscopy ，f就代表有时间属性？）**：过放置在我们大脑头上的光源和探测器进行局部血流信号的测量；时间分辨率比fMRI技术快，空间分辨率比EEG技术大；便携性和伪影干扰小
  
  * 数据集地址[hubandad/fNIRS-Dataset: Public fNIRS dataset (github.com)](https://github.com/hubandad/fNIRS-Dataset)
* <img src="https://mdgraph-1301162508.cos.ap-shanghai.myqcloud.com/2022/20221027153111.png" style="zoom:50%;" />

<img src="https://mdgraph-1301162508.cos.ap-shanghai.myqcloud.com/2022/image-20221027153037088.png" style="zoom:50%;" />

* 多模态研究中，EEG-fNIRS、EEG-fMRI、fNIRS-fMRI以及EEG超扫描和fNIRS超扫描也是相应的使用
  * 不知道能不能使用多模态做类似**Image Captioning** 的工作



* 实验对象：植物状态（VS）患者，最小意识状态（MCS）患者

* 诱发动作电位 (ERP)

* MRI一般指核磁共振成像

  * 对SSVEP信号的处理

* 检测

  * 卡方检测：患者是否能够完成实验任务以及长时间保持注意力的重要指标
  * 近似熵：前提是患者脑电信号较弱，所以近似熵越高，EEG包含P300可能性越高
  * ERP波形：会在刺激后出现一个正的波峰，判断患者是否遵循任务
  * 不漏诊：真阳性率（true positive rate, TPR）；不误诊：真阴性率（true negative rate,TNR）

* 设计的思路：肯定正常人听从了命令，感觉留一个信号，后面告知闪烁次数

  <img src="https://mdgraph-1301162508.cos.ap-shanghai.myqcloud.com/2022/20221026204617.png" style="zoom:50%;" />

* 通道数会不会有点少？