# 分享一些关于改进Yolov5的tricks以及实验结果
# Share some tricks of improving Yolov5  and experiment results

## 《Yolov5实验数据全部开源》

分享一些改进YOLOv5的技巧，不同的数据集效果肯定是不同的。有算力的话还是要多尝试

-----

有关代码怎么使用我就不过多介绍了，大家可以去看我的博文，或者官方的文档，我在这统一做一个汇总

1.[手把手带你调参Yolo v5 (v6.1)（一）](https://blog.csdn.net/weixin_43694096/article/details/124378167)🌟强烈推荐

2.[手把手带你调参Yolo v5 (v6.1)（二）](https://blog.csdn.net/weixin_43694096/article/details/124411509?spm=1001.2014.3001.5502)🚀

3.[如何快速使用自己的数据集训练Yolov5模型](https://blog.csdn.net/weixin_43694096/article/details/124457787)

4.[手把手带你Yolov5 (v6.1)添加注意力机制(一)（并附上30多种顶会Attention原理图）](https://blog.csdn.net/weixin_43694096/article/details/124443059?spm=1001.2014.3001.5502)🌟

5.[手把手带你Yolov5 (v6.1)添加注意力机制(二)（在C3模块中加入注意力机制）](https://blog.csdn.net/weixin_43694096/article/details/124695537)

6.[Yolov5如何更换激活函数？](https://blog.csdn.net/weixin_43694096/article/details/124413941?spm=1001.2014.3001.5502)

7.[Yolov5 (v6.1)数据增强方式解析](https://blog.csdn.net/weixin_43694096/article/details/124741952?spm=1001.2014.3001.5502)

8.[Yolov5更换上采样方式( 最近邻 / 双线性 / 双立方 / 三线性 / 转置卷积)](https://blog.csdn.net/weixin_43694096/article/details/125416120)🍀

9.[Yolov5如何更换EIOU / alpha IOU / SIoU？](https://blog.csdn.net/weixin_43694096/article/details/124902685)🍀

10.[Yolov5更换主干网络之《旷视轻量化卷积神经网络ShuffleNetv2》](https://blog.csdn.net/weixin_43694096/article/details/126109839?spm=1001.2014.3001.5501)

11.[YOLOv5应用轻量级通用上采样算子CARAFE](https://blog.csdn.net/weixin_43694096/article/details/126148795)

12.持续更新中

------

本人所用数据集是网络上购买的黑夜行人数据集（训练集9424，验证集2357，测试集3249），数据集只包含一个Person类别

这里简单展示一些数据集的内容



![image](https://user-images.githubusercontent.com/58406737/180331142-1c20eb86-d798-41ea-8cdd-dcc20dc3bdf3.png)






------

这里我也免费分享这个数据集，数据集已经划分成了Yolo的格式，大家下载后直接可以使用。

>百度网盘
>
>链接：https://pan.baidu.com/s/1bD88KAps5jjliI-ElYLvDg?pwd=3mh0 
>提取码：3mh0




------

实验结果

| Model             | epoch | freeze | multi_scale | mAP 0.5(val)  | Parameters(M) | GFLOPs |
| ----------------- | ----- | ------ | ----------- | --------- | ------------- | ------ |
| Yolov5s           | 300   | 0      | false       | **0.953** | Nan           | Nan    |
| Yolov5s           | 120   | 8      | false       | 0.936     | Nan           | Nan    |
| Yolov5s_SE        | 120   | 7      | false       | 0.874     | Nan           | Nan    |
| Yolov5s_ECA       | 200   | 7      | false       | 0.937     | Nan           | Nan    |
| Yolov5s_CBAM      | 200   | 7      | **true**    | 0.882     | Nan           | Nan    |
| Yolov5s_BiFPN     | 200   | 7      | false       | 0.935     | Nan           | Nan    |
| Yolov5s_BiFPN_ECA | 200   | 0      | false       | 0.951     | Nan           | Nan    |

------
🍀2022年6月24日 添加了Inception_Conv模块，替换了第一层的6x6卷积，新的模块比6x6卷积参数量减少了一半

还有一些其他tircks的实验结果我正在整理中，后续我会更新在Github的


