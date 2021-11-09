# 原来 *HTML* 还有这些知识



本节课我们主要来看一下 *HTML* 的补充知识。



## 按钮



平时我们在制作页面时，少不了按钮的制作，举几个平时常见的场景：

百度的首页“百度一下”实际上就是一个提交按钮。

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-09-013348.png" alt="image-20211109093348286" style="zoom:50%;" />

再比如当你填写表单的时候，也会涉及到按钮

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-09-013638.png" alt="image-20211109093637574" style="zoom:50%;" />

因此，*HTML* 也为我们提供了按钮的标签。



### 提交表单

仔细想一想，什么时候按钮用得最多？没错，其实就是和表单打交道的时候，表单有一个很重要的场景，那就是提交表单

对应的按钮类型有：

- `<input type="submit" value="提交">`
- `<input type="image" src="" alt="">`



### 重置表单

这个按钮类型目前用得已经不多了，因为没有人会因为某一项填错了把整个表单填写的内容全部重置掉。

但是既然 *HTML* 里面提供了，我们就还是一起来看一下。

- `<input type="reset" value="重置">`



### 普通按钮

如果在表单中，你想用写一个普通的按钮，可以将 *type* 值设置为 *button* 即可。

- `<input type="button" value="普通按钮">`



### *button* 元素

目前来讲，一般推荐使用 *button* 元素来书写按钮，首先该元素在语义上就是一个按钮，其次该元素是不像 *input* 那样是自闭合元素，*button* 元素比 *input* 元素更容易使用样式。你可以在元素内添加 *HTML* 内容（像 *em、strong* 甚至 *img*），以及 *::after* 和 *::before* 伪元素来实现复杂的效果，而 *input* 只支持文本内容。



*button* 的类型。可选值：

- *submit*: 此按钮将表单数据提交给服务器。如果未指定属性，或者属性动态更改为空值或无效值，则此值为默认值。
- *reset*:  此按钮重置所有组件为初始值。
- *button*: 此按钮没有默认行为。它可以有与元素事件相关的客户端脚本，当事件出现时可触发。



## *placeholder*



*placeholder* 属性是 *HTML5* 中的新属性。提供可描述输入字段预期值的提示信息（*hint*），该提示会在输入字段为空时显示，并会在字段获得焦点时消失。*placeholder* 属性适用于的 input 类型有：*text、search、url、telephone、email* 以及 *password*。

应用场景：几乎所有的表单为了更好的用户体验，都会设置 *placeholder* 属性。

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-09-085206.png" alt="image-20211109165205767" style="zoom:50%;" />



## *textarea*



*textarea* 元素定义多行的文本输入控件。

可以通过 *cols* 和 *rows* 属性来规定 *textarea* 的尺寸，不过更好的办法是使用 *CSS* 的 *height* 和 *width* 属性。

所有浏览器都支持 *textarea* 标签。

*textarea* 默认是可以拖动的，可以通过 *resize:none* 来让 *textarea* 不可拖动。



## *contenteditable*



*contenteditable* 属性指定元素内容是否可编辑，当元素中没有设置 *contenteditable* 属性时，元素将从父元素继承。目前所有主流浏览器都支持 *contenteditable* 属性。

例如：

```html
<p contenteditable="true">这是一个可编辑段落。</p>
```

常见的应用场景：

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-09-085030.png" alt="image-20211109165030327" style="zoom:50%;" />



## *link favicon*



在前面我们学习过 *link* 标签，表示引入外部的 *CSS* 代码。那么这个 *link* 就只能引入 *CSS* 代码么？

实际上，*link* 的应用场景挺多的，今天给大家介绍一下关于使用 *link* 引入页面图标。

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-09-021246.png" alt="image-20211109101245949" style="zoom:50%;" />

当我们打开一个页面时，你会发现页面标题的左侧都有自己网站的图标，该图标可以在地址栏中看到，并用于宣传公司或商标。另一方面，它对用户很有用，以便可以在其加书签的站点中快速找到他要单击的 *URL*，这就可以通过 *link* 来引入。

例如：

```html
<link rel="icon" href="https://gw.alipayobjects.com/zos/rmsportal/rlpTLlbMzTNYuZGGCVYM.png" type="image/x-icon">
```

如今，*favicon* 对所有浏览器均具有完全支持，并且该支持还扩展到了其他各种文件类型格式。

根据网站图标的格式，我们需要书写对应的 *type* 属性。

- 对于 *PNG*，您需要使用 *image/png*
- 对于 *GIF*，您需要使用 *image/gif*
- 对于 *JPEG*，您需要使用 *image/gif*
- 对于 *ICO*，您需要使用 *image/x-icon*
- 对于 *SVG*，您需要使用 *image/svg+xml*



## *table*



*table* 表示表格，在最最最早期的时候，人们制作网页布局就采用的 *table* 布局。当然，这已经成为历史了，现在早已不用 *table* 来布局了。*table* 回归了最初设计该元素时所表达的意义，就是表示表格。

```html
<table>
  <thead>
    <tr>
      <th>姓名</th>
      <th>年龄</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>张三</td>
      <td>21</td>
    </tr>
    <tr>
      <td>李四</td>
      <td>19</td>
    </tr>
  </tbody>
</table>
```



## 课后练习



上面介绍了一些零零散散的 *HTML* 知识，下面我们将这些知识串联起来，做一个小练习。

完成下面练习：

<img src="https://xiejie-typora.oss-cn-chengdu.aliyuncs.com/2021-11-09-101830.png" alt="image-20211109181830054" style="zoom:50%;" />

-*EOF*-