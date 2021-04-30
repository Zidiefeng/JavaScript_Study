# JavaScript

狂神说Java系列-个人学习笔记

## 前端认知

- [ ]  [P11、聊聊JavaScript这个东西19:36](https://www.bilibili.com/video/BV1JJ41177di?p=1)

Ref 完整版笔记：[https://www.cnblogs.com/cbpm-wuhq/p/12325734.html](https://www.cnblogs.com/cbpm-wuhq/p/12325734.html)

### 前端知识体系

- 前端三要素
    - html: hyper text markup language, 内容，结构
    - CSS: cascading style sheets, 样式
        - markdown language, 不是编程语言，不可以定义变量，不可以引用，不支持各种语法（最新的可以支持一些编程）
        - 语法不强大，不能嵌套书写，可能要写重复的选择器
        - 没有变量，没有复用机制（java中的类）
        - 后来出来了 css预处理工具
    - JavaScript: 弱类型脚本语言，不需要经过编译，用浏览器解释运行，控制网页behavior

### css预处理器

- 是一种新的编程语言，给CSS增加编程特性（页面设置）
- 生成的output就是css 文件
- 常见css预处理器
    - `SASS`：基于Ruby，通过服务器处理，功能强大，解析效率高，需要学习Ruby语言，上手难于LESS
    - `LESS`：基于NodeJS（未来必学项），通过客户端处理，使用和功能都更简单，解析效率低于SASS，但是开发中够用了，如果后来人员需要的话，建议LESS
        - [官网](https://lesscss.org/#:~:text=Less)（有中文版）
        - 需要安装NodeJS

### JavaScript

- 最开始JS原生开发，使用简单，应用强大（前端+后端）
- 能在浏览器上执行的脚本
- NodeJS可以支持完整的 web项目（但是不能支持高并发）
- 标准：
    - ECMAScript标准，简称ES，所有浏览器都支持
        - 常用版本ES6, 全部支持版本：ES5
        - ES6 可能要用webpack打包成ES5
        - 最新出到ES9（draft），逐步增加新特性
    - TypeScript 微软的标准, 生成JavaScript文件

### JavaScript框架

- JQuery
    - 是一个库，不是一个框架，封装了很多方法，但用的越来越少，因为已经有很多其他成熟框架了
- 框架1：Angular
    - google收购的，一群Java人开发
    - 特点是将后台的MVC模式帮到前端，增加了module开发的理念
    - 与微软合作，采用TypeScript语法开发
    - version迭代不是很合理
    - 对前端不友好，对后端友好
- 框架2：React
    - Facebook出品，高性能的JS前端框架
    - 特点是提出了【虚拟DOM】概念，减少真实DOM操作，在内存中模拟DOM操作，提升了前端渲染效率
    - 缺点：复杂，需要学习JSX语言
- 框架3：Vue
    - 结合了Angular的module开发，和 React的 虚拟DOM
    - 现在很火
    - 有路由，状态管理的新特性
- Axios：
    - 前端通信框架，较为交单
    - 因为 Vue 的边界很明确，就是为了处理 DOM，所以并不具备通信能力，此时就需要额外使用一个通信框架与服务器交互
    - 当然也可以直接选择使用 jQuery 提供的 AJAX 通信功能

### UI框架

- `Ant-Design`:
    - 阿里巴巴
    - [https://ant.design/index-cn](https://ant.design/index-cn)
- `ElementUI`, `iview`, `ice`: 饿了么出品，基于Vue的UI框架
- `Bootstrap`: Twitter推出的用于前端开发的开源工具包
- `AmazeUI`: 妹子UI， HTML5 跨前端框架，很多博主用

### JavaScript 构建工具

- Babel: JS编译工具，用于构建打包，用于浏览器不支持的ES新特性，比如用于编译TypeScript
- WebPack：模块大伯其，用于打包，压缩，合并，按序加载
    - 上面都需要JavaNode

### 三端统一

- 三端：PC， Android， IOS
- 微信小程序：WeUI

### 后端技术

- 主要技术：NodeJS

    前端人员为了方便开发也需要掌握一定的后端技术，但我们 Java 后台人员知道后台知识体系极其庞大复杂，所以为了方便前端人员开发后台应用，就出现了 NodeJS 这样的技术。

    NodeJS 的作者已经声称放弃 NodeJS（说是架构做的不好再加上笨重的 node_modules，可能让作者不爽了吧），开始开发全新架构的 Deno

- 既然是后台技术，那肯定也需要框架和项目管理工具，NodeJS 框架及项目管理工具如下：
    - Express：NodeJS 框架
    - Koa：Express 简化版
    - NPM：项目综合管理工具，类似于 Maven
    - YARN：NPM 的替代方案，类似于 Maven 和 Gradle 的关系

### 什么是JavaScript

- JavaScript是最流行的Markdown语言
- 浏览器解释执行
- JavaScript与Java没有关系，基本是为了蹭热度
- 10天就开发出来了（Netscape Communications Corporation）,因为那个公司想要自己发布的浏览器有 动态效果
- 一个合格的后端，必须精通JavaScript(工作中可能写的比Java多)

### ECMAScript

- Eurpean computer manufacturers association通过的标准
- 最新版本：ES6
- 但是浏览器大部分只停留在支持ES5代码，问题是，开发环境与线上环境版本不一致

## 快速入门

- [ ]  [P22、基本使用及HelloWorld08:36](https://www.bilibili.com/video/BV1JJ41177di?p=2)

### 引入JavaScript

1. 内部引用：用`script`标签表示

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled.png)

2. 外部引用：用script连接到javaScript文件

    ```jsx
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

    <script src="js/qj.js"></script>
    </head>
    ```

### 注意点

- 可以放在html内，也可以单独弄成file，跟CSS一样
- 一般放在body最下面，或者head中
- 注意，不要见写后面的`</script>`
- type是optional的`<script type="text/javascript"></script>`
- js注释：`//` 后面必须加一个空格再写

## 基本语法入门

- [ ]  [P33、浏览器控制台使用14:38](https://www.bilibili.com/video/BV1JJ41177di?p=3)

### 调整版本

- 我没有找到这个plug-in
    - JavaScript and TypeScript （[https://www.jetbrains.com/help/idea/javascript-specific-guidelines.html#ws_JavaScript_before_you_start](https://www.jetbrains.com/help/idea/javascript-specific-guidelines.html#ws_JavaScript_before_you_start)）
- 应该跳到es6

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%201.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%201.png)

### 变量

- `var var_name = value;`(不需要确定类型)
- 语句需要`；` 结尾，因为解释的时候会打包成一行
- 可以用`$`, `_` 做变量的开头，但不能用数字开头

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%202.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%202.png)

- 可以用中文做变量名称
    - Java是可以用中文变量的

        ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%203.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%203.png)

    - JavaScript中

        ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%204.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%204.png)

### Inspect-浏览器调试须知

- Element：爬网站，看html, CSS
- Console: 调试JS
- Source：打JS断点
- Network：抓包？
- Application：网站cookie

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%205.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%205.png)

### 在Inspect的console中运行

- console中接受的是javascript语法， 可以直接写JS code运行，而且可以直接cal该界面已经定义的variable

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%206.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%206.png)

