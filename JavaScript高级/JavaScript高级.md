## 1.数据类型的分类和判断
* 基本(值)类型
  * Number ----- 任意数值 -------- typeof
  * String ----- 任意字符串 ------ typeof
  * Boolean ---- true/false ----- typeof
  * undefined --- undefined ----- typeof/===
  * null -------- null ---------- ===
* 对象(引用)类型
  * Object ----- typeof/instanceof
  * Array ------ instanceof
  * Function ---- typeof

##### 问题：

- undefined与null的区别?
  1. undefined代表定义未赋值
  2. nulll定义并赋值了, 只是值为null

- 什么时候给变量赋值为null呢?
  1. 初始赋值, 表明将要赋值为对象 
  2. 结束前, 让对象成为垃圾对象(被垃圾回收器回收)

- 严格区别变量类型与数据类型?

  1. 数据的类型

     -  基本类型

     -  对象类型

  2. 变量的类型(变量内存值的类型)

     - 基本类型: 保存就是基本类型的数据
     - 引用类型: 保存的是地址值

```js
// 实例: 实例对象
  // 类型: 类型对象
  function Person (name, age) {// 构造函数  类型
    this.name = name
    this.age = age
  }
  var p = new Person('tom', 12) // 根据类型创建的实例对象
  // Person('jack', 12)
  // 1. undefined与null的区别?
  var a
  console.log(a)  // undefined
  a = null
  console.log(a) // null
  //起始
  var b = null  // 初始赋值为null, 表明将要赋值为对象
  //确定对象就赋值
  b = ['atguigu', 12]
  //最后
  b = null // 让b指向的对象成为垃圾对象(被垃圾回收器回收)
  // b = 2
  var c = function () {

  }
```

## 2.数据,变量, 内存的理解

* 什么是数据?
  * 在内存中可读的, 可传递的保存了特定信息的'东东'
  * 一切皆数据, 函数也是数据
  * 在内存中的所有操作的目标: 数据
* 什么是变量?
  * 在程序运行过程中它的值是允许改变的量
  * 一个变量对应一块小内存, 它的值保存在此内存中  
* 什么是内存?
  * 内存条通电后产生的存储空间(临时的)
  * 内存产生和死亡: 内存条(电路版)==>通电==>产生内存空间==>存储数据==>处理数据==>断电==>内存空间和数据都消失
  * 一块内存包含2个方面的数据
    * 内部存储的数据
    * 地址值数据
  * 内存空间的分类
    * 栈空间: 全局变量和局部变量
    * 堆空间: 对象 
* 内存,数据, 变量三者之间的关系
  * 内存是容器, 用来存储不同数据
  * 变量是内存的标识, 通过变量我们可以操作(读/写)内存中的数据  
  
#### 问题1：

var a = xxx, a内存中到底保存的是什么?

1. xxx是基本数据, 保存的就是这个数据
2. xxx是对象, 保存的是对象的地址值
3. xxx是一个变量, 保存的xxx的内存内容(可能是基本数据, 也可能是地址值)

```javascript
var a = 3
  a = function () {
  }
  var b = 'abc'
  a = b
  b = {}
  a = b
```

#### 问题2：

关于引用变量赋值问题？

1. 2个引用变量指向同一个对象, 通过一个变量修改对象内部数据, 另一个变量看到的是修改之后的数据
2.  2个引用变量指向同一个对象, 让其中一个引用变量指向另一个对象, 另一引用变量依然指向前一个对象

```javascript
 var obj1 = {name: 'Tom'}
  var obj2 = obj1
  obj2.age = 12
  console.log(obj1.age)  // 12
  function fn (obj) {
    obj.name = 'A'
  }
  fn(obj1)
  console.log(obj2.name) //A
  var a = {age: 12}
  var b = a
  a = {name: 'BOB', age: 13}
  b.age = 14
  console.log(b.age, a.name, a.age) // 14 Bob 13
  function fn2 (obj) {
    obj = {age: 15}
  }
  fn2(a)
  console.log(a.age)
```

## 3.对象的理解和使用

* 什么是对象?
  * 多个数据(属性)的集合
  * 用来保存多个数据(属性)的容器
* 属性组成:
  * 属性名 : 字符串(标识)
  * 属性值 : 任意类型
* 属性的分类:
  * 一般 : 属性值不是function  描述对象的状态
  * 方法 : 属性值为function的属性  描述对象的行为
* 特别的对象
  * 数组: 属性名是0,1,2,3之类的索引
  * 函数: 可以执行的
* 如何操作内部属性(方法)
  * .属性名
  * ['属性名']: 属性名有特殊字符/属性名是一个变量
  
## 4.函数的理解和使用
* 什么是函数?
  * 用来实现特定功能的, n条语句的封装体
  * 只有函数类型的数据是可以执行的, 其它的都不可以
* 为什么要用函数?
  * 提高复用性
  * 便于阅读交流
