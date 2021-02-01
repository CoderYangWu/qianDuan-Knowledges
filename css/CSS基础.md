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