- `alert()` 是跳出弹框
- `console.log(score)` 相当于print (一般用这个查看，不用`alert()`)

### 在Inspect中打断点运行一个网页

- Sources储存了code和相关sources
- 如果点开html，然后打一个断点，刷新网页之后，会运行到断点，然后可以用下面的控制器一步一步运行来debug

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%207.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%207.png)

### Inspect查看请求

- 点击Network, 刷新网页，这里可以看到所有对网页的请求

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%208.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%208.png)

### Inspect查看数据库

- Storage - Local Storage
- Cookie
- Cache缓存
- Application中可以看到简单储存在web中的database，实际上存在本地的浏览器中（看不到后台的）

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%209.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%209.png)

### 其他注意点

- 区分大小写
- `/**/`

## 简介-数据类型

- [ ]  [P44、数据类型快速浏览24:46](https://www.bilibili.com/video/BV1JJ41177di?p=4)

数值，文本，图形，音频

### number

- 数字类型, JS不区分小数，整数

- code

    ```jsx
    123 //整数 123
    123.3 //float
    1.123e3 //1123
    NaN // Not a Number
    -99 //negative
    Infinity // infinity
    ```

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2010.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2010.png)

### String

- `'abc'` `"abc"`

### Bool

- true
- false

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2011.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2011.png)

### Logic

- `&&`
- `||`
- `!`

### Comparison

- = 赋值
- == 等于（类型可以不一样，只要value一样就行，比如1和“1”）
- === 绝对等于（类型一样，value一样，才是true，推荐使用）
    - 注意，NaN与所有的都不想等，包括自身
    - `isNaN(NaN)` 来判断自身

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2012.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2012.png)

### 浮点数问题

- 可能存在精度的损失

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2013.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2013.png)

- 解决办法：abs（a-b）<threshold

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2014.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2014.png)

    - 跟Java中bigDecimal原理一样

### null与undefined

- `null` 空
- `undefined` 未定义，比如用了一个没有定义的variable(报错)

### 数组

- 数组：可以不同类的 一系列对象
    - (Java需要一系列相同类型的对象）
- 定义方法

    ```jsx
    var arr = [1,2,3,4,5,"hello"] //推荐这种
    new Array(1,2,3,4,5,"hello")
    ```

- slice&下标越界
    - 下标越界：`undefined`

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2015.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2015.png)

### 严格检查模式

- [ ]  [P55、严格检查模式strict07:27](https://www.bilibili.com/video/BV1JJ41177di?p=5)
- 用`i = 1` 可以成功定义var，而且是全局var ，如果大家都随意写，同一个html加载多个javaScript的文件的时候，就会出错！

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2016.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2016.png)

- `var i = 1` 定义局部变量（ES5之前）
- （ES6之后）建议用let定义：`let i = 1`
- 严格检查模式：
    - 写上 `“use strict”`，之后如果再定义全局变量就会出错（自动检查）
    - 预防JavaScript随意性 导致的一些列问题，报错之后
    - `“use strict”` 必须写在JavaScript的第一行
    - 使用前提：IDEA设置support ES6语法

## 深入讲解-数据类型

### 字符串

