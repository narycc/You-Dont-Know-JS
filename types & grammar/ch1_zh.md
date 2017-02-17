# 你不知道的JS：类型与语法
# 第1章：类型


大多数开发者会说动态语言（比如JS）是没有“类型”的概念的。让我们来看下[ES5.1 规范](http://www.ecma-international.org/ecma-262/5.1/)中关于这个话题是怎么说的：
> 这份规范中的算法操作有对应类型的值。可能的值类型都在这份规范中有定义。类型在这里被细分成ECMAScript 语言类型和规范类型。
>
> ECMAScript 语言类型对应被ECMAScript 程序员使用ECMAScript 语言操作的值。ECMAScript语言类型有：Undefined, Null,Boolean,String,Number, 和Object.

如果你现在是强类型（静态类型）语言的粉丝，你或许会反对使用“类型”这个词。在那些语言中，“类型”的含义比JS中的表示的要多的多。

有些人说JS不应该称作有“类型”，他们应该被称为“标签”或者“子类型”。

我们将使用这个粗略的定义：“类型”是JavaScript 固有的内建一套特征，标识了特定值的行为并使引擎和开发者能将它与其他值区分开来。

换句话说，如果引擎和开发者把`42`和`"42"`当成是不一样的值，那么这两个值就有不一样的类型，分别是：数字和字符串。使用`42`表明你想做一些数字相关的事情，比如数学。使用`"42"`的时候表明你想做一些字符串相关的事情，比如将它输出到页面上。这两值有不同的类型。

这决不是一个完美的定义。但是用于讨论足够了。它与JS如果描述自己是一致的。


# 取其他名字的类型

除了学术定义的不一致，为什么JavaScript 是否有“类型”那么重要呢？

正确理解每个“类型”以及它的本质行对理解如何正确将值转化成不同的类型非常必要（参见强制转换，第4章）。几乎每一个JS程序都需要以某种形式处理值类型转换，因此你对这种转换负责并自信十足就十分重要了。

如果你有一个number 值为42，但是你想把它当成一个字符串，比如取出位置为1 时候的字符“2”， 很明显你需要将它强制转换成string 类型。

这看起来再简单不过了。

但是这种强制转换有很多种方式。有一些是显式的，很容易看出来，也可靠。但是如果你不仔细，强制转换发生的情况可能会非常奇怪。

强制转换的困扰或许是JavaScript 开发者最悠久的一个障碍了。它经常被批判为危险行为，被视为这门语言的设计缺陷建议避免使用。

完全理解了JavaScript 类型之后，我们要展示为什么强制转换的坏名声是被过度夸大，倍感冤屈。我们重新审视强制转换的力量和用处。但是首先，我们要先好好掌握值和类型。

## 内建类型

JavaScript 定义了7种内建类型：

* `null`
* `undefined`
* `boolean`
* `number`
* `string`
* `object`
* `symbol` -- ES6中加入的。

**说明：** 除了“object”其他所有的类型都称为基本数据类型。 

`typeof`操作符检测给定值的类型，通常返回以上7种类型之一，但是以上7种类型并不存在精确的一一对应。

```js
typeof undefined     === "undefined"; // true
typeof true          === "boolean";   // true
typeof 42            === "number";    // true
typeof "42"          === "string";    // true
typeof { life: 42 }  === "object";    // true

// added in ES6!
typeof Symbol()      === "symbol";    // true
```

这六个类型有对应的值与之对应，返回的一个同名的字符串。Symbol ES6的一个新数据类型，第3章中会说明。

正如你注意到的，我把null 排除在上面的展示之外。它比较特殊，特殊在当你把它和typeof 操作符结合使用的时候会有点奇怪：

```js
typeof null === "object"; // true
```

如果它会返回“null”那就太好了，但是这个最初的bug 在JS存在了近20年，它可能永远也不会被修复，因为有太多的现有网页依赖了这个有问题的行为，如果修复了这个bug 那么可能会引起web 软件行业更多的bug。

如果你想要使用它的类型测试一个null 值，你需要使用混合条件：

```js
var a = null;

(!a && typeof a === "object"); // true
```

null是唯一一个看起来错误的原始数据类型，但是typeof 检测的时候还是会返回“object”。

那么第七个typeof 会返回的字符串值是什么呢？

```js
typeof function a(){ /* .. */ } === "function"; // true
```

很容易想到function 是JS 中重量级的内建类型，可以使用typeof 操作符查看它的类型。然而，如果你阅读以下规范，你会发现它其实是object 的子类型。函数是一个可以调用的对象，这个对象的内部`[[Call]]`属性允许它被调用。

函数是对象的事实非常有用，最主要的是它们可以有属性，如：

```js
function a(b,c) {
	/* .. */
}
```

这个函数对象有一个length 的属性表示它声明时候正式参数的个数。
```js
a.length; // 2
```

函数声明的时候提供了两个正式命名参数（`b` 和 `c`），这个函数的长度就是2。

那么数组呢？ 它们是JS 原生的，它们是特殊类型吗？

```js
typeof [1,2,3] === "object"; // true
```

不，对象而已。把它们视为对象的子类型最好不过了，相对于普通对象使用字符串为key，数组通过数字索引，并且有一个动态更新的“length” 属性。

## 值类型

在JavaScript 中，值有类型，变量是没有类型的。变量随时可以存储任何值。

另一种思考JS类型的方式是JS没有强制类型，引擎中不会有某个变量只能存储它最开始指定的类型的值的情况。一个变量在一个赋值语句中能存储“string”，也能在下一个赋值语句中存储“number”。

`42` 最开始的类型是number, 它的类型是可变的。 `"42"`的类型是string，可以通过将数字42 经过强制转化获得。

如果在一个变量上使用typeof，不要以为它是在问这个变量的类型是什么，因为JS 变量没有类型。它是在问这个变量中存储的值的类型是什么。

```js
var a = 42;
typeof a; // "number"

a = true;
typeof a; // "boolean"
```

typeof 操作符总是返回一个字符串，因此：

```js
typeof typeof 42; // "string"
```

`typeof 42`返回number，所以上面的语句其实等价于`typeof "number"`，结果是“string”。

### undefined 和未声明

当前无值的变量的值其实是`undefined`，调用typeof 的时候返回`"undefined"`。

```js
var a;

typeof a; // "undefined"

var b = 42;
var c;

// later
b = c;

typeof b; // "undefined"
typeof c; // "undefined"
```

大部分开发者会把“undefined” 和为声明当成近义词。但是在JS 中它们是两个完全不同的概念。

一个“undefined” 的变量是在一个可访问的作用域中已经被声明了的变量，但是当前还没有值。与之对比，未声明的变量是指那些在可访问作用域内没有被正式声明的变量。

参见：

```js
var a;

a; // undefined
b; // ReferenceError: b is not defined
```

最让人讨厌的是浏览器在这种情况下给出的出错信息。正如你看到的，提示信息为“b is not defined” 也就是“b 未定义”，所以很容跟“b is undefined” 也就是“b 是undefined”混淆。再说一遍：undefined 和is not defined 是两回事。如果浏览器给出的信息是“b 找不到” 或者“b 未声明”可能会更好点，可以减少混淆。

另外，typeof 测试一个未声明的变量的返回值更加加深了混淆，如下：

```js
var a;

typeof a; // "undefined"

typeof b; // "undefined"
```

“undeclared” 或者“not defined”的变量执行typeof 时返回了“undefined”。注意，就算是b 未声明，执行typeof 的时候并没有抛出异常，这是typeof 操作的一种特殊安全防护。

和上面类似，如果未声明的变量使用typeof 操作的时候返回“undeclared” 多好，而不会和undefined 的情况返回的值返回。

### 未声明变量的typeof

尽管如此，这种安全防护是浏览器处理JavaScript很有用的特性，浏览器中可以在共享的全局命名空间中加载多个脚本文件。

**说明：** 很多开发者认为全局命名空间中不应该有任何变量，所有的代码都应该写在模块中和各自的命名空间中。理想很丰满，但现实不可能，但这仍然是我们努力的目标。幸运的是，ES6 给模块提供了最好的支持，这将会让我们的目标更加容易实现。

一个简单的例子，设想你的项目中有一个调试模式，由全局变量“DEBUG”标志。 在执行一个调试任务比如将日志信息打印到console控制台，你想在执行这个调试任务之前检测这个变量是否被声明。在全局的顶部的声明`var DEBUG = true` 只会被包含在“debug.js” 文件中，这个文件你只在开发环境或者测试的时候加载，生产环境不会加载。

然而，你必须注意在另外的应用代码中你是怎么检测这个全局的DEBUG变量的，要不然可能会抛出`ReferenceError`。这时候安全防护 typeof 就是我们的好朋友了。

```js
// 这样会抛错哦
if (DEBUG) {
	console.log( "Debugging is starting" );
}

// 这才是一个安全检测的方案
if (typeof DEBUG !== "undefined") {
	console.log( "Debugging is starting" );
}
```

这类检测在处理非用户定义变量时非常有用，比如DEBUG。如果你要做一个内建API 特性检测，你会发现它非常有用而且不会抛出错误：
```js
if (typeof atob === "undefined") {
	atob = function() { /*..*/ };
}
```

**说明：** 如果你要定义一个尚未存在的特性的“polyfill”（替代功能），你不想使用var来定义atob。如果你在if 语句中使用`var atob`声明，这个声明会被提升到作用域的顶部，尽管if 条件语句不成立（因为全局的atob 已经存在了）。对于某些浏览器和某些特殊的全局内建变量，这种重复声明会报错。去掉var 可以防止变量提升。

有另一种不使用typeof 安全防护的方式来检测全局变量：所有的全局变量都是全局对象的属性，浏览器中就是window 对象。因此，上面的检测也可以这样进行（很安全）：


```js
if (window.DEBUG) {
	// ..
}

if (!window.atob) {
	// ..
}
```

与引用未定义的变量不同，尝试访问对象不存在的属性（甚至是全局的window对象）不会抛出`ReferenceError` 错误。

另一方面，一些开发者避免手动的引用全局的window，尤其是当你的代码要在多个JS环境中运行的时候（不仅仅是浏览器，比如服务器端的node.js），全局的对象不一定是window。

总的来说，typeof 安全防护在不能使用全局变量的情况下非常有用，尽管这种情况不常见，一些开发者可能发现这种设计方式不是很令人满意。假设一个工具函数，你想要被人复制粘贴到他们的项目或者模块中去，你想在这个工具函数中检测这个包含它的程序中是否已经已经了某个变量（没定义你才能使用）：

```js
function doSomethingCool() {
	var helper =
		(typeof FeatureXYZ !== "undefined") ?
		FeatureXYZ :
		function() { /*.. default feature ..*/ };

	var val = helper();
	// ..
}
```

`doSomethingCool()` 测试变量`FeatureXYZ`，如果找到了，就是用它，如果没找到就用它自己定义的。现在，如果谁要把这段代码放到它自己的模块或者程序中，就能很安全的检测是否已经定义了`FeatureXYZ`。

```js
// an IIFE (参见 "立即执行函数")
(function(){
	function FeatureXYZ() { /*.. my XYZ feature ..*/ }

	// include `doSomethingCool(..)`
	function doSomethingCool() {
		var helper =
			(typeof FeatureXYZ !== "undefined") ?
			FeatureXYZ :
			function() { /*.. default feature ..*/ };

		var val = helper();
		// ..
	}

	doSomethingCool();
})();
```

`FeatureXYZ`不是一个全局变量，但我们仍然使用typeof 安全防护来保证检测安全。重要的是，这里没有对象可以用来做检测，所以typeof 就非常有用了.

有些开发者倾向使用一种叫“依赖注入”的设计模式，不在`doSomethingCool()`中隐式地检测在函数外定义的`FeatureXYZ`，它需要显式地传入一个依赖，如：

```js
function doSomethingCool(FeatureXYZ) {
	var helper = FeatureXYZ ||
		function() { /*.. default feature ..*/ };

	var val = helper();
	// ..
}
```

设计这里功能的时候有很多选择，没有一种模式是对的或者错的，每种方式都有很多权衡。但是总的来说，typeof 未声明的安全防护给我们提供了更多的选择。

## 回顾

JavaScript 有其中内置类型：`null`，`undefined`，`boolean`，`number`，`string`，`object`，`symbol`。它们可以通过typeof 来识别。

变量没有类型，它们保存的值有。这些类型定义了这些值的行为方式。

很多开发者认为“undefined” 和“undeclared” 是大致相同的东西，但是在JavaScript 中，他们是完全不同的。undefined 是一个已经声明的变量保存的值，undeclared 的意思是这个变量从未被声明。

JavaScript 很不幸地混淆了这两个词，不仅在错误提示上（"ReferenceError: a is not defined"），而是在typeof 的返回值（`"undefined"`）上都误导了我们。

然而，在未声明的变量上使用 typeof 安全防护（防止报错）在某些场景是非常有用的。