* 函数也是对象
  * instanceof Object===true
  * 函数有属性: prototype
  * 函数有方法: call()/apply()
  * 可以添加新的属性/方法
* 函数的3种不同角色
  * 一般函数 : 直接调用
  * 构造函数 : 通过new调用
  * 对象 : 通过.调用内部的属性/方法
* 函数中的this
  * 显式指定谁: obj.xxx()
  * 通过call/apply指定谁调用: xxx.call(obj)
  * 不指定谁调用: xxx()  : window
  * 回调函数: 看背后是通过谁来调用的: window/其它
* 匿名函数自调用:
  ```
  (function(w, obj){
    //实现代码
  })(window, obj)
  ```
  * 专业术语为: IIFE (Immediately Invoked Function Expression) 立即调用函数表达式						  
* 回调函数的理解
  * 什么函数才是回调函数?
    * 你定义的
    * 你没有调用
    * 但它最终执行了(在一定条件下或某个时刻)
  * 常用的回调函数
    * dom事件回调函数
    * 定时器回调函数
    * ajax请求回调函数(后面讲解)
    * 生命周期回调函数(后面讲解)
  

## 5.原型与原型链

* 所有函数都有一个特别的属性:

  * `prototype` : 显式原型属性

    ```javascript
    <!--
    1. 函数的prototype属性(图)
      * 每个函数都有一个prototype属性, 它默认指向一个Object空对象(即称为: 原型对象)
      * 原型对象中有一个属性constructor, 它指向函数对象
    2. 给原型对象添加属性(一般都是方法)
      * 作用: 函数的所有实例对象自动拥有原型中的属性(方法)
    -->
    <script type="text/javascript">
    
      // 每个函数都有一个prototype属性, 它默认指向一个Object空对象(即称为: 原型对象)
      console.log(Date.prototype, typeof Date.prototype)
      function Fun () {//alt + shift +r(重命名rename)
    
      }
      console.log(Fun.prototype)  // 默认指向一个Object空对象(没有我们的属性)
    
      // 原型对象中有一个属性constructor, 它指向函数对象
      console.log(Date.prototype.constructor===Date)
      console.log(Fun.prototype.constructor===Fun)
    
      //给原型对象添加属性(一般是方法) ===>实例对象可以访问
      Fun.prototype.test = function () {
        console.log('test()')
      }
      var fun = new Fun()
      fun.test()
    ```

* 所有实例对象都有一个特别的属性:

  * `__proto__` : 隐式原型属性

* 显式原型与隐式原型的关系

  * 函数的prototype: 定义函数时被自动赋值, 值默认为{}, 即用为原型对象

  * 实例对象的__proto__: 在创建实例对象时被自动添加, 并赋值为构造函数的prototype值

  * 原型对象即为当前实例对象的父对象

    ![](/img/显式原型与隐式原型.png)

    ```javascript
    <!--
    1. 每个函数function都有一个prototype，即显式原型(属性)
    2. 每个实例对象都有一个__proto__，可称为隐式原型(属性)
    3. 对象的隐式原型的值为其对应构造函数的显式原型的值
    4. 内存结构(图)
    5. 总结:
      * 函数的prototype属性: 在定义函数时自动添加的, 默认值是一个空Object对象
      * 对象的__proto__属性: 创建对象时自动添加的, 默认值为构造函数的prototype属性值
      * 程序员能直接操作显式原型, 但不能直接操作隐式原型(ES6之前)
    -->
    <script type="text/javascript">
      //定义构造函数
      function Fn() {   // 内部语句: this.prototype = {}
    
      }
      // 1. 每个函数function都有一个prototype，即显式原型属性, 默认指向一个空的Object对象
      console.log(Fn.prototype)
      // 2. 每个实例对象都有一个__proto__，可称为隐式原型
      //创建实例对象
      var fn = new Fn()  // 内部语句: this.__proto__ = Fn.prototype
      console.log(fn.__proto__)
      // 3. 对象的隐式原型的值为其对应构造函数的显式原型的值
      console.log(Fn.prototype===fn.__proto__) // true
      //给原型添加方法
      Fn.prototype.test = function () {
        console.log('test()')
      }
      //通过实例调用原型的方法
      fn.test()
    ```

