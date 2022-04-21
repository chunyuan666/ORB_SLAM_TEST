# Tracking线程
## 流程图
![avatar](https://img-blog.csdn.net/20170718173524799?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2hpc2h1aWRleXU=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
## localMapping线程
![avatar](https://img-blog.csdnimg.cn/20210514104933257.png)
![avatar](https://img-blog.csdn.net/20180816203845438?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zODM1ODQzNQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
>  `Tracking`线程 只是判断当前帧是否需要加入关键帧，并没有真的加入地图， 因为`Tracking`线程的主要功能是局部定位， 而处理地图中的关键帧，地图点，包括如何加入，如何删除的工作是在`LocalMapping`线程完成的  

``` C++
LocalMapping::Run()
```
SetAcceptKeyFrames(false);