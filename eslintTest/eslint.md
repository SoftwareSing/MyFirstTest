# 規則說明



## brace-style
[大括号风格要求](http://eslint.cn/docs/rules/brace-style)
```js
// "1tbs"
if (foo) {
  bar();
} else {
  baz();
}
```

```js
// "stroustrup"
if (foo) {
  bar();
}
else {
  baz();
}
```

```js
// "allman"
if (foo)
{
  bar();
}
else
{
  baz();
}
```



## indent
[强制使用一致的缩进](http://eslint.cn/docs/rules/indent)
* 两个空格，不要 tab： Google、npm、Node.js、Idiomatic、Felix
* tab：jQuery
* 四个空格：Crockford



## no-var
[要求使用 let 或 const 而不是 var](http://eslint.cn/docs/rules/no-var)

`var` 是一個很危險的東西，請不要在es6使用他
```js
var test = "A";
if (true) {
  var test = "B";
  var t2 = "C";
  console.log(test);  // B
  console.log(t2);  // C
}
console.log(test);  // B
console.log(t2);    // C
```
```js
const test = "A";
if (true) {
  const test = "B";
  const t2 = "C";
  console.log(test);  // B
  console.log(t2);  // C
}
console.log(test);  // A
console.log(t2);  // undefind
```



## prefer-const
[建议使用const](http://eslint.cn/docs/rules/prefer-const)

如果你不打算變更你的值，就不要使用 `let`
```js
let a = 1;
a += 1; // 改變了值, 用 let 是ok的

const b = [];
b.push(a) // b 一直都是 list，並未改變他的物件，應用 const
// 物件內部不在 const 的限制範圍內
```



## quotes
[强制使用一致的反勾号、双引号或单引号](http://eslint.cn/docs/rules/quotes)

預設 `"double"`

符號  `  在es中含特殊用法，已開啟允許使用
```js
var double = "double";
var single = 'single';
var backtick = `backtick`;

var a = "xyz";
var b = `a is ${a}`;
console.log(b);
//輸出: a is xyz
```



## max-params
[限制函数定义中最大参数个数](http://eslint.cn/docs/rules/max-params)

限制輸入值最多個數 (預設3)
```javascript
function foo(bar, baz, qux, qxx) { // four parameters
    doSomething();
}
```



## semi
[要求或禁止使用分号代替 ASI](http://eslint.cn/docs/rules/semi)

強制 加分號 或 不加分號
```js
var name = "ESLint"
var name = "ESLint";
```



## arrow-body-style
[要求箭头函数体使用大括号](http://eslint.cn/docs/rules/arrow-body-style)
是否強制要求 lambda 使用 `{}`
```js
(a, b) => a - b;
```
```js
(a, b) => {
  return a - b;
}
```



## arrow-parens
[要求箭头函数的参数使用圆括号](http://eslint.cn/docs/rules/arrow-parens)
是否強制要求 lambda的輸入值 使用 `()`
```js
a => {
  console.log(a);
}
```
```js
(a) => {
  console.log(a);
}
```



## operator-linebreak
[强制操作符使用一致的换行符风格](http://eslint.cn/docs/rules/operator-linebreak)

`+` 或其他符號在 before 或 after

預設 after
```js
var fullHeight = borderTop +
                 innerHeight +
                 borderBottom;
```
```js
var fullHeight = borderTop
               + innerHeight
               + borderBottom;
```



## one-var
[强制函数中的变量在一起声明或分开声明](http://eslint.cn/docs/rules/one-var)

```js
// one variable declaration per function
function foo() {
    var bar, baz;
}
```
```js
// multiple variable declarations per function
function foo() {
    var bar;
    var baz;
}
```



## no-plusplus
[禁止使用一元操作符 ++ 和 --](http://eslint.cn/docs/rules/no-plusplus)
```js
j ++;   // error
j += 1; // ok
```

用 `+= 1` 比 `++` 好多了



## no-multiple-empty-lines
[不允许多个空行](http://eslint.cn/docs/rules/no-multiple-empty-lines)

預設最多2空行
```js
var foo = 5;


var bar = 3;
```



## newline-per-chained-call
[要求方法链中每个调用都有一个换行符](http://eslint.cn/docs/rules/newline-per-chained-call)
```js
d3.select("body").selectAll("p").data([4, 8, 15, 16, 23, 42 ]).enter().append("p").text(function(d) { return "I'm number " + d + "!"; });
```
```js
d3
  .select("body")
  .selectAll("p")
  .data([
    4,
    8,
    15,
    16,
    23,
    42
  ])
  .enter()
  .append("p")
  .text(function (d) {
    return "I'm number " + d + "!";
  });
```



## newline-before-return
[要求 return 语句之前有一空行](http://eslint.cn/docs/rules/newline-before-return)
```js
if (a) {
  console.log("test");

  return;
}
else {
  return;
}
```
```js
if (a) {
  console.log("test");
  return;
}
else {
  return;
}
```


## key-spacing
[强制在对象字面量的键和值之间使用一致的空格](http://eslint.cn/docs/rules/key-spacing)



## comma-style
[逗号风格](http://eslint.cn/docs/rules/comma-style)

```js
var foo = ["apples",
           "oranges"];
```
```js
var foo = ["apples"
          ,"oranges"];
```



## comma-spacing
[强制在逗号周围使用空格](http://eslint.cn/docs/rules/comma-spacing)
```js
var foo = 1, bar = 2;
var foo = 1 ,bar = 2;
var foo = 1 , bar = 2;
```



## block-spacing
[禁止或强制在代码块中开括号前和闭括号后有空格](http://eslint.cn/docs/rules/block-spacing)
```js
function foo() {return true;}
function foo() { return true; }
```



## array-bracket-spacing
[禁止或强制在括号内使用空格](http://eslint.cn/docs/rules/array-bracket-spacing)
```js
var arr = [ 'foo', 'bar' ];
var [ x, y ] = z;
```
```js
var arr = ['foo', 'bar'];
var [x,y] = z;
```





## dot-location
[强制在点号之前或之后换行](http://eslint.cn/docs/rules/dot-location)

* 如果它的值是 "object"，表达式中的点号操作符应该和对象部分在同一行。默认是 "object"。
* 如果它的值是 "property"，表达式中的点号操作符应该和属性在同一行。

```js
const a = universe.
          galaxy;
// object
```
```js
const b = universe
          .galaxy;
// property
```



## camelcase
[要求使用骆驼拼写法](http://eslint.cn/docs/rules/camelcase)

```js
const variableName = 1;  // OK
const _variableName = 1; // OK
const variable_name = 1; // error 
```



## curly
[要求遵循大括号约定 (curly)](http://eslint.cn/docs/rules/curly)

就是一定要寫 {} 不能省略



## import/prefer-default-export
[強制用 default export](https://kyriejoshua.github.io/jo.github.io/2016/08/08/eslint-about-import-prefer-default-export/)

建議 off



## no-unused-expressions
[禁止未使用过的表达式](http://eslint.cn/docs/rules/no-unused-expressions)

禁止寫沒有用到的垃圾 如:
```javascript
n + 1;
```
n + 1; 然後呢? 沒有意義的一句，這就是垃圾



## no-unused-vars
[禁止未使用过的变量](http://eslint.cn/docs/rules/no-unused-vars)

定義了變數就要用他，不然你定義他幹嘛
```javascript
function test() {
  const a = 1;  // 定義這個 a 完全沒用到，是沒有意義的變數
  console.log("test");
}
```


## no-console
[禁用 console](http://eslint.cn/docs/rules/no-console)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。

目前改設為 off



## no-debugger
[禁用 debugger](http://eslint.cn/docs/rules/no-debugger)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。



## no-unsafe-negation
[禁止对关系运算符的左操作数使用否定操作符](http://eslint.cn/docs/rules/no-unsafe-negation)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。

开发人员可能会把 `-(a + b)` 写错成 `-a + b` 来表示一个负数，也可能会把 `!(key in object)` 错写成 `!key in object` 来测试一个键是否在对象中。类似的情况也有 `!obj instanceof Ctor`。



## valid-jsdoc
[强制使用有效的 JSDoc 注释](http://eslint.cn/docs/rules/valid-jsdoc)

如果要寫 JSDoc ，要寫完整，不能缺項
```javascript
/**
 * Add two numbers.
 * @param {number} num1 The first number.
 * @param {number} num2 The second number.
 * @returns {number} The sum of the two numbers.
 */
function add(num1, num2) {
    return num1 + num2;
}
```



## accessor-pairs
[强制getter/setter成对出现在对象中](http://eslint.cn/docs/rules/accessor-pairs)

如果只定义 `setter` 而没有定义 `getter` ，该规则会发出警告
(在沒有額外設定的情況下，只有 `getter` 不會發出警告)
```javascript
const object1 = {
    set a(value) {
        this.val = value;
    }
};
// 由於沒有 getter , object1.a 會是 undefind
// 只能直接拿 object1.val
```



## array-callback-return
[强制数组方法的回调函数中有 return 语句](http://eslint.cn/docs/rules/array-callback-return)



## complexity
[限制圈复杂度](http://eslint.cn/docs/rules/complexity)
```javascript
/*eslint complexity: ["error", 2]*/
function a(x) {
    if (true) {
        return x;
    } else if (false) {
        return x+1;
    } else {
        return 4; // 3rd path
    }
}
// 由於限制為 2 ，因此此段噴錯
```
目前設為 off



## eqeqeq
[要求使用 === 和 !==](http://eslint.cn/docs/rules/eqeqeq)

**寫js用 `==` 跟 `!=` 是自殺行為**

請使用 `===` 跟 `!==`



## no-caller
[禁用 caller 或 callee](http://eslint.cn/docs/rules/no-caller)

在 JavaScript 的新版本中它们已被弃用，同时在 ECMAScript 5 的严格模式下，它们也是被禁用的。



## no-div-regex
[禁止使用看起来像除法的正则表达式](http://eslint.cn/docs/rules/no-div-regex)

```js
function bar() { return /=foo/; } // error
function bar() { return /\=foo/; } // ok
```



## no-empty-function
[禁止出现空函数](http://eslint.cn/docs/rules/no-empty-function)

你的function裡沒有code，連註解都沒有，那到底在幹嘛?
```js
function errorFunction() {
    
}
```
```js
function goodFunction() {
    // do nothing.
}
```
起碼在裡面寫個註解吧



## no-eval
[禁用 eval()](http://eslint.cn/docs/rules/no-eval)

如果你要用 `eval()` ，最好有個好理由



## no-extra-bind
[禁止不必要的函数绑定](http://eslint.cn/docs/rules/no-extra-bind)



## no-extra-label
[禁用不必要的标签](http://eslint.cn/docs/rules/no-extra-label)



## no-floating-decimal
[禁止浮点小数](http://eslint.cn/docs/rules/no-floating-decimal)



## no-global-assign
[禁止对原生对象或只读的全局对象进行赋值](http://eslint.cn/docs/rules/no-global-assign)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。



## no-implied-eval
[禁用隐式的eval()](http://eslint.cn/docs/rules/no-implied-eval)



## no-invalid-this
[禁止 this 关键字在类或类对象之外出现](http://eslint.cn/docs/rules/no-invalid-this)



## no-iterator
[禁用迭代器](http://eslint.cn/docs/rules/no-iterator)

這裡說的是 `__iterator__` 屬性，不是pattern



## no-lone-blocks
[禁用不必要的嵌套块](http://eslint.cn/docs/rules/no-lone-blocks)



## no-loop-func
[禁止循环中存在函数](http://eslint.cn/docs/rules/no-loop-func)

如果你要定義一個 function ，應該在 `for` 或其他迴圈的外面定義他



## no-multi-spaces
[禁止出现多个空格](http://eslint.cn/docs/rules/no-multi-spaces)
```js
a === b;
a  ===  b;
// 這2個是一樣的，你不需要這麼多空格
```



## no-multi-str
[禁止多行字符串](http://eslint.cn/docs/rules/no-multi-str)



## no-new-func
[禁用Function构造函数](http://eslint.cn/docs/rules/no-new-func)



## no-new-wrappers
[禁止原始包装实例](http://eslint.cn/docs/rules/no-new-wrappers)



## no-new
[禁止使用 new 以避免产生副作用](http://eslint.cn/docs/rules/no-new)

應該要有人去接住那個 `new` ，而不是讓他憑空出現在那
```js
const person = new Person();  // ok
new Person(); // error
```



## no-octal-escape
[禁止在字符串字面量中使用八进制转义序列](http://eslint.cn/docs/rules/no-octal-escape)



## no-proto
[禁用__proto__](http://eslint.cn/docs/rules/no-proto)

`__proto__` 属性在 ECMAScript 3.1 中已经被弃用，并且不应该在代码中使用。使用 `getPrototypeOf` 方法替代 `__proto__` 



## no-return-assign
[禁止在返回语句中赋值](http://eslint.cn/docs/rules/no-return-assign)



## no-script-url
[禁用 Script URL](http://eslint.cn/docs/rules/no-script-url)



## no-self-compare
[禁止自身比较](http://eslint.cn/docs/rules/no-self-compare)



## no-sequences
[不允许使用逗号操作符](http://eslint.cn/docs/rules/no-sequences)



## no-unmodified-loop-condition
[禁用一成不变的循环条件](http://eslint.cn/docs/rules/no-unmodified-loop-condition)

```js
const a = true;
while (a) {
  console.log(a);
}
```
你從來沒有改變 a ，那不就是無窮迴圈嗎



## no-useless-call
[禁用不必要的 .call() 和 .apply()](http://eslint.cn/docs/rules/no-useless-call)



## no-useless-concat
[禁止没有必要的字符拼接](http://eslint.cn/docs/rules/no-useless-concat)



## no-useless-escape
[禁用不必要的转义](http://eslint.cn/docs/rules/no-useless-escape)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。



## no-void
[禁止使用void操作符](http://eslint.cn/docs/rules/no-void)



## no-with
[禁用 with 语句](http://eslint.cn/docs/rules/no-with)



## radix
[要求必须有基数](http://eslint.cn/docs/rules/radix)



## no-catch-shadow
[不允许在 catch 语句中遮盖变量](http://eslint.cn/docs/rules/no-catch-shadow)



## no-delete-var
[禁止删除变量](http://eslint.cn/docs/rules/no-delete-var)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。



## no-label-var
[禁用与变量同名的标签](http://eslint.cn/docs/rules/no-label-var)



## no-shadow-restricted-names
[关键字不能被遮蔽](http://eslint.cn/docs/rules/no-shadow-restricted-names)

```js
var undefined = "foo";
```
如果你嘗試這麼做，應該去買個主機板來跪



## comma-dangle
[要求或禁止使用拖尾逗号](http://eslint.cn/docs/rules/comma-dangle)



## eol-last
[要求或禁止文件末尾保留一行空行](http://eslint.cn/docs/rules/eol-last)



## func-call-spacing
[要求或禁止在函数标识符和其调用之间有空格](http://eslint.cn/docs/rules/func-call-spacing)



## keyword-spacing
[强制关键字周围空格的一致性](http://eslint.cn/docs/rules/keyword-spacing)

```js
if (foo) {
    // ...
} else {
    // ...
}
```
```js
if (foo) {
    // ...
}else{
    // ...
}
```



## max-depth
[强制块语句的最大可嵌套深度](http://eslint.cn/docs/rules/max-depth)
```js
function foo() {
    for (;;) { // Nested 1 deep
        let val = () => (param) => { // Nested 2 deep
            if (true) { // Nested 3 deep
                if (true) { // Nested 4 deep
                    if (true) { // Nested 5 deep
                    }
                }
            }
        };
    }
}
```



## max-len
[强制行的最大长度](http://eslint.cn/docs/rules/max-len)

限制一行幾個字



## max-nested-callbacks
[强制回调函数最大嵌套深度](http://eslint.cn/docs/rules/max-nested-callbacks)
```js
foo(function () {
    bar(function () {
        baz(function() {
            qux(function () {

            });
        });
    });
});
```
預設10層



## max-statements-per-line
[强制每一行中所允许的最大语句数量](http://eslint.cn/docs/rules/max-statements-per-line)
```js
function () { var bar; if (condition) { bar = 1; } else { bar = 2; } return true; }
```
預設 max: 1



## new-cap
[要求构造函数首字母大写](http://eslint.cn/docs/rules/new-cap)
```js
var friend = new Person();
```



## new-parens
[要求调用无参构造函数时带括号](http://eslint.cn/docs/rules/new-parens)



## no-array-constructor
[禁止使用 Array 构造函数](http://eslint.cn/docs/rules/no-array-constructor)



## no-bitwise
[禁止使用按位操作符](http://eslint.cn/docs/rules/no-bitwise)



## no-lonely-if
[禁止 if 语句作为唯一语句出现在 else 语句块中](http://eslint.cn/docs/rules/no-lonely-if)
```js
if (foo) {
    // ...
} else {
    if (bar) {
        // ...
    }
}
```
```js
if (foo) {
    // ...
} else if (bar) {
    // ...
}
```



## no-mixed-operators
[禁止混合使用不同的操作符](http://eslint.cn/docs/rules/no-mixed-operators)
```js
var foo = a && b || c || d;    /*BAD: Unexpected mix of '&&' and '||'.*/
var foo = (a && b) || c || d;  /*GOOD*/
```



## no-new-object
[禁止使用 Object 构造函数](http://eslint.cn/docs/rules/no-new-object)
```js
var myObject = new Object();  //error
var myObject = {};  //ok
```



## no-tabs
[禁用 tab](http://eslint.cn/docs/rules/no-tabs)



## no-trailing-spaces
[禁用行尾空白](http://eslint.cn/docs/rules/no-trailing-spaces)



## no-unneeded-ternary
[禁止可以表达为更简单结构的三元操作符](http://eslint.cn/docs/rules/no-unneeded-ternary)
```js
// Bad
var isYes = answer === 1 ? true : false;

// Good
var isYes = answer === 1;


// Bad
var isNo = answer === 1 ? false : true;

// Good
var isNo = answer !== 1;
```



## no-whitespace-before-property
[禁止属性前有空白](http://eslint.cn/docs/rules/no-whitespace-before-property)
```js
user.money
user. money
```



## padded-blocks
[要求或禁止块内填充](http://eslint.cn/docs/rules/padded-blocks)



## quote-props
[要求对象字面量属性名称使用引号](http://eslint.cn/docs/rules/quote-props)

```js
var x = {
    "while": 1,
    "foo": "bar"  // Would normally have caused a warning
};

var object2 = {
    foo: 'bar',
    baz: 42,
    true: 0,
    0: 0,
    'qux-lorem': true
};
```



## semi-spacing
[强制分号前后有空格](http://eslint.cn/docs/rules/semi-spacing)

預設 `{"before": false, "after": true}`
```js
for (i = 0; i < 10; i++) {}
```



## space-before-blocks
[要求或禁止语句块之前的空格](http://eslint.cn/docs/rules/space-before-blocks)
```js
if (a) {
}
```
```js
if (a){
}
```



## space-before-function-paren
[要求或禁止函数圆括号之前有一个空格](http://eslint.cn/docs/rules/space-before-function-paren)
```js
function withoutSpace(x) {
    // ...
}
```
```js
function withSpace (x) {
    // ...
}
```



## space-in-parens
[禁止或强制圆括号内的空格](http://eslint.cn/docs/rules/space-in-parens)
```js
foo( 'bar' );
var x = ( 1 + 2 ) * 3;
```
```js
foo('bar');
var x = (1 + 2) * 3;
```



## space-infix-ops
[要求中缀操作符周围有空格](http://eslint.cn/docs/rules/space-infix-ops)
```js
1 + 2;
1+2;
```



## space-unary-ops
[要求或禁止在一元操作符之前或之后存在空格](http://eslint.cn/docs/rules/space-unary-ops)



## arrow-spacing
[要求箭头函数的箭头之前或之后有空格](http://eslint.cn/docs/rules/arrow-spacing)
```js
// { "before": true, "after": true }
(a) => {}
```
```js
// { "before": false, "after": false }
(a)=>{}
```



## generator-star-spacing
[强制 generator 函数中 * 号周围有空格](http://eslint.cn/docs/rules/generator-star-spacing)
```js
function* generator() {
    yield "44";
    yield "55";
}
```
```js
function *generator() {
    yield "44";
    yield "55";
}
```



## no-duplicate-imports
[禁止重复导入](http://eslint.cn/docs/rules/no-duplicate-imports)
```js
// error
import { merge } from 'module';
import { find } from 'module';
```
```js
// ok
import { merge, find } from 'module';
```



## no-useless-computed-key
[禁止在对象中使用不必要的计算属性](http://eslint.cn/docs/rules/no-useless-computed-key)
```js
var foo = {["a"]: "b"}; // error
var foo = {"a": "b"}; // ok
```



## no-useless-constructor
[禁用不必要的构造函数](http://eslint.cn/docs/rules/no-useless-constructor)
```js
class A {
    constructor() {
    }
}
```
這個 `constructor()` 是不必要的，可以不寫



## no-useless-rename
[禁止在 import 和 export 和解构赋值时将引用重命名为相同的名字](http://eslint.cn/docs/rules/no-useless-rename)
```js
// 這沒有意義
import { foo as foo } from "bar";
export { foo as foo };
let { foo: foo } = bar;
```
```js
// 這樣就好了
import { foo } from "bar";
export { foo };
let { foo } = bar;
```



## prefer-arrow-callback
[要求使用箭头函数作为回调](http://eslint.cn/docs/rules/prefer-arrow-callback)

已設為 `off`



## prefer-rest-params
[建议使用剩余参数代替 arguments](http://eslint.cn/docs/rules/prefer-rest-params)



## prefer-spread
[建议使用扩展运算符而非.apply()](http://eslint.cn/docs/rules/prefer-spread)
```js
// 不建議
var args = [1, 2, 3, 4];
Math.max.apply(Math, args);
```
```js
// 推薦
var args = [1, 2, 3, 4];
Math.max(...args);
```



## require-yield
[禁用函数内没有yield的 generator 函数](http://eslint.cn/docs/rules/require-yield)

配置文件中的 "extends": "eslint:recommended" 属性启用了此规则。



## rest-spread-spacing
[强制剩余和扩展运算符及其表达式之间有空格](http://eslint.cn/docs/rules/rest-spread-spacing)
```js
// 不建議
fn(... args)

// 推薦
fn(...args)
```



## symbol-description
[要求 symbol 描述](http://eslint.cn/docs/rules/symbol-description)



## template-curly-spacing
[强制模板字符串中空格的使用](http://eslint.cn/docs/rules/template-curly-spacing)
```js
const a = "Apple";

console.log(`eat ${a}`);  // 推薦
console.log(`eat ${ a }`);  // 不建議
```



## yield-star-spacing
[强制在 yield* 表达式中 * 周围使用空格](http://eslint.cn/docs/rules/yield-star-spacing)

