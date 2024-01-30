<header>

# CSS样式

</header>

## 文本颜色

<h2 style="color: blue;">CatPhotoApp</h2>

十六进制编码颜色 
道奇蓝：#1E90FF
绿色：#00FF00
橙色：#FFA500
红色：#FF0000
互补色
红色（#FF0000）和蓝绿色 (#00FFFF)
绿色（#00FF00）和品红色（#FF00FF）
蓝色（#0000FF）和黄色（#FFFF00）
RGB
* White is rgb(255,255,255)
* Black is rgb(0,0,0)
* Red is rgb(255,0,0)
* Green is rgb(0,255,0)
* Blue is rgb(0,0,255)

hsl（色相，饱和度，亮度）


## 字体大小
h1 {
font-size: 30px;
}

## 字体
h2 {
font-family: sans-serif;
}

## 谷歌字体https://fonts.google.com/

要引入 Google Font，你需要从 Google Fonts 上复制字体的 URL，并粘贴到代码编辑器顶部，即放到 style 标签之前。
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">

## 使用元素选择器来设置元素的样式

<style>
h2 {
color: red;
}</style>
让所有 h2 元素都变成红色

## 使用 class 选择器设置多个元素的样式

<style>
  .red-text {
    color: red;
  }
</style>
再将class="red-text"添加到相应元素上。


## 设置元素的 id

<h2 id="cat-photo-app">
id 属性应是唯一的，不要给多个元素设置相同的 id。

## 使用 id 属性来设定元素的样式

#cat-photo-element {
background-color: green;
}

## 使用属性选择器来设置元素的样式

[type='radio'] {
margin: 20px 0px 20px 0px;}
会改变所有 type 为 radio 的元素的外边距。

## Important样式

color: red !important;

## 样式中的优先级

Important>内联样式>Id选择器>Class选择器>继承样式

## 在元素周围添加边框

CSS 边框具有 style、color、width 属性。
假如我们要将一个 HTML 元素边框设置为 5px 的红色实线边框，我们可以这样做：
<style>
.thin-red-border {
border-color: red;
border-width: 5px;
border-style: solid;
}</style>
圆角边框：border-radius:10px；
圆形图片：border-radius: 50%;

## 给 div 元素添加背景色

.green-background {
background-color: green;}

## 内边距 padding、外边距 margin 、边框 border        

padding 用来控制着元素内容与 border 之间的空隙大小。
外边距 margin 用来控制元素的边框与其他元素之间的 border 距离。如果你把元素的 margin 设置为负值，元素会变得占用更多空间。
CSS 允许你使用 padding-top、padding-right、padding-bottom、padding-left 属性来设置四个不同方向的 padding 值。
.red-box {
    background-color: crimson;
    color: #fff;
    padding-top: 40px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 40px;
  }
## 使用顺时针标记指定元素的外边距

margin: 10px 20px 10px 20px;
这四个值按顺时针排序：上、右、下、左，并且设置的效果等同于分别声明每一个方向的外边距值。

## 自定义CSS变量

创建：--penguin-skin: gray;
使用：background: var(--penguin-skin);
设置备用值：background: var(--penguin-skin, black);
继承：CSS 变量定义在 :root 元素内，这样就可被所有选择器继承。
:root {
--penguin-belly=pink;
  }

## 更改元素的相对位置

下面的例子展示了段落向上偏移 10px：
p {
position: relative;
bottom: 10px;
}
position:absolute;绝对定位的参照物是元素的父元素
position:fixed;固定定位的参照物是浏览器的窗口,元素不会随着屏幕滚动而移动

## 使用 float 属性将元素左浮动或右浮动

float:left;
float:right;

## 使用 z-index 属性更改重叠元素的位置

z-index 的取值是整数，数值大的元素会叠放到数值小的元素上面。

## 使用 margin 属性将元素水平居中

margin:auto;

## 线性渐变

background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);
第一个参数指定了颜色过渡的方向——它的值是角度，90deg 表示垂直渐变（从左到右），45deg 表示沿对角线渐变（从左下方到右上方）。 其他参数指定了渐变颜色的顺序：
例如：background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));

## 条纹

background: repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    );

## 通过添加细微图案作为背景图像来创建纹理

