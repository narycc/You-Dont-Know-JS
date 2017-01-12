# You Don't Know JS: 起步
# 第一章：程序入门

遵循的翻译规范 ['协作翻译规范'](https://github.com/react-guide/ETC)


**行动** 这一章介绍一些编程的基本概念（当然这里特指JS编程），以及如何阅读和理解这一系列的其他标题。尤其是，如果你刚刚接触JavaScript编程，这本书会带着你去探索入门该做些什么。

这本书以解释较高水平的编程基本准则为开端。这是特意为那些在开始这本书之前没有任何编程经验，并且希望这些书能帮助你以JavaScript的视角理解编程的朋友准备的。

第一章是程序入门的快速介绍。这里也列出了一些非常精彩的编程资源来帮助你更深入的研究这些主题，我支持你在读完这章节之后去学习一下。

你对编程的基本概念了解之后，第二章将引导你熟悉JavaScript的编程风格。第二章介绍了JavaScript是什么，但又不是一个全面的指南，那是这本书剩余的部分要讲的内容。

如果你已将JavaScript 使用的得心应手，可以直接跳到第三章看一眼这本书能学到什么内容。

## 代码

我们开始吧。

程序，通常指”源代码“或者”代码“，是告诉计算机要执行什么任务的一系列特殊命令的集合。代码通常被保存在text 文件中，JavaScript 代码也可以在浏览器的开发者控制台中直接输入，这部分我们会有简短的概述。

计算机语言，也叫语法，规定了正确的格式和命令的组合规则。跟英语教你如何拼写单词，用单词和标点造一个正确的句子是一样的。


### 语句

计算机语言中，一组执行一个特定命令的单词，数字和操作符称为“语句”。在JavaScript 中，语句是这样的：
```js
a = b * 2;
```

`a` 和 `b` 是变量，就像一个个可以存储东西的箱子。在程序中，变量存储值（比如数字24）。就把它们认为是值的占位符。

 `2` 是值本身，叫“字面量”，因为它没有用变量存储。

`=` 和 `*` 是“操作符”，它们执行赋值或者数学计算的操作。

JavaScript 中大部分语句以 `;` 结尾。

`a = b * 2;` 告诉计算机将存储在变量 `b` 中的值乘以`2`然后将得到的结果存储在变量`a`中。

程序就是大量语句的集合，它们共同描述了程序执行的每一步。


### 表达式

语句由一个或者多个表达式组成。表达式可以是一个变量或一个值，也可以是一组由操作符连接的变量和值，例如：

```js
a = b * 2;
```

这个语句包含四个表达式：

* `2` 是一个字面量表达式
* `b` 是一个变量表达式，用于或许它当前的值
* `b * 2` 是一个乘法的算术表达式
* `a = b * 2` 是一个赋值表达式，讲 b * 2 的结果赋值给变量a


如下所示的一个单独的表达式称为表达式语句：
```js
b * 2;
```
这种表达式语句不常见也没多大用处，因为它对程序的执行没有什么影响。它获得b 的值再乘以2，但是得到结果之后没有做任何事情。

一个更为常见的语句叫调用表达式（参见“函数”），函数调用了一个表达式：

```js
alert( a );
```

### 程序的执行

这些程序语句是怎么告诉计算机做什么操作的？程序需要被执行。 

像`a = b * 2` 这样的语句对于开发者来说易于读写，但是计算机理解不了。所以就有了一个特殊的工具用来将我们写的代码转换成计算机能够理解的命令，称为翻译机或者编译器。

一些计算机语言的翻译过程是从上到下逐行进行的，每一次执行程序的过程叫代码解释。

还有一些语言，翻译的过程是先做好，叫作代码编译。所以程序运行的时候其实是运行已经编译好的计算机指令。

JavaScript 执行的过程叫代码解释，因为JavaScript 源代码是每次运行的时候被处理，但并不完全准确。JavaScript 引擎事实上是一边编译源码，一边立马执行编译好的代码。

**贴士** 更多关于JavaScript 编译的信息，参见 **作用域和闭包** 的头两章节。 

## 动动你的小手

这一章将会以代码片段的方式介绍每一个变成的概念，当然所有的例子都是JavaScript 写的。

重要的事情说三遍：当你阅读这一章节内容的时候（或许你会反复阅读好几遍），你一定通过自己动手去写每一段代码来理解这些概念。最简单的方式就是用离你最近的浏览器的开发者工具控制台编写， 火狐，谷歌，IE 浏览器都行。

**贴士：**一般情况下你可以使用快捷键或者从菜单栏来快速打开控制台，[Mastering The Developer Tools Console](http://blog.teamtreehouse.com/mastering-developer-tools-console) 这篇文章有更多关于控制台的开启和使用的详细信息。在控制台下面输入多行代码需要使用`<shift> + <enter>`切换到下一行输入，如果你敲下`<enter>`，控制台会执行你在控制台中输入的内容。

那我们就来熟悉一下控制台下面执行代码的流程。首先，我建议你在浏览器中打开一个空白的面白，我一般会在地址栏中通过输入`about:blank`完成。然后确保你打开了控制台。

现在，输入这些代码，看看它会如何运行：

```js
a = 21;

b = a * 2;

console.log( b );
```

在chrome 浏览器中输入上述的代码，会产生如下所示的结果：

<img src="fig1.png" width="500">

加油，尝试吧。学习编程最好的方式就是开始码代码！
### 输出

在上面的代码片段中，我们使用了`console.log(..)`。让我们来稍微看一下那几行代码到底是什么。

或许你已经猜到了，那就是我们在开发者控制台下面打印文本的方式。我们要解释一下那一句的两个特征。

首先，`log( b )` 部分是一个函数调用。我们把`b` 传入到那个函数当中，并把它的值打印到控制台中。

第二，`console.` 部分是`log(..)` 所属的一个对象引用。 第2章会涵盖对象和属性的内容。

另外一种创建可见输出的方式是运行`alert(..)`，例如：
```js
alert( b );
```

运行，你会发现它不是在console 下面输出内容，而是弹出一个带有“OK”按钮的提示框，里面会显示b 变量的值。`console.log(..)`在学习编码和运行程序时使用起来比`alert(..)`更方便，因为它可以一次打印多个值，而不会影响浏览器界面展示。

这本书我们使用 `console.log(..)` 来输出。

### 输入


我们讨论输出的时候，你是不是对输入（从用户那儿接收信息）也充满好奇？

最常见的方式是在HTML页面上有一组表单元素，比如文本框，用户可以进行输入，然后使用JS 来读这些输入，并传给程序变量。

不过，对于简单的学习和展示，这本书中我们有一种更简便的方式，那就是使用`prompt(..)`函数：
```js
age = prompt( "Please tell me your age:" );

console.log( age );
```

你或许已经猜到了，这个实例中传给`prompt(..)`的信息`"Please tell me your age:"` 会被打印在弹出框中。

结果看起来会像这样：
<img src="fig2.png" width="500">

当你点击“OK”的时候，输入的文本就被提交了，并被存储在`age` 变量中，然后被`console.log(..)`输出：
<img src="fig3.png" width="500">

为了使学习基本编程概念的时候尽量保持简单，我们这本书中的例子不需要输入。但我们已经学会了如何使用`prompt(..)`，所以如果你想挑战自己，你可以在探索实例的时候尝试使用输入。
## 运算符

运算符决定了在变量和值之间执行怎样的运算。我们已经看到过两种JavaScript 的运算符了，`=` 和 `*`。

`*` 执行的是数学乘法运算，是不是很简单？

`=` 等号运算符用于赋值，我们先把右边的值（源值）计算出来，然后赋给左边定义好的变量（目标变量）上。
**警告：** 赋值看起来像是个奇怪的逆序。可能一些语言会把 `a = 42`反过来，把源放在左边目标变量放在右边，如 `42 -> a` （JavaScript 是不合法的）。很不幸，`a = 42` 的顺序不可变，这种形式在现代编程语言中特别流行，如果你感觉不自然，那么你只能花点时间适应这种顺序并习以为常了。

看看下面：

```js
a = 2;
b = a + 1;
```

把`2`赋给变量`a`。然后我们把a 变量的值加1 得到的结果3 存储到变量b 中。

程序中会用到一个非运算符的关键字`var`声明变量。

变量在使用之前需要先声明，但在一个作用域中只需要声明一次，然后在作用域内可以多次使用，例如：

```js
var a = 20;

a = a + 1;
a = a * 2;

console.log( a );	// 42
```

以下是JavaScrip 中最常用的一些运算符：

* 赋值： `=` 如 `a = 2`.
* 数学： `+` （加法）， `-` （减法）， `*` 乘法， 和 `/` （除法）如 `a * 3`.
* 复合运算： `+=`， `-=`， `*=`， 和 `/=` 称为复合运算符，它把数学运算符和赋值结合起来使用，如 `a += 2` 等同于 `a = a + 2`。
* 自增、自减： `++` （自增）， `--` （自减）如 `a++` 等同于 `a = a + 1`。
* 获取对象属性： `.`如 `console.log()`。

   `obj.a` 表示`obj`对象有一个属性名叫 `a`。属性也可以通过`obj["a"]`获取值，参见第二章。
   
* 相等： `==`（相等）， `===` （恒等）， `!=`（不相等） `!==` （不恒等） 如`a == b`.

   参见第二章的“值与类型”。
* 比较运算符： `<` （小于）， `>` （大于）， `<=` （小于等于）， `>=` （大于等于）如 `a <= b`.

    参见第二章的“值与类型”。
* 逻辑运算符：`&&` （且） `||` （或），如 `a || b` 表示 `a` 或 `b`.

这些运算符在表示复合运算条件的时候常用到（参见条件语句），比如判断`a` 或 `b`是否为真。

**说明：** MDN的["Expressions and Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators) 中会有更多关于运算符的详细信息，以及这里没有提到的运算符。

## 值和类型

如果你问一个手机店员一个手机多少钱，他们说99.99美金，他们会给你一个实际的含税价格表示你要买一部手机需要支付的钱。如果你想买两部，那么你马上心算出来两部手机的基本费用是199.98美金。

如果他再拿起另外一款手机告诉你这部手机“免费”，他没有给你一个确切的数字，“免费”的用另外一种表达就是$0.00。

然后你问这部手机是否包含充电器，得到的回答只能是“是”或者“否”。

类似的，在程序中要根据你的目的选择不同的方式表达值。

这些不同的值表达在编程术语中就叫“类型”。JavaScript 为这些原始值提供了内建的类型。

* 当你想做数学预算的时候你需要一个`number` 类型；
* 当你想打印值在屏幕上面，你需要一个`string`类型（一两个字母，单词，或者句子）；
* 当你想做决定的时候，你需要一个`boolean` （`true` 或 `false`）。

源代码中直接包含的内容叫“字面量”。`string` 字面量用双引号或者单引号引起来 -- 唯一的区别是格式偏好。`number`和`boolean` 字面量就表示它的真是内容。

看下面：

```js
"I am a string";
'I am also a string';

42;

true;
false;
```

除了 `string`/`number`/`boolean` 值类型，通常编程语言也提供了 *arrays*，*objects*，*functions*以及其他。本章和接下来的章节会涉及到更多的值和类型的内容。

### 类型转换

假设你有一个`number`类型的值，但是想把它打印在屏幕上，你需要把它转化成`string`，JavaScript 中的这种转换叫“强制转换”。同样，如果有人在一个电子商务网站上的表单中输入了一系列数字字符，它是y一个`string`类型，但是你想在数学运算中使用这个值，你需要把它强制转换成`number`类型。

JavaScript 提供了多种方法进行类型间的强制转换，比如：
```js
var a = "42";
var b = Number( a );

console.log( a );	// "42"
console.log( b );	// 42
```

`Number(..)`（一个内置的函数）显式地将其他类型转换成`number`类型，那样最直接。

但是在比较两个不同类型的值时，那种方式就有争议了，这个时候需要隐式转换。

字符串`"99.99"`和数值`99.99`比较，大部分人都觉得他们应该相等。但是他们并不是完全相等，对吧？这是同一个值的两种不同的表达方式，两个不同的类型。你也可以说他们相等，是吧？

为了帮你弄清楚这种类似的情况，JavaScript 有时候为了类型匹配需要隐式转换。

如果你使用`==` 对`"99.99" == 99.99`进行比较，JavaScript 会把左边的`"99.99"` 转换成数字类型，也就是`99.99`，然后就变成了`99.99 == 99.99`，结果为true。

如果你尚未花时间掌握隐式转换的操作规则，很容易困惑，大部分的JS 开发者并未掌握，因此大多数都感觉隐式转换令人困惑，会引起程序出现意想不到的bug，所以应该尽量避免。这甚至被认为是这个语言设计的一个缺陷。

然而，隐式转换机制是完全可以掌握的，希望认真学习JavaScript 开发的人甚至应该去掌握。一旦你掌握了规则，你不仅不会困惑，而且会写出更好的程序。努力是值得的。

**说明：** 强制转换的话题，会在第二章及第四章中的“类型和语法”中有更多的讨论。 

## 代码注释

The phone store employee might jot down some notes on the features of a newly released phone or on the new plans her company offers. These notes are only for the employee -- they're not for customers to read. Nevertheless, these notes help the employee do her job better by documenting the hows and whys of what she should tell customers.

One of the most important lessons you can learn about writing code is that it's not just for the computer. Code is every bit as much, if not more, for the developer as it is for the compiler.

Your computer only cares about machine code, a series of binary 0s and 1s, that comes from *compilation*. There's a nearly infinite number of programs you could write that yield the same series of 0s and 1s. The choices you make about how to write your program matter -- not only to you, but to your other team members and even to your future self.

You should strive not just to write programs that work correctly, but programs that make sense when examined. You can go a long way in that effort by choosing good names for your variables (see "Variables") and functions (see "Functions").

But another important part is code comments. These are bits of text in your program that are inserted purely to explain things to a human. The interpreter/compiler will always ignore these comments.

There are lots of opinions on what makes well-commented code; we can't really define absolute universal rules. But some observations and guidelines are quite useful:

* Code without comments is suboptimal.
* Too many comments (one per line, for example) is probably a sign of poorly written code.
* Comments should explain *why*, not *what*. They can optionally explain *how* if that's particularly confusing.

In JavaScript, there are two types of comments possible: a single-line comment and a multiline comment.

Consider:

```js
// This is a single-line comment

/* But this is
       a multiline
             comment.
                      */
```

The `//` single-line comment is appropriate if you're going to put a comment right above a single statement, or even at the end of a line. Everything on the line after the `//` is treated as the comment (and thus ignored by the compiler), all the way to the end of the line. There's no restriction to what can appear inside a single-line comment.

Consider:

```js
var a = 42;		// 42 is the meaning of life
```

The `/* .. */` multiline comment is appropriate if you have several lines worth of explanation to make in your comment.

Here's a common usage of multiline comments:

```js
/* The following value is used because
   it has been shown that it answers
   every question in the universe. */
var a = 42;
```

It can also appear anywhere on a line, even in the middle of a line, because the `*/` ends it. For example:

```js
var a = /* arbitrary value */ 42;

console.log( a );	// 42
```

The only thing that cannot appear inside a multiline comment is a `*/`, because that would be interpreted to end the comment.

You will definitely want to begin your learning of programming by starting off with the habit of commenting code. Throughout the rest of this chapter, you'll see I use comments to explain things, so do the same in your own practice. Trust me, everyone who reads your code will thank you!

## 变量

Most useful programs need to track a value as it changes over the course of the program, undergoing different operations as called for by your program's intended tasks.

The easiest way to go about that in your program is to assign a value to a symbolic container, called a *variable* -- so called because the value in this container can *vary* over time as needed.

In some programming languages, you declare a variable (container) to hold a specific type of value, such as `number` or `string`. *Static typing*, otherwise known as *type enforcement*, is typically cited as a benefit for program correctness by preventing unintended value conversions.

Other languages emphasize types for values instead of variables. *Weak typing*, otherwise known as *dynamic typing*, allows a variable to hold any type of value at any time. It's typically cited as a benefit for program flexibility by allowing a single variable to represent a value no matter what type form that value may take at any given moment in the program's logic flow.

JavaScript uses the latter approach, *dynamic typing*, meaning variables can hold values of any *type* without any *type* enforcement.

As mentioned earlier, we declare a variable using the `var` statement -- notice there's no other *type* information in the declaration. Consider this simple program:

```js
var amount = 99.99;

amount = amount * 2;

console.log( amount );		// 199.98

// convert `amount` to a string, and
// add "$" on the beginning
amount = "$" + String( amount );

console.log( amount );		// "$199.98"
```

The `amount` variable starts out holding the number `99.99`, and then holds the `number` result of `amount * 2`, which is `199.98`.

The first `console.log(..)` command has to *implicitly* coerce that `number` value to a `string` to print it out.

Then the statement `amount = "$" + String(amount)` *explicitly* coerces the `199.98` value to a `string` and adds a `"$"` character to the beginning. At this point, `amount` now holds the `string` value `"$199.98"`, so the second `console.log(..)` statement doesn't need to do any coercion to print it out.

JavaScript developers will note the flexibility of using the `amount` variable for each of the `99.99`, `199.98`, and the `"$199.98"` values. Static-typing enthusiasts would prefer a separate variable like `amountStr` to hold the final `"$199.98"` representation of the value, because it's a different type.

Either way, you'll note that `amount` holds a running value that changes over the course of the program, illustrating the primary purpose of variables: managing program *state*.

In other words, *state* is tracking the changes to values as your program runs.

Another common usage of variables is for centralizing value setting. This is more typically called *constants*, when you declare a variable with a value and intend for that value to *not change* throughout the program.

You declare these *constants*, often at the top of a program, so that it's convenient for you to have one place to go to alter a value if you need to. By convention, JavaScript variables as constants are usually capitalized, with underscores `_` between multiple words.

Here's a silly example:

```js
var TAX_RATE = 0.08;	// 8% sales tax

var amount = 99.99;

amount = amount * 2;

amount = amount + (amount * TAX_RATE);

console.log( amount );				// 215.9784
console.log( amount.toFixed( 2 ) );	// "215.98"
```

**Note:** Similar to how `console.log(..)` is a function `log(..)` accessed as an object property on the `console` value, `toFixed(..)` here is a function that can be accessed on `number` values. JavaScript `number`s aren't automatically formatted for dollars -- the engine doesn't know what your intent is and there's no type for currency. `toFixed(..)` lets us specify how many decimal places we'd like the `number` rounded to, and it produces the `string` as necessary.

The `TAX_RATE` variable is only *constant* by convention -- there's nothing special in this program that prevents it from being changed. But if the city raises the sales tax rate to 9%, we can still easily update our program by setting the `TAX_RATE` assigned value to `0.09` in one place, instead of finding many occurrences of the value `0.08` strewn throughout the program and updating all of them.

The newest version of JavaScript at the time of this writing (commonly called "ES6") includes a new way to declare *constants*, by using `const` instead of `var`:

```js
// as of ES6:
const TAX_RATE = 0.08;

var amount = 99.99;

// ..
```

Constants are useful just like variables with unchanged values, except that constants also prevent accidentally changing value somewhere else after the initial setting. If you tried to assign any different value to `TAX_RATE` after that first declaration, your program would reject the change (and in strict mode, fail with an error -- see "Strict Mode" in Chapter 2).

By the way, that kind of "protection" against mistakes is similar to the static-typing type enforcement, so you can see why static types in other languages can be attractive!

**Note:** For more information about how different values in variables can be used in your programs, see the *Types & Grammar* title of this series.

## Blocks

The phone store employee must go through a series of steps to complete the checkout as you buy your new phone.

Similarly, in code we often need to group a series of statements together, which we often call a *block*. In JavaScript, a block is defined by wrapping one or more statements inside a curly-brace pair `{ .. }`. Consider:

```js
var amount = 99.99;

// a general block
{
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

This kind of standalone `{ .. }` general block is valid, but isn't as commonly seen in JS programs. Typically, blocks are attached to some other control statement, such as an `if` statement (see "Conditionals") or a loop (see "Loops"). For example:

```js
var amount = 99.99;

// is amount big enough?
if (amount > 10) {			// <-- block attached to `if`
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

We'll explain `if` statements in the next section, but as you can see, the `{ .. }` block with its two statements is attached to `if (amount > 10)`; the statements inside the block will only be processed if the conditional passes.

**Note:** Unlike most other statements like `console.log(amount);`, a block statement does not need a semicolon (`;`) to conclude it.

## Conditionals

"Do you want to add on the extra screen protectors to your purchase, for $9.99?" The helpful phone store employee has asked you to make a decision. And you may need to first consult the current *state* of your wallet or bank account to answer that question. But obviously, this is just a simple "yes or no" question.

There are quite a few ways we can express *conditionals* (aka decisions) in our programs.

The most common one is the `if` statement. Essentially, you're saying, "*If* this condition is true, do the following...". For example:

```js
var bank_balance = 302.13;
var amount = 99.99;

if (amount < bank_balance) {
	console.log( "I want to buy this phone!" );
}
```

The `if` statement requires an expression in between the parentheses `( )` that can be treated as either `true` or `false`. In this program, we provided the expression `amount < bank_balance`, which indeed will either evaluate to `true` or `false` depending on the amount in the `bank_balance` variable.

You can even provide an alternative if the condition isn't true, called an `else` clause. Consider:

```js
const ACCESSORY_PRICE = 9.99;

var bank_balance = 302.13;
var amount = 99.99;

amount = amount * 2;

// can we afford the extra purchase?
if ( amount < bank_balance ) {
	console.log( "I'll take the accessory!" );
	amount = amount + ACCESSORY_PRICE;
}
// otherwise:
else {
	console.log( "No, thanks." );
}
```

Here, if `amount < bank_balance` is `true`, we'll print out `"I'll take the accessory!"` and add the `9.99` to our `amount` variable. Otherwise, the `else` clause says we'll just politely respond with `"No, thanks."` and leave `amount` unchanged.

As we discussed in "Values & Types" earlier, values that aren't already of an expected type are often coerced to that type. The `if` statement expects a `boolean`, but if you pass it something that's not already `boolean`, coercion will occur.

JavaScript defines a list of specific values that are considered "falsy" because when coerced to a `boolean`, they become `false` -- these include values like `0` and `""`. Any other value not on the "falsy" list is automatically "truthy" -- when coerced to a `boolean` they become `true`. Truthy values include things like `99.99` and `"free"`. See "Truthy & Falsy" in Chapter 2 for more information.

*Conditionals* exist in other forms besides the `if`. For example, the `switch` statement can be used as a shorthand for a series of `if..else` statements (see Chapter 2). Loops (see "Loops") use a *conditional* to determine if the loop should keep going or stop.

**Note:** For deeper information about the coercions that can occur implicitly in the test expressions of *conditionals*, see Chapter 4 of the *Types & Grammar* title of this series.

## Loops

During busy times, there's a waiting list for customers who need to speak to the phone store employee. While there's still people on that list, she just needs to keep serving the next customer.

Repeating a set of actions until a certain condition fails -- in other words, repeating only while the condition holds -- is the job of programming loops; loops can take different forms, but they all satisfy this basic behavior.

A loop includes the test condition as well as a block (typically as `{ .. }`). Each time the loop block executes, that's called an *iteration*.

For example, the `while` loop and the `do..while` loop forms illustrate the concept of repeating a block of statements until a condition no longer evaluates to `true`:

```js
while (numOfCustomers > 0) {
	console.log( "How may I help you?" );

	// help the customer...

	numOfCustomers = numOfCustomers - 1;
}

// versus:

do {
	console.log( "How may I help you?" );

	// help the customer...

	numOfCustomers = numOfCustomers - 1;
} while (numOfCustomers > 0);
```

The only practical difference between these loops is whether the conditional is tested before the first iteration (`while`) or after the first iteration (`do..while`).

In either form, if the conditional tests as `false`, the next iteration will not run. That means if the condition is initially `false`, a `while` loop will never run, but a `do..while` loop will run just the first time.

Sometimes you are looping for the intended purpose of counting a certain set of numbers, like from `0` to `9` (ten numbers). You can do that by setting a loop iteration variable like `i` at value `0` and incrementing it by `1` each iteration.

**Warning:** For a variety of historical reasons, programming languages almost always count things in a zero-based fashion, meaning starting with `0` instead of `1`. If you're not familiar with that mode of thinking, it can be quite confusing at first. Take some time to practice counting starting with `0` to become more comfortable with it!

The conditional is tested on each iteration, much as if there is an implied `if` statement inside the loop.

We can use JavaScript's `break` statement to stop a loop. Also, we can observe that it's awfully easy to create a loop that would otherwise run forever without a `break`ing mechanism.

Let's illustrate:

```js
var i = 0;

// a `while..true` loop would run forever, right?
while (true) {
	// stop the loop?
	if ((i <= 9) === false) {
		break;
	}

	console.log( i );
	i = i + 1;
}
// 0 1 2 3 4 5 6 7 8 9
```

**Warning:** This is not necessarily a practical form you'd want to use for your loops. It's presented here for illustration purposes only.

While a `while` (or `do..while`) can accomplish the task manually, there's another syntactic form called a `for` loop for just that purpose:

```js
for (var i = 0; i <= 9; i = i + 1) {
	console.log( i );
}
// 0 1 2 3 4 5 6 7 8 9
```

As you can see, in both cases the conditional `i <= 9` is `true` for the first 10 iterations (`i` of values `0` through `9`) of either loop form, but becomes `false` once `i` is value `10`.

The `for` loop has three clauses: the initialization clause (`var i=0`), the conditional test clause (`i <= 9`), and the update clause (`i = i + 1`). So if you're going to do counting with your loop iterations, `for` is a more compact and often easier form to understand and write.

There are other specialized loop forms that are intended to iterate over specific values, such as the properties of an object (see Chapter 2) where the implied conditional test is just whether all the properties have been processed. The "loop until a condition fails" concept holds no matter what the form of the loop.

## Functions

The phone store employee probably doesn't carry around a calculator to figure out the taxes and final purchase amount. That's a task she needs to define once and reuse over and over again. Odds are, the company has a checkout register (computer, tablet, etc.) with those "functions" built in.

Similarly, your program will almost certainly want to break up the code's tasks into reusable pieces, instead of repeatedly repeating yourself repetitiously (pun intended!). The way to do this is to define a `function`.

A function is generally a named section of code that can be "called" by name, and the code inside it will be run each time. Consider:

```js
function printAmount() {
	console.log( amount.toFixed( 2 ) );
}

var amount = 99.99;

printAmount(); // "99.99"

amount = amount * 2;

printAmount(); // "199.98"
```

Functions can optionally take arguments (aka parameters) -- values you pass in. And they can also optionally return a value back.

```js
function printAmount(amt) {
	console.log( amt.toFixed( 2 ) );
}

function formatAmount() {
	return "$" + amount.toFixed( 2 );
}

var amount = 99.99;

printAmount( amount * 2 );		// "199.98"

amount = formatAmount();
console.log( amount );			// "$99.99"
```

The function `printAmount(..)` takes a parameter that we call `amt`. The function `formatAmount()` returns a value. Of course, you can also combine those two techniques in the same function.

Functions are often used for code that you plan to call multiple times, but they can also be useful just to organize related bits of code into named collections, even if you only plan to call them once.

Consider:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
	amt = amt + (amt * TAX_RATE);

	// return the new amount
	return amt;
}

var amount = 99.99;

amount = calculateFinalPurchaseAmount( amount );

console.log( amount.toFixed( 2 ) );		// "107.99"
```

Although `calculateFinalPurchaseAmount(..)` is only called once, organizing its behavior into a separate named function makes the code that uses its logic (the `amount = calculateFinal...` statement) cleaner. If the function had more statements in it, the benefits would be even more pronounced.

### Scope

If you ask the phone store employee for a phone model that her store doesn't carry, she will not be able to sell you the phone you want. She only has access to the phones in her store's inventory. You'll have to try another store to see if you can find the phone you're looking for.

Programming has a term for this concept: *scope* (technically called *lexical scope*). In JavaScript, each function gets its own scope. Scope is basically a collection of variables as well as the rules for how those variables are accessed by name. Only code inside that function can access that function's *scoped* variables.

A variable name has to be unique within the same scope -- there can't be two different `a` variables sitting right next to each other. But the same variable name `a` could appear in different scopes.

```js
function one() {
	// this `a` only belongs to the `one()` function
	var a = 1;
	console.log( a );
}

function two() {
	// this `a` only belongs to the `two()` function
	var a = 2;
	console.log( a );
}

one();		// 1
two();		// 2
```

Also, a scope can be nested inside another scope, just like if a clown at a birthday party blows up one balloon inside another balloon. If one scope is nested inside another, code inside the innermost scope can access variables from either scope.

Consider:

```js
function outer() {
	var a = 1;

	function inner() {
		var b = 2;

		// we can access both `a` and `b` here
		console.log( a + b );	// 3
	}

	inner();

	// we can only access `a` here
	console.log( a );			// 1
}

outer();
```

Lexical scope rules say that code in one scope can access variables of either that scope or any scope outside of it.

So, code inside the `inner()` function has access to both variables `a` and `b`, but code in `outer()` has access only to `a` -- it cannot access `b` because that variable is only inside `inner()`.

Recall this code snippet from earlier:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
	amt = amt + (amt * TAX_RATE);

	// return the new amount
	return amt;
}
```

The `TAX_RATE` constant (variable) is accessible from inside the `calculateFinalPurchaseAmount(..)` function, even though we didn't pass it in, because of lexical scope.

**Note:** For more information about lexical scope, see the first three chapters of the *Scope & Closures* title of this series.

## Practice

There is absolutely no substitute for practice in learning programming. No amount of articulate writing on my part is alone going to make you a programmer.

With that in mind, let's try practicing some of the concepts we learned here in this chapter. I'll give the "requirements," and you try it first. Then consult the code listing below to see how I approached it.

* Write a program to calculate the total price of your phone purchase. You will keep purchasing phones (hint: loop!) until you run out of money in your bank account. You'll also buy accessories for each phone as long as your purchase amount is below your mental spending threshold.
* After you've calculated your purchase amount, add in the tax, then print out the calculated purchase amount, properly formatted.
* Finally, check the amount against your bank account balance to see if you can afford it or not.
* You should set up some constants for the "tax rate," "phone price," "accessory price," and "spending threshold," as well as a variable for your "bank account balance.""
* You should define functions for calculating the tax and for formatting the price with a "$" and rounding to two decimal places.
* **Bonus Challenge:** Try to incorporate input into this program, perhaps with the `prompt(..)` covered in "Input" earlier. You may prompt the user for their bank account balance, for example. Have fun and be creative!

OK, go ahead. Try it. Don't peek at my code listing until you've given it a shot yourself!

**Note:** Because this is a JavaScript book, I'm obviously going to solve the practice exercise in JavaScript. But you can do it in another language for now if you feel more comfortable.

Here's my JavaScript solution for this exercise:

```js
const SPENDING_THRESHOLD = 200;
const TAX_RATE = 0.08;
const PHONE_PRICE = 99.99;
const ACCESSORY_PRICE = 9.99;

var bank_balance = 303.91;
var amount = 0;

function calculateTax(amount) {
	return amount * TAX_RATE;
}

function formatAmount(amount) {
	return "$" + amount.toFixed( 2 );
}

// keep buying phones while you still have money
while (amount < bank_balance) {
	// buy a new phone!
	amount = amount + PHONE_PRICE;

	// can we afford the accessory?
	if (amount < SPENDING_THRESHOLD) {
		amount = amount + ACCESSORY_PRICE;
	}
}

// don't forget to pay the government, too
amount = amount + calculateTax( amount );

console.log(
	"Your purchase: " + formatAmount( amount )
);
// Your purchase: $334.76

// can you actually afford this purchase?
if (amount > bank_balance) {
	console.log(
		"You can't afford this purchase. :("
	);
}
// You can't afford this purchase. :(
```

**Note:** The simplest way to run this JavaScript program is to type it into the developer console of your nearest browser.

How did you do? It wouldn't hurt to try it again now that you've seen my code. And play around with changing some of the constants to see how the program runs with different values.

## Review

Learning programming doesn't have to be a complex and overwhelming process. There are just a few basic concepts you need to wrap your head around.

These act like building blocks. To build a tall tower, you start first by putting block on top of block on top of block. The same goes with programming. Here are some of the essential programming building blocks:

* You need *operators* to perform actions on values.
* You need values and *types* to perform different kinds of actions like math on `number`s or output with `string`s.
* You need *variables* to store data (aka *state*) during your program's execution.
* You need *conditionals* like `if` statements to make decisions.
* You need *loops* to repeat tasks until a condition stops being true.
* You need *functions* to organize your code into logical and reusable chunks.

Code comments are one effective way to write more readable code, which makes your program easier to understand, maintain, and fix later if there are problems.

Finally, don't neglect the power of practice. The best way to learn how to write code is to write code.

I'm excited you're well on your way to learning how to code, now! Keep it up. Don't forget to check out other beginner programming resources (books, blogs, online training, etc.). This chapter and this book are a great start, but they're just a brief introduction.

The next chapter will review many of the concepts from this chapter, but from a more JavaScript-specific perspective, which will highlight most of the major topics that are addressed in deeper detail throughout the rest of the series.

