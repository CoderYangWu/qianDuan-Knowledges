# CSS基础

#### 半透明效果

```css
background: rgba(0,0,0,.3)
```

最后一个参数是alpha透明度，取值范围再0-1之间

#### 背景位置定位

```
background-position:
x px,y px  x轴  y轴定位
center top left right bottom
```

#### 背景附着

```
background-attachment :fixed  背景固定
					  :scroll 背景滚动
```

#### CSS层叠性

就近原则

#### CSS继承性

子标签会继承父标签

```
font:12px/1.5   行高为12*1.5=18
```

#### CSS优先级

优先级： !import>行内>#> .=:>标签>继承或者*

 权重累加

### CSS盒子模型

boder   边框  

padding   内边距

margin   外边距

#### 边框  border

width  style   color

style： solid实线边框

dashed虚线边框   dotted  虚点边框

复合写法  boder：5px，solid ，pink

#### 内边距padding

顺序：  top   right    bottom   left

即边框和内容之间的距离

padding会影响盒子大小   盒子大小会加上padding值

字数不一的导肮栏 用padding-left|right撑开盒子

#### 外边距margin

顺序：  top   right    bottom   left

复合写法和padding相同

#### 盒子居中显示

margin ：0 auto

#### 外边距合并

垂直外边距塌陷  可以为父元素添加 overflow：hidden

#### 清除内外边距

```
* {
margin=0;
padding:0
}
```

list-style: none  去掉li前面的小圆点

#### 圆角边框

```
boder-radius:length
```

#### 盒子阴影

```
box-shadow: 10px 10px 10px 10px rgba(0,0,0,.3)
```

#### 文字阴影

```
text-shadow: 10px 10px 10px 10px rgba(0,0,0,.3)
```

### 浮动（float）

竖着排列用标准流

横着排列用浮动

none :不浮动

left:向左浮动

right:向右浮动

1.脱离标准流，移动到指定位置（脱标）

2.浮动的盒子不再保留原先的位置

3.浮动元素具有行类块元素的特点

行内元素有了浮动，则不需要块级转换就可以直接给高度和宽度

浮动经常和标准流父级搭配使用

浮动只会影响浮动盒子后面的标准流

父盒子高度不能写死，最好让子盒子撑开

但是如果里面是浮动盒子，父盒子高度就会变成0；

需要清除浮动（清除浮动元素造成的影响）

```
clear:both
1.额外标签法：
在浮动盒子最后面加上一个标签
2.给父元素添加overflow：hidden
3。伪元素法：
.clearfix:after {
content:""
display:block
height:0;
clear: both;
visibility: hidden;
}

.clearfix { /*IE6,7专有*/
*zoom:1;
}
4.双伪元素清除浮动(同样是添加给父元素)
.clearfix:before,.clearfix:after {
content:"";
display:table;
}
.clearfix:after{
clear:both;
}
.clearfix{
*zoom:1;
}
```

为什么清除浮动：

1.父级没有高度

2.子盒子浮动了

3.影响下面布局了，所以需要清除浮动

PSD是网页的设计稿格式

#### 整体页面布局思路

1.确定页面版心（宽度）

2.分析页面中的行木块，以及每个行模块中的列模块，其实页面布局第一准则

3.一行的列模块经常浮动布局，先确定每个列的大小之后确定列的位置，页面布局第二准则

4.制作HTML结构。我们还是遵循，现有结构，后有样式的原则。结构永远最重要

5，所以，先理清楚布局结构，再写代码尤为重要，这需要我们多写多积累。

### 定位

为什么需要定位：标准流和浮动都不能实现

定位：将盒子定道某个位置

定位=定位模式+边偏移

定位模式用于指定一个元素再文档中的定位方式，边偏移则决定该元素的最终位置

#### 静态定位

```
选择器 {position: static}
```

#### 相对定位

```
选择器 {position: relative}
```

参照自己原来的点进行定位

原来位置继续保留（不脱标）

#### 绝对定位

```
选择器{position: absolute}
```

以父元素为边

如果没有父元素或者父元素没有定位，仍然以浏览器边定位

以最近一级带有定位的边为参照点

绝对定位不再占有之前的位置（脱标）

子绝父相用得比较多

#### 固定定位fiexd（重要）

```
选择器{
position: fixed
}
```

可视窗口的位置，和父元素没有任何关系

固定位置不占用位置（脱标）例：两边广告

小算法：

先left：50%，再margin-left：50%

#### 粘性定位 sticky

必须要有 left,top,right,bottom其中一个

#### 定位的叠放次序Z-index

值大的压住值小的

数值后面没有单位

标准流和浮动定位没有这个属性

#### 绝对定位盒子的居中算法

加了绝对定位的盒子不能margin：0 auto居中

```
position: absolute
left:50%
margin-left:100px 让盒子移动自身宽度的一半
```

#### 定位的拓展

1.行内元素添加绝对定位或者固定定位，可以直接设置高度和宽度

