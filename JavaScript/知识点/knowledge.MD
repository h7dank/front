# JavaScript 知识点整理

## 一、JavaScript基础

### 变量和类型

1. JavaScript 规定了几种语言类型？

JavaScript 基本类型(primitive)包括 String、Number、Boolean、Null、Undefined、Symbol、BigInt，复杂类型包括Object。基本类型的值一般存储在栈空间中，引用类型的值一般存储在堆空间中。基本类型的赋值会复制变量值，引用类型赋值会复制引用地址。

2. JavaScript 底层数据结构是怎么样的？

同上，同时解释为什么typeof null为Object 由于JavaScript语言为二进制存储，所有null的存储值为000，底层的判断机制为如果前三位为000 就是object，所有就会有typeof null === 'object' 这个bug

3. 基本类型对应的内置对象，以及他们之间的装箱拆箱操作

为了方便操作原始值，ECMAScript提供了3种特殊的引用类型：Boolean、Number和String，每当使用原始值的方法或者属性时，后台都会创建一个相应原始包装类型的对象，从而暴露出操作原始值的各种方法

```js
  /**
   * 1.创建一个string的实例
   * 2.调用实例上特定的方法
   * 3.销毁实例
   */
  let s1 = 'some text'
  let s2 = s1.substring(2)

```

等同于

```js
  let s1 = new String('some text')
  let s2 = s1.substring(2)
  s1 = null
```

原始类型创建的引用类型只存在于访问它的那行代码执行期间

4. 理解值类型和引用类型

值类型的数据值都是存在栈中，引用类型的值都是存在堆中，值类型复制之后修改不影响原来的值，而引用类型由于是在栈中存储引用地址，当复制之后的值改变之后，会影响倒原来的值

5. null和undefined的区别

6. 至少可以说出三种判断JavaScript数据类型的方式，以及他们的优缺点，如何准确的判断数组类型

7. 可能发生隐式类型转换的场景以及转换原则，应如何避免或巧妙应用
8. 出现小数精度丢失的原因，JavaScript可以存储的最大数字、最大安全数字，JavaScript处理大数字的方法、避免精度丢失的方法