* 原型链

  * 所有的实例对象都有__proto__属性, 它指向的就是原型对象

  * 这样通过__proto__属性就形成了一个链的结构---->原型链

  * 当查找对象内部的属性/方法时, js引擎自动沿着这个原型链查找

  * 当给对象属性赋值时不会使用原型链, 而只是在当前对象中进行操作

    ![](/img/原型链分析.png)

    ```javascript
    <!--
    1. 原型链(图解)
      * 访问一个对象的属性时，
        * 先在自身属性中查找，找到返回
        * 如果没有, 再沿着__proto__这条链向上查找, 找到返回
        * 如果最终没找到, 返回undefined
      * 别名: 隐式原型链
      * 作用: 查找对象的属性(方法)
    2. 构造函数/原型/实体对象的关系(图解)
    3. 构造函数/原型/实体对象的关系2(图解)
    -->
    <script type="text/javascript">
      // console.log(Object)
      //console.log(Object.prototype)
      console.log(Object.prototype.__proto__)
      function Fn() {
        this.test1 = function () {
          console.log('test1()')
        }
      }
      console.log(Fn.prototype)
      Fn.prototype.test2 = function () {
        console.log('test2()')
      }
    
      var fn = new Fn()
    
      fn.test1()
      fn.test2()
      console.log(fn.toString())
      console.log(fn.test3)
      // fn.test3()
      /*
      1. 函数的显示原型指向的对象默认是空Object实例对象(但Object不满足)
       */
      console.log(Fn.prototype instanceof Object) // true
      console.log(Object.prototype instanceof Object) // false
      console.log(Function.prototype instanceof Object) // true
      /*
      2. 所有函数都是Function的实例(包含Function)
      */
      console.log(Function.__proto__===Function.prototype)
      /*
      3. Object的原型对象是原型链尽头
       */
      console.log(Object.prototype.__proto__) // null
    ```

- 原型链_属性问题

  - 读取对象的属性值时: 会自动到原型链中查找

  - 设置对象的属性值时: 不会查找原型链, 如果当前对象中没有此属性, 直接添加此属性并设置其值

  - 方法一般定义在原型中, 属性一般通过构造函数定义在对象本身上

    ```javascript
    function Fn() {
    
      }
      Fn.prototype.a = 'xxx'
      var fn1 = new Fn()
      console.log(fn1.a, fn1)
    
      var fn2 = new Fn()
      fn2.a = 'yyy'
      console.log(fn1.a, fn2.a, fn2)
    
      function Person(name, age) {
        this.name = name
        this.age = age
      }
      Person.prototype.setName = function (name) {
        this.name = name
      }
      var p1 = new Person('Tom', 12)
      p1.setName('Bob')
      console.log(p1)
    
      var p2 = new Person('Jack', 12)
      p2.setName('Cat')
      console.log(p2)
      console.log(p1.__proto__===p2.__proto__) // true
    ```

    

- instanceof是如何判断的?

  - 表达式: A instanceof B

  - 如果B函数的显式原型对象在A对象的原型链上, 返回true, 否则返回false

- Function是通过new自己产生的实例

  ```javascript
  /*
    案例1
     */
    function Foo() {  }
    var f1 = new Foo()
    console.log(f1 instanceof Foo) // true
    console.log(f1 instanceof Object) // true
  
    /*
    案例2
     */
    console.log(Object instanceof Function) // true
    console.log(Object instanceof Object) // true
    console.log(Function instanceof Function) // true
    console.log(Function instanceof Object) // true
  
    function Foo() {}
    console.log(Object instanceof  Foo) // false
  ```

  - 06_面试题

    ```javascript
     /*
      测试题1
       */
      function A () {
    
      }
      A.prototype.n = 1
    
      var b = new A()
    
      A.prototype = {
        n: 2,
        m: 3
      }
    
      var c = new A()
      console.log(b.n, b.m, c.n, c.m)//1 undefine 2 3
    
    
      /*
       测试题2
       */
      function F (){}
      Object.prototype.a = function(){
        console.log('a()')
      }
      Function.prototype.b = function(){
        console.log('b()')
      }
      
      var f = new F()
      f.a() //a()
      // f.b()//报错
      F.a()//a()
      F.b()//b()
      console.log(f)
      console.log(Object.prototype)
      console.log(Function.prototype)
    
    ```

    

## 6.执行上下文与执行上下文栈

* 变量提升与函数提升

  * 变量提升: 在变量定义语句之前, 就可以访问到这个变量(undefined)

  * 函数提升: 在函数定义语句之前, 就执行该函数

  * 先有变量提升, 再有函数提升

    ```JavaScript
    <!--
    1. 变量声明提升
      * 通过var定义(声明)的变量, 在定义语句之前就可以访问到
      * 值: undefined
    2. 函数声明提升
      * 通过function声明的函数, 在之前就可以直接调用
      * 值: 函数定义(对象)
    3. 问题: 变量提升和函数提升是如何产生的?
    -->
    <script type="text/javascript">
      console.log('-----')
      /*
      面试题 : 输出 undefined
       */
      var a = 3
      function fn () {
        console.log(a)
        var a = 4
      }
      fn()
    
      console.log(b) //undefined  变量提升
      fn2() //可调用  函数提升
      // fn3() //不能  变量提升
    
      var b = 3
      function fn2() {
        console.log('fn2()')
      }
    
       var fn3 = function () {
        console.log('fn3()')
      }
    ```