2.块级元素添加绝对或固定定位，如果不给宽度或者高度，默认大小是内容的大小

脱标的盒子不会发生塌陷



浮动的元素不会压住盒子 里的文字

绝对定位会完全压住

如果一个盒子既有left又有right，执行left

### 元素的显示和隐藏

#### display

none：隐藏（位置也会消失）

block：转换为块级元素同时也有显示的意思

#### visibility

和display最大区别就是是否保存原来的位置

还是display用的多

#### overflow溢出

overflow：visibility

​				：hidden

​				：scroll 滚动条

​				：auto 超出加滚动条

### CSS高级技巧导读

#### 精灵图（雪碧）

为什么需要精灵图？

将小图片呵呵曾大图片返回

解决服务器压力过大原因

精确测量大图片中的小图片的位置

用background-position

切片：background：url（.jpg）no-repeat -px -px

#### 字体图标

轻量、灵活

结构样式比较简单的小图标就可以用

复杂的还是需要使用精灵图

字体库 icomoon、icofont

#### 字体图标的引用

设置字体样式为：icomoon

#### css画三角形

```
        .box1 {
            width: 0px;
            height: 0px;
            border-left:10px solid red ;
            border-top: 10px solid blue;
            border-right: 10px solid black;
            border-bottom: 10px solid green;
        }
        .box2 {
            width: 0px;
            height: 0px;
            border: 50px solid transparent;
            border-top-color:  blue;
            margin: 100px auto;
        }
```

#### 用户界面

鼠标样式 cursor

default默认

pointer小手

move移动

text文字

not-allowed禁止

轮廓线：input{outline：none}

文本域：textarea{resize：none}

#### vertical-align

bottom 底线对齐

middle 中线对齐

#### 溢出文字省略号显示

必须满足三个条件；

1.如果文字显示不开，必须强制一行显示：

white-space：nowrap

2.溢出的部分隐藏起来：

overflow：hidden

3.文字溢出的时候用省略号来显示：

text-overflow：ellipsis

多行文本溢出加省略号

推荐后台人员来做

#### 布局技巧

margin负值

行内块巧妙运用

梯形：三角强化：bottom 0px，left 0px，top改成100px透明，只保留右边边框为直角三角形和矩形合成梯形

#### CSS初始化

### HTML5新特性

IE9+以上才能兼容

新增语义化标签：header\nav\aside\article\section\footer

新增得多媒体标签：audio video

新增input表单拥有多种type类型email，url...

新增表单属性：

### CSS新特性

新增选择器

1.属性选择器：input[value]:选择带value属性得input  权重为10

2.结构伪类选器

：nth-child（n）

n可以是数字、公式、关键字、

：nth-of-type（n）

3.伪元素选择器可以帮助我们利用css创建新标签，而不需要html标签，从而简化html

::before   :始终在盒子的前面

::after	  :始终在盒子的后面

4.伪元素清除浮动：上面有写

css3盒子模型

box-size:盒子的大小就等于width和heigh

滤镜fliter： bluer(px)模糊图像

calc函数

calc（）括号里可以用+-*/

过度

transition

必须在末尾加时间

谁做过度给谁加

#### 狭义的HTML5 CSS3

#### web服务器

#### css3 2D转换

transform 是css中具有颠覆性的功能之一 ，可以实现位移、旋转、缩放等效果

移动：transform：translate（x，y）

不会影响其他元素的位置

%是相当于移动自身元素长宽度的百分比

旋转：transform：translate（x deg）

可以设置转换的中心点：transform-origin

可以像素设置，也可以位置设置

scale缩放：transform：scale（x，y）

scale（2，2）数字代表倍数：宽高都变为两倍

overflow：hidden 溢出隐藏

转换可以同时使用多个功能

#### 动画（animation）

先定义动画

在调用动画

在@keyframe中定义动画

#### 3D 转换

transfrom： translateZ（ px）

transfrom：translate3d（x，y，z）

##### 透视 perspective

#### 移动流式布局

meta视口标签布局视口宽度应该和理想视口宽度一样

在移动端1px并不等于1物理像素

iphone8里是两倍的关系

Retina（视网膜屏幕）是一种显示技术、可以把更多的w物理像素点压缩在一块屏幕里

流式布局就是百分比布局，不受固定像素的限制

#### flex布局

pc端还是建议传统布局

移动端建议flex布局

display ：flex

felx-drection：row横向排列

col纵向排列

justify-concent：设置主轴排列方式

align-items：设置侧轴排列方式

align-content：设置多行侧轴上的排列方式

flex-flow

#### less

##### css弊端

不方便维护和扩展

新建.less文件

保存自动生成css文件

#### rem适配方案

首先选一套标准尺寸 750为准

用屏幕尺寸 除以 划分的份数得到字体大小

#### 响应式开发

原理：更具媒体查询针对不同宽度的设备进行布局和样式设置，从而适配不同设备的目的

通过布局容器 .containter

#### Bootstrap前端开发框架