- [ ]  [P66、字符串类型详解15:00](https://www.bilibili.com/video/BV1JJ41177di?p=6)
- 正常字符串：`‘’`或 `“”`
- 转义符`\`

    ```jsx
    "use strict"
    console.log("a");
    console.log('a');
    console.log('a\'');
    console.log('a\nb');
    console.log('a\tb');
    console.log('a\u4e2d');//unicode, format: \u####
    console.log('\x41');// Ascll字符
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2017.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2017.png)

- 换行输入, 长字符串：````

    ```jsx
    var msg = `
    hello
    world
    你好呀
    `
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2018.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2018.png)

- 模板字符串

    ```jsx
    var msg = `
            hello
            world
            你好呀
            `
    let name = "Kaitan";
    let message = `${msg} \n ${name}`
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2019.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2019.png)

- 字符串常见方法、属性
    - `.length`看长度
    - 截取 `[]`(注意，string不接受赋值变更)
    - `.indexOf()` 查某个字符所在位置
    - 大小写 `.toUpperCase()`
    - subtring含头不含尾：`[,)`

        ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2020.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2020.png)

- [ ]  [P77、数组类型详解19:01](https://www.bilibili.com/video/BV1JJ41177di?p=7)

### 数组

重点：如何存，如何取

- Array可以包含任意数据类型

    ```jsx
    var arr = [1,2,3,4,5]
    ```

- 数组可以变动长度，也可以重新赋值

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2021.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2021.png)

- length赋值太小，会直接丢掉其他元素

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2022.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2022.png)

- 获得元素的index

    ```jsx
    //arr = [0, 2, 3]
    arr.indexOf(2)
    //1
    ```

- array中的1 与 “1” 不同
- slice array中的一部分

    ```jsx
    var arr = [1,3,2,5,6,7,8]
    arr.slice(2,5)
    //(3) [2, 5, 6]
    ```

- 从尾部分别 `pop`删除, `push`增加 一些element

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2023.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2023.png)

- `unshift()` `shift` （头部处理）

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2024.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2024.png)

- 排序

    ```jsx
    //(5) ["a", 3, 5, 6, 7]
    arr.sort()
    //(5) [3, 5, 6, 7, "a"]
    ```

- reverse

    ```jsx
    arr
    //(5) [3, 5, 6, 7, "a"]
    arr.reverse()
    //(5) ["a", 7, 6, 5, 3]
    ```

- concat
    - 不修改原array

    ```jsx
    arr.reverse()
    //(5) ["a", 7, 6, 5, 3]
    arr.concat([1,2,3])
    //(8) ["a", 7, 6, 5, 3, 1, 2, 3]
    arr
    //(5) ["a", 7, 6, 5, 3]
    ```

- join

    ```jsx
    arr.join("-")
    "a-7-6-5-3"
    ```

- 多维数组

    ```jsx
    let arr1=[[24,3,5], [5,2], [3,4,1,2,4,[3,2]]]
    arr1
    //(3) [Array(3), Array(2), Array(6)]
    arr1[2][1]
    //4
    ```

- fill

    ```jsx
    arr
    //(5) ["a", 7, 6, 5, 3]
    arr.fill(1)
    // (5) [1, 1, 1, 1, 1]
    ```

 

- [ ]  [P88、对象类型详解10:26](https://www.bilibili.com/video/BV1JJ41177di?p=8)

### 对象

- 对象用大括号，数组用中括号，如 `var person = {}`
    - 非常类似python的dict，所有的key都是String，value则可以是任何对象
- 每个属性用`，` 隔开，最后一个后面不加`，`

    ```jsx
    //Java类 Person person = new Person("KK", 3, ["js","java","css"] );
    var person = {
        name:"KK",
        age:3,
        tags: ["js","java","css"]
    }
    ```

- 属性调用

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2025.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2025.png)

- 总结

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2026.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2026.png)

    `in` 可以检测一个key(属性)是否属于一个class的类or(父类)方法
    `.hasOwnProperty` 检测的是attribute(key), (父类)方法会为false

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2027.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2027.png)

## 流程控制

- [ ]  [P99、分支和循环详解12:44](https://www.bilibili.com/video/BV1JJ41177di?p=9)

### if

```jsx
'use strict';
var age = 3;
if (age>3){
    alert("haha");
} else {
    alert("so hard");
}
```

### while

```jsx
while(age<100){
    age = age +1;
    console.log(age);
}

//必先执行一次do
do{
    age = age +1;
    console.log(age);
}while(age<100)
```

### for

```jsx
for (let i = 0; i<20; i++){
    console.log(i)
}
```

### loop an array

```jsx
var data = [3,1,5,22,1,123];

//用函数，并不是array循环
var data = [3,1,5,22,1,123];
data.forEach(function(v){
    console.log(v);
});

//for in
for(var num in data){
    console.log(num);
}
//result: index
0
1
2
3
4
5

//for in
for(var num in data){
    console.log(data[num]);
}
//result:value
3
1
5
22
1
123

```

### 永远关不掉的弹窗

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2028.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2028.png)