* 理解

  * 执行上下文: 由js引擎自动创建的对象, 包含对应作用域中的所有变量属性

    ```JavaScript
    <!--
    1. 代码分类(位置)
      * 全局代码
      * 函数(局部)代码
    2. 全局执行上下文
      * 在执行全局代码前将window确定为全局执行上下文
      * 对全局数据进行预处理
        * var定义的全局变量==>undefined, 添加为window的属性
        * function声明的全局函数==>赋值(fun), 添加为window的方法
        * this==>赋值(window)
      * 开始执行全局代码
    3. 函数执行上下文
      * 在调用函数, 准备执行函数体之前, 创建对应的函数执行上下文对象(虚拟的, 存在于栈中)
      * 对局部数据进行预处理
        * 形参变量==>赋值(实参)==>添加为执行上下文的属性
        * arguments==>赋值(实参列表), 添加为执行上下文的属性
        * var定义的局部变量==>undefined, 添加为执行上下文的属性
        * function声明的函数 ==>赋值(fun), 添加为执行上下文的方法
        * this==>赋值(调用函数的对象)
      * 开始执行函数体代码
    -->
    <script type="text/javascript">
      // 全局执行上下文
      console.log(a1, window.a1)//undefined  undefined 
      window.a2()//a2()
      console.log(this)//window
    
      var a1 = 3
      function a2() {
        console.log('a2()')
      }
      console.log(a1) //3
    
      // 函数执行上下文
      function fn(a1){
        console.log(a1);//3
        console.log(a2);//undefined
        a3()
        console.log(this);//windown
        console.log(arguments);//伪数组（2,3）
        var a2=3
        function a3 (){
          console.log('a3()')
        }
      }
      fn(2.3)
    ```

  * 执行上下文栈: 用来管理产生的多个执行上下文

    ```JavaScript
    <!--
    1. 在全局代码执行前, JS引擎就会创建一个栈来存储管理所有的执行上下文对象
    2. 在全局执行上下文(window)确定后, 将其添加到栈中(压栈)
    3. 在函数执行上下文创建后, 将其添加到栈中(压栈)
    4. 在当前函数执行完后,将栈顶的对象移除(出栈)
    5. 当所有的代码执行完后, 栈中只剩下window
    -->
    <script type="text/javascript">
                                //1.进入全局执行上下文
      var a = 10
      var bar = function (x) {
        var b = 5
        foo(x + b)              //3.进入foo执行上下文
      }
      var foo = function (y) {
        var c = 5
        console.log(a + c + y)
      }
      bar(10)                  //2.进入bar函数执行上下文
      // bar(10)
    
    ```

* 分类:

  * 全局: window
  * 函数: 对程序员来说是透明的

* 生命周期

  * 全局 : 准备执行全局代码前产生, 当页面刷新/关闭页面时死亡
  * 函数 : 调用函数时产生, 函数执行完时死亡

* 包含哪些属性:

  * 全局 : 
    * 用var定义的全局变量  ==>undefined
    * 使用function声明的函数   ===>function
    * this   ===>window
  * 函数
    * 用var定义的局部变量  ==>undefined
    * 使用function声明的函数   ===>function
    * this   ===> 调用函数的对象, 如果没有指定就是window 
    * 形参变量   ===>对应实参值
    * arguments ===>实参列表的伪数组

* 执行上下文创建和初始化的过程

  * 全局:
    * 在全局代码执行前最先创建一个全局执行上下文(window)
    * 收集一些全局变量, 并初始化
    * 将这些变量设置为window的属性
  * 函数:
    * 在调用函数时, 在执行函数体之前先创建一个函数执行上下文
    * 收集一些局部变量, 并初始化
    * 将这些变量设置为执行上下文的属性

```JavaScript
<!--
1. 依次输出什么?
  gb: undefined
  fb: 1
  fb: 2
  fb: 3
  fe: 3
  fe: 2
  fe: 1
  ge: 1
2. 整个过程中产生了几个执行上下文?  5
-->
<script type="text/javascript">
  console.log('gb: '+ i)
  var i = 1
  foo(1)
  function foo(i) {
    if (i == 4) {
      return
    }
    console.log('fb:' + i)
    foo(i + 1) //递归调用: 在函数内部调用自己
    console.log('fe:' + i)
  }
  console.log('ge: ' + i)

```

##### 面试题

```JavaScript
  /*
   测试题1:  先执行变量提升, 再执行函数提升
   */
  function a() {}
  var a
  console.log(typeof a) // 'function'


  /*
   测试题2:
   */
  if (!(b in window)) {
    var b = 1
  }
  console.log(b) // undefined

  /*
   测试题3:变量名与函数名同名报错
   */
  var c = 1
  function c(c) {
    console.log(c)
    var c = 3
  }
  c(2) // 报错

```

## 7.作用域与作用域链

