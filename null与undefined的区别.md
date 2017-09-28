## null与undefined的区别
* 在阅读了阮老师的博客后，对null以及undefined有了一个新的认识。
``` javascript
var a = undefined;
var a = null;
undefined == null
// true
```
别的语言只会存在一个null,但是为什么在Javascript中，我们会遇到两个代表“空”的东西呢！<br/>
* JavaScript的<b>最初版本</b>是这样区分的：<b>null是一个表示"无"的对象，转为数值时为0；undefined是一个表示"无"的原始值，转为数值时为NaN。</b>
``` javascript
Number(undefined)
// NaN

5 + undefined
// NaN
```
* 目前的用法。
<b>null表示"没有对象"，即该处不应该有值。</b>典型用法是
``` javascript
（1） 作为函数的参数，表示该函数的参数不是对象。
（2） 作为对象原型链的终点。

Object.getPrototypeOf(Object.prototype)
// null
```
<b>undefined表示"缺少值"，就是此处应该有一个值，但是还没有定义。</b>典型用法是:
``` javascript
（1）变量被声明了，但没有赋值时，就等于undefined。
（2) 调用函数时，应该提供的参数没有提供，该参数等于undefined。
（3）对象没有赋值的属性，该属性的值为undefined。
（4）函数没有返回值时，默认返回undefined。

var i;
i // undefined

function f(x){console.log(x)}
f() // undefined

var  o = new Object();
o.p // undefined

var x = f();
x // undefined
```
