# Contents

## Day01-Git & Github

> 内容: Git介绍、版本控制、Github介绍、Github操作、Git操作

* **Git介绍**
  * Git是一个**工具，用来对文件进行版本控制**
* **版本控制**
  * 什么是版本控制呢？
    * 版本是我们做一个东西，有时它不是一次就完成了的，我们需要迭代进行，所以会产生许多的版本，就像写一篇文章，第一天写了20％，我们可以称为*未完成1*版本，第二天写了80％，可以称为*未完成2*版本，第三天写完了，可以称为*完成1*版本，然后第四天发现有些不足的地方，进行了一些修改，我们称为*完成2*版本，这些产生的所谓*未完成1/2*,*完成1/2*就称为**版本**，而控制，就是管理这些版本，例如我们想从*完成2*切换到*完成1*的这个过程就可以称为**版本控制**
  * 为什么要版本控制呢？
    * 接写文章那个例子，我们想从*完成2*切换到*完成1*，凭我们的记忆是很难记住都修改了哪些内容的，所以如果有一个工具可以帮助我们记录这些是非常方便的
    * 想象一个具体的场景，你打开了电脑，在桌面新建了一个文件夹*GoodDay*，然后在这个文件夹内存储了一个名为*a.txt*的文件，然后进行了编辑，写入了内容*123*，保存关闭，我们称它为*版本1*，到了第二天，把*123*删除了，又写入了新的内容*456*，我们把它称为*版本2*；如果我不借助任何工具，想从*版本2*切换到*版本1*呢？如果我们记忆好，我们知道*版本1*的内容是*123*，我们可以很简单的打开文件删掉*456*，改为*123*；可我们现在接触的是成千上万行的代码，我们很难记住曾经的修改，所以我们需要一个工具来进行版本控制
  * 如何进行版本控制呢？
    * 我们有一个工具名为**git**，git是一种分布式的版本管理系统，Linux的创造者Linus写的[[1]](https://www.zhihu.com/question/27470418),有了git我们只需要记住几个命令，而不用记住我们修改过的内容了

* **Github介绍**
  * **Github**我们可以将其理解为是一个*移动U盘*，可以用来存储文件，例如那个我们修改的*a.txt*文件；移动意味着我们可以在不同的电脑上去操作这个*a.txt*文件，也可以与不同的人共同去操作这个文件；而这背后一切都是使用**git**这个工具，所以git和github是一对好伙伴
  * 举个例子，假如我们有两台电脑(A电脑在地球上和B电脑在月球上),我们居住在月球上，但是在地球上工作，我在地球上A电脑上修改了a.txt文件，然后到了晚上回到月球上，此时我还想继续修改一下a.txt文件该怎么办呢？这时Github就派上用场了，我们可以用git这个工具将我们修改的文件上传(git中的命令对应push)到Github上，晚上回到月球，再将文件下载(git中命令对应pull)下来，这样一来，就解决这个问题

* **Github操作**
  * 设置Github账号

  > Notice: 由于Github取消了用密码访问，所以我们需要设置另外一种方式去访问的Github，叫Token <br> *remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead. remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.* 

  * Settings / Developer settings / Personal access tokens / Generate new token
  * New (Create a new repository)

* **Git操作**
  * Git中的几个概念
    * repository: 仓库 - 仓库可以简单的理解为就是*GoodDay*这个文件夹
    * branch：分支 - 默认分支名为master如果没有设置过任何分支的话
    * index: 索引 - 将其理解为本地的暂存区，存储了我们修改了的文件，并且已经是纳入版本控制中了
  * Git的几个关于初始的命令
      ```bash
      # 新建一个仓库
      > git init
      # 查看当前分支
      > git branch
      # 查看当前仓库状态
      > git status
      # 设置邮箱与用户名
      > git config user.email "aaaronmack@gmail.com"
      > git config user.name "Aaron"
      # 添加远程仓库地址 (也就是那个移动U盘的地址)
      > git remote add origin https://github.com/<YourName>/<RepositoryName>.git
      ```
  * 记住几个常用的命令
    ```bash
    # 添加修改到暂存区
      > git add .
    # 提交本次修改
      > git commit -m "<YourComment>"
    # 提交内容到github
      > git push
    # 第一次提交内容到github
      > git push -u origin master
    # 查看所有的提交
      > git log --oneline
    # 切换到某个版本 (根据某次提交的Hash码) 注意: 切换完毕后要再切换回master分支
      > git checkout <HashCode>
    # 切换到master分支
      > git checkout master
    # 拉取上次的提交 (不同电脑，不同伙伴之间的提交)
      > git pull
    ```

## Day02-Docsify & Markdown

> 内容: Docsify介绍、图床介绍、Markdown介绍

**工欲善其事，必先利其器。**

* **Docsify介绍**
  * Docsify可以将你的Markdown文件生成为**一个网站**，首先它会加载和解析你的**Markdown文件**，然后将它们经过渲染处理并**显示为一个非常美观的网站**可供浏览；在我们做笔记时，当然不止一个笔记文件，会有很多笔记文件，如果没有这个工具，会非常的不便于管理，而使用这个工具后，我们将我们的笔记整理的很简洁，也便于查找
  * (这个大家使用我已经配置好的一套模板就可以啦，然后只需要修改或者新建自己的.md文件)

* **图床介绍**
  * 将我们的图片存储到Internet上，而非本地，只要我们有网络既可以随时访问我们存储的图片
  * 可以收藏这个[地址](picx.xpoet.cn)，填入我们的Token并配置好之后，那么以后可以从这里上传我们的图片

* **Markdown介绍**
  * Markdown是一种轻量级标记**语言**，用于使用纯文本编辑器**创建格式化文本**,文件后缀为.md，当我们写好我们的.md文件后，就可以使用**Docsify**将我们的markdown文件(也就是我们做的笔记)生成我们的网页来浏览了

* 链接
  * [Docsify](https://docsify.js.org/#/)
  * [Latex-Math](https://latex.codecogs.com/eqneditor/editor.php)
  * [PicX 图床](https://github.com/XPoet/picx)


## Day03-JavaScript & TypeScript

> 内容: HTML CSS JS介绍、JavaScript基础、TypeScript基础

* **词汇表Glossary**
  * Variable 变量
  * Operator 运算符
  * Function 函数
  * Object 对象
  * Array 数组
  * Condition Statement 条件语句
  * Loop Statement 循环语句
  * Class 类

* *index.html*

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
  <title>Page Title</title>
</head>
<body>

  <h1>This is a Heading</h1>

  <h2>This is a JavaScript Example</h2>

  <script src="script.js"></script>

  <button type="button" onclick="MyFunction()">
  Click me to display Date and Time.</button>

  <p id="demo"></p>

</body>
</html>
```

* *style.css*

```css
h1 {
  color: orange;
  text-align: center;
}
```

* *script.js*

```javascript
function MyFunction(){
	document.getElementById('demo').innerHTML = Date()
}
```

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/life/Html-example.6hc9xee52ec0.webp" width="790"></div>

  * 当点击了 **Click me to display Date and Time**这个按钮后网页显示了当前的时间

* **HTML CSS JS介绍**
  * HTML: 网页显示的内容
  * CSS: 网页显示内容的样式、布局等
  * JavaScript: 在网页端定义了用户如何与网页交互；是一门编程语言，简称JS，就像Python、C++一样

  * 大家可以仔细阅读上述的三个文件总共20几行代码再结合介绍当中的内容，来查看它们之间是如何"各司其职"的；html是网页的主体内容，包括按钮以及两个标签的内容，css更改了html网页中h1这个标签的颜色以及文本对齐方式，当网页的按钮点击了之后，调用了MyFunction这个函数，而这个函数将内容改为当前的系统时间，是不是很奇妙？所以说HTML+CSS+JS构成了网页的**三大基石**

> 其它几个易混淆的概念

  * ECMAScript: 一种JavaScript标准，旨在确保网页在不同浏览器之间的互操作性；就像质量标准，你符合我制定的质量标准，那么就是质量合格的产品
  * Node.js: JS的运行时环境；可以理解为外部独立执行JS代码的一个运行环境 (上方的例子是只能由浏览器来执行，当想在外部执行JS代码时就需要Node.js)
  * Web Browsers JavaScript Engine：用于执行JS代码，可以理解为浏览器内部执行JS代码的一个运行环境；主流浏览器都带有JSEngine
  * TypeScript: Js的超集；强调了类型声明，是强类型，而JS是弱类型;并且还有一些错误检查，其本质是用tsc(TypeScriptCompiler)将ts代码编译为js代码

* **JavaScript基础**

> Variable/变量

```javascript
// 这是注释，将不会执行 (单行)
/* 这也是注释,
  也不会执行
  (多行)*/

var a = 5;  //定义了一个变量a，被赋值为5
let b = 6; // 同样定义了一个变量b，但不可以被再次定义 e.g. let b = 10;就会报错
const p = 7; //const为常值，意味着不能被重新赋值，不能被再次定义

// 变量类型
let length = 16;                               // Number
let lastName = "Johnson";                      // String
let x = {firstName:"John", lastName:"Doe"};    // Object
let b = 1==1;                                  // Boolean

typeof(length)
```

> Operator/运算符

```javascript
// 算数运算符
+    加
-    减
*    乘
/    除
**   幂
%    取模
++   增长一个单位 //例如 var a = 5; a++结果为6，a--结果为4
--   减少一个单位

//赋值运算符 (更多: https://www.w3schools.com/js/js_operators.asp JavaScript Assignment Operators)
=    赋值 //例如 x=5; y=x;将x的值赋给y，那么y也就等于5了
+=   相加再赋值 //例如 x+=y; 与x=x+y是等价的

//逻辑运算符
&&   与 //真真为真，真假为假，假假为假
||   或 //真真为真，真假为真，假假为假
!    非 //真为假，假为真

//位运算符 (更多: https://www.w3schools.com/js/js_operators.asp JavaScript Bitwise Operators)
...

//比较运算符
==   值是否相等  //例如x=5;这里是number5,如果有另一个y="5"这里是字符串5,判断x==y,则会得到true的结果
===  不仅值是否相等，并且类型也要相等
!=   值是否不等
!==  值是否不等或类型不等
>    大于
<    小于
>=   大于等于
<=   小于等于

//一些例子 (可以在cmd中启动node，然后手动输入这些去练习)

let x = 100 + 50; 

let a = 2;
let x = (100 + 50) * a;

let x = 5;
x++;

let x = 5;
let y = 3;
let r = (x<10 && y>1) // is true
```

> Function/函数

* 为什么使用函数？函数是为了我们可以重复使用一段代码块；并且可以定义一些参数，让函数有不同的行为

```javascript
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}

let x = myFunction(5,6); //函数调用,并将返回结果赋给变量x
let result = "The result is " + myFunction(5,6); //也可以搭配一起使用
```
  * 可以把函数想象成一个自动售货机，一个机器，喂入两个硬币，这里也就是参数p1,p2，返回可乐给你，在这里也就是函数返回结果p1*p2两个数相乘的结果
  * **function**是关键字，声明我们在这里定义一个函数，**return**是返回结果的关键字，告诉程序函数已经返回结果并执行完毕了

> Object/对象

* [图片-Variable与Objects的比较](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/life/Comparison-of-knives-and-multipurpose-knives.4ohozsvd07s0.webp)

* 与c++中的结构体比较像，可以定义不同类型的变量以及函数，可以这样理解，单个变量和单个函数都是一个小铅笔刀，而Objects是一个多功能的会变形的铅笔刀

```javascript
const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
}; //我们可以看到定义了不同的变量类型，还有函数

//使用，与之前一样，只不过多了前缀对象名
person.id
person.firstName
person.fullName()
```

> Array/数组

* 为什么使用数组？我们将相同的一组事物放到一起这样便于操作与管理

```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars[0]
let car = cars[2]; //使用索引来取值和赋值
cars[1] = "B";
cars.push("A"); //添加新元素到cars这个列表中
```

> Conditional Statement/条件语句

```javascript
let age = 10;
if (age < 10) {
  // Little boy
} else if (age < 20) {
  // Young boy
} else {
  // Big Man
}
```

> Loop Statement/循环语句

```javascript
// for 循环
const cars = ["A", "B", "C"]
for(let i=0; i < cars.length; i++){
  console.log("Car name: " + cars[i])
}

for(let i in cars){
  console.log("Car name: " + cars[i])
}

for(let x of cars){
  console.log("Car name: " + x)
}

// While 循环
var i = 5;
while (i < 10) {
  i++;
  console.log("The number is " + i);
} //Output: 6,7,8,9,10

// ---- 如果想要在i等于8的时候就让循环终止呢？
//      就需要用到break关键字了
i = 5;
while (i < 10) {
  i++;
  console.log("The number is " + i);

  if(i == 8){
    break;
  }
} //Output: 6,7,8

// ---- 如果不仅想要在i等于8的时候终止循环，
//      并且还想要在i等于7的时候跳过这次循环该怎么做呢？
//      就需要用到continue关键字了
i = 5;
while (i < 10) {
  i++;
  if(i === 7){
    continue;
  }
  console.log("The number is " + i);

  if(i == 8){
    break;
  }
}//Outputs: 6,8
```

> Class/类

* 什么是类?
  * 类和Object很像，当远不止这些，一个类可以拥有更多的结构，这些结构就是面向对象(包括**封装、继承、多态**)的这些特性
  * 我们生存的世界可以进行**抽象**，把一些具有共同特征和行为的事物抽象为一个集合,例如动物代表某一类集合，他们共同的特征有颜色，行为有叫这个动作，而猫，狗就是这一类集合中两个事物，猫有黄色、黑色、等等，当发出叫声是*喵miao*的声音；狗也有颜色，叫声是*汪wang*的声音，我们把这些事物，在这里就是动物、猫和狗称为**类**；而面向对象就是围绕这个类而展开的
* 面向对象三大特性
  * **封装**: 封装就是**隐藏**类内部的一些细节，我们不需要知道，我们只需要知道它表现出来的行为就可以了，例如动物发出叫声的时候，可能经过大脑先发出信号，然后控制声带发出声音等等一系列的行为才最终表现出来了叫这个行为，而这些内部的隐藏的过程与细节就叫做封装
  * **继承**: 我们知道动物这个类有颜色特征与叫这个行为，而猫和狗又都是属于动物，所以猫和狗呢就"天生的"**继承**了这些**特征与行为**，就像子承父业，例如我们定义个Animal动物这个类，Animal有一个属性color和一个行为叫shout；猫和狗属于动物这个类别，就是猫Cat和狗Dog继承了Animal这个类，所以Cat和Dog"天生的"继承了Animal这个类的所有属性与行为，在这里也就是继承了颜色color和行为shout，这就叫继承
  * **多态**: 我们知道，虽然动物都有颜色这个特征和叫这个行为，但每个动物的颜色都是不一样的，叫声也是不一样的，例如猫叫声是喵，而狗的叫声是汪，这种**同一类事物的不同行为我们称之为多态** (<span style="color:green">看，这些都是与我们的生活所息息相关的</span>)

```javascript
class Animal {
  constructor(color) {
    this.color = color;
  }

  shout(){
    console.log("XXX~");
  }
}

class Cat extends Animal {
    constructor(color) {
        super(color);
    }
    shout() {
        console.log("Miao~");
    }
}

class Dog extends Animal {
    constructor(color) {
        super(color);
    }
    shout() {
        console.log("Wang~");
    }
}
class Bird extends Animal {
      constructor(color) {
        super(color);
    }
}

let cat = new Cat("Orange");
let dog = new Dog("Yellow");
let bird = new Bird("white");
cat.shout();
dog.shout();
bird.shout(); 

//Outputs: XXX~ 
//我们忘记了给bird定义叫这个行为了
//所以用回了默认的动物的叫声
```

  * extends关键字表示继承关系；每个动物都定义自己的shout行为就是多态，封装在这里没有体现出来，是由于一些其它的原因，有兴趣可以去了解~

* **TypeScript基础**

  * 一个简单的例子
    * 在下方这个代码中，`user.location`是没有定义的；在js中，user.location会返回给你一个**undefined**，并不会让程序终止；通常这不是我们想要的，因为这会让将来的程序很难找到错误；所以typescript出现了，我们可以将下方的代码保存后缀为`.ts`,然后执行`tsc test.ts --noEmitOnError`看看会发生什么？我们会得到`error TS2339: Property 'location' does not exist on type '{ name: string; age: number; }'.`<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/cmd-tsc.3v52rujquqg0.webp"></div>
    * 总的来说，**TypeScript**就是帮助我们检查我们在使用js中可能出现的任何类型的错误，提升我们的**效率**

  * *test.ts*
  ```js
  const user = {
    name: "Daniel",
    age: 26,
  };
  user.location; // returns undefined
  ```

  * *error_example.js*

  ```js
  // ----> 1 not callable
  const message = "Hello World!";
  
  message();
  
  // ----> 2 not defined
  const user = {
      name: "Daniel",
      age: 26,
  };
  user.location;
  
  // ----> 3 typos
  const announcement = "Hello World!";
  
  // How quickly can you spot the typos?
  announcement.toLocaleLowercase();
  announcement.toLocalLowerCase();
  
  // We probably meant to write this...
  announcement.toLocaleLowerCase();
    
  // ----> 4 uncalled functions
  
  function flipCoin() {
      // Meant to be Math.random()
      return Math.random < 0.5;
  }
  
  // ----> 5 basic logic errors
  const value = Math.random() < 0.5 ? "a" : "b";
  if (value !== "a") {
    // ...
  } else if (value === "b") {
    // Oops, unreachable
  }
  
  // ----> 6 arguments miss
  // This is an industrial-grade general-purpose greeter function:
  function greet(person, date) {
      console.log(`Hello ${person}, today is ${date}!`);
  }
  
  greet("Brendan");
  ```

  * *example.ts*

  ```js
  // ----> 1 Function parameter type declaration & Downleveling
  function greet(person: string, date: Date) {
      console.log(`Hello ${person}, today is ${date.toDateString()}!`);
  }
  
  // greet("Maddison", Date());  // error: Argument of type 'string' is not assignable to parameter of type 'Date'.
  greet("Maddison", new Date());
  
  "use strict"; // like preventing you from using undeclared variables.
  function greet1(person, date) {
      console.log("Hello " + person + ", today is " + date.toDateString() + "!");
  }
  greet1("Maddison", new Date());
  ```
  
  * tsc命令行参数
    * `tsc --noEmitOnError`
      * more strictly,当检查到错误时不会生成.js文件

* 链接
  * [1] The TypeScript Handbook https://www.typescriptlang.org/docs/handbook/intro.html
  * [2] JavaScript Tutorial https://www.w3schools.com/js/default.asp
  * [3] Object Oriented Programming in JavaScript – Explained with Examples https://www.freecodecamp.org/news/how-javascript-implements-oop/
  * [4] JavaScript有多态吗？有的话怎么实现？ https://www.zhihu.com/question/33596850

## Day04-Math Basis

> 内容: 方程与行列式、方程与坐标轴、坐标基矢与变换、变换复合、转置、对偶矢量、余弦定理、点乘、叉乘、线性变换(缩放、非均匀缩放、反射、错切、旋转)、平移与齐次坐标、重心坐标

* **词汇表Glossary**
  * determinant 行列式
  * equation 方程
  * coefficient matrix 系数矩阵
  * area 面积
  * coordinate axis 坐标轴
  * polar coordinate system 极坐标系
  * coordinate basis vector 坐标基矢
  * transformation 变换
  * scale 缩放
  * Non-Uniform scale 非均匀缩放
  * reflection 反射
  * shear 错切
  * vector 向量
  * rotate 旋转
  * translation 平移
  * homogenous coordinates 齐次坐标
  * coordinate component 坐标分量
  * complex transformation 复合变换
  * transpose 转置
  * projection 投影
  * dot product 点乘
  * cross product 叉乘
  * dual vector 对偶矢量
  * linear transformation 线性变换
  * affine transformation 仿射变换
  * interpolation 插值
  * barycentric coordinates 重心坐标

* **方程与行列式**

有一个方程，我们试着解一下$$\begin{array}{l} \left \{ \begin{matrix}  5x+6y=7 \ \ (1) \\ 9x+4y=3 \ \ (2) \end{matrix} \right. \end{array}$$我们用消去法$$\begin{array}{l} (2) \times \frac{5}{9} - (1) \\ (1)\times \frac{4}{6} - (2) \end{array}$$最终可以得到$$\begin{array}{l} y(5\times 4-6\times 9)=3\times 5-7\times 9 \\ x(5\times 4-6\times 9)=7\times 4-6\times 3 \end{array}$$

大家有没有注意到$x$和$y$后面的$$(5\times 4-6\times 9)$$他们是一样的，所以为了简化计算，我们将这个$(5\times 4-6\times 9)$拿出来排列成$$\left ( \begin{matrix} 5 & 6 \\ 9 & 4 \end{matrix} \right ) $$这样一组数,再定义$$\left ( \begin{matrix} 5 & 6 \\ 9 & 4 \end{matrix} \right ) = 5\times 4 - 6\times 9$$叫做**行列式**, 而$\left ( \begin{matrix} 5 & 6 \\ 9 & 4 \end{matrix} \right ) $也是方程中的系数(称作**系数矩阵**)，通用格式就是$$\left ( \begin{matrix} a&b \\ c&d \end{matrix} \right ) = ad-bc$$

---

再看另外一个方程$$\left \{ \begin{matrix}  1x+0y=0 \\ 0x+1y=0 \end{matrix} \right.$$ 列出系数矩阵形式$$\left ( \begin{matrix} 1 & 0 \\ 0 & 1 \end{matrix} \right )$$

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘二维坐标系.qt5rv7k809s.webp" width="490"></div>

观察图中我们看到如果我们把$(1,0)$和$(0,1)$"围起来"，我们会得到一个正方形，在应用我们刚刚学的的行列式的计算方法，我们正好得到一个数字$1\times 1-0\times 0=1$，(同样的$2\times 2-0\times 0=4$，面积为4)，如果我们抛开坐标系不谈论，就单纯的把围成的区域看做是一个正方形，它的面积正好为1，不是吗？那是不是我们可以把**行列式与面积联系起来**呢？答案是：可以，我们再来看另外一个例子，我们现在讨论的是(1,0)和(0,1)下围成的区域，它正好是一个正方形，那么其它的情况呢？

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/行列式的一般情形.7gtqx3nj4x80.webp" width="790"></div>

我们两个坐标$(a,c)$和$(b,d)$系数矩阵为$\left ( \begin{matrix}  a & b \\ c & d \end{matrix} \right )$,现在形成的面积是一个平行四边形，经过计算后我们发现也满足。

* **方程与坐标轴**

我们从方程出发，知道了行列式这么一个家伙，下面再来看看方程是什么，方程中的**等号**是问题的核心

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘一维坐标轴.2fvv0l7brt7o.webp" width="590"></div>

我们先定义**坐标轴**这个家伙，首先定义一条直直的线，然后我们再在这条线上定义一些单位，也就是**刻度**(1,2,3...)等，这些都是我们定义的，刻度$1$可以代表任何事物，例如一个苹果，移动了一米等等都可以，而这条直线呢，也是我们定义的，就像我们走路都是直直的前往某个地方，所以为了刻画这种东西，所以我们定义坐标轴也为直的，如果我们每个人都走路是沿曲折的曲线前进，那么我们的坐标轴估计也就是弯弯曲曲的了 (只是猜测)，好了，我们定义完了"坐标轴"，来看一个例子

首先让我们来思考个问题，先假设$(0,)$到$(1,)$之间表示$1$米，假设小红站在$(0,)$点不动，小明从$(0,)$出发走到了$(2,)$这个位置，走了$2$米，请问，小红需要走多少个$1$米就可以达到小明现在的位置，我们假设需要走$x$个$1$米就可以达到小明的位置，表现为方程就是$1x=2,x=2$,小红需要走$2$个$1$米这么长的距离才可以达到小明的位置，这就是**方程**，描述两个事物之间的相等关系，其中等号是核心，只不过在一维情况下，比较简单，到了二维时，就要稍微复杂那么一丢丢了

---

这里举一个简单的二维情况下，我们还是以小明和小红走路这个例子为例，前面是在数轴上，他们可以活动的范围太小了，只在一条线上，我们现在把它扩大到一个平面上，现在取两条数轴，还有刻度，然后再让这两条数轴垂直，像$(x,y)$那样，那么能不能斜着呢？可以，只不过这些都是与我们的生活相贴近的，就像展开的地球，如果我们生活的地方就像第二张被错切之后的那样,其中的任何事物都是错切的形状，那估计我们的坐标系也就是会是那样定义了，就像$(x',y')$那样 (只是猜测)

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘二维斜坐标系.51qcwl4w6hg0.webp" width="590"></div> (二维坐标系，两条不相互垂直的坐标轴，就像我们所生活的世界，我们在一个巨大的平面上)

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/世界地图展开.6s0a9v3ifao0.webp" width="490"></div>

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/世界地图展开-shear.5a4qowcfi4k0.webp" width="490"></div>

现在把这两个数轴放到一个平面中去，那么我们的维度就上升了一个层面，定义完之后，也就是说，我们不仅可以左右移动了，也可以上下移动了

假设我们在$(0,0)$点，想要前往到$(2,2)$点，我们能想象得到也比较直观的就是，沿着左右方向中的右那个方向走$2$个单位，然后再沿着上下方向中的上那个方向走$2$个单位，就到了$(2,2)$，你们可能想，这也太麻烦了，我直接从$(0,0)$到$(2,2)$之间连一条线，然后沿着那条线走不就行了嘛，是的，**这就是极坐标系的由来，我们看待同一种问题的不同视角**，这里我们先讨论直角坐标系

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/二维坐标移动行程例子.6iwav4dmdck0.webp" width="590"></div>

回到问题，$(0,0) \rightarrow (2,2)$, 分开来看，就是先往右移动$2m$到达$p1$，再往上移动$2m$到达$p2$，设往右移动$x$个$1m$才能到达$p1$处,然后往上移动$y$个$1m$才能到达$p2$处, 则我们有$$\begin{array}{l} \left \{ \begin{matrix} 1x=2 \\ 1y=2 \end{matrix} \right.\\ \left \{ \begin{matrix} x=2\\ y=2 \end{matrix} \right. \end{array}$$ 往右移动$2$个$1m$才能到达$p1$处，然后往上移动$2$个$1m$才能到达$p2$处，**这就是方程，希望到了这里，我们已经建立起了方程与行列式，方程与坐标轴，且行列式的那种表示形式，后面我们就会知道，这种表示形式就是矩阵**

* **坐标基矢与变换**
  * **坐标基矢**
    * 坐标基矢是我们人为定义的事物；一维情形下就是数轴上$0$到$1$之间那个距离，记为$$(1,)$$二维有两个坐标轴，分别为$$(1,0)$$ 叫做$i$帽，符号记为$\hat{i}$和$$(0,1)$$叫做$j$帽，符号记为 $\hat{j}$ <div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘坐标基.2pvxzz9z2es0.webp" width="790"></div>刚才我们未引入坐标基矢，引入坐标基矢后，现在就有了一种统一的形式，上述例子的完整情况为$$\left \{ \begin{matrix} 1x+0y=2 \\ 0x+1y=2 \end{matrix} \right.$$ 矩阵形式$$\left ( \begin{matrix} 1 & 0 \\ 0 & 1 \end{matrix} \right ) \left ( \begin{matrix} x \\ y \end{matrix} \right ) = \left ( \begin{matrix} 2 \\ 2 \end{matrix} \right ) \ \ (x=2,y=2)$$
    * 其实我们可以看到，我们想要去到的那个点$(2,2)$，本质上就是我们定义的坐标基矢(i帽和j帽)<span style="color:green">"去到了"</span>点$(2,2)$,我们把这种<span style="color:green">"去到了"</span>哪里，称为**变换**
    * $x=2, y=2$是满足方程的一组数，也就是**坐标基矢变化的量** 这样，每当我们看到像$\left ( \begin{matrix} 2\\2 \end{matrix} \right )$都应想起是笛卡尔坐标系中的两个**坐标基矢的变换**, 像$\left ( \begin{matrix} 1\\1 \end{matrix} \right )$可以看做$$\left ( \begin{matrix} 1 & 0 \\ 0 & 1 \end{matrix} \right ) \left ( \begin{matrix} x \\ y \end{matrix} \right ) = \left ( \begin{matrix} 1 \\ 1 \end{matrix} \right ) \ \ (x=1,y=1)$$只不过这两个坐标基没有产生任何的变化; 再如$\left ( \begin{matrix} 2\\2 \end{matrix} \right )$可以看做$$\left ( \begin{matrix} 2 & 0 \\ 0 & 2 \end{matrix} \right )$$ 为了便于描述，我们还通常给我们要去的$(2,2)$那个点称作**向量**，不仅有方向还有箭头，如$\vec{a}=(2,2),\ a_1=2, \ a_2=2$这是在二维的情形下

---

* **变换复合**
  * 变换是可以复合的考虑一组数$$\left ( \begin{matrix} -1 \\ 1 \end{matrix} \right ) 和 \left ( \begin{matrix} 2 \\ 2 \end{matrix} \right )$$其中$\left ( \begin{matrix} 2 \\ 2 \end{matrix} \right )$我们知道是由$\left ( \begin{matrix} 2 & 0 \\ 0 & 2 \end{matrix} \right )$变换而来，而$\left ( \begin{matrix} -1 \\ 1 \end{matrix} \right )$是由$\left ( \begin{matrix} -1 & 0 \\ 0 & 1 \end{matrix} \right )$变换而来，我们是可以将这两个变换组合到一起的,组合到一起最终就是$$\left ( \begin{matrix} -1 & 0 \\ 0 & 1 \end{matrix} \right )\left ( \begin{matrix} 2 & 0 \\ 0 & 2 \end{matrix} \right )$$其中变换计算的顺序是从右到左的，如果交换顺序，结果不一定相等；其中后者这个变换如之前一样，在图像上来看，就是缩放，那么前者呢？就是$i$帽从$(1,0)$变到了$(-1,0)$去，$j$帽保持不变，这种变换就像我们平常看书时翻页一样，叫做**Reflection反射**
  * 最终结果就是从坐标基(①)开始先作用缩放(②)最后作用反射(③)<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘复合变换.7kd8flleofs.webp" width="790"></div>

* **转置**
  * 假设我们有一个矩阵$$A=\left ( \begin{matrix} 5 & 6 \\ 9 & 4 \end{matrix} \right )$$它表示了从$2$维到$2$维空间的变换，对应任意的$m*n$矩阵，都表示一个从 n 维空间到 m 维空间的变换，例如我们有一个$1*2$矩阵$\left ( \begin{matrix} 1 & -2 \end{matrix} \right )$，它表示了一个从2维空间到1维空间的变换，如图中我们可以看到$(1,-2)$变换到了$-1$<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/2维到1维的变换.3zimar96skc0.webp" width="520"></div>可以想象成一部机器，喂入两个数，得到一个数，具体的操作过程与**投影**有关,就像一个小人在数轴上，先移动了$1$步，然后又移动了$-2$步，那么最终看来，这个小人只移动了$-1$步,即后退了一步
  * 而转置呢，操作上来说就是*行变为列，列变成行*，转了一下，例如$$\left ( \begin{matrix} 1 & -2 \end{matrix} \right )$$转过来就是$$\left ( \begin{matrix} 1 \\ -2 \end{matrix} \right )$$ (即我们应当结合维度变换的角度去理解转置)
  * 将这些操作转换成代数上就是$$\left ( \begin{matrix} 1 & -2 \end{matrix} \right ) \cdot \left ( \begin{matrix} 1 \\ 1 \end{matrix} \right ) = 1\cdot 1+ (-2\cdot 1)=-1$$我们使用$\cdot$这个小点来表示这种"走了1步，又走了-2步"这种计算，而这种计算呢，又恰巧就是我们待会要讲到的**点乘**
  * 补充：关于更加详细的**坐标变换**， 见链接[1]-线性代数的本质
* **对偶矢量**
  * 给定一个**矢量**,如果存在这样一个**映射**,它把给定的矢量映射为一个实数,就说这个映射是**对偶矢量**。例如一个$n$维行向量$$(a_1,a_2\cdots a_n)$$它既可以理解为**行向量**,也可理解为某种**映射**,该映射把给定的$n$维**列向量**$$\left ( \begin{matrix} b_1\\b_2 \\ \cdots \\ b_n \end{matrix}\right )$$(矢量)映射为实数$k$, $$k=a_1b_1+a_2b_2+\cdots+a_nb_n$$即矩阵的乘积。则这个映射满足对偶矢量的定义,因此行向量$(a_1,a_2\cdots a_n)$是矢量$\left ( \begin{matrix} b_1\\b_2 \\ \cdots \\ b_n \end{matrix}\right )$的对偶矢量。

* **余弦定理**
  * 余弦定理是描述**三角形中三边长度与一个角的余弦值关系**的数学定理，是**勾股定理在一般三角形情形下的推广**，勾股定理是余弦定理的特例<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/Law-of-Cosines.46vagpeucam0.webp" width="790"></div>$$\begin{array}{l}a^2=b^2+c^2-2bc\ cos A \\ b^2=a^2+c^2-2ac\ cos B \\ c^2=a^2+b^2-2ab\ cos C \\ cos A = \frac{-a^2+b^2+c^2}{2bc} \\ cos B = \frac{a^2-b^2+c^2}{2ac} \\ cos C = \frac{a^2+b^2-c^2}{2ab} \\ \end{array}$$
  * **延伸**
    * 根据$$\cos^2A+sin^2A=1$$
    * 我们有$$\cos A=\frac{a^4+b^4+c^4-2a^2b^2+2b^2c^2-2a^2c^2}{4b^2c^2} $$$$ \sin A=\sqrt{1-\cos^2a}=\sqrt{\frac{4b^2c^2}{4b^2c^2}-\frac{a^4+b^4+c^4-2a^2b^2+2b^2c^2-2a^2c^2}{4b^2c^2}}$$$$ =\sqrt{\frac{4b^2c^2-(a^4+b^4+c^4-2a^2b^2+2b^2c^2-2a^2c^2)}{4b^2c^2}}$$$$ =\frac{\sqrt{-a^4-b^4-c^4+2b^2c^2+2c^2a^2+2a^2b^2}}{2bc}$$
    * 三角形面积有$$\Delta=\frac{1}{2}bc \sin A$$
    * 代入$\sin A$有$$\Delta=\frac{1}{4}\sqrt{(a+b+c)(-a+b+c)(a-b+c)(a+b-c)}$$ (排列组合)

* **点乘 Dot Product**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/点乘.78lv308m6p80.webp" width="290"></div>
  * 点乘我们通常用于衡量两个向量的方向差，或者衡量"做功"的大小，通常我们将它们单位化，然后再计算，这样取值范围就在$-1$到$1$之间，例如两个向量共向，那么值为$1$，反向则为$-1$，垂直为$0$
  * **代数定义**
    * 两个向量${\displaystyle {\vec {a}}=[a_{1},a_{2},\cdots ,a_{n}]}$和${\displaystyle {\vec {b}}=[b_{1},b_{2},\cdots ,b_{n}]}$的点积定义为$$\begin{aligned} \vec{a}\cdot \vec{b} = \sum_{i=1}^{n} a_ib_i \end{aligned}$$其中$n$是维度，在2维情况下就是$a_1b_1+a_2b_2$,例如$$\left ( \begin{matrix} 5_{(a_1)} & 6_{(b_1)} \\ 9_{(a_2)} & 4_{(b_2)} \end{matrix} \right )$$就是$5\times 6+9\times 4$ （这里需要注意与行列式的计算是不一样的，行列式是$5\times 4-6\times 9$）**这里点乘的计算和我们在转置那里讲到的投影是一回事**
  * **几何定义**
    * 在欧几里得空间中，点积可以直观地定义为$${\displaystyle {\vec {a}}\cdot {\vec {b}}=|{\vec {a}}|\,|{\vec {b}}|\cos \theta \;}$$其中$\theta$为两向量之间的夹角
  * **推导**
    * 两个定义之间是等价的并可以互相推出
    * 根据余弦定理则我们有$$|| a-b ||^2 = ||a||^2+||b||^2-2||a||\ ||b||cos\alpha$$展开得$$\begin{aligned} \sum^{n}_{i=1}(a_i-b_i)^2 =\sum^{i=1}_{n}a_i^2+\sum^{n}_{n=1}b_i^2-2||a||\ ||b||cos\alpha \end{aligned}$$在二维情况下展开有$$\begin{aligned} (a_1^2+b_1^2-2a_1b_1)+(a_2^2+b_2^2-2a_2b_2) = a_1^2+a_2^2 + b_1^2+b_2^2 - 2||a||\ ||b||cos\alpha \end{aligned}$$消去所有的$a_1^2,\ b_1^2$整理后有$$-2a_1b_1 + (-2a_2b_2) =  - 2||a||\ ||b||cos\alpha$$两边再同除以$-2$有$$a_1b_1 + (a_2b_2) = ||a||\ ||b||cos\alpha = \vec{a}\cdot \vec{b}$$ 同样可以推广到$n$维 □
  * **点乘在投影上的应用**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/DotProductForProjection.20f8sxq8tejk.webp" width="390"></div>
    * 计算出向量$\vec{b}$在$\vec{a}$上的投影值,则有$||\vec{b}_{\perp}|| = ||\vec{b}||cos\theta$ 
* **叉乘 Cross Product**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/叉乘.1eb9eyex849s.webp" width="290"></div>
  * 叉乘只在三维中有定义，<span style="color:purple">两个向量的叉乘可以产生一个与这两个向量都垂直的新向量</span>。例如计算一个物体表面的法向量
  * **叉乘定义**$${\displaystyle \mathbf {a} \times \mathbf {b}=\left\|\mathbf {a} \right\|\left\|\mathbf {b} \right\|\sin(\theta)\mathbf{n}}$$其中$\theta$表示$\mathbf{a}$向量和$\mathbf{b}$向量之间的夹角，而 ${\displaystyle \mathbf {n} }$则是一个与${\displaystyle \mathbf {a} }$、${\displaystyle \mathbf {b} }$所构成的平面垂直的单位向量，方向由右手定则决定 [[Wikipedia]](https://zh.wikipedia.org/wiki/%E5%8F%89%E7%A7%AF)
  * **模长计算**$${\displaystyle \left\|\mathbf {a} \times \mathbf {b} \right\|=\left\|\mathbf {a} \right\|\left\|\mathbf {b} \right\|\sin(\theta)}$$
    * <span style="color:purple">模长等于以两个向量为边的平行四边形的面积</span>
  * **叉乘计算**
    * **Part1**
      * 叉乘计算规则：如果两个向量一样，叉乘结果为$0$
      * 通过引入单位向量，向量就可以转化成代数形式，例如$$a=a_1i+a_2j+a_3k, \ \ b=b_1i+b_2j+b_3k$$
      * $i，j，k$是三个相互垂直的向量。它们刚好可以构成一个坐标系。这三个向量就是$$i=(1,0,0), \ j=(0,1,0), \ k=(0,0,1)$$
    * **Part2**$$\mathbf{a}=(a_1,a_2,a_3),\mathbf{b}=(b_1,b_2,b_3)$$分别为两三维向量，叉乘为$$\mathbf{a}\times \mathbf{b}=\ <a_2b_3-a_3b_2,\ \ a_3b_1-a_1b_3,\ \ a_1b_2-a_2b_1>$$也可以写成**伪行列式**的形式$$a\times b = \left ( \begin{matrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{matrix} \right ) = \mathbf{i}(a_2b_3-a_3b_2) + \mathbf{j}(a_3b_1-a_1b_3) + \mathbf{k}(a_1b_2-a_2b_1)$$$$\mathbf{a}\times \mathbf{b} = \left ( \begin{matrix} a_2b_3-a_3b_2 \\ a_3b_1-a_1b_3 \\ a_1b_2-a_2b_1 \end{matrix} \right )$$
    * **Part3**
      * 先以二维为例，假设有一个向量$\mathbf{a}=(a_1,a_2)$然后我们引入反对称矩阵$$\mathbf{H} = \left ( \begin{matrix} 0&-1\\1&0 \end{matrix}\right )$$然后计算$$\mathbf{a}\mathbf{H}\mathbf{a}^T$$得结果为$$\left ( \begin{matrix} a_1&a_2 \end{matrix} \right )  \left ( \begin{matrix} 0&-1 \\ 1&0 \end{matrix} \right )  \left ( \begin{matrix} a_1\\a_2 \end{matrix} \right ) = \left ( \begin{matrix} a_1&a_2 \end{matrix} \right )  \left ( \begin{matrix} -a_2 \\a_1 \end{matrix} \right ) = \left ( \begin{matrix} a_1(-a_2) + a_2a_1 \end{matrix} \right ) = 0$$<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/反对称矩阵比较.190iia091ml.webp"></div><div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/反对称变换-图解.6sycqrfdsxk0.webp"></div>
      * 由叉乘的规则我们有$$a\times a = [a]_\times * a = 0$$其中$[a]_\times$表示某个叉乘矩阵，然后作用到了$a$得结果为$0$,通过对比，我们可以发现，$\mathbf{a}\mathbf{H}$就是向量a的叉乘矩阵，当$\mathbf{a}$为列向量时，$\mathbf{a}^T\mathbf{H}$为a向量的叉乘矩阵，如果向量$\mathbf{a} = (a_1,a_2,a_3)$为三维向量，那么H为$$\mathbf{H} = \left ( \begin{matrix} H_1\\H_2\\H_3 \end{matrix}\right ) \ \mathbf{H_1} = \left ( \begin{matrix} 0&0&0\\0&0&\textcolor{#00FF00}{-1}\\0&\textcolor{#00FF00}{1}&0 \end{matrix}\right ) \ \mathbf{H_2} = \left ( \begin{matrix} 0&0&\textcolor{#0000FF}{1}\\0&0&0\\\textcolor{#0000FF}{-1}&0&0 \end{matrix}\right ) \ \mathbf{H_3} = \left ( \begin{matrix} 0&\textcolor{#FF0000}{-1}&0\\\textcolor{#FF0000}{1}&0&0\\0&0&0 \end{matrix}\right )$$最后将变换合并起来就是$$\mathbf{H} = \left ( \begin{matrix} 0&\textcolor{#FF0000}{-1}&\textcolor{#0000FF}{1}\\\textcolor{#FF0000}{1}&0&\textcolor{#00FF00}{-1}\\\textcolor{#0000FF}{-1}&\textcolor{#00FF00}{1}&0 \end{matrix}\right )$$则最终有$$\mathbf{a}\mathbf{H} = \left ( \begin{matrix} 0&\textcolor{#FF0000}{-a_3}&\textcolor{#0000FF}{a_2}\\\textcolor{#FF0000}{a_3}&0&\textcolor{#00FF00}{-a_1}\\\textcolor{#0000FF}{-a_2}&\textcolor{#00FF00}{a_1}&0 \end{matrix}\right )$$$$\mathbf{a}\times \mathbf{b} = \mathbf{A}*\mathbf{b} = \left ( \begin{matrix} 0&-a_3&a_2 \\ a_3&0&-a_1 \\ -a_2&a_1&0 \end{matrix} \right )\left ( \begin{matrix} b_1\\b_2\\b_3 \end{matrix} \right )$$
    * **Part4**
      * 根据内积和外积的定义$$(\mathbf{a}\times \mathbf{b})\cdot \mathbf{a} =<a_2b_3-a_3b_2,\ \ a_3b_1-a_1b_3,\ \ a_1b_2-a_2b_1> \cdot \mathbf{a} \\ =\ a_1(a_2b_3-a_3b_2) + a_2(a_3b_1-a_1b_3) + a_3(a_1b_2-a_2b_1) \\ $$     　　　　　　$=$<span style="color:red">$a_1a_2b_3$</span>$-$<span style="color:orange">$a_1a_3b_2$</span>$ + $<span style="color:blue">$a_2a_3b_1$</span>$-$<span style="color:red">$a_2a_1b_3$</span>$ + $<span style="color:orange">$a_3a_1b_2$</span>$-$<span style="color:blue">$a_3a_2b_1$</span>$=0$
      * 假设有两个不共线的向量，分别为$(a_1,a_2,a_3),(b_1,b_2,b_3)$,我们设我们要找的垂直于这两个向量的向量为$(x,y,z)$，那么我们则有如下方程$$\left ( \begin{matrix} a_1&a_2&a_3\\b_1&b_2&b_3 \end{matrix} \right )\left ( \begin{matrix} x\\y\\z \end{matrix} \right ) = \left ( \begin{matrix} 0\\0 \end{matrix} \right ) =0$$ $$\Rightarrow \left \{ \begin{matrix} a_1x+a_2y+a_3z=0 \\ b_1x+b_2y+b_3z=0 \end{matrix} \right .$$ (这里可以看做向量$(a_1,a_2,a_3)$和$(b_1,b_2,b_3)$分别与要求向量$(x,y,z)$的点乘，如果垂直点乘结果为$0$) 令式子中的$z=1$,则我们有$$\left \{ \begin{matrix} a_1x+a_2y=-a_3 \ (1)\\b_1x+b_2y=-b_3 \ (2) \end{matrix}\right .$$ (因为我们的方程组的秩小于未知数的个数，这里不妨设$z=1$然后再求解)
      * 然后解二元一次方程，另$(1)\times \frac{b_1}{a_1}-(2)$得$$y=\frac{a_1b_3-a_3b_1}{a_2b_1-a_1b_2}$$与$$x=\frac{a_3b_2-a_2b_3}{a_2b_1-a_1b_2}$$因此所求向量为$$(\frac{a_3b_2-a_2b_3}{a_2b_1-a_1b_2}, \ \frac{a_1b_3-a_3b_1}{a_2b_1-a_1b_2}, \ 1)$$ 改变一下形式我们有$$(a_3b_2-a_2b_3, \ a_1b_3-a_3b_1, \ a_2b_1-a_1b_2)$$这个形式与之前的形式相差了一个$-$号，还有另外一种解法使用$(2)\times \frac{a_1}{b_1} - (1)$所得的结果的形式与之前的形式相同
  * 补充[[1]](https://github.com/Krasjet/quaternion/blob/master/quaternion.pdf)
    * 叉乘的定义在历史顺序上来说是从Graßmann积中导出

* **线性变换Linear Transforms**
  * **缩放Scale**$$\left ( \begin{matrix} x'\\ y' \end{matrix} \right ) = \left ( \begin{matrix} s&0\\ 0&s \end{matrix} \right ) \left ( \begin{matrix} x\\ y \end{matrix} \right )$$

[UniformScale](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/UniformScale.mp4 ':include :type=video controls width=100% height=360px')

  * **非均匀缩放 Scale (Non-Uniform)**$$\left ( \begin{matrix} x'\\ y' \end{matrix} \right ) = \left ( \begin{matrix} s_1&0\\ 0&s_2 \end{matrix} \right ) \left ( \begin{matrix} x\\ y \end{matrix} \right )$$

[NonUniformScale](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/NonUniformScale.mp4 ':include :type=video controls width=100% height=360px')

  * **反射Reflection**$$\left ( \begin{matrix} x'\\ y' \end{matrix} \right ) = \left ( \begin{matrix} -1&0\\ 0&1 \end{matrix} \right ) \left ( \begin{matrix} x\\ y \end{matrix} \right )$$

[Reflection](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/Reflection.mp4 ':include :type=video controls width=100% height=360px')

  * **错切Shear**$$\left ( \begin{matrix} x'\\ y' \end{matrix} \right ) = \left ( \begin{matrix} 1&a\\ 0&1 \end{matrix} \right ) \left ( \begin{matrix} x\\ y \end{matrix} \right )$$

[ShearMatrix](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/ShearMatrix.mp4 ':include :type=video controls width=100% height=360px')

[Shear](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/Shear.mp4 ':include :type=video controls width=100% height=360px')

  * **旋转Rotate**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘-Rotate.3lljascgw0k0.webp" width="790"></div> 
    $$\mathbf{R}_\theta = \left ( \begin{matrix} \textcolor{#ddeeff}{cos\theta} & \textcolor{black}{-sin\theta} \\  \textcolor{#ddeeff}{sin\theta} & \textcolor{black}{cos\theta} \end{matrix} \right )$$

[Rotation](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/Rotation.mp4 ':include :type=video controls width=100% height=360px')

* **平移Translation与齐次坐标Homogenous Coordinates**
  * **平移**
    * 平移不是一个线性变换，它是一个**仿射变换**，因为线性变换其中的一个特性就是变换前后坐标系的原点保持不变，显然平移不满足这个特性；或者还可以说我们无法用一个矩阵去描述这个变换，不像之前的旋转缩放等变换我们都可以用一个矩阵就可以描述。再从另外一个角度来描述就是我们"无法通过只使用乘法来描述这个变换"
    * 我们假设一个场景，在一维情景下，我们有一个数轴，还有三个点在$$a=1,\ b=2,\ c=3$$处，我们想要将这三个点往右移动一个单位,也就是$$a'=a+1;\ b'=b+1,\ c'=c+1$$这是对这三个点都使用"+1"这个一个同样的操作我们做到了，那么我们可不可以使用乘法呢？我们观察到，$a'=2,\ a=1$，要想使用乘法就需要乘以$2$，因为之间相差$2$倍，也就是$a'=2a$,但是对于另外两个点，$2b$和$2c$则不是我们想要的结果，问题我们是否可以找到一个像"+1"这么一个统一又优美的操作，使乘法也可以作用于变换呢？答案是，我们暂时找不到
    * 所以，Translation我们需要使用这种方式来表示$$\left ( \begin{matrix} x'\\ y' \end{matrix} \right ) = \left ( \begin{matrix} a&b\\ c&d \end{matrix} \right ) \left ( \begin{matrix} x\\ y \end{matrix} \right ) + \left ( \begin{matrix} t_x\\ t_y \end{matrix} \right )$$可这样表示后面会多出$$\left ( \begin{matrix} t_x\\ t_y \end{matrix} \right )$$使得偏偏平移变换与其它的变换**不同**，那有没有其它的方法呢？
  * **齐次坐标**
    * 以二维为例，我们新增一个**坐标分量**叫$w$，让其先等于$1$
    * 则平移的矩阵可以表示为$$\left ( \begin{matrix} x'\\ y' \\1 \end{matrix} \right ) = \left ( \begin{matrix} 1&0&t_x\\ 0&1&t_y\\0&0&1 \end{matrix} \right ) \left ( \begin{matrix} x\\ y\\1 \end{matrix} \right ) = \left ( \begin{matrix} x+t_x\\ y+t_y\\1 \end{matrix} \right )$$再来看一下用齐次坐标是否可以表示之前的那些变换,均匀缩放$$\left ( \begin{matrix} x'\\ y'\\1 \end{matrix} \right ) = \left ( \begin{matrix} s&0&0\\ 0&s&0\\0&0&1 \end{matrix} \right ) \left ( \begin{matrix} x\\ y\\1 \end{matrix} \right )$$以及旋转$$\mathbf{R}_\theta = \left ( \begin{matrix} cos\theta & -sin\theta&0 \\  sin\theta & cos\theta&0 \\0&0&1 \end{matrix} \right )$$都是可以的
  * **变换复合**
    * 如果还记得之前的变换复合，那么现在给你一个复合也会很容易就理解$$\mathbf{T}_{(1,0)}\mathbf{R}_{45^\circ} = \left ( \begin{matrix} 1&0&1\\ 0&1&0\\0&0&1 \end{matrix} \right ) \left ( \begin{matrix} cos45^\circ &-sin45^\circ &0\\ sin45^\circ & cos45^\circ &0\\0&0&1 \end{matrix} \right )$$3维下$$\left ( \begin{matrix} x'\\ y' \\z'\\1 \end{matrix} \right ) = \left ( \begin{matrix} 1&0&0&t_x\\ 0&1&0&t_y\\0&0&1&t_z \\0&0&0&1 \end{matrix} \right ) \left ( \begin{matrix} x\\ y\\z\\1 \end{matrix} \right ) = \left ( \begin{matrix} x+t_x\\ y+t_y\\ z+t_z\\1 \end{matrix} \right )$$

* **重心坐标**
  * **插值Interpolation**
    * 给一段距离，再选取这段距离上的一个区间并记刻度$0-1$，然后使用插值我们可以计算出这段距离上的每一处的值，当在中间时，就是$0.5$; 或者说我们将$0$刻度处设为<span style="color:red">红色</span>，$1$刻度处设为<span style="color:green">绿色</span>，同样使用插值我们可以计算出这段距离上每一处的颜色，使用颜色混合，当在中间时，红色和绿色的强度是一样的，我们知道可以混合出<span style="color:yellow">黄色</span>
  * **重心坐标的引入**
    * 模型可以使用许多三角形来表示<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/手绘模型三角形表示.11qpyej3om0g.webp"></div>刚才举例中的在一段距离上插值两个颜色应用到三角形上该如何表示呢？答案是使用**重心坐标**, 重心坐标就是在一个三角形内使用三个数值 ($\alpha\ \beta\ \gamma$)，用这三个数值来表示这个三角形内每一个点的位置，并且需要满足这三个数值相加起来等于$1$<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/重心坐标介绍.4cy6cafle480.webp" width="790"></div>用一种直观的感受，我们小时候应该玩过一种玩具，一个透明的塑料盖子里有一个迷宫，里面有一个小铁球，我们通过前后左右摆动来控制小铁球走出迷宫<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/重力球迷宫图片.1m4djnzlcrmo.webp"></div>将这个迷宫想象成三角形，当我们摇动时，这个小球就会前往这个三角形中不同的地方，是不是就是<span style="color:blue">"重心"</span>再往那个地方偏呢在，在数学中也是一样的道理。<br>现在我们向左下移动，那么这个小球就会"铛"的一声，停靠在左下方<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/重心坐标示例.4ba7m720nk00.webp" width="490"></div>那么就像所有的"重心"都落在了左下方这个$A$点上了，在数学上表示呢，就是$\alpha$的数值为$1$,$\beta$和$\gamma$的值为$0$
  * **如何计算这个坐标**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/重心坐标计算用图.j14mugbo4k0.webp" width="790"></div>
    * $P$点分别与三角形的三个顶点相连，我们可以得到三个小三角形，然后**通过分别计算这个三个小三角形的面积与整个三角形的面积的比值**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/重心坐标计算1.g6q54cfe988.webp" width="790"></div>那么之前的那个例子通过计算就是小三角形$A_A$占据了整个三角形，与整个三角形的面积比值为$\frac{1}{1}=1$,而小三角形$A_B$与$A_C$与整个三角形的面积比为$\frac{0}{1}=0$,现在的问题就是我们如何计算这个**面积比值**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/重心坐标计算示例.2fikhcexbois.webp" width="390"></div>
    * 首先是三角形上的法线计算，使用叉乘$$\mathbf{n}=(b-a)\times (c-a)$$求得法线 (两个向量叉乘得第三个向量且垂直于这两个向量) 为什么要计算法线呢？因为计算法线与求面积有关,让我们继续往下看，在我们求得法线之后，我们就有三角形的面积为 $$area = \frac{1}{2} ||n||$$这里为什么面积是$\frac{1}{2}$倍的法线的模？抛开叉乘的几何意义，我们从代数意义去看叉乘<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/叉乘与三角形面积.6bri9yhngtc0.webp"></div>其中$${\displaystyle \left\|\mathbf {a} \times \mathbf {b} \right\|=\left\|\mathbf {a} \right\|\left\|\mathbf {b} \right\|\sin(\theta)}$$是叉乘的模长计算公式，其中$a$向量的模也就是$a$的边长，$b$向量的模就是$b$的边长,根据三角形面积的计算公式$$\Delta = \frac{1}{2}ah$$我们发现，计算叉乘的过程正好是计算三角形面积的过程，只不过少除以了一个$2$，所以叉乘的模长的$\frac{1}{2}$倍正好就是三角形的面积
    * 计算其中两个小三角形的面积和整个三角形的面积，其中
      * ①的面积为$$\frac{1}{2}\times ||(a-p)\times (c-p)||$$②的面积为$$\frac{1}{2}\times ||(b-p)\times (c-p)||$$整个三角形的面积为$$\frac{1}{2}\times ||(b-a)\times (c-a)||$$则我们最终有$$ \begin{array}{l} \alpha =\frac{①的面积}{整个三角形面积} \\ \beta =\frac{②的面积}{整个三角形面积} \\ \gamma =1-\alpha-\beta \end{array}$$
    * 注：计算方法不唯一，还有一些其它的计算方法

* 链接
  * [1] 【线性代数】线性代数的本质 https://www.bilibili.com/video/BV18J411T7vS
  * [2] 余弦定理_百度百科 https://baike.baidu.com/item/%E4%BD%99%E5%BC%A6%E5%AE%9A%E7%90%86/957460
  * [3] Games-101 https://sites.cs.ucsb.edu/~lingqi/teaching/games101.html
  * [4] 两向量叉乘结果为什么垂直于原向量? https://www.zhihu.com/question/30118900
  * [5] 2d matrix! https://ncase.me/matrix/
  * [6] Triangle Area https://mathworld.wolfram.com/TriangleArea.html
  * [7] Fundamentals of Computer Graphics

## Day05-Graphics Basis

> 内容: 两条管道/流水线(空间变换、渲染管道)、相关概念(Local Space、World Space、View Space、Clip Space、NDC Space、Screen Space)、深度(线性深度、非线性深度)

<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/life/enable-webgpu-on-googlechrome_dev.5l6548c2hg00.webp" width="1200"></div>

* **词汇表Glossary**
  * Local Space 本地空间 
  * World Space 世界空间
  * View Space 观察空间
  * Clip Space 裁切空间
  * NDC Space 标准设备坐标空间
  * Screen Space 屏幕空间
  * Model Transformation 模型变换
  * View Transformation 观察变换
  * Perspective Transformation 透视变换
  * Orthogonal Transformation 正交变换
  * Viewport Transformation 视口变换
  * Rasterization 光栅化

* **两条管道/流水线**
  * **渲染管道**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/WebGPU渲染管线.3vst1o5hmbs0.webp" width="790"></div>
    * <span style="color:blue">顶点数据</span> ----> <span style="color:red">顶点着色</span> ----> <span style="color:blue">光栅化</span> ----> <span style="color:red">片段着色</span> ----> <span style="color:blue">屏幕显示</span>
  * **空间变换"管道"**
    * <span style="color:blue">本地空间</span> ----> (<span style="color:red">模型变换</span>) ----> <span style="color:blue">世界空间</span> -> (<span style="color:red">观察变换</span>) -> <span style="color:blue">观察空间</span> ----> (<span style="color:red">投影变换</span>) -> <span style="color:blue">裁切空间</span> ----> (<span style="color:purple">除以w分量</span>) ----> <span style="color:blue">规格化设备坐标空间</span> ----> (<span style="color:purple">视口变换</span>) -> <span style="color:blue">屏幕空间</span>
  * 补充：其中两个管道中的红色部分是我们参与其中的，就是那三个变换和那两个着色
* **空间变换**
  * 什么是空间变换？当我们想渲染一个物品到屏幕中，例如一个小盒子，从小盒子的角度出发，也就是**Local Space**，它看所有的物品都是相对于它来说的，例如小盒子的正前方有一个小球，是相对于小盒子来说它的前方有一个小球，但是对于小球来说，那么就不一定了，可能是小球的后方或者前后左右上下都有可能，那么就会出现小盒子说，不行，大家要以我为参考，小球会说，凭什么以你为参考呢？以我为参考不好吗？争执不下，那这样下去不行，所以最后我们规定某个指定的地方插一个小旗子:triangular_flag_on_post:，就指定这个地方在三维下就是$(0,0,0)$为坐标原点，所有的物品不管是小盒子还是小球或者其它什么物品，都必须以这个原点为相对参考，那么这样就清晰明了了，小盒子相对于原点在$(1,0,0)$处，等等，小球相对于原点在$(0,1,0)$处，这就是**World Space**
  * 当我们观察一个物品时，以我们自己为原点，朝前方规定为朝$-z$方向看去，所以假设有一个小盒子在我们的左手边时，也就是$-x$方向，我们需要朝左转动头部90°，如果在上方的话，也就是$+y$方向，我们就需要朝上转动头部90°，但每次都要转动头部，好麻烦对吧？那么有没有其它的方法呢？还是假设这个小盒子在我们的左手边，如果我们想要观察它，则需要向左转动头部90°对吧，那么我就在想能不能不转动头部而是把这个小盒子拿到我的前方，也就是把这个小盒子相对我来说往右转动90°到我的正前方，仔细想想可以吗？是可以的，排除其它所有的事物，就想象只有我们自己和这个小盒子，**我们朝左转动去看这个小盒子和把这个小盒子朝右转动到我们面前再去看，最终的观察效果是一模一样的**！所以我们给在世界空间中的所有物品再做一个变换，能够让我们观察到，就像类似这个小盒子朝右转动一样，类似这样的变换之后的空间我们称作**View Space**
  * 到了这里，我们知道物品的位置了，还知道了观察的方向，但是似乎还缺少一些东西，那就是如何去观察，就像我们的:eyes:眼睛一样，你是激光眼，透视眼，还是千里眼，还是写轮眼，眼睛不一样，看到的画面就会有不一样的效果，而我们的眼睛看到的呢就是最普通的透视效果，叫做**Perspective Transformation**，例如两条平行的铁轨<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/PerspectiveProjection.6ujk7r238gs0.webp" width="190"></div>我们最终看到的画面是这种近大远小的，并且超出画面外的物品，也就是我们所看不到的都会被"裁切"掉，这种在指定了我们如何去**观察的方式**之后的我们称为**Clip Space**，当然还有另外一种常用的观察方式叫做**Orthogonal Transformation**，我们待会会讲到这两种的区别
  * 所以对于任何物体，应用**Model Transformation**到**World Space**，然后应用**View Transformation**到**View Space**，再应用**Perspective Transformation**或者**Orthogonal Transformation**到**Clip Space**，再除以w分量到**NDC Space**，最后再应用**Viewport Transformation**到**Screen Space**，**Screen Space**就是最终的显示屏幕, 以上统称为**空间变换**
* **渲染管道**
  * 什么是渲染管道？想象一个汽车:car:生产车间，我们知道车间内部是有许多道工序的，但纵观整个车间来看，它就是一个很复杂的机器，我们给这个机器喂入一些原材料，例如金属，橡胶，设计图等等的东西，然后这个机器就会产出一辆汽车出来，它中间的工序我们可以先不用关心，最后这个机器会生产出汽车来，但只生产出汽车我们还不满意，希望可以在其中增加一些可以**定制化**的东西，例如在生产汽车的这个车间进行到了锻造这个工序的时候，我们可以自定义配置汽车的尺寸大小，然后到了喷漆这个工序的时候，我们可以自定义配置汽车的颜色，等等就像这样我们可以自己去配置的步骤，类比于渲染管道中对应的就是 锻造 -> **顶点着色**，喷漆 -> **片段着色**,而整个车间的生产工序就是类比于这个**渲染管道**本身，**顶点数据**就像我们生产这个汽车所喂入的原材料
  * 补充：通常我们在自定义顶点着色的时候对这些原始的顶点数据应用**模型、观察和透视矩阵**

* **相关概念**
  * **World Space**
    * 应用了Model Transform后，模型就从自身的Local Space转换到了World Space，通常是应用位移、旋转和缩放变换等
  * **View Space**
    * 之前我们介绍过，我们看向一个物体与把一个物体拿到我们面前是一样的，所以我们可以对世界空间中的物体应用一个View Transform从世界空间到观察者空间(或者称作相机空间)，通常是应用位移和旋转变换
  * **Clip Space**
    * **透视变换Perspective Transformation**
      * 什么是透视变换？[图片](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/Perspective.4ihgtm58l9u0.webp) 透视变换是一个投影过程，其中透视变换就像将人的眼睛当做一个中心点，外部世界是一个大平面，在眼睛与这个平面之间形成一个椎体，然后将这个平面上的内容投射到眼睛内。
      * 为什么变换之后的空间被称为裁切空间？裁切就是把不需要的部分去除掉，就是这幅图片中一样，投影平面在左侧<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/projection.1onr15yp0sv4.webp" width="490"></div>而在投影中心另一侧的右侧的点我们是不需要的，假设这个点的坐标为$$(2,5,10)$$应用计算之后是$$x'=\frac{2}{-10}=-0.2$$ $$y'=\frac{5}{-10}=-0.5$$ $$z'=\frac{10}{-10}=-1$$ 那么这个计算过程是如何进行的呢？根据相似三角形<center><img style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/projection.5bbo6m777gs0.webp"><br><div style="color:orange; border-bottom: 1px solid #d9d9d9; display: inline-block; color: #999; padding: 2px;">Figure5.1 (从$P$投射到$P'$)</div></center>我们有$$\frac{BA=\textcolor{blue}{z_{blue}}=1}{EA=\textcolor{green}{z_{green}}=3}=\frac{BC=y'}{EF=y}$$ $$y'=\frac{y*\textcolor{blue}{z_{blue}}}{\textcolor{green}{z_{green}}}$$其中，由于我们的摄像机是看向$-z$方向的，所以$\textcolor{green}{z_{green}}$在计算的时候前面要加$-$号，这就是式子$y'=\frac{5}{-10}=-0.5$中$z$的值为$10$，计算是为$-10$<center><img style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/透视校正插值.3imenutihfe0.webp" width="490"><br><div style="color:orange; border-bottom: 1px solid #d9d9d9; display: inline-block; color: #999; padding: 2px;">Look at the projection from another aspect</div></center>
      * **步骤**
        * 假设我们有一个矩阵 $$\begin{aligned} \left [ \begin{matrix} 1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1 \end{matrix}\right ] \end{aligned}$$
        * 我们先让$z$坐标分量等于$-1$,这样计算后的$z'$就等于$1$,就可以满足如Figure5.1中的$$z'=z=1$$接下来，再调整$w$分量从$$[0,0,0,1] \rightarrow [0,0,-1,0]$$这样一来,当除以$w$分量从齐次转三维中的点时，除以$w$分量相当于除以了$-z$分量，经过这样调整后我们有$$\begin{aligned} \left [ \begin{matrix} 1&0&0&0\\0&1&0&0\\0&0&-1&-1\\0&0&0&0 \end{matrix}\right ] \end{aligned}$$ 其计算过程正好是我们想要的 $$\begin{aligned} \left \{ \begin{matrix} x'=x*1+y*0+z*0+1*0\ =x\\ y'=x*0+y*1+z*0+1*0\ =y\\ z'=x*0+y*0+z*{-1}+1*0\ ={-z}\\ w'=x*0+y*0+z*{-1}+1*0\ ={-z} \end{matrix}\right. \end{aligned}$$ $$\begin{array}{ll} x' = \dfrac{x'=x}{w'=-z},\\ y' = \dfrac{y'=y}{w'=-z},\\ z' = \dfrac{z'=-z}{w'=-z} = 1. \end{array}$$ 其中$z'=\frac{z}{w} = \frac{-z}{-z} = 1$,　　$x'=\frac{x}{w} = \frac{x}{-z}$,　　$y'=\frac{y}{w} = \frac{y}{-z}$接下来我们就需要详细计算每个部分了
        * [计算投影点的$x'$和$y'$坐标,将范围映射到[-1,1]](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/PerspProjectionDerivation.6edn0immf7o0.webp) $$\left[\begin{array}{cccc} { \frac{2n}{ r-l } } & 0 & ... & 0 \\ 0 & { \frac{2n}{ t-b } } & ... & 0 \\ { \frac{r + l}{ r-l } } & { \frac{t + b}{ t-b } } & ... & {-1}\\ 0 & 0 & ... & 0\\ \end{array}\right]$$
        * [将投影点的z坐标重新映射到范围[-1,1]](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/Remapping-the-z-coordinate-of-the-projected.2oof8otgmpu0.webp) 
          * (我们根据齐次转三维点时, $(x,y,z)$这三个分量都要除以$w$分量，我们有$$(x', y', z') = (x/w, y/w, z/w)$$其中$x$和$y$对$z$无影响)，则上一步骤中的矩阵可以设为$$\left[\begin{array}{cccc} { \frac{2n}{ r-l } } & 0 & 0 & 0 \\ 0 & { \frac{2n}{ t-b } } & 0 & 0 \\ { \frac{r + l}{ r-l } } & { \frac{t + b}{ t-b } } & \textcolor{#FF0000}{A} & {-1}\\ 0 & 0 & \textcolor{#FF0000}{B} & 0\\ \end{array}\right]$$ 其中<span style="color:red">A</span>和<span style="color:red">B</span>是我们要求的,则可以列出等式$$z' = \dfrac{0 * x + 0 * y + A * z + B * w}{w = -z} \rightarrow \dfrac{A z + B}{w = -z}.$$ **注意这里的$w=1$是$(x,y,z,w=1)$中的$w$，而不是这个矩阵中的$w$分量**<br>再根据我们已知$z$正好落在$near$近平面时应当等于$-1$，正好落在$far$远平面时应当等于$1$, 我们可以列出式子$$\left\{ \begin{array}{ll} \dfrac{(z=-n)A + B}{(-z=-(-n)=n)} = -1 &\text{ when } z = n\\ \\ \dfrac{(z=-f)A + B}{(-z=-(-f)=f)} = 1 & \text{ when } z = f \end{array} \right. $$ $$ \rightarrow  \left\{ \begin{array}{ll} {-nA + B} = -n & (1)\\  {-fA + B} = f & (2) \end{array} \right.$$ $$ A=-\frac{f+n}{f-n} $$ $$ B=-\frac{2fn}{f-n} $$ (也可以映射到[0,1]范围内)
      * **资料**
        * ①关于$P'_x = \frac{P_x}{-P_z}$
          * 链接: https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/projection-matrices-what-you-need-to-know-first
          * 为什么除以了$-z$呢？投影过程中的相似三角形中的比例关系
        * ②关于透视矩阵中的齐次项的$-1$
          * 链接: https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/building-basic-perspective-projection-matrix
          * 将原来透视矩阵中的$(0,0,0,1)$变为$(0,0,-1,0)$之后, 就说当我们用这个透视矩阵的$w$分量乘以一个齐次点$$(x,y,z,1)$$时，我们有$$x*0+y*0+z*-1+1*0 = -z$$也就是说，这个齐次点$w$的值经过矩阵计算之后从之前的$1$变为了$-z$,同时，齐次点$(x,y,z)$变为三维点时需要经过$(x/w, y/w, z/w)$，此时这样就有$$(x/w, y/w, z/w) \Rightarrow (x/{-z}, y/{-z}, z/{-z})$$
        * ③关于透视矩阵中的$z$项的$-1$
          * 链接: https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/building-basic-perspective-projection-matrix
          * 因为摄像机是朝向$-z$方向的，所以摄像机前所有的点的$z$坐标都是负的，这就是为什么【资料①】中$$x' = \frac{x}{-z}$$中的$z$前方带有负号
      * **透视变换矩阵**$$\begin{aligned} M_{persp} = \left [ \begin{matrix} \frac{2n}{r-l} & 0 & \frac{l+r}{l-r} & 0 \\ 0 & \frac{2n}{t-b} & \frac{b+t}{b-t} & 0 \\ 0 & 0 & \frac{f+n}{f-n} & \frac{2nf}{n-f} \\ 0 & 0 & 1 & 0 \end{matrix}\right ] \end{aligned}$$ 或 $$\begin{aligned} M_{persp} = \left [ \begin{matrix} \frac{2n}{r-l} & 0 & 0 & 0 \\ 0 & \frac{2n}{t-b} & 0 & 0 \\ \frac{r+l}{r-l} & \frac{t+b}{t-b} & -\frac{f+n}{f-n} & -1 \\ 0 & 0 & -\frac{2nf}{n-f} & 0 \end{matrix}\right ] \end{aligned}$$ <center>(注意其中两者之间的负号)</center><br>则我们有$$[x', y', z', w'] = \left [ \begin{matrix} x\\y\\z\\w=1 \end{matrix} \right ] * M_{persp}$$ 其中$$w'=0*x + 0*y - 1*z + 0*1 = -z$$
        * 计算并验证一下，假设$n=1，f=20$公式$$\frac{-\frac{f+n}{f-n} *z -\frac{2fn}{f-n} }{-z}$$代入$n$和$f$并计算得$$\frac{-\frac{21}{19} * z - \frac{40}{19}}{-z}$$其中$\frac{-21}{19}=-1.1$和$\frac{-40}{19}=-2.1$则得到结果
        $$z=1 \rightarrow \frac{-1.1*1 -2.1}{-1} = 3.2$$ $$z=-1 \rightarrow \frac{-1.1*-1 -2.1}{1} = -1$$ $$z=-20 \rightarrow \frac{-1.1*-20 -2.1}{20} = 0.995$$ $$z=-21 \rightarrow \frac{-1.1*-21 -2.1}{21} = 1.1$$
    * **正交变换Orthographic Transformation**
      * 什么是正交变换？[图片](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/orthographic.24gyysktzse8.webp) 正交变换也是一个投影过程，这里则不像透视变换中那样是一个椎体了，而是一个方体，所以在正交变换中，近大远小这种情况则不存在，相反，你会看到所有的物体无论远近，在投影平面上都是有相仿的大小
      * **步骤**
        * 创建一个能够包含的下场景内所有物体的一个BoundingBox, $(l:left, r:right, t:top, b:bottom, f:front, b:back)$,然后将其映射到$(-1,-1,-1)$到$(1,1,1)$范围内；$x$坐标映射到$(l, r) \Rightarrow (-1,1)$, $y$坐标映射到$(t,b) \Rightarrow (1,-1)$，然后将内容投射到投影平面上
      * **资料**
        * ①正交矩阵计算过程
          * https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/orthographic-projection-matrix
      * **正交变换矩阵**$$\begin{aligned} M_{ortho} \left [ \begin{matrix} \frac{2}{r-l} & 0 & 0 & -\frac{r+l}{r-l} \\ 0 & \frac{2}{t-b} & 0 & -\frac{t+b}{t-b} \\ 0 & 0 & \frac{2}{n-f} & - \frac{n+f}{n-f} \\ 0&0&0&1 \end{matrix}\right ] \end{aligned}$$
        * 计算并验证一下，首先场景中那个包含所有物体的那个BoundingBox的值我们需要知道，这里假设场景中有一个正方体尺寸为$1x1x1$,并且放置在世界中心原点处，那么它的左右上下边界值分别为$$(l:-0.5,　r:0.5,　t:0.5,　b:-0.5)$$然后再设置远近平面我们假设为$$(n:0.01,　f:100)$$则我们有$$left=-0.5,　right=0.5,　top=0.5,　bottom=-0.5,　\\near=0.01,　far=100$$根据这些我们最终可以计算出矩阵$$\begin{aligned} M_{ortho} \left [ \begin{matrix} 2 & 0 & 0 & 0 \\ 0 & 2 & 0 & 0 \\ 0 & 0 & -0.02 & -1.002 \\ 0&0&0&1 \end{matrix}\right ] \end{aligned}$$ 正方体其中一个顶点$(-0.5, -0.5, -0.5)$经过正交变换后有$$\begin{aligned}  \left [ \begin{matrix} -0.5&-0.5&-0.5&1 \end{matrix}\right ] \end{aligned} \begin{aligned}  \left [ \begin{matrix} 2 & 0 & 0 & 0 \\ 0 & 2 & 0 & 0 \\ 0 & 0 & -0.02 & 0 \\ 0&0&-1.002&1 \end{matrix}\right ] \end{aligned}\begin{aligned}  \left [ \begin{matrix} -1&-1&-0.992&1 \end{matrix}\right ] \end{aligned}$$ 再举一个例子$$\begin{aligned}  \left [ \begin{matrix} -0.6&-0.5&-100.1&1 \end{matrix}\right ] \end{aligned} \begin{aligned}  \left [ \begin{matrix} 2 & 0 & 0 & 0 \\ 0 & 2 & 0 & 0 \\ 0 & 0 & -0.02 & 0 \\ 0&0&-1.002&1 \end{matrix}\right ] \end{aligned}\begin{aligned}  \left [ \begin{matrix} -1.2&-1&1.002&1 \end{matrix}\right ] \end{aligned}$$可以看到，后者超出了$(-1,1)$范围会被裁切掉
    * **透视变换与正交变换**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/orthographic_perspective_view.6van0bm8j340.webp" width="790"></div> [图片](https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/Perspective-and-Orthographic-Frustum.424xa80owoe.webp)
      * 透视变换是将一个锥内我们所可以看到的事物，最终投射到一"点"处
      * 正交变换是将一个方体内我们所可以看到的事物，最终投射到一"面"上
  * **NDC Space**
    * 从裁切空间转换到标准设备坐标空间，也就是把模型的$x、y、z$的范围重映射到$-1$到$1$范围内
    * **在透视变换中和正交变换中**,我们已经这样做了，我们在构造矩阵的各个分量$xy$和$z$时已经将范围映射到$-1$到$1$之间了，(在正交矩阵中，最终除以$w$分量$(w=1)$得结果还是原先的数值)
  * **Screen Space**
    * 从NDC（三维）到我们的屏幕空间（二维），也就是真正要显示在屏幕上；首先NDC空间范围是$-1$到$1$，而屏幕空间表示像素范围对应的是$(0,0)$到$(w, h)$例如我们屏幕分辨率为$520\times 520$那么就是$(520,520)$，也就是说我们需要从NDC的$(-1,-1)$到$(1,1)$映射到屏幕的$(0,0)$到$(520,520)$;假设有一点顶点为$(-0.5,-0.5,-0.5,1)$，是左下角的一个顶点 （也就是正交变换里我们计算并验证中的那个小盒子上的一个边界点）经过一个正交变换后是$(-1,1,-0.992,1)$，假设有一屏幕长为$520$，宽为$520$顶点$(-0.5,-0.5)$也就是NDC中的$(-1,-1)$会变换到屏幕空间中的$(0,0)$,同理如果是顶点$(0.5,0.5)$，NDC中的$(1,1)$会变成屏幕空间中的$(520, 520)$,我们假设另外一个顶点$(0.25,0.25)$,对应NDC中的$(0.5,0.5)$会变成屏幕空间中的$(390, 390)$<center><img style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/ScreenSpace.6m3i63w9eqc0.webp"><br><div style="color:orange; border-bottom: 1px solid #d9d9d9; display: inline-block; color: #999; padding: 2px;">Figure5.2</div></center>根据这些我们可以得到我们的**视口变换矩阵**$$\begin{aligned} \left [ \begin{matrix} \frac{w}{2} & 0 & 0 & \frac{w}{2} \\ 0 & \frac{h}{2} & 0 & \frac{h}{2} \\ 0 & 0 & \frac{1}{2} & \frac{1}{2} \\ 0&0&0&1 \end{matrix}\right ] \end{aligned}$$ （矩阵中的$z$为$\frac{1}{2}$是为保持$z$值不变） 来验证一下,假设我们的屏幕是$520\times 520$的，则矩阵为$$\begin{aligned} \left [ \begin{matrix} 260 & 0 & 0 & 260 \\ 0 & 260 & 0 & 260 \\ 0 & 0 & 0.5 & 0.5 \\ 0&0&0&1 \end{matrix}\right ] \end{aligned}$$ 顶点$(0.25,0.25)$，NDC中为$(0.5，0.5)$则$$\begin{aligned} \left [ \begin{matrix} 0.5&0.5&1&1 \end{matrix} \right ] \end{aligned} \begin{aligned} \left [ \begin{matrix} 260 & 0 & 0 & 260 \\ 0 & 260 & 0 & 260 \\ 0 & 0 & 0.5 & 0.5 \\ 0&0&0&1 \end{matrix}\right ] \end{aligned} \begin{aligned}  \left [ \begin{matrix} 390&390&1&1 \end{matrix}\right ] \end{aligned}$$ 顶点$(-0.5,-0.5)$，NDC中为$(-1，-1)$则$$\begin{aligned} \left [ \begin{matrix} -1&-1&1&1 \end{matrix} \right ] \end{aligned} \begin{aligned} \left [ \begin{matrix} 260 & 0 & 0 & 260 \\ 0 & 260 & 0 & 260 \\ 0 & 0 & 0.5 & 0.5 \\ 0&0&0&1 \end{matrix}\right ] \end{aligned} \begin{aligned}  \left [ \begin{matrix} 0&0&1&1 \end{matrix}\right ] \end{aligned}$$映射到屏幕坐标$(0,0)$像素点（也就是说最左下的那个小盒子的边界点正好映射到屏幕的左下角）
    * 如果长宽是不一样的<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/ScreenSpace.7cnosi0vi480.webp"></div>长宽不一样我们依然可以处理，只不过要多一个概念$aspect$,$$aspect=\frac{width}{height}$$它是一个比例<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/视口变换演示.19ypc5014qkg.webp"></div> 左上图是比例为$1:1$的情况下，如果我们改变了窗口大小，例如改为了$640\times 480$，也就是比例为$1:1.3333$,如果我们此时什么都不做，则我们会得到左下的结果（仔细想想，为什么，是因为我们的视口变换矩阵，像素是一一对应的，**即使窗口大小变了，但映射关系并没有变**）所以我们如果才能得到右上的结果呢？ 很简单，在进行正交变换或者透视变换的时候将$x$方向也就是水平方向按照$aspect$比例收缩一些[[PerspectiveProjection.py]](day05-graphics/PerspectiveProjection.py)
  * **Space Transformation**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/空间变换.3uujhna7v4o0.webp"></div>
  * **深度**
    * **线性深度**$$F_{depth}=\frac{z-near}{far-near}$$
      * 接近近平面的时值为$0$，远平面时为$1$，但我们通常不使用这个深度，因为我们的投影特性导致插值不是线性的(由于在投影平面上的相同步长随着三角形面与相机之间的距离增加而在三角形面上产生更大的步长-《Mathematics for 3D Game Programming and Computer Graphics-P107) (正交投影与透视投影的视锥不同，所以不存在透视投影中的近大远小效果，在这样的情况下，正交投影中的深度可以使用线性深度)
    * **非线性深度**$$\begin{aligned} F_{depth} = \frac{\frac{1}{z}-\frac{1}{near}}{\frac{1}{far}-\frac{1}{near}} \end{aligned}$$
      * 为什么是非线性？<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/x分之1的函数图像.1wcc3u4z1sow.webp"></div>观察$\frac{1}{x}$的图像我们可以知道，将$x$看做$z$，透视变换中我们也比上了$z$，所以最终总体的结果与这个函数的图像是类似的，通过观察我们可以看到$[0,0.5]$之间的区域占了总共了的$\frac{4}{5}$还多，这也就意味着，**距离屏幕越近的模型将会获得越高的精度，反之，越远精度越低，而线性则是非常平均的，无论远近，精度一致**，这只是一个观察结果；在透视变换矩阵除以$w(w=-z)$分量进入NDC空间之前，它们是线性的，除以了$w$分量之后进入了NDC空间，就变为了非线性;此外除了深度，其它坐标也是非线性
      * 函数图像链接: https://www.geogebra.org/m/zqnpanc7
* **坐标转换**
  * 到了这里我们已经可以从一个顶点一路经过各种变换到最终把它渲染在屏幕上，同样的，给你一个屏幕上的像素坐标且包含$z$值，你也同样可以从屏幕空间一路经过各种逆变换最终获取到最原始的顶点信息

* **补充概念**
  * **CanvasContext** - 我们最终呈现的画面它是由一系列的画布组合而成的，而这些画布配置是需要我们参与的，它们的名字叫做Attachments<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/FrameBufferAttachments.1tj7p0e7jkps.webp" width="790"></div>
  * **NDC Space** (Normalized device coordinate/规格化设备坐标) 归一化设备坐标或NDC空间是独立于屏幕的显示坐标系统; 它包含一个立方体，其中$x、y$和$z$组件的范围从$−1$到$1$。 
  * **W Component**
    * 可以通过增大$w$分量的值，是点朝向原点移动，减小$w$分量的值，可以使点朝向无穷点。[[1]](https://stackoverflow.com/questions/2422750/in-opengl-vertex-shaders-what-is-w-and-why-do-i-divide-by-it)
    * 在到clip空间后，我们会根据$-w \leq x,y,z \leq w$来决定丢弃哪些模型,因为这是都是超出了屏幕之外的。[[PerspectiveProjection.py]](day05-graphics/PerspectiveProjection.py), 例如$-w \leq x \leq w$是在$x$轴向上超出了，以此类推，这里为什么是与$w$的值比较与在NDC空间中为什么是除以$w$的值是归一化是如出一辙的。
  * **FOV(Field-Of-View) & Aspect Ratio**
    * **原理**
      * 透视矩阵中我们使用$top、bottom、left、right、near、far$来定义，但通常我们不这样做，而是使用$fov、aspect\ ratio、near、far$来定义，但他们本质上都是一样的，像人的眼睛也是有$fov$，叫做[视度](https://baike.baidu.com/item/%E4%BA%BA%E7%9C%BC%E8%A7%86%E5%BA%A6/5997035#)这么一说的,顾名思义，视度越大，我们看到的事物也就越多，例如$fov90$就比$fov60$看到的多，它是视点中心到视锥左侧与视点中心到视锥右侧所张开的角度，当然这样只能计算出左右侧的，还需要一个$aspect\ ratio$(屏幕纵横比)来计算上下侧的。
    * **计算**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/FOV-image.5ljfnjoc8mc0.webp"></div>
      * 根据三角函数$$\begin{array}{l} \tan( \dfrac{ FOV } {2}) = \dfrac{ opposite } { adjacent } = \dfrac {BC}{AB} = \dfrac{top}{near} \\ top = \tan( \dfrac{ FOV } {2}) * near \\ bottom = -top \end{array}$$如果我们的$aspect\ ratio$(宽高比)为$1$的话，则$$\begin{array}{l} right = top\\ left = bottom = -top \end{array}$$但通常我们的屏幕的宽高比都不是$1:1$的，如<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/graphics/AspectRation.3dftg4ztsu00.webp"></div>图中右边所示，我们有公式$$\frac{width}{height}=\frac{right}{top}$$ $$\frac{width}{height}=\frac{left}{bottom}$$ (宽与左右对应，高与上下对应) 则我们有$$\begin{array}{l} right = top * aspect\ ratio \\ left = bottom * aspect\ ratio \end{array}$$其中$$aspect\ ratio = \frac{width}{height}$$ $$bottom = -top$$
    * [[PerspectiveProjection.py]](day05-graphics/PerspectiveProjection.py)

* 链接
  * [1] From 0 to glTF with WebGPU: The First Triangle - Updated https://www.willusher.io/graphics/2021/08/29/0-to-gltf-triangle
  * [2] Raw WebGPU - Alain Galvan https://alain.xyz/blog/raw-webgpu
  * [3] awesome-webgpu https://github.com/mikbry/awesome-webgpu/blob/master/readme.md
  * [4] LearningWebGPU https://github.com/hjlld/LearningWebGPU
  * [5] webgpu-samples https://austineng.github.io/webgpu-samples/
  * [6] Chrome Platform Status- WebGPU https://chromestatus.com/feature/6213121689518080
  * [7] Building a Basic Perspective Projection Matrix https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/building-basic-perspective-projection-matrix
  * [8] The OpenGL Orthographic Projection Matrix https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/orthographic-projection-matrix
  * [9] Orthographic Projection https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_04.pdf
  * [10] 深度缓冲中的深度值计算及可视化 https://www.cnblogs.com/bzyzhang/p/12667859.html
  * [11] 深度测试 https://learnopengl-cn.github.io/04%20Advanced%20OpenGL/01%20Depth%20testing/#_1
  * [12] WebGL 3D Perspective https://webglfundamentals.org/webgl/lessons/webgl-3d-perspective.html