background: url("https://cdn-media-1.freecodecamp.org/imgr/MJAkxbh.png");

## 使用 CSS Transform scale 属性可以更改元素的大小

p {
transform: scale(2);
}

## 使用CSS Transform scale 属性在悬停时缩放元素

p:hover {
transform: scale(1.1);
}

## 使用 CSS Transform skex 属性沿X轴倾斜元素
p {
transform: skewX(-32deg);
}

## CSS 的关键帧和动画
#rect {
    animation-name: rainbow;
    animation-duration: 4s;
  }

  @keyframes rainbow {
    0% {
      background-color: blue;
    }
    50% {
      background-color: green;
    }
    100% {
      background-color: yellow;
    }
  }

## 使用CSS动画更改按钮的悬停状态
<style>
  button {
    border-radius: 5px;
    color: white;
    background-color: #0F5897;
    padding: 5px 10px 8px 10px;
  }

  button:hover {
    animation-name: background-color;
    animation-duration: 500ms;
animation-fill-mode: forwards; 用户把鼠标悬停在按钮上时，按钮保持高亮。
  }
 @keyframes background-color {
    100% {
      background-color: #4791d0;
      }
      
</style>

<button>Register</button>

## 使用 CSS 动画创建动画
<style>
  div {
    height: 40px;
    width: 70%;
    background: black;
    margin: 50px auto;
    border-radius: 5px;
    position: relative;
  }

 #rect {
  animation-name: rainbow;
  animation-duration: 4s;
}

@keyframes rainbow {
  0% {
    background-color: blue;
    top: 0px;
    left:0px;
  }
  50% {
    background-color: green;
    top: 25px;
    left: 25px;
  }
  100% {
    background-color: yellow;
    top: 50px;
    left:-25px;
  }
}
</style>

<div id="rect"></div>

