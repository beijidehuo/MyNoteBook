# 基于 HTML 的 css 样式

## 直接在 html 标签开始元素后跟 style（内联样式）

example

```html
<h2 style="color:blue">直接在html元素后跟样式</h2>
```

## 更加便于维护的样式————层叠样式表(Cascading Style Sheets)

### 改变所有特定 html 标签元素的样式（元素选择器）

example

```html
<style>
  选择器 {属性名称: 属性值;}
  h2 {color: red;}
</style>
```

直接通过申明`h2`标签元素来对所有 h2 标签元素进行样式申明

### 改变特定类别的样式(类选择器)

example

```html
<style>
  .blue-text {
    color: blue;
  }
</style>
```

通过添加一个`.+cssClassName`这种方式申明了一个 blut-text 的类样式，之后在 html 标签后面直接引用即可，这种类样式可以应用在多个 html 标签元素中。

### 改变标签元素的字体属性

example

```html
h1 {
  font-size: 30px; // 字体大小
  font-family: Sans-serif,Monospace; // 字体属性,定义多个代表指定字体层级，当首选的字体不可用时，自动降级到后面的字体，一次类推
}
```

### 通过 link 标签引入外部样式

example

```html
<link href="https://fonts.gdgdocs.org/css?family=Lobster" rel="stylesheet" type="text/css">
```

其中 link 元素不像其他 html 元素一样需要结束标记

### 引入图片元素

example

```html
<img src="https://www.your-image-source.com/your-image.jpg">
```

`img`元素时自关闭元素，不需要结束标记

### 通过 css 控制元素的大小、边界、以及间距等

example

```html
<style>
  .larger-image {
    width: 500px; // 标签元素的宽
    height: 39px; // 标签元素的高
    border-color: red; // 边框颜色
    border-width: 5px; // 边框宽度
    border-style: solid; // 边框样式
    border-radius: 10px; // 边框半径，也就是圆角属性设置也可以设置成百分比`50%`就可以把一个边框样式设置成圆形
  }
</style>
```

### 通过 anchor 锚点元素实现外部链接跳转和内部导航

example

```html
<p>Here's a <a href="http://freecodecamp.cn"> link to FreeCodeCamp中文社区 </a> for you to follow.</p>
```

其中可以通过将 herf 的值设置成#号使得 anchor 元素变成固定链接

```html
<p>Click here for <a href="#">cat photos</a>.</p>
```

可以通过把其他 html 元素嵌套 nesting 进 anchor 元素使得其变成一个链接
example

```html
<a href="#"><img src="/images/relaxing-cat.jpg"></a>
```

上述方式可以使图片变成一个链接
