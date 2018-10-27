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
<img src="https://www.your-image-source.com/your-image.jpg" alt="图片没有加载">
```

`img`元素时自关闭元素，不需要结束标记，其中之后的`alt`元素在图片记载失败的时候会显示出来，可以用于异常时候的提示

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

### 列表添加，包括有序列表和无序列表

#### 分项无序列表

example

```html
<ul>  // unordered list
  <li>milk</li>  // list
  <li>cheese</li>
</ul>
```

其中`ul`元素列表代表 unordered list 的意思，`li`html 标签元素代表其中的子项

#### 有序列表

example

```html
<ol> // ordered list
  <li>Garfield</li> // list
  <li>Sylvester</li>
</ol>
```

添加了`ol`有序列表的 html 标签后，在添加`li`列表元素标签里面的元素会自动排序

### 获取用户输入`input`

#### 通过文本输入框来获取用户输入

example

```html
<input type="text" placeholder="预设文本,当用户没有任何输入时,可以给与用户相关提示">
```

其中`input`元素也是自关闭的

#### 通过表单元素获取用户的输入并提交到服务器

example

```html
<form action="/submit-cat-photo">
  <input type="text" placeholder="cat photo URL" required>
  <button type="submit">Submit</button>
</form>
```

- 其中`form`html 元素中的 action 操作代表制定表单提交到服务器的地址
- 也可以定制一个类型为 submit 的按钮元素来执行 enter 的操作
- 其中 required 属性代表此项为必填项,用户只有填写了这一项之后才能提交表单,并且这个属性在 **safari** 浏览器中**不起作用**

#### 创建单选按钮

example

```html
<label><input type="radio" name="indoor-outdoor"> Indoor</label>
<label><input type="radio" name="indoor-outdoor"> outdoor</label>
```

- `input`标签元素的**type**属性设置为 radio
- 所有的单选按钮都需要嵌套进`label`标签元素中,这个是与 text 的输入框不同的
- 所有关联的单选按钮要具有相同的**name**元素可以实现单选操作

#### 创建多选按钮

example

```html
<label><input type="checkbox" name="personality"> Loving</label>
<label><input type="checkbox" name="personality"> hating</label>
<label><input type="checkbox" name="personality"> doing</label>
```

- `input`标签元素的**type**属性设置为 checkbox
- 同样需要嵌套进入`label`元素中
- **name**应该表示同一属性,在提交表单的时候有用
