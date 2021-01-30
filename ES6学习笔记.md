### ES6学习笔记

#### 兼容性

ES6(ES2015)--IE10+\Chrome\Firefox\移动端\Node.js

es6->es5    可以使用通过babel来转换

#### ES6有新特性:

1.变量

2.函数

3.数组

4.字符串

5.面向对象

6.Promise

7.generator

8.模块化

#### 变量

js烂的地方:

> var 
>
> > 可以重复声明
> >
> > 无法限制修改
> >
> > 没有块级作用域

##### let

> let
>
> > 不能重复声明
> >
> > 具有块级作用域
> >
> > 变量-能被修改

##### const

>const
>
>>不能重复声明
>>
>>具有块级作用域
>>
>>常量-不能被修改



#### 箭头函数

1.如果只有一个参数,()可以省

2.如果只有一行return,return和{}可以省



#### 函数

1.参数扩展/数组展开

2.默认参数



1.参数扩展:

1.收集参数

```javascript
function show(a,b, ...args){}
```

*Rest Parameter必须是最后一个

2.展开数组

展开后的效果,更直接把数组内容写在这一样



2.默认参数

拥有默认值



#### 解构赋值

1.左右两边结构必须一样

2.右边必须是个东西

3,声明和赋值

```
let [{a,b},[n1,n2,n3],'abc']=[a,b,c]
or
let [a,b,c]=[{a,b},[n1,n2,n3]
```

注意两边结构相同

#### 数组

新方法:

map			映射  一个对一个

reduce		汇总  一堆出来一个

```
计算总和
let arr[12,69,180,8763]
arr.reduce(function(tmp,item,index){
return tmp+item
})
```

```
计算平均数
let arr[12,69,180,8763]
arr.reduce(function(tmp,item,index){
if(index!=arr.length-1){
return tmp+item}else{
return (tmp + item)/arr.length
}
})
```



filter			过滤器

```
let arr = [1,2,3,4,5,6,7,8]
let result = arr,filter(item=>item%3==0)
result=[3,6]
```

forEach		循环(迭代)

#### 字符串

1.多了两个新方法

startsWith检测开头字符

endsWich检测结尾字符

2.字符串模板

``

```
let a=12
let res=`a${a}B`
res=a12B
```

#### ES6面向对象

```
function User(naem,pass){
this.name=name;
this.age=name;
}

class User{

}
```

1.class关键字\构造器和类分开了

2.class里面直接家方法



继承:

```
class vipUser extends User{
	constructor(name,pass,level){
	super(name,pass);
	this.level=level
	}
	
	showLevel(){
	alert(this.level)
	}
}
```

super==超类==父类

面向对象的应用--React

React:

1.组件化-class

2jsx

JSX==babel==browser.js

render  :  渲染

#### json

JSON对象

JSON.stringify

JSON.parse

```
let json={a:12,b:15}

```

json 的简写

名字跟值(key和value)一样的    留一个就行

方法										 :function一块删

​		show:  function(){...}

​		show(){...}

json的标准写法



1.只能用双引号

2.所有的名字都必须用引号包起来

#### Promise   --承诺

异步:操作之间没啥关系,同时进行多个操作

同步:同时只能做一件事

异步:代码更复杂

同步:代码简单

Promise---消除异步操作

promise.all

promise.race

#### generator -生成器

普通函数----一路到底

generator------走走停停



```javascript
function *show(){
    alert('a');
    yield;
    alert('b')
}
```



yield在哪停在哪

##### generator-yield

yield传参\返回

![image-20210123215437098](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123215437098.png)

![image-20210123220139879](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123220139879.png)