* 理解:

  * 作用域: 一块代码区域, 在编码时就确定了, 不会再变化

    ```JavaScript
    <!--
    1. 理解
      * 就是一块"地盘", 一个代码段所在的区域
      * 它是静态的(相对于上下文对象), 在编写代码时就确定了
    2. 分类
      * 全局作用域
      * 函数作用域
      * 没有块作用域(ES6有了)
    3. 作用
      * 隔离变量，不同作用域下同名变量不会有冲突
    -->
    <script type="text/javascript">
    /*  //没块作用域
      if(true) {
        var c = 3
      }
      console.log(c)*/
    
      var a = 10,
        b = 20
      function fn(x) {
        var a = 100,
          c = 300;
        console.log('fn()', a, b, c, x)
        function bar(x) {
          var a = 1000,
            d = 400
          console.log('bar()', a, b, c, d, x)
        }
    
        bar(100)
        bar(200)
      }
      fn(10)
    
    ```

    

  * 作用域链: 多个嵌套的作用域形成的由内向外的结构, 用于查找变量

    ```
    
    ```

* 分类:

  * 全局
  * 函数
  * js没有块作用域(在ES6之前)

* 作用

  * 作用域: 隔离变量, 可以在不同作用域定义同名的变量不冲突

  * 作用域链: 查找变量

    ```JavaScript
    <!--
    1. 理解
      * 多个上下级关系的作用域形成的链, 它的方向是从下向上的(从内到外)
      * 查找变量时就是沿着作用域链来查找的
    2. 查找一个变量的查找规则
      * 在当前作用域下的执行上下文中查找对应的属性, 如果有直接返回, 否则进入2
      * 在上一级作用域的执行上下文中查找对应的属性, 如果有直接返回, 否则进入3
      * 再次执行2的相同操作, 直到全局作用域, 如果还找不到就抛出找不到的异常
    -->
    <script type="text/javascript">
      var a = 1
      function fn1() {
        var b = 2
        function fn2() {
          var c = 3
          console.log(c)
          console.log(b)
          console.log(a)
          console.log(d)
        }
        fn2()
      }
      fn1()
    
    ```

* 区别作用域与执行上下文

  * 作用域: 静态的, 编码时就确定了(不是在运行时), 一旦确定就不会变化了

  * 执行上下文: 动态的, 执行代码时动态创建, 当执行结束消失

  * 联系: 执行上下文环境是在对应的作用域中的

    ```JavaScript
    <!--
    1. 区别1
      * 全局作用域之外，每个函数都会创建自己的作用域，作用域在函数定义时就已经确定了。而不是在函数调用时
      * 全局执行上下文环境是在全局作用域确定之后, js代码马上执行之前创建
      * 函数执行上下文是在调用函数时, 函数体代码执行之前创建
    2. 区别2
      * 作用域是静态的, 只要函数定义好了就一直存在, 且不会再变化
      * 执行上下文是动态的, 调用函数时创建, 函数调用结束时就会自动释放
    3. 联系
      * 执行上下文(对象)是从属于所在的作用域
      * 全局上下文环境==>全局作用域
      * 函数上下文环境==>对应的函数使用域
    -->
    <script type="text/javascript">
      var a = 10,
        b = 20
      function fn(x) {
        var a = 100,
          c = 300;
        console.log('fn()', a, b, c, x)
        function bar(x) {
          var a = 1000,
            d = 400
          console.log('bar()', a, b, c, d, x)
        }
    
        bar(100)
        bar(200)
      }
      fn(10)
    
    ```

##### 面试题

```JavaScript
var x = 10;
  function fn() {
    console.log(x);
  }
  function show(f) {
    var x = 20;
    
    f();
  }
  show(fn);
  
  /***************************************************/
   var fn = function () {
    console.log(fn)
  }
  fn()

  var obj = {
    fn2: function () {
     console.log(fn2)
     //console.log(this.fn2)
    }
  }
  obj.fn2()

```

## 8.闭包 

* 理解:

  * 当嵌套的内部函数引用了外部函数的变量时就产生了闭包
  * 通过chrome工具得知: 闭包本质是内部函数中的一个对象, 这个对象中包含引用的变量属性

* 常见的闭包

  - 将函数作为另一个函数的返回值

  - 将函数作为实参传递给另一个函数调用

    ```JavaScript
    // 1. 将函数作为另一个函数的返回值
      function fn1() {
        var a = 2
        function fn2() {
          a++
          console.log(a)
        }
        return fn2
      }
      var f = fn1()
      f() // 3
      f() // 4
    
      // 2. 将函数作为实参传递给另一个函数调用
      function showDelay(msg, time) {
        setTimeout(function () {
          alert(msg)
        }, time)
      }
      showDelay('atguigu', 2000)
    
    ```

