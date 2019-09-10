# CNN_Denoiser_pytorch

Pytorch框架下采用CNN去除高斯噪声（盲去噪，未像DnCNN事先给出相对固定的信噪比）,尝试采用类似RPN+残差网络的结构。

具体模型结构的搭建：

1.模型输入大小设定主要是由于此模型最初为了应对一个小型比赛，因此输入大小采用了竞赛中的图像大小。

2.网络结构靠感觉居多,未进行对比实验。

3.网络的部分卷积层的设定有意背离目前一些分类网络的设定上:

    (1)S2的Conv或者Pooling放在了靠后位置，并采用大kernel，希望能够尽可能保留一些细节；
    
    (2)另外也是处于验证的目的采用了Pixel Shuffle————发现貌似比bilinear显存占用少一些；
    
    (3)Batchsize较小，尝试GroupNorm；
    
    (3)数据集为超分辨率数据集经过多次缩放和裁剪得到————多尺度训练；
    
    (4)去噪PSNR范围限定在在10-40；
   
4.整体思路参照Beyond A Gaussian Denoiser论文(DnCNN)————具体网络结构尝试大换血；

5.数据集采用DIV2K数据集；

6.个人GPU算力及显存大小的限制，实际条件不允许尝试更深的网络

部分去噪效果：

!(https://github.com/M0reDr1nk/CNN_Denoiser_pytorch/blob/master/example_result/1.png?raw=true)


如果对您可以起到任何作用或者帮助请回复或者联系我，我会很高兴。
或者您发现了一些问题或建议，请留言，谢谢。

另：如有人有能力或者资源愿意合作完善，也请联系我，十分感谢。
