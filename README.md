# CNN_Denoiser_pytorch

Pytorch框架下采用CNN去除高斯噪声（盲去噪，未像DnCNN事先给出相对固定的信噪比）,采用类似RPN+残差网络的结构。
具体模型结构的搭建：
1.模型输入大小设定主要是由于此模型最初为了应对一个小型比赛，因此输入大小采用了竞赛中的图像大小。
2.网络结构靠感觉居多,未进行对比实验。
3.网络的部分卷积层的设定有意背离目前一些分类网络的设定上:
    (1)S2的Conv或者Pooling放在了靠后位置，并采用大kernel，希望能够尽可能保留一些细节；
    (2)另外也是处于验证的目的采用了Pixel Shuffle————发现貌似比bilinear显存占用少一些；
    (3)数据集为超分辨率数据集经过多次缩放和裁剪得到————多尺度训练；
4.整体思路参照Beyond A Gaussian Denoiser论文(DnCNN)————具体网络结构尝试大换血；

如果对您可以起到任何作用或者帮助请回复或者联系我，我会很高兴—————当然，DO WHAT EVER YOU WANT！
或者您发现了一些问题或建议，请留言，谢谢。

另：如有人愿意合作完善，也请联系我，谢谢。