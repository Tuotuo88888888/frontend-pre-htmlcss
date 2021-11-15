# *CSS* 实战-美化单选框前置知识



## 前置知识

首先我们来介绍一下前置知识，一会儿会用到  + 和 ~，这是 *CSS3* 新增了许多实用的选择器。

这两个选择器都可以称之为兄弟选择器，但是在选择上面有一些具体的区别。

首先我们来看 ~ 选择器，该选择会选择某元素**后**所有同级的指定元素，强调的是**所有**的同级元素。

例如：

```html
<p>这是段落标签</p>
<p>这是段落标签</p>
<p>这是段落标签</p>
<h3 class="h3">这是标题标签</h3>
<p>这是段落标签</p>
<p>这是段落标签</p>
<p>这是段落标签</p>
<h3>这是标题标签</h3>
<p>这是段落标签</p>
<p>这是段落标签</p>
<p>这是段落标签</p>
```

```css
.h3~p {
  color: red;
}
```

效果如下：

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-01-073449.png" alt="image-20211101153448993" style="zoom:50%;" />

接下来来看 + 选择器，该选择器则表示某元素后相邻的兄弟元素，也就是紧挨着的，是单个的。

例如：

```css
.h3+p {
  color: red;
}
```

效果如下：

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-01-073608.png" alt="image-20211101153607813" style="zoom:50%;" />



## 美化单选框原理



在正式开始实战之前，我们先来看一下美化单选框的原理。

这里首先就要复习一下关于 *label* 标签的使用了。



*label* 标签主要用于和 *input* 标签进行关联。

将一个 \<*label*> 和一个 \<*input*> 元素相关联主要有这些优点：

- 标签文本不仅与其相应的文本输入元素在视觉上相关联，程序中也是如此。 这意味着，当用户聚焦到这个表单输入元素时，屏幕阅读器可以读出标签，让使用辅助技术的用户更容易理解应输入什么数据。

- 你可以点击关联的标签来聚焦或者激活这个输入元素，就像直接点击输入元素一样。这扩大了元素的可点击区域，让包括使用触屏设备在内的用户更容易激活这个元素。



将一个 \<*label*> 和一个 \<*input*> 元素匹配在一起，你需要给 \<*input*> 一个 *id* 属性。而 \<*label*> 需要一个 *for* 属性，其值和  \<*input*> 的 *id* 一样。例如：

```html
<label for="male">男</label>
<input type="radio" name="gender" id="male">
<label for="female">女</label>
<input type="radio" name="gender" id="female">
```



另外，也可以将 \<*input*> 直接放在 \<*label*> 里，此时则不需要 *for* 和 *id* 属性，因为关联已隐含存在

```html
<label>男<input type="radio" name="gender" id="male"></label>
<label>女<input type="radio" name="gender" id="female"></label>
```



而美化单选框的原理就在于此。隐藏原本丑陋的单选框：

```css
input[type="radio"]{
  display : none;
}
```

但是一旦单选框隐藏了，用户怎么点击单选框呢？

没关系，我们让单选框和 *label* 相关联，这样用户就可以通过点击 *label* 从而点击到单选框。

而针对 *label* 标签，我们就可以做各种各样的样式优化。



-*EOF*-