* 作用:

  * 延长局部变量的生命周期

  * 让函数外部能操作内部的局部变量

    ```JavaScript
    <!--
    1. 使用函数内部的变量在函数执行完后, 仍然存活在内存中(延长了局部变量的生命周期)
    2. 让函数外部可以操作(读写)到函数内部的数据(变量/函数)
    
    问题:
      1. 函数执行完后, 函数内部声明的局部变量是否还存在?  一般是不存在, 存在于闭中的变量才可能存在
      2. 在函数外部能直接访问函数内部的局部变量吗? 不能, 但我们可以通过闭包让外部操作它
    -->
    <script type="text/javascript">
      function fn1() {
        var a = 2
        function fn2() {
          a++
          console.log(a)
          // return a
        }
        function fn3() {
          a--
          console.log(a)
        }
        return fn3
      }
      var f = fn1()
      f() // 1
      f() // 0
    
    ```

* 闭包的生命周期

  - 产生: 在嵌套内部函数定义执行完时就产生了(不是在调用)

  - 死亡: 在嵌套的内部函数成为垃圾对象时

    ```JavaScript
    function fn1() {
        //此时闭包就已经产生了(函数提升, 内部函数对象已经创建了)
        var a = 2
        function fn2 () {
          a++
          console.log(a)
        }
        return fn2
      }
      var f = fn1()
      f() // 3
      f() // 4
      f = null //闭包死亡(包含闭包的函数对象成为垃圾对象)
    
    ```

* 写一个闭包程序

  ```JavaScript
  <!--
  1. 如何产生闭包?
    * 当一个嵌套的内部(子)函数引用了嵌套的外部(父)函数的变量(函数)时, 就产生了闭包
  2. 闭包到底是什么?
    * 使用chrome调试查看
    * 理解一: 闭包是嵌套的内部函数(绝大部分人)
    * 理解二: 包含被引用变量(函数)的对象(极少数人)
    * 注意: 闭包存在于嵌套的内部函数中
  3. 产生闭包的条件?
    * 函数嵌套
    * 内部函数引用了外部函数的数据(变量/函数)
  -->
  function fn1() {
    var a = 2;
    function fn2() {
      a++;
      console.log(a);
    }
    return fn2;
  }
  var f = fn1();
  f();
  f();
  
  ```

* 闭包应用:

  * 模块化: 封装一些数据以及操作数据的函数, 向外暴露一些行为

  * 循环遍历加监听

  * JS框架(jQuery)大量使用了闭包

    ```javascript
    //应用1
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <title>05_闭包的应用_自定义JS模块</title>
    </head>
    <body>
    <!--
    闭包的应用2 : 定义JS模块
      * 具有特定功能的js文件
      * 将所有的数据和功能都封装在一个函数内部(私有的)
      * 只向外暴露一个包信n个方法的对象或函数
      * 模块的使用者, 只需要通过模块暴露的对象调用方法来实现对应的功能
    -->
    <script type="text/javascript" src="myModule.js"></script>
    <script type="text/javascript">
      var module = myModule()
      module.doSomething()
      module.doOtherthing()
    </script>
    </body>
    </html>
    /*******************************myModule*********************/
    function myModule() {
      //私有数据
      var msg = 'My atguigu'
      //操作数据的函数
      function doSomething() {
        console.log('doSomething() '+msg.toUpperCase())
      }
      function doOtherthing () {
        console.log('doOtherthing() '+msg.toLowerCase())
      }
    
      //向外暴露对象(给外部使用的方法)
      return {
        doSomething: doSomething,
        doOtherthing: doOtherthing
      }
    }
    
    
    //应用2
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <title>05_闭包的应用_自定义JS模块2</title>
    </head>
    <body>
    <!--
    闭包的应用2 : 定义JS模块
      * 具有特定功能的js文件
      * 将所有的数据和功能都封装在一个函数内部(私有的)
      * 只向外暴露一个包信n个方法的对象或函数
      * 模块的使用者, 只需要通过模块暴露的对象调用方法来实现对应的功能
    -->
    <script type="text/javascript" src="myModule2.js"></script>
    <script type="text/javascript">
      myModule2.doSomething()
      myModule2.doOtherthing()
    </script>
    </body>
    </html>
    /*******************************myModule2*********************/
    
    (function () {
      //私有数据
      var msg = 'My atguigu'
      //操作数据的函数
      function doSomething() {
        console.log('doSomething() '+msg.toUpperCase())
      }
      function doOtherthing () {
        console.log('doOtherthing() '+msg.toLowerCase())
      }
    
      //向外暴露对象(给外部使用的方法)
      window.myModule2 = {
        doSomething: doSomething,
        doOtherthing: doOtherthing
      }
    })()
    
    ```

* 缺点:

  * 变量占用内存的时间可能会过长

  * 可能导致内存泄露

  * 解决:

    * 及时释放 : f = null; //让内部函数对象成为垃圾对象

      ```JavaScript
      1. 缺点
        * 函数执行完后, 函数内的局部变量没有释放, 占用内存时间会变长
        * 容易造成内存泄露
      2. 解决
        * 能不用闭包就不用
        * 及时释放
      -->
      <script type="text/javascript">
        function fn1() {
          var arr = new Array[100000]
          function fn2() {
            console.log(arr.length)
          }
          return fn2
        }
        var f = fn1()
        f()
      
        f = null //让内部函数成为垃圾对象-->回收闭包
      
      ```

