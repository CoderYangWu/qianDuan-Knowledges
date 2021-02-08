## Vue学习笔记

#### computed（计算属性）

与watch和method相比性能更优更简洁

#### setter   getter

设置函数和调用返回函数

#### 样式绑定 ：class

```
:class="{activated:isActivated}"
```

先定义，再在方法中设置函数

```
:class="[actived,activatedOne]"
```

先定义样式，再在方法中传值

```
:style="styleObj"
```

内联样式，先在data中定义样式：将styleObj写成css语句

#### Vue条件渲染

v-if和v-else   渲染后dom都不展示

v-show		  渲染后有语句不展示

v-if和v-else标签要连在一起

#### v-for（列表渲染）

一般用v-for和：key使用

#### vue 中的set方法

```
Vue.set(vm.userInfo,1,5)
```

可以直接改变userInfo数组中的第1项为5

#### 组件中使用的细节点

is=""可以嵌入特定的标签

```
<tr is="row"></tr>
```

#### 父子组件之间的数据传递

父传子需要子用props接收

#### 给组件绑定原生事件

@click.native

#### 非父子组件之间传值

总线机制

通过Bus

#### 在Vue中使用插槽

<slot></slot>

具名插槽通过slot/name对应

v-once可以有效提高一些性能

#### Vue中的CSS动画

可以在Animate.css库

velocity.js是一个js库

