### Webpack 学习笔记

是一个打包软件

同时还进行了翻译的工作（loader）

不仅强大而且灵活

![image-20210123155608417](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123155608417.png)

##### webpack其实并不简单

#### 课程重点

> 理解前端模块化
>
> 理解Webpack打包核心思路
>
> 理解webpack中的"关键人物"

#### 误区规定

>不要执着Api和命令

#### 学习路径

> 作用域
>
> 命名空间
>
> 模块化

**面向模块编程**

#### 作用域

文件多了容易发生命名冲突

加上命名空间

![image-20210123161531981](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123161531981.png)

对象苏珊就是一个命名空间

#### 闭包

>> 函数内部的函数
>
>> 外部可访问
>
>>始终保存在内存中(可能造成内存泄漏)

#### 模块作用域

保护该保存的,

返回可访问的

![image-20210123163443601](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123163443601.png)

#### 模块化的优点

> 作用于封装

>重用性

> 解除耦合

#### 模块化的进化史

AMD(异步模块定义)

![image-20210123163939702](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123163939702.png)

COMMONJS

![image-20210123164007070](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123164007070.png)

ES6 MODULE

![image-20210123164100723](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123164100723.png)

#### webpack的打包机制

![image-20210123164826472](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123164826472.png)

#### npm包管理器

可以直接把包安装下来

package.json

npm --save (将下载下来的包信心保存咋在packa.json中)

​			--dev(开发环境)

![image-20210123165824418](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123165824418.png)

##### npm install的过程

>寻找包版本信息文件(package.json),依照她来进行安装

> 查package.json中的依赖,并检查项目中的其他版本信息文件

>如果发现了新包,就更新版本信息文件

#### webpack的核心特性

![image-20210123171041896](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123171041896.png)

webpack.config.js可以指定入口文件,不一定非要是index.js

entry:''//工程资源的入口

output:{}//对打包的结果进行配置

devServe可配置项目访问端口来预览项目

#### loader

 css loader的配置顺序和加载顺序相反

![image-20210123172612309](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123172612309.png)

#### plugins

uglifyjsplugins:丑化代码以进行压缩打包文件

#### webpack构建工程

![image-20210123173020561](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123173020561.png)

#### babel

可以将高版本的代码编译成低版本的代码

比如将ES6代码编译成ES5代码:   **npm install @babel/preset-env **

先找babelrc文件,没有就向外遍历

#### HMR(热刷新)

#### Webpack性能调优

![image-20210123190534689](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210123190534689.png)

###### 体积优化

uglifyplugin

WerserPlugin是uglify的一个分支

bundleAnalyZerPlugin分析器可以分析打包中各部分的大小

webpack单线程

HappyPack可以分成多个子任务加速代码的构建.创建线程池 

threead-loader

tree-shake

#### webpack是什么

前端发展的产物

模块化打包方案

工程化方案