##### 面试题

```JavaScript
//代码片段一
  var name = "The Window";
  var object = {
    name : "My Object",
    getNameFunc : function(){
      return function(){
        return this.name;
      };
    }
  };
  alert(object.getNameFunc()());  //?  the window


  //代码片段二
  var name2 = "The Window";
  var object2 = {
    name2 : "My Object",
    getNameFunc : function(){
      var that = this;
      return function(){
        return that.name2;
      };
    }
  };
  alert(object2.getNameFunc()()); //?  my object
/***************************************************************************/
 function fun(n,o) {
    console.log(o)
    return {
      fun:function(m){
        return fun(m,n)
      }
    }
  }
  var a = fun(0)
  a.fun(1)
  a.fun(2)
  a.fun(3)//undefined,0,0,0

  var b = fun(0).fun(1).fun(2).fun(3)//undefined,0,1,2

  var c = fun(0).fun(1)
  c.fun(2)
  c.fun(3)//undefined,0,1,1

```

## 9.内存溢出与内存泄露

1. 内存溢出

  * 一种程序运行出现的错误
  * 当程序运行需要的内存超过了剩余的内存时, 就出抛出内存溢出的错误

2. 内存泄露

  * 占用的内存没有及时释放

  * 内存泄露积累多了就容易导致内存溢出

  * 常见的内存泄露:

    * 意外的全局变量

    * 没有及时清理的计时器或回调函数

    * 闭包

      ```JavaScript
      <!--
      1. 内存溢出
        * 一种程序运行出现的错误
        * 当程序运行需要的内存超过了剩余的内存时, 就出抛出内存溢出的错误
      2. 内存泄露
        * 占用的内存没有及时释放
        * 内存泄露积累多了就容易导致内存溢出
        * 常见的内存泄露:
          * 意外的全局变量
          * 没有及时清理的计时器或回调函数
          * 闭包
      -->
        // 1. 内存溢出
        var obj = {}
        for (var i = 0; i < 10000; i++) {
          obj[i] = new Array(10000000)
          console.log('-----')
        }
      
        // 2. 内存泄露
          // 意外的全局变量
        function fn() {
          a = new Array(10000000)
          console.log(a)
        }
        fn()
      
         // 没有及时清理的计时器或回调函数
        var intervalId = setInterval(function () { //启动循环定时器后不清理
          console.log('----')
        }, 1000)
      
        // clearInterval(intervalId)//解决方法
      
          // 闭包
        function fn1() {
          var a = 4
          function fn2() {
            console.log(++a)
          }
          return fn2
        }
        var f = fn1()
        f()
      
        // f = null//解决方法
      
      ```


## 10.对象的创建模式

* Object构造函数模式

  ```JavaScript
  <!--
  方式一: Object构造函数模式
    * 套路: 先创建空Object对象, 再动态添加属性/方法
    * 适用场景: 起始时不确定对象内部数据
    * 问题: 语句太多
  -->
  <script type="text/javascript">
    /*
    一个人: name:"Tom", age: 12
     */
    // 先创建空Object对象
    var p = new Object()
    p = {} //此时内部数据是不确定的
    // 再动态添加属性/方法
    p.name = 'Tom'
    p.age = 12
    p.setName = function (name) {
      this.name = name
    }
  
    //测试
    console.log(p.name, p.age)
    p.setName('Bob')
    console.log(p.name, p.age)
  ```

* 对象字面量模式

  ```JavaScript
  <!--
  方式二: 对象字面量模式
    * 套路: 使用{}创建对象, 同时指定属性/方法
    * 适用场景: 起始时对象内部数据是确定的
    * 问题: 如果创建多个对象, 有重复代码
  -->
  <script type="text/javascript">
    var p = {
      name: 'Tom',
      age: 12,
      setName: function (name) {
        this.name = name
      }
    }
  
    //测试
    console.log(p.name, p.age)
    p.setName('JACK')
    console.log(p.name, p.age)
  
    var p2 = {  //如果创建多个对象代码很重复
      name: 'Bob',
      age: 13,
      setName: function (name) {
        this.name = name
      }
    }
  ```

* 工程模式

  ```JavaScript
  <!--
  方式三: 工厂模式
    * 套路: 通过工厂函数动态创建对象并返回
    * 适用场景: 需要创建多个对象
    * 问题: 对象没有一个具体的类型, 都是Object类型
  -->
  <script type="text/javascript">
    function createPerson(name, age) { //返回一个对象的函数===>工厂函数
      var obj = {
        name: name,
        age: age,
        setName: function (name) {
          this.name = name
        }
      }
  
      return obj
    }
  
    // 创建2个人
    var p1 = createPerson('Tom', 12)
    var p2 = createPerson('Bob', 13)
  
    // p1/p2是Object类型
  
    function createStudent(name, price) {
      var obj = {
        name: name,
        price: price
      }
      return obj
    }
    var s = createStudent('张三', 12000)
    // s也是Object
  ```

  

