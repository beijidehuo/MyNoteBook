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

### 改变特定 id 的样式（ID 选择器）

example

```css
#cat-photo-element {
  background-color: green;
}
```

通过给`html`标签元素添加 id，之后在 css 里面通过`#+id`的形式给具体 id 的标签元素赋值

### 改变标签元素的字体属性

example

```css
h1 {
  font-size: 30px; // 字体大小
  font-family: Sans-serif, Monospace; // 字体属性,定义多个代表指定字体层级，当首选的字体不可用时，自动降级到后面的字体，一次类推
}
```

### html 布局之 padding(内边距),margin(外边距),border(边框)

example

```css
.injected-text {
  margin-bottom: -25px;
  text-align: center;
}

.box {
  border-style: solid; // 边框样式
  border-color: black; // 边框颜色
  border-width: 5px; // 边框
  text-align: center; // 字体对齐方式
}

.yellow-box {
  background-color: yellow;
  padding: 20px 40px 20px 40px; // 内边距，从上开始顺时针方向
}

.red-box {
  background-color: red;
  margin: 20px 40px 20px 40px; // 外边框间距，从上开始顺时针方向
}

.green-box {
  background-color: green;
  margin: 40px 20px 20px 40px;
}
```

- 元素 padding 控制元素里面的内容和 border 之间的间距（可以理解成包围内容的边框大小）
- 元素 margin 控制元素 border 和元素实际所占空间的距离（可以理解成包围整个元素的不边框大小）
- 打开浏览器开发者工具的 style 项目可以清楚的的知道里面具体怎么设置和分配

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
<label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
<label><input type="radio" name="indoor-outdoor"> outdoor</label>
```

- `input`标签元素的**type**属性设置为 radio
- 所有的单选按钮都需要嵌套进`label`标签元素中,这个是与 text 的输入框不同的
- 所有关联的单选按钮要具有相同的**name**元素可以实现单选操作
- 添加`checked`属性可以选中该项目

#### 创建多选按钮

example

```html
<label><input type="checkbox" name="personality" checked> Loving</label>
<label><input type="checkbox" name="personality"> hating</label>
<label><input type="checkbox" name="personality"> doing</label>
```

- `input`标签元素的**type**属性设置为 checkbox
- 同样需要嵌套进入`label`元素中
- **name**应该表示同一属性,在提交表单的时候有用
- 添加`checked`属性可以选中该项目

## CSS 样式执行优先级

example

```html
<style>
  body {
    background-color: black;
    font-family: Monospace;
    color: green;
  }
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink;  // 如果在写成  color: pink !important;则最总结果为pink
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 id="orange-text" class="pink-text blue-text" style="color: white">Hello World!</h1>
```

以上代码最终显示成粉色

- 在**类选择器样式冲突**中，浏览器读取 css 样式的顺序是从上到下，这意味着，在发生冲突时，浏览器会使用最后的 css 声明，所有`pink-text`的申明被`blue-text`覆盖
- 在**id 样式声明和类选择器冲突**中，由于 id 声明不受类选择器样式的顺序影响，id 声明具有更高的优先级，故即使 id 声明在两个类选择器的上面，其样式也被覆盖成了 orange
- 最后由于内联样式比其他声明方式的优先级更高，最终元素呈现的效果为白色
- 如果在样式后面添加 important，则该样式拥有最高优先级，万不得已不建议这么用，会影响其他样式的显示

## css 中颜色的设置

### 采用 hex code(十六进制编码)的形式来选择颜色

example

```css
<style>
  body {
    background-color: #FFFFFF;
  }
</style>
```

1. 0 是 hex code 中最小的一个，代表颜色完成丢失
2. F 是 hex code 中最大的一个，代表颜色的最大值
3. 可以采取`#F00`这种仅仅代表 rgb 三种颜色的简短形式

### 采用 rgb 的形式来选择颜色

example

```css
<style>
  body {
    background-color: rgb(0, 0, 0) ;
  }
</style>
```

- rgb 颜色选择器中每个值可以用 0 到 255 这 256 个值去填充，就是 16\*16 的效果，所有这里就用一个十进制数字代表两位 hex code 的颜色，他们能选择的颜色的总数是相同的
