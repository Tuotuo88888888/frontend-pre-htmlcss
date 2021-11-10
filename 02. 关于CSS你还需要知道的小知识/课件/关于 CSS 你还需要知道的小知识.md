# 关于 *CSS* 你还需要知道的小知识



## *CSS* 重置



### 为什么需要重置 *CSS*



*CSS* 重置样式主要是为了让各个浏览器的 *CSS* 样式有一个统一的基准，由于不同的浏览器对有些标签的默认值是不同的，如果不对 *CSS* 初始化往往会出现浏览器之间的页面显示存在差异，因此为了使 *HTML* 元素样式在跨浏览器时有一致性的显示效果，我们需要进行样式初始化。



### 如何进行样式初始化



最生猛的方法那就是直接使用通配符来进行操作，例如常见的：

```css
*{
  margin: 0;
  padding : 0;
}
```

上面的 `*` 号代表将所有的元素的 *margin* 和 *padding* 设置为 *0*，也被称之为全局 *Reset*。

在平时做练习的时候，我们这样重置没有问题，但是如果是实际项目开发，是不推荐这样重置化的，因为存在缓慢和低效率的问题。



那么在真实的开发中，我们应该如何进行初始化样式呢？

常见的重置文件有：

- *reset.css*
- *normailze.css*



其中 *reset.css* 相对“暴力”，不管你有没有用，统统重置成一样的效果，且影响的范围很大，讲求跨浏览器的一致性。*normailze.css* 相对“平和”，注重通用的方案，重置掉该重置的样式，保留有用的 *user agent* 样式，同时进行一些 *bug* 的修复，这点是  *reset.css*  所缺乏的。

下面这篇文章讨论了 *normailze.css* 相比 *reset.css* 的特点以及优势：

> 扩展阅读：*https://jerryzou.com/posts/aboutNormalizeCss/*



### 如何引入 *normailze.css*

前期推荐大家直接使用 *CDN* 的方式来引入，地址如下：

> *Bootcdn*：*https://www.bootcdn.cn/normalize/*



## *letter-spacing*

*letter-spacing* 属性增加或减少字符间的空白。

能够设置的值如下：

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-10-062518.png" alt="image-20211110142517898" style="zoom:50%;" />



## *object-fit*

*object-fit* 是 *CSS3* 新增的属性，指定元素的内容应该如何去适应指定容器的高度与宽度。该属性一般用于 *img* 和 *video* 标签，一般可以对这些元素进行保留原始比例的剪切、缩放或者直接进行拉伸等。

```css
object-fit: fill|contain|cover|scale-down|none|initial|inherit;
```

常用的属性值其实就 *2* 个：

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-10-062848.png" alt="image-20211110142847844" style="zoom:50%;" />



## 透明通道

*RGBA* 是 *CSS3* 新引入的特性。在此之前，我们设置颜色可以通过 *RGB* 来指定颜色，那么后面添加了一个 *A* 是什么呢？*A* 的全称为 *Alpha*，也就是透明通道。透明度取值范围任意，但是渲染范围为 *0～1*，也就是小于 *0* 的透明度会当作 *0* 来渲染，大于 *1* 的透明度会当作 *1* 渲染。

下面的语法都是合法的：

```css
rgba(255, 0, 0, .9)
rgba(255, 0, 0, 999)
rgba(255, 0, 0, -999)
```

在现代浏览器中，对 *RGB* 颜色的使用已经变得无比自由。例如 *RGB* 和 *RGBA* 函数的语法互通：

```css
rgb(0, 0, 0, 1)
rgba(0, 0, 0)
```

透明度可以使用百分比来表示：

```css
rgb(0, 0, 0, 100%)
```

*RGB* 函数中的逗号可以省略：

```css
rgb(255 0 0)
```

现代浏览器还支持全新的空格加斜杠语法，例如：

```css
rgb(255 0 153 / 1)
rgba(51 170 51 / 0.4)
rgb(255 0 153 / 100%)
rgba(51 170 51 / 40%)
```



当然，对于多数同学来讲，有一个疑问就是 *RGBA* 设置透明和 *opacity* 设置透明有啥区别？

其实最大的不同就是 *opacity* 作用于元素，以及元素内的所有内容的透明度，而 *RGBA* 只作用于元素的颜色或其背景色，也就是说设置 *RGBA* 透明的元素的子元素不会继承透明效果。



-*EOF*-