* 构造函数模式

  ```JavaScript
  <!--
  方式四: 自定义构造函数模式
    * 套路: 自定义构造函数, 通过new创建对象
    * 适用场景: 需要创建多个类型确定的对象
    * 问题: 每个对象都有相同的数据, 浪费内存
  -->
  <script type="text/javascript">
    //定义类型
    function Person(name, age) {
      this.name = name
      this.age = age
      this.setName = function (name) {
        this.name = name
      }
    }
    var p1 = new Person('Tom', 12)
    p1.setName('Jack')
    console.log(p1.name, p1.age)
    console.log(p1 instanceof Person)
  
    function Student (name, price) {
      this.name = name
      this.price = price
    }
    var s = new Student('Bob', 13000)
    console.log(s instanceof Student)
  
    var p2 = new Person('JACK', 23)
    console.log(p1, p2)
  ```

* 构造函数+原型的组合模式

  ```JavaScript
  <!--
  方式六: 构造函数+原型的组合模式
    * 套路: 自定义构造函数, 属性在函数中初始化, 方法添加到原型上
    * 适用场景: 需要创建多个类型确定的对象
  -->
  <script type="text/javascript">
    function Person(name, age) { //在构造函数中只初始化一般函数
      this.name = name
      this.age = age
    }
    Person.prototype.setName = function (name) {
      this.name = name
    }
  
    var p1 = new Person('Tom', 23)
    var p2 = new Person('Jack', 24)
    console.log(p1, p2)
  ```

## 11.继承模式

* 原型链继承 : 得到方法

  ```JavaScript
  <!--
  方式1: 原型链继承
    1. 套路
      1. 定义父类型构造函数
      2. 给父类型的原型添加方法
      3. 定义子类型的构造函数
      4. 创建父类型的对象赋值给子类型的原型
      5. 将子类型原型的构造属性设置为子类型
      6. 给子类型原型添加方法
      7. 创建子类型的对象: 可以调用父类型的方法
    2. 关键
      1. 子类型的原型为父类型的一个实例对象
  -->
  <script type="text/javascript">
    //父类型
    function Supper() {
      this.supProp = 'Supper property'
    }
    Supper.prototype.showSupperProp = function () {
      console.log(this.supProp)
    }
  
    //子类型
    function Sub() {
      this.subProp = 'Sub property'
    }
  
    // 子类型的原型为父类型的一个实例对象
    Sub.prototype = new Supper()
    // 让子类型的原型的constructor指向子类型
    Sub.prototype.constructor = Sub
    Sub.prototype.showSubProp = function () {
      console.log(this.subProp)
    }
  
    var sub = new Sub()
    sub.showSupperProp()
    // sub.toString()
    sub.showSubProp()
  
    console.log(sub)  // Sub
  ```

  ![](/img/原型链继承.png)

* 借用构造函数 : 得到属性

  ```JavaScript
  <!--
  方式2: 借用构造函数继承(假的)
  1. 套路:
    1. 定义父类型构造函数
    2. 定义子类型构造函数
    3. 在子类型构造函数中调用父类型构造
  2. 关键:
    1. 在子类型构造函数中通用call()调用父类型构造函数
  -->
  <script type="text/javascript">
    function Person(name, age) {
      this.name = name
      this.age = age
    }
    function Student(name, age, price) {
      Person.call(this, name, age)  // 相当于: this.Person(name, age)
      /*this.name = name
      this.age = age*/
      this.price = price
    }
  
    var s = new Student('Tom', 20, 14000)
    console.log(s.name, s.age, s.price)
  ```

* 组合

  ```JavaScript
  <!--
  方式3: 原型链+借用构造函数的组合继承
  1. 利用原型链实现对父类型对象的方法继承
  2. 利用super()借用父类型构建函数初始化相同属性
  -->
  <script type="text/javascript">
    function Person(name, age) {
      this.name = name
      this.age = age
    }
    Person.prototype.setName = function (name) {
      this.name = name
    }
  
    function Student(name, age, price) {
      Person.call(this, name, age)  // 为了得到属性
      this.price = price
    }
    Student.prototype = new Person() // 为了能看到父类型的方法
    Student.prototype.constructor = Student //修正constructor属性
    Student.prototype.setPrice = function (price) {
      this.price = price
    }
  
    var s = new Student('Tom', 24, 15000)
    s.setName('Bob')
    s.setPrice(16000)
    console.log(s.name, s.age, s.price)
  ```

* new一个对象背后做了些什么?

  * 创建一个空对象
  * 给对象设置__proto__, 值为构造函数对象的prototype属性值   this.__proto__ = Fn.prototype
  * 执行构造函数体(给对象添加属性/方法)