## 通过从左到右淡化元素来创建视觉方向
@keyframes fade {
    50% {
      left: 60%;
      opacity: 0.1;
    }

## 使用无限的动画计数制作永不停止的动画
animation-iteration-count: infinite;

## 使用关键字更改动画定时器
animation-timing-function:ease; 默认值是 ease，动画以低速开始，然后加快，在结束前变慢。
animation-timing-function:ease-out; 动画以高速开始，以低速结束。
animation-timing-function:ease-in; 动画以低速开始，以高速结束。
animation-timing-function:linear; 动画从头到尾的速度是相同的。


# Flexbox

## 使用 display: flex; 定位两个盒子
使用 flex-direction 属性创建一个行
{display: flex;
flex-direction:row;}
row,row-reverse,column,column-reverse

## 使用 justify-content 属性对齐元素-如何沿主轴线排放 flex 项目
justify-content: center; 即 flex 子元素在 flex 容器中居中排列。
* flex-start：从 flex 容器的起始位置开始排列项目。 对行来说是把项目移至左边， 对于列是把项目移至顶部。 如未设置 justify-content 的值，那么这就是默认值。
* flex-end：从 flex 容器的终止位置开始排列项目。 对行来说是把项目移至右边， 对于列是把项目移至底部。
* space-between：项目间保留一定间距地沿主轴居中排列。 第一个和最后一个项目被放置在容器边沿。 例如，在行中第一个项目会紧贴着容器左边，最后一个项目会紧贴着容器右边，然后其他项目均匀排布。
* space-around：与space-between相似，但头尾两个项目不会紧贴容器边缘，所有项目之间的空间均匀排布。
* space-evenly：在 flex 项目之间均匀分配空间，在 flex 容器的任一端都有一个完整的空间。

## 使用 align-items 属性对齐元素
CSS 中的 align-items 属性用来定义 flex 子元素沿交叉轴的对齐方式。
* flex-start：从 flex 容器的起始位置开始对齐项目。 对行来说，把项目移至容器顶部； 对列来说，是把项目移至容器左边。
* flex-end：从 flex 容器的终止位置开始对齐项目。 对行来说，把项目移至容器底部； 对列来说，把项目移至容器右边。
* center：把项目居中放置。 对行来说，垂直居中（项目距离顶部和底部的距离相等）； 对列来说，水平居中（项目距离左边和右边的距离相等）。
* stretch：拉伸项目，填满 flex 容器。 例如，排成行的项目从容器顶部拉伸到底部。 如未设置align-items的值，那么这就是默认值。
* baseline：沿基线对齐。 基线是文本相关的概念，可以认为它是字母排列的下端基准线。

## 使用 flex-wrap 属性包裹一行或一列-使项目换行展示
* nowrap：默认值，不换行。
* wrap：如果排列以行为基准，就将行从上往下排列；如果排列以列为基准，就将列从左往右排列。
* wrap-reverse：如果排列以行为基准，就将行从下往上排列；如果排列以列为基准，就将列从右往左排列。

## 使用 flex-shrink 属性定义 flex 子元素的收缩规则

## 使用 flex-grow 属性定义 flex 子元素的增长系数

## 使用 flex-basis 属性设置元素的初始大小

## 使用 flex 短方法属性
属性的默认设置是 flex: 0 1 auto;
flex-grow、flex-shrink 、flex-basis

## 使用 order 属性重新排列子元素

## 使用 align-self 属性设置对齐方式


# CSS网格

## 创建网格
display:grid;

## 使用 grid-template-columns 添加多列
.container {
display: grid;
grid-template-columns: 50px 50px;}

## 使用 grid-template-rows 添加多行

## 使用 CSS 网格单位来更改列和行的大小
fr：设置列或行占剩余空间的比例，
auto：设置列宽或行高自动等于它的内容的宽度或高度，
%：将列或行调整为它的容器宽度或高度的百分比，
grid-template-columns: auto 50px 10% 2fr 1fr;
这段代码添加了五个列。 第一列的宽与它的内容宽度相等；第二列宽 50px；第三列宽是它容器的 10%；最后两列，将剩余的宽度平均分成三份，第四列占两份，第五列占一份。

## 使用 grid-gap 为网格添加间距
使用 grid-column-gap 创建多列之间的间距
grid-column-gap: 10px;
使用 grid-row-gap 创建多行之间的间距

## 使用 grid-column  grid-row来控制空间大小
grid-column: 1 / 3;这会让网格项从左侧第一条线开始到第三条线结束，占用两列。

## 使用 justify-self 水平对齐 align-self 垂直对齐 项目
strecth（默认）：使内容占满整个单元格的宽度
start：使内容在单元格左侧对齐，
center：使内容在单元格居中对齐，
end：使内容在单元格右侧对齐，

## 将网格划分为区域模板

grid-template-areas:
"header header header"
"advert content content"
"advert footer footer";
上面的代码将网格单元格分成四个区域：header、advert、content 和 footer。 每个单词代表一个单元格，每对引号代表一行。

## 使用 grid-area 属性将项目放置在网格区域中
.item1 {
grid-area: header;}

## 使用 grid-area 创建区域模板
item1 { grid-area: 1/1/2/4; }
上例中数字代表这些值：
grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;
因此，示例中的网格项将占用第 1 条水平网格线（起始）和第 2 条水平网格线（终止）之间的行，及第 1 条垂直网格线（起始）和第 4 条垂直网格线（终止）之间的列。

## 使用 repeat 函数减少重复
以下为添加 100 行网格的例子，每行高度均为 50px：
grid-template-rows: repeat(100, 50px);
grid-template-columns: repeat(2, 1fr 50px) 20px;
效果相当于：grid-template-columns: 1fr 50px 1fr 50px 20px;

## 使用 minmax 函数限制项目大小
grid-template-columns: 100px minmax(50px, 200px);
在上面的代码中，我们通过 grid-template-columns 添加了两列，第一列宽度为 100px，第二列宽度最小值是 50px，最大值是 200px。

## 使用 auto-fill 创建弹性布局
repeat(auto-fill, minmax(60px, 1fr));
上面的代码效果是这样：首先，列的宽度会随容器大小改变。其次，只要容器宽度不足以插入一个宽为 60px 的列，当前行的所有列就都会一直拉伸。

## 使用 auto-fit 创建弹性布局
不同点仅在于，当容器的大小大于各网格项之和时，auto-fill 会持续地在一端放入空行或空列，这样就会使所有网格项挤到另一边；而 auto-fit 则不会在一端放入空行或空列，而是会将所有网格项拉伸至合适的大小。















