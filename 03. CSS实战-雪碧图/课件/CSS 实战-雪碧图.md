# *CSS* 实战-雪碧图



## 什么是雪碧图



雪碧图，源于英语的 *CSS Sprite*，中文翻译有挺多的，例如“精灵图”、“雪碧图”、“图片整合技术”、“图片拼合技术”。

其特点就是将多个小图标和背景图像合并到一张图片上，然后利用 *CSS* 的背景定位来显示需要显示的图片部分。



![img](https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-11-021301.png)



之所以使用雪碧图，是为了减少 *HTTP* 请求数量，加速内容显示。因为每请求一次，就会和服务器建立一次链接，而建立链接是需要额外的时间的。（ *HTTP* 请求涉及网络课程知识 ）



目前，由于可以使用 *CSS3* 来制作字体图标，所以有一部分的场景已经完全可以使用字体图标来解决了。

也出现了好几个字体图标库，例如：

- *iconfont*：*https://www.iconfont.cn/*
- *Font Awesome*：*https://fontawesome.dashgame.com/*

例如淘宝的导航栏左侧的图标就是完全使用图表字体来实现的。

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-11-022449.png" alt="image-20211111102449449" style="zoom:50%;" />



但是这并不意味着雪碧图完全就消失了，某些特殊场景还是需要使用图片的话，雪碧图就仍然好使，例如淘宝、京东页尾的工商信息，就是使用雪碧图制作的。

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-11-022732.png" alt="image-20211111102732022" style="zoom:50%;" />



## 雪碧图关键技术



接下来我们来具体看一下雪碧图的实现。

要使用雪碧图，有两个点很关键：

- 知道每个图标的位置
- 知道 *background-position* 属性



首先第一步我们需要知道图标在整张图里面的位置，例如：

![2018103115313026.png](https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-11-023128.png)

从上面的图片不难看出雪碧图中各个小图标（ *icon* ）在整张雪碧图的起始位置。

例如第一个图标（裙子）在雪碧图的起始位置为 *x : 0 , y : 0*，第二个图标（鞋子）在雪碧图的起始位置为 *x : 0 , y : 50px*，第三个图标（足球）在雪碧图的起始位置为 *x : 0 , y : 100px*，依次类推可以得出各个图片相对于雪碧图的起始位置。

为什么要知道这一点呢？

因为之后我们要通过  *background-position* 来设置背景图的位置。

这里我们首先来复习一下   *background-position* 属性的使用，该属性设置背景图像的起始位置，是一个从 *CSS1* 开始就有的属性

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-11-023958.png" alt="image-20211111103958319" style="zoom:50%;" />



## 雪碧图实战案例



最后，我们来看一个雪碧图的实战案例，利用雪碧图完成一个早期电商的导航栏。

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-11-031535.png" alt="image-20211111111534878" style="zoom:50%;" />



-*EOF*-