- [ ]  [P1010、Map和Set集合12:14](https://www.bilibili.com/video/BV1JJ41177di?p=10)

### map

- key, value pair

```jsx
//ES6 新出的
//var names = ["tom","jessy","john"];
//var scores = [80,90,10];
var map = new Map([["tom",80],["jessy",90],["john",10]]);
var sc = map.get("jessy");//get value from key
map.set("admin",312);
map.delete("tom");
```

### Set

无序不重复集合

```jsx
var set = new Set([1,2,2,1,2]);
//Set(2) {1, 2}
set.add(4);
set.delete(1);
set.has(2) //判断是否属于一个set
```

- [ ]  [P1111、Iterable迭代和下周安排11:03](https://www.bilibili.com/video/BV1JJ41177di?p=11)

## Iterater

### for of 可以loop array, set, map

```jsx
//loop through array, set, map
"use strict";
var arr = [3,4,5];
for (let x of arr){
    console.log(x);
}

```

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2029.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2029.png)

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2030.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2030.png)

### 尽量不要用let x in 了

```jsx
"use strict";
var arr = [3,4,5];
arr.name="213"
for (var x of arr){
    console.log(x);
}
// 3 4 5 显示元素，不包含value的 213，正常

for (let x in arr){
    console.log(x);
}
// 0 1 2 name 包含了attribute 的name，类似一个bug
```

## 函数

- [ ]  [P1212、函数的定义和参数获取22:46](https://www.bilibili.com/video/BV1JJ41177di?p=12)

### 方法vs函数

- 看上去一样
- 方法：对象中的，（对象里，有attribute和 方法）
- 函数：非对象中
- 一旦return，函数结束

### 函数定义 方式1

- 格式

    注意，如果函数没有执行return（如→），会返回结果，会返回`undefined` or `NaN`

    ```jsx
    //JavaScript
    function abs(x){
    	if(x>=0){
    			return x;
    	} else {
    			return  -x;
    	}
    }
    ```

![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2031.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2031.png)

- 与Java 对比

    ```java
    //Java
    public 返回值类型 方法名(){
    	return 返回值；	
    }
    ```

### 定义方式2

- `function(){}` 其实是一个匿名函数，可以把结果赋值给abs, 这样用abs来调用就好

    ```jsx
    var abs = function(){
    }
    ```

### 参数问题

- JavaScript可以传入任意个参数，也可以不传参数

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2032.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2032.png)

- 太过随意，可以在function里面加一些check, 比如`arguments.length` , 增加自动报错

    ```jsx
    function abs(x){
    //throw error
        if(typeof x !== 'number'){
            throw 'not a number';
        }
        if(x>=0){
                return x;
        } else {
                return  -x;
        }
    }
    ```

### arguments

- arguments是一个JS免费赠送的关键字
    - x其实只是第一个输入值，return也是针对x的
    - 但是arguments记录了所有unique的参数值，是一个数组

    ```jsx
    function abs(x){
    	console.log("x=>"+x);
    	for (var i =0; i<arguments.length;i++){
    	    console.log(arguments[i]);
    	}
    	
    	
    	if(x>=0){
    	        return x;
    	} else {
    	        return  -x;
    	}
    }
    //abs(1,3123,1231,3123,123,123,123,12,32)
    x=>1
    1
    3123
    1231
    3123
    123
    12
    32
    1
    ```

### arguments的问题 & `rest`

- arguments包含所有的参数，有时候我们只想用后面的参数做附加操作，希望能排除已有参数
- `rest` 专门可以获取非定义的所有参数的array

    定义的时候记得写`...rest` 标识

    ```jsx
    //old ways to handle the other parameters
    function aaa(a,b){
        console.log("a=>"+a);
        console.log("b=>"+b);
        if (arguments.length>2){
            for (var i =2 ; i<arguments.length;i++){
                
            }
        }
    }

    //using rest
    function aaa(a,b,...rest){
        console.log("a=>"+a);
        console.log("b=>"+b);
        console.log(rest);
    }
    //aaa(1,3123,1231,3123,123,123,123,12,32)
    a=>1
    b=>3123
    (7) [1231, 3123, 123, 123, 123, 12, 32]

    ```

## 变量作用域

- [ ]  [P1313、变量的作用域、let、const详解38:24](https://www.bilibili.com/video/BV1JJ41177di?p=13)

- 在函数内声明的variable, 在func外 不可用

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2033.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2033.png)

- 如果想实现从外部访问内部函数，可以研究`闭包`
- 不同函数内部可以declare相同的variable,互相独立
- func中嵌套的function可以拿到外部的function的参数，外部function拿不到内部function的参数

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2034.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2034.png)

- 如果内外function有相同变量，内部引用的时候，会先查找内部function 的var，找不到，再找到外部的
- 如果在一个function中，用到的var在后面才定义，会出现notdefined（而不会显示报错，但是不会把后面的value 赋值过来）, 下面两个func相互等价

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2035.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2035.png)

- 书写习惯：在function第一行，declare所有variable(不必赋值)  用于代码维护

### 全局变量

- 正常定义在Script中的，都是全局function, 全局variable (function可以理解为一个var类型)
- 全局variable和全局function都可用 `window.` 访问（window代表浏览器）
    - 比如`alert` 等价于 `window.alert`

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2036.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2036.png)

- JavaScript实际上只有一个全局作用域，任何var（function也是var）。如果在function内没有找到一个var，会在外面查找，最后在全局查找，如果还没有，会显示ReferenceError
- window.alert可以赋值给别的var,也可以被重新define

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2037.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2037.png)

- 由于所有的全局变量都会绑定到windows,如果不同的js文件使用了全局var，会conflict。
    - 解决方法，每个javaScript文件 自己define 一个全局变量模拟window , 降低全局conflict

        比如JQuery就是这么做的

        ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2038.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2038.png)

### 局部作用域-let

- 建议用let
- 用var声明，可能会出作用域

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2039.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2039.png)

### 常量

- 声明常量：`const`

    ```jsx
    const PI = "3.14";
    ```

- ES6之前，只是用大写来区分常量

## 方法

- [ ]  [P1414、方法的定义和调用、apply11:16](https://www.bilibili.com/video/BV1JJ41177di?p=14)

### 方法

- 方法：把function放进class
- class 只有 attribute和method
- 例子

    ```jsx
    var jessy = {
        name:"jessy",
        birth: 1995,
        age: function(){
            var now = new Date().getFullYear();
            return now - this.birth;
        }
    }
    //jessy.age()
    26
    ```

    等价于下面

    - 但是不能直接调用getAge(), 因为`this`指向调用他的人
    - 在全局中，默认调用的是window,因为window并没有birth属性, 运行失败

    ```jsx
    var getAge = function(){
        var now = new Date().getFullYear();
        return now - this.birth;
    }

    var jessy = {
        name:"jessy",
        birth: 1995,
        age: getAge
    }
    ```

    拆开写的好处的是可以被多个class 使用

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2040.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2040.png)

### apply

- 可以把function指向一个 class （默认是window），就可以使用this了
- 如下（如果没有参数，就传入一个空的array）

    ```jsx
    getAge.apply(jessy,[]);
    ```

## 内部对象

- [ ]  [P1515、Date日期对象10:28](https://www.bilibili.com/video/BV1JJ41177di?p=15)

### 标准对象

- typeof

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2041.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2041.png)

### Date

- get时间

    ```jsx
    var now = new Date();
    now.getFullYear();
    now.getMonth(); //0~11
    now.getDate();
    now.getDay();
    now.getHours();
    now.getTime();
    now.getHours();
    now.getMinutes();
    now.getSeconds();
    now.getTime();//全世界统一,时间戳
    new Date(1578106175991);

    now
    //Fri Apr 23 2021 22:56:03 GMT-0400 (Eastern Daylight Time)
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2042.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2042.png)

- 时间转换

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2043.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2043.png)

## JSON

- [ ]  [P1616、JSON对象15:09](https://www.bilibili.com/video/BV1JJ41177di?p=16)

### JSON介绍

- 早期，所有data传输都习惯使用XML文件
- 轻量级数据交换格式
- 层次结构简单

### JavaScript与JSON

- 在JavaScript一切皆为对象，任何JS支持的类型都可以用JSON表示
- 对象都用{}, 数组都用[], 所有的key, value 都是 `key: value`
- 例子

    ```jsx
    var user = {
        name: "jessy",
        age:3,
        sex: 'female'
    }
    var jsonUser = JSON.stringify(user);
    var checkUser = JSON.parse('{"name":"jessy","age":3,"sex":"female"}');

    //-------------results
    //jsonUser
    "{"name":"jessy","age":3,"sex":"female"}"

    //user， checkUser
    {name: "jessy", age: 3, sex: "female"}
    	age: 3
    	name: "jessy"
    	sex: "female"
    	__proto__: Object
    ```

### JSON与JS对象区别

- 一般后端给前端传json，然后前端解析json（类似parse）

    ```jsx
    var obj = {a: 'hello', b:'hi b'};
    var json = '{"a": "hello", "b":"hi b"}'
    ```

### Ajax

- 原生的js写法（`xhr`异步请求）
- 还可以用JQuery封装好的方法`$("#name").ajax("")`
- `axios`请求（推荐，专业）

## 面向对象编程

- [ ]  [P1717、面向对象原型继承08:17](https://www.bilibili.com/video/BV1JJ41177di?p=17)

### 什么是面向对象

- 类：模板， 对象：具体的实例
- JavaScript， Java， C#，...
- JavaScript与其他language的区别：

### 用`__proto__`继承

- 如下`kathy.__proto__=Student;` 就让kathy继承了student,
    - 可以直接用`kathy.run()`, `kathy.age`来访问`Student` 的attribute和method
    - `kathy.name`是“kathy”，相当于自身重写了`Student`的name attribute

        ```jsx
        var Student = {
            name:"jessy",
            age:3,
            run:function(){
                console.log(this.name+" is running ...");
                }
        }

        var kathy = {
            name: "kathy"
        }

        kathy.__proto__=Student;
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2044.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2044.png)

- [ ]  [P1818、面向对象class继承13:15](https://www.bilibili.com/video/BV1JJ41177di?p=18)

### 用class继承

- 旧方法（根据object找prototype，然后添加method）
    - 这个没有测试成功（不知道如何测试，是不是应该先定义prototype）
    - 这里用了构造函数
    - 不用记这个方法

    ```jsx
    //构造函数
    function Student(name){
        this.name = name;
    }

    //add a method in Student
    Student.prototype.hello = function(){
        alert("Hello")
    }
    ```

- 用class，定义class（attribute, methods）

    ```jsx
    class Student{
      constructor(name){
          this.name = name;
      }

      hello(){
          alert("hello")
      }
    }

    var jessy = new Student("jessy")
    var kathy = new Student("kathy")

    jessy.hello()
    ```

- 用class继承
    - 模板class其实就是JavaScript中的prototype对象

    ```jsx
    class PrimaryStudent extends Student{
        constructor(name, grade){
            super(name)
            this.grade = grade;
        }
        myGrade(){
            alert("I am a primary school student")
        }
    }

    var hong = new PrimaryStudent("hong",49);
    hong.myGrade()
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2045.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2045.png)

### prototype链

- 一个class的`__proto__` 指向下一个对象，最终指向`object`...的过程
- `object` 的prototype也是object，链会一直持续下去
- 在JavaScript中，每一个function 都有`__proto__` ，每个构造函数都有一个prototype object, (包含一个指针指向父类)
- 理解：
[https://www.cnblogs.com/loveyaxin/p/11151586.html](https://www.cnblogs.com/loveyaxin/p/11151586.html)

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2046.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2046.png)

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2047.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2047.png)

## BOM

- [ ]  [P1919、操作BOM对象28:49](https://www.bilibili.com/video/BV1JJ41177di?p=19)

### BOM

- browser object model 浏览器对象模型
- browser内核
    - IE version 6 - 11(最新)
    - Chrome (google)
    - Safari
    - Fairefox (linux默认)
    - Opera 塞班系统（用的很少，忽略）
- 第三方浏览器（非原生，利用上面的内核）
    - QQ浏览器
    - 360浏览器
- JavaScript最开始是为了能够在browser中运行

### Window对象

- window代表浏览器窗口
- 获得窗口的长宽（调整窗口大小之后，再run会变）

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2048.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2048.png)

### Navigator

- 代表浏览器（封装了浏览器的信息）
- 常见信息

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2049.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2049.png)

- 一般不会用`navigator`对象，因为可以被人认为修改
- 不建议用这些属性来判断编写代码

### Screen

- 屏幕

    ```jsx
    screen.height
    1080
    screen.width
    1620
    ```

### location

- 重要，返回当前位置，比如：
    - 主机host:
    - 位置：href

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2050.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2050.png)

- `location.reload()`重新加载页面（刷新）的意思
- 设置webpage 的跳转link（设置新的定位）

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2051.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2051.png)

### document

- 当前页面
- 比如html是靠DOM树（document）展示的
- 比如窗口tab名

    ```jsx
    document.title
    "New Tab"
    document.title="wowo~~~"
    "wowo~~~"
    ```

- 可以获取DOM树结点，进而add/remove结点，从而动态控制结点，修改网页
    - 还可以`ByClassName`, `ByTargetName`

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2052.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2052.png)

- `document.cookie` document可以获取cookie（前端获取方式）
- cookie是客户端的本地信息，会被发到server服务，如果没有cookie，就登陆不了了

### 劫持cookie的原理

- cookie可以被劫持
- 假设现在taobao.com, 引入了javascript
    - 一般浏览器不会防范下面的script
    - 如果`aa.js` 含有`document.cookie`, 获取你的cookie然后上传到ta自己的服务器，privacy就没了

    ```jsx
    <script src = "aa.js"></script>
    ```

- 还可以伪造cookie，不需用户名密码就可以登录
    - 比如，淘宝和天猫，如果一个登陆成功，另一个也就登陆了（一方劫取了cookie传给了另外一方）
    - 服务器端可以设置`httpOnly`以保证不被获取，read only

### history

- 代表browser的历史记录
- 前进，后退

    ```jsx
    history.back() //返回上一页
    history.forward() //下一页
    ```

## DOM

- [ ]  [P2020、获得DOM节点10:41](https://www.bilibili.com/video/BV1JJ41177di?p=20)

### 操作DOM

- 整个browser网页就是一个DOM树形结构
    - 更新：更新DOM结点，比如换一个style
    - 遍历DOM结点：得到DOM结点
    - 删除DOM结点
    - 添加DOM结点
- 要操作一个DOM结点，必须要先获得这个DOM结点
- DOM结点：基本对照任意element

### 获取DOM结点

- 基础获取方式：
    - `document.getElementsByTagName`
    - `document.getElementById`
    - `document.getElementsByClassName`
- 如果有子node，可以通过`.children`， `.parent.lastElementChild` , `.firstElementChild`
- 注意这里都是原生代码，

```jsx
<div id="parent">
    <h1>header 1 </h1>
    <p id="p1">p1</p>
    <p class="p2">p2</p>
</div>

<script>
    var h1 = document.getElementsByTagName("h1");
    var p1 = document.getElementById("p1");
    var p2 = document.getElementsByClassName("h1");
    var parent = document.getElementById("parent");
    var children = parent.children;
    var lastChild = parent.lastElementChild;
    var firstChild = parent.firstElementChild;
</script>
```

- [ ]  [P2121、更新DOM节点07:43](https://www.bilibili.com/video/BV1JJ41177di?p=21)

### 更新结点

- 可以通过js来操作element的 html, css, JavaScript

    注意驼峰命名

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2053.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2053.png)

- [ ]  [P2222、删除DOM节点06:25](https://www.bilibili.com/video/BV1JJ41177di?p=22)

### 删除结点

- 先获取parent结点，然后通过parent 结点删除自己

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2054.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2054.png)

- 完整实现

    ```jsx
    var self = document.getElementById("p1");
    var parent = p1.parentElement;
    parent.removeChild(p1);
    ```

- 下面的方法也可以，注意array[0]被删除之后，新的array[0]对应之前的array[1]

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2055.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2055.png)

- [ ]  [P2323、创建和插入DOM节点25:45](https://www.bilibili.com/video/BV1JJ41177di?p=23)

### 插入结点

- 获得DOM node之后，假如原本的DOM node为空，通过innerHTML可以增加一个element了，但是这个DOM node 已经存在element, 就不能这样了，会覆盖掉旧的
- 移动结点，追加一个结点（`append`）

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2056.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2056.png)

- 创建新的标签，然后插入

    ```jsx
    var newP = document.createElement("p");
    newP.id="newP";
    newP.innerText='hello, Jessy';
    list.appendChild(newP);
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2057.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2057.png)

- 插入特定标签，设置属性

    `myScript.setAttribute("type","text/javascript")`

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2058.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2058.png)

- 对body进行修改操作

    注意getElements返回的是一个array，需要用[0]

    ```jsx
    var body = document.getElementsByTagName("body");
    body[0].setAttribute("style","background-color:yellow");
    body[0].style.backgroundColor="red";
    ```

- 另一种方法该背景色：再head后面出入一个css标签

    ```jsx
    var myStyle = document.createElement("style");
    myScript.setAttribute("type","text/css");
    myStyle.innerHTML = 'body{background-color:green;}'
    var head = document.getElementsByTagName('head')[0];
    head.append(myStyle);
    ```

- 插在前面`insertBefore(newNode, targetNode)`
    - 在`list`的`ee`前面插入`js`

    ```jsx
    var js = document.getElementBdeyId("js");
    var list = document.getElementById("list");
    var ee = document.getElementById('ee');
    list.insertBefore(js,ee);
    ```

### JQuery文档

[jQuery API 中文文档 | jQuery API 中文在线手册 | jquery api 下载 | jquery api chm](https://jquery.cuishifeng.cn/)

## 操作表单

- [ ]  [P2424、获得和设置表单的值10:26](https://www.bilibili.com/video/BV1JJ41177di?p=24)

### 表单是什么

- 表单也是DOM树种的一个结点
- 常见内容：文本框`text`，下拉框`select`，单选框`radio`，多选框`checkbox`，隐藏框`hidden`，密码框`password`...
- 表单目的：提交信息

### 获得要提交的信息

- 获取填入值 `.value`

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2059.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2059.png)

- 也可以修改content：`input_text.value="yes"`
- 对于单选，多选，value已经定义好，所以需要用`checked` 来判断或者修改，不能再用`value`了

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2060.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2060.png)

## **高级表单验证**

- [ ]  [P2525、表单提交验证及前端密码MD5加密17:53](https://www.bilibili.com/video/BV1JJ41177di?p=25)

### 提交form的方式

1. 用默认的submit方式 `<input type="submit">` ，会出现一个submit按钮
2. 也可以使用button：`<button type="submit" onclick="test_fun()">submit</button>`
    - `onclick` ：点击button之后执行的什么JavaScript代码
    - 比如test_fun

        ```java
        <script>
            function test_fun(){
                alert("test")
            }
        </script>
        ```

### button触发JS

- form中，`<button type="button" onclick="test_fun()"> submit </button>`
- 触发JS，就可以获取用户的填入值

    ```jsx
    function test_fun(){
        var uname= document.getElementById("username");
        var pwd = document.getElementById("password");
        ****console.log(uname.value);
        console.log(pwd.value);
    }
    ```

### 密码加密案例

- 比如，user输入了 111111作为username，222222作为密码
- 但是下面的password自动被加密，其实运行了一个拦截函数-javascript

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2061.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2061.png)

### MD5 工具类

- 在head载入md5类包
- 然后使用md5加密password

    ```jsx
    //MD5算法
    pwd.value=md5(pwd.value);
    ```

### 密码加密过程

- 可以在form中保有两个password项
    1. 客户输入密码，比如input-password

        ```jsx
        <span>password: </span> <input type="text" id="password">
        ```

    2. hidden的真正密码（MD5加密后）

        ```jsx
        <input type="hidden" id="md5" name="password">
        ```

- 设定流程
    - 只显示input password的格子
    - 将input password用md5加密，然后储存在hidden格子对应的value里（用户就不会看到密码突然变长了）
    - 提交的时候，提交的是真正的md5密码格子，和username
    - 注意点击提交 触发的JS 可以设定在`form`层级：`onsubmit="return test_fun()"`

    ```jsx
    <form action="https://www.baidu.com/" method="post" onsubmit="return test_fun()">
        <p><span>username: </span> <input type="text" id="username" name="username"></p>
        <p><span>password: </span> <input type="password" id="input-password"></p>
        <input type="hidden" id="md5-password" name="password">

        <button type="submit">submit</button>
    </form>

    <script>
        function test_fun(){
            var uname= document.getElementById("username");
            var pwd = document.getElementById("input-password");
            var md5pwd = document.getElementById("md5-password");

            md5pwd.value=md5(pwd.value);
            return true;
            }
    </script>
    ```

- 注意input加有`name`的才会显示在form data上

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2062.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2062.png)

## JQuery基础理解

- [ ]  [P2626、初识jQuery及公式08:48](https://www.bilibili.com/video/BV1JJ41177di?p=26)

### JavaScript与jQuery

- JQuery：封装了大量javaScript函数的库

### 获取JQuery

- 官网：[https://jquery.com/](https://jquery.com/)
- 下载：有一个development版，还有一个production版（小）
    - link：[https://jquery.com/download/](https://jquery.com/download/)
        - [https://code.jquery.com/jquery-3.6.0.min.js](https://code.jquery.com/jquery-3.6.0.min.js)
        - [https://code.jquery.com/jquery-3.6.0.js](https://code.jquery.com/jquery-3.6.0.js)
- 也可以搜索Jquery CDN，直接用link

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2063.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2063.png)

### HTML中加载Jquery的方式

- 下载之后，加载到script `<script src="lib/jquery-3.6.0.js"></script>`
- 直接通过link载入到script `<script src="https://code.jquery.com/jquery-3.6.0.js"></script>`
    - 注意这个link可以换成上面搜索的CDN的link

### JQuery基本公式

- `$(selector).action()`
    - `$`: 代表JQuery
    - `selector`：选择器
- 例子

    注意用单引号，外面再用双引号

    ```jsx
    $('#test1').click(function(){
        alert('hello jQuery')
    })
    ```

    等价于

    ```jsx
    var id = document.getElementById("id");
    id.click ...
    ```

- [ ]  [P2727、jQuery选择器05:35](https://www.bilibili.com/video/BV1JJ41177di?p=27)

### JQuery文档查询

- 去这个网站查如何做选择器
- 去查看event
    - 

[jQuery API 中文文档 | jQuery API 中文在线手册 | jquery api 下载 | jquery api chm](https://jquery.cuishifeng.cn/)

### JQuery选择器

- 对比原生写法

```jsx
document.getElementsByTageName();
document.getElementsByClassName();
document.getElementById();

$('p').click()
$('.class1').click()
$('#id1').click()
```

- [ ]  [P2828、jQuery事件08:56](https://www.bilibili.com/video/BV1JJ41177di?p=28)

### JQuery事件

- 网页element加载完完毕之后，响应事件
    - 老版写法：`$(document).ready(function(){})`
    - 新版简化代码 `$(function(){})`
- 例子：
    - 页面加载完自动执行：`$(function(){})`
        - 对divMove框来获取mouse移动的 event
        - 函数中的input就是mouse光标参数，可以设成任意var（习惯设定为e），通过e可以找到光标的特性，比如实时位置`.pageY`, `.pageX`
        - 将在divMove框中捕捉的光标位置，输出在`mouseMove` 框中

    ```jsx
    <head>
    ...
    <script src="https://code.jquery.com/jquery-3.6.0.js"></script>
    <style>
        #divMove{
            width: 500px;
            height: 500px;
            border: 1px solid red;
        }
    </style>
    </head>
    <body>
    <!--获取鼠标-->
    mouse: <span id="mouseMove"></span>
    <div id="divMove">Move your mouse</div>

    <script>
    //网页element加载完完毕之后，响应事件
    $(function(){
        $('#divMove').mousemove(function(e){
            $('#mouseMove').text("x:"+e.pageX+" y:"+e.pageY);        })
    })
    </script>
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2064.png](%E3%80%90%E7%8B%82%E3%80%91JavaScript%205cb8ffa41c6a4c689128b040aa057a28/Untitled%2064.png)

- [ ]  [P2929、jQuery操作Dom元素11:57](https://www.bilibili.com/video/BV1JJ41177di?p=29)

### 操作DOM元素

- 获得、修改text

    ```jsx
    $('#test-ul li[name=python]').text()
    $('#test-ul li[name=python]').text("hello");
    ```

- 获得、修改html

    ```jsx
    $('#test-ul li[name=python]').html();
    $('#test-ul li[name=python]').html('<strong>123</strong>');
    ```

- 修改css

    ```jsx
    $('#test-ul li[name=python]').css("color","red");
    $('#test-ul li[name=python]').css({"color":"red"});
    ```

- element显示和隐藏

    `.hide()`相当于 display = none

    ```jsx
    $('#test-ul li[name=python]').hide();
    $('#test-ul li[name=python]').show();
    $('#test-ul li[name=python]').toggle();//hide->show, show->hide
    ```

- 其他测试

    ```jsx
    $(window).width()
    $(window).height()

    ```

## 小结

- [ ]  [P3030、前端小结及开发技巧分享26:50](https://www.bilibili.com/video/BV1JJ41177di?p=30)

### 未来学习

- 可以去看html游戏源码：[https://www.mycodes.net/166/](https://www.mycodes.net/166/)
    - 无后台设计游戏
- 仿网站
    - 在inspect-elements中，删除没用的（只要不影响页面就删除）
    - 然后将其他剩余的html下载到local
    - 进行修改，先弄个静态的网站

### 参考网站

- 友人c
- vue官网（vue press）
- ant design
- docsify
- Layui - 扩展组件-弹窗组件-弹出层layer
- ElementUI-组件（感觉比bootstrap更好看）

### tips

- 巩固JS：看框架源码（jQuery），看游戏源码
- 扒网站：如何巩固html，css（整个下载，对应修改，或者直接一块一块扣）
- 专业前端会主攻扒网站，扒不扒网站会跟别人拉出很大差距
- 提高审美还是很重要的
