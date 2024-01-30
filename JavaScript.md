# 基础JS

## 创建 JavaScript 对象
const cat = {
"name": "Whiskers",
"legs": 4,
"tails": 1,
"enemies": ["Water", "Dogs"]};

## 通过点号表示法访问对象属性
const myObj = {
prop1: "val1",
prop2: "val2"};

const prop1val = myObj.prop1;const prop2val = myObj.prop2;

## 使用方括号表示法访问对象属性
const myObj = {
"Space Name": "Kirk",
"More Space": "Spock",
"NoSpace": "USS Enterprise"};

myObj["Space Name"];
myObj['More Space'];
myObj["NoSpace"];

## 通过变量访问对象属性
const dogs = {
Fido: "Mutt",
Hunter: "Doberman",
Snoopie: "Beagle"};

const myDog = "Hunter";const myBreed = dogs[myDog];

const someObj = {
propName: "John"};

function propPrefix(str) {
const s = "prop";
return s + str;}

const someProp = propPrefix("Name");
console.log(someObj[someProp]);
注意，当使用变量名访问属性时，我们没有使用引号包裹它，因为我们正在使用的是变量的值，而不是变量的名字。

## 给 JavaScript 对象添加新属性
ourDog.bark = "bow-wow";或者ourDog["bark"] = "bow-wow";

## 删除对象的属性
delete ourDog.bark;

.hasOwnProperty(propname)检查对象是否有指定的属性

## 数据类型
undefined（未定义）、null（空）、boolean（布尔型）、string（字符串）、symbol、number（数字）、bigint（可以表示任意大的整数）和 object（对象）

## 使用 var 关键字声明变量可以轻松覆盖变量声明，使用 var 关键字声明变量时，它是全局声明的，如果在函数内部声明则是局部声明的。
const s = [5, 6, 7];
s = [1, 2, 3];
s[2] = 45;
console.log(s);
s = [1, 2, 3] 将导致错误。 console.log 将显示值 [5, 6, 45]。
因为使用了 const，所以不能使用变量标识符 s 来指向一个使用赋值运算符的不同数组。
使用 let 时，同名的变量只能声明一次，在代码块、语句或表达式中使用 let 关键字声明变量时，其作用域仅限于该代码块、语句或表达式。
使用 const 关键字声明只读变量

## 防止对象改变Object.freeze(obj);

## 用加号运算符连接字符串
const ourStr = "I come first. " + "I come second.";

## 查找字符串的长度
console.log("Alan Peter".length);

## 使用方括号查找字符串中的第N个字符-从0开始
const firstName = "Ada";
const secondLetterOfFirstName = firstName[1];

## 使用方括号查找字符串中的倒数第 N 个字符
const firstName = "Augusta";
const thirdToLastLetter = firstName[firstName.length - 3];

## 注释
// This is an in-line comment.
/* This is a
multi-line comment */

## 转义字符串中的引号
可以通过在引号前面使用反斜杠（\）来转义引号。
const sampleStr = "Alan said, \"Peter is learning JavaScript\".";

## 转义字符


## 使用 JavaScript 数组将多个值存储在一个变量中
const sandwich = ["peanut butter", "jelly", "bread"];
嵌套数组：const teams = [["Bulls", 23], ["White Sox", 45]];

## 通过索引修改数组中的数据-字符串不可变
与字符串不同，数组的条目是 可变的 并且可以自由更改，即使数组是用 const 声明的。
const ourArray = [50, 40, 30];
ourArray[0] = 15;

.push()接受一个或多个参数，并把它压入到数组的末尾。
.pop()函数移除数组末尾的元素并返回这个元素。
.shift()移除第一个元素
.unshift()在数组的头部添加元素

相等运算符==  严格相等运算符===  不相等运算符！=  严格不等运算符！==
逻辑与运算符&&  逻辑或运算符||

## else if 语句
if (condition1) {
statement1
} else if (condition2) {
statement2
} else if (condition3) {
statement3
. . .} else {
statementN
}

## switch 语句
switch (num) {
case value1:
statement1;
break;
case value2:
statement2;
break;...
default:
defaultStatement;
break;}

## while 循环
当 while 指定的条件为真，循环才会执行，反之不执行
while (i < 5) {
ourArray.push(i);
i++;}

## for 循环
for (a; b; c)，其中a为初始化语句，b为条件语句，c 是最终的表达式。
for (let i = 0; i < 5; i++) {
ourArray.push(i);}

## do...while 循环
首先 do（运行）循环里的第一部分代码，然后 while（当）规定的条件被评估为 true（真）的时候，它会继续运行循环。
do {
ourArray.push(i);
i++;} while (i < 5);

## 使用三元运算符
语法是：a ? b : c, where a 是条件，当条件返回 true 的时候运行代码 b，当条件返回 false 的时候运行代码 c。
function findGreater(a, b) {
return a > b ? "a is greater" : "b is greater or equal";}

## 使用递归代替循环
function multiply(arr, n) {
if (n <= 0) {
return 1;
} else {
return multiply(arr, n - 1) * arr[n - 1];
}
}

## 使用 Math.random() 生成随机小数
可以用 Math.random() 生成一个在0（包括 0）到 1（不包括 1）之间的随机小数。 因此 Math.random() 可能返回 0，但绝不会返回 1。

## 使用 JavaScript 生成随机整数
1. 用 Math.random() 生成一个随机小数。
2. 把这个随机小数乘以 20。
3. 用 Math.floor() 向下取整，获得它最近的整数。
记住 Math.random() 永远不会返回 1。同时因为我们是在向下取整，所以最终我们获得的结果不可能有 20。 这确保了我们获得了一个在 0 到 19 之间的整数。
Math.floor(Math.random() * 20);

## 生成某个范围内的随机整数
Math.floor(Math.random() * (max - min + 1)) + min

## parseInt() 函数解析一个字符串返回一个整数
const a = parseInt("007");
上述函数将字符串 007 转换为整数 7。 如果字符串中的第一个字符不能转换为数字，则返回 NaN。

## parseInt(string, radix);
const a = parseInt("11", 2);
变量 radix 表示 11 是在二进制系统中。 这个示例将字符串 11 转换为整数 3。

# 数组和对象

## 使用方括号访问数组的元素
如果我们要从数组 ourArray 中取出数据 a 并将其赋值给另一个变量，可以这样写：
let ourVariable = ourArray[0];
设置一个索引位置的元素值：
ourArray[1] = "not b anymore";

## 使用 push() 和 unshift() 为数组添加元素
.push()方法会将元素插入到数组的末尾，而 .unshift()方法会将元素插入到数组的开头。

## 使用 pop() 和 shift() 从数组中删除元素
.pop()会从数组的末尾移除一个元素，而.shift()会从数组的开头移除一个元素。

## 使用 splice() 删除添加元素
splice() 的第一个参数代表从数组中的哪个索引开始移除元素，而第二个参数表示要从数组中的这个位置开始删除多少个元素。
array.splice(2, 2);
第三个参数可以是一个或多个元素，这些元素会被添加到数组中。
numbers.splice(startIndex, amountToDelete, 13, 14);

## 使用 slice() 复制数组元素
.slice(1, 3)不会修改数组，而是会复制，或者说*提取（extract）*给定数量的元素到一个新数组。 slice() 只接收 2 个输入参数：第一个是开始提取元素的位置（索引），第二个是提取元素的结束位置（索引）。 提取的元素中不包括第二个参数所对应的元素。

## 使用展开运算符复制数组
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];

## 使用展开运算符合并数组
let thisArray = ['sage', 'rosemary', 'parsley', 'thyme'];

let thatArray = ['basil', 'cilantro', ...thisArray, 'coriander'];
thatArray 会有值 ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']

## 使用 indexOf() 检查元素是否存在
.indexOf('dates');方法接受一个元素作为输入参数，并返回该元素在数组中的位置（索引）；若该元素不存在于数组中则返回 -1。

## 删除对象的属性
delete ourDog.bark;

.hasOwnProperty(propname)检查对象是否有指定的属性

## 将键值对添加到对象中
如果要设置的属性中存在空格，或者要设置的属性是一个变量，那我们必须使用方括号表示法（bracket notation）来为对象添加属性。

## 使用 for...in 语句遍历对象
for (let user in users) {
console.log(user);}

## 使用 Object.keys() 生成由对象的所有属性组成的数组

# 基础数据结构

## 使用方括号访问数组的元素
如果我们要从数组 ourArray 中取出数据 a 并将其赋值给另一个变量，可以这样写：
let ourVariable = ourArray[0];
设置一个索引位置的元素值：
ourArray[1] = "not b anymore";

## 使用 push() 和 unshift() 为数组添加元素
.push()方法会将元素插入到数组的末尾，而 .unshift()方法会将元素插入到数组的开头。

## 使用 pop() 和 shift() 从数组中删除元素
.pop()会从数组的末尾移除一个元素，而.shift()会从数组的开头移除一个元素。

## 使用 splice() 删除添加元素
splice() 的第一个参数代表从数组中的哪个索引开始移除元素，而第二个参数表示要从数组中的这个位置开始删除多少个元素。
array.splice(2, 2);
第三个参数可以是一个或多个元素，这些元素会被添加到数组中。
numbers.splice(startIndex, amountToDelete, 13, 14);

## 使用 slice() 复制数组元素
.slice(1, 3)不会修改数组，而是会复制，或者说*提取（extract）*给定数量的元素到一个新数组。 slice() 只接收 2 个输入参数：第一个是开始提取元素的位置（索引），第二个是提取元素的结束位置（索引）。 提取的元素中不包括第二个参数所对应的元素。

## 使用展开运算符复制数组
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];

## 使用展开运算符合并数组
let thisArray = ['sage', 'rosemary', 'parsley', 'thyme'];

let thatArray = ['basil', 'cilantro', ...thisArray, 'coriander'];
thatArray 会有值 ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']

## 使用 indexOf() 检查元素是否存在
.indexOf('dates');方法接受一个元素作为输入参数，并返回该元素在数组中的位置（索引）；若该元素不存在于数组中则返回 -1。

## 将键值对添加到对象中
如果要设置的属性中存在空格，或者要设置的属性是一个变量，那我们必须使用方括号表示法（bracket notation）来为对象添加属性。

## 使用 for...in 语句遍历对象
for (let user in users) {
console.log(user);}

## 使用 Object.keys() 生成由对象的所有属性组成的数组

# 调试

## 使用控制台检查变量值
console.log() 方法可能是最有用的调试工具，它可以将括号中的内容输出到控制台。
console.log('Hello world!');

## 使用 type of 检查变量的类型
console.log(typeof "");
console.log(typeof 0);
console.log(typeof []);
console.log(typeof {});
JavaScript 有七种原始（不可变）数据类型： Boolean，Null，Undefined，Number，String，Symbol （new with ES6），BigInt （new with ES2020）和一种可变数据类型：Object。 注意：在 JavaScript 中，数组在本质上是一种对象。

# 面向对象编程

## 在对象上创建方法
let duck = {
name: "Aflac",
numLegs: 2,
sayName: function() {return "The name of this duck is " + duck.name + ".";}};
duck.sayName();

## 使用 this 关键字提高代码重用性
sayName: function() {return "The name of this duck is " + this.name + ".";}
在当前的上下文环境中，this 指向的就是与这个方法有关联的 duck 对象。 如果把对象的变量名改为 mallard，那使用 this 后就没有必要在代码中找到所有指向 duck 的部分。 这样可以使得代码更具有可读性和复用性。

## 定义构造函数
function Bird() {
this.name = "Albert";
this.color = "blue";
this.numLegs = 2;}
构造函数遵循一些惯例规则：
* 构造函数函数名的首字母大写，这是为了方便我们区分构造函数（ constructors）和其他非构造函数。
* 构造函数使用 this 关键字来给它将创建的这个对象设置新的属性。 在构造函数里面，this 指向的就是它新创建的这个对象。
* 构造函数定义了属性和行为就可创建对象，而不是像其他函数一样需要设置返回值。

## 使用构造函数创建对象
let blueBird = new Bird();
注意：通过构造函数创建对象的时候要使用 new 操作符。

## 扩展构造函数以接收参数
function Bird(name, color) {
this.name = name;
this.color = color;
this.numLegs = 2;}
然后将值通过参数的方式传递给 Bird 构造函数来定义每一个唯一的小鸟实例： let cardinal = new Bird("Bruce", "red"); 这给 Bird 的 name 和 color 属性分别赋值为 Bruce 和 red 色。 但 numLegs 属性仍然设置为 2。

## 使用 instanceof 验证对象的构造函数
instanceof 允许你将对象与构造函数之间进行比较，根据对象是否由这个构造函数创建的返回 true 或者 false。
let Bird = function(name, color) {
this.name = name;
this.color = color;
this.numLegs = 2;}

let crow = new Bird("Alexis", "black");

crow instanceof Bird;

## 了解自有属性
下面的代码将 duck 的所有自身属性都存到一个叫作 ownProps 的数组里面：
let ownProps = [];

for (let property in duck) {
if(duck.hasOwnProperty(property)) {
ownProps.push(property);
}}

console.log(ownProps);

## 使用原型属性来减少重复代码
prototype 是一个可以在所有 Bird 实例之间共享的对象。 以下是一个在 Bird prototype 中添加 numLegs 属性的示例：
Bird.prototype.numLegs = 2;
现在所有的 Bird 实例都拥有了共同的 numLegs 属性值。

## 迭代所有属性
现在你已经了解了两种属性: 自身属性和 prototype 属性。 自身属性是直接在对象上定义的。 而原型属性在 prototype 上定义。
这个示例会告诉你如何将 duck 的自身属性和 prototype 属性分别添加到 ownProps 数组和 prototypeProps 数组里面：
let ownProps = [];let prototypeProps = [];

for (let property in duck) {
if(duck.hasOwnProperty(property)) {
ownProps.push(property);
} else {
prototypeProps.push(property);
}}

console.log(ownProps);
console.log(prototypeProps);

## 了解构造函数属性
constructor 属性的一个好处是可以通过检查这个属性来找出它是一个什么对象。 下面是一个例子，来看看是怎么使用的：
function joinBirdFraternity(candidate) {
if (candidate.constructor === Bird) {
return true;
} else {
return false;
}}
注意： 由于 constructor 属性可以被重写（在下面两节挑战中将会遇到），所以最好使用instanceof 方法来检查对象的类型。

## 将原型更改为新对象，记得设置构造函数属性
Bird.prototype = {
constructor: Bird,
numLegs: 2,
eat: function() {
console.log("nom nom nom");
},
describe: function() {
console.log("My name is " + this.name);
}};

## 了解对象的原型来自哪里
duck 从 Bird 构造函数那里继承了它的 prototype。 你可以使用 isPrototypeOf 方法来验证他们之间的关系：
Bird.prototype.isPrototypeOf(duck);

## 了解原型链
hasOwnProperty 是定义在 Object.prototype 上的一个方法，尽管在 Bird.prototype 和 duck上并没有定义该方法，但是我们依然可以在这两个对象上访问到。 这就是 prototype 链的一个例子。 在这个prototype 链中，Bird 是 duck 的 supertype，而 duck 是 subtype。 Object 则是 Bird 和 duck 实例共同的 supertype。 Object 是 JavaScript 中所有对象的 supertype，也就是原型链的最顶层。 因此，所有对象都可以访问 hasOwnProperty 方法。

## 使用继承避免重复
可以通过创建一个 Animal supertype（或者父类）来重写这段代码

## 从超类继承行为
let animal = Object.create(Animal.prototype);
Object.create(obj) 创建了一个新对象，并指定了 obj 作为新对象的 prototype。 回忆一下，我们之前说过 prototype 就像是创建对象的“配方”。 如果我们把 animal 的 prototype 设置为与 Animal 构造函数的 prototype 一样，那么就相当于让 animal 这个实例具有与 Animal 的其他实例相同的“配方”了。
animal.eat();
animal instanceof Animal;

## 将子辈的原型设置为父辈
Bird.prototype = Object.create(Animal.prototype);

## 重置一个继承的构造函数属性
当一个对象从另一个对象那里继承了其 prototype 时，那它也继承了父类的 constructor 属性。
可以手动将 Bird 的构造函数属性设置为 Bird 对象：
Bird.prototype.constructor = Bird;

## 继承后添加方法
Bird 是一个构造函数，它继承了 Animal 的 prototype：
function Animal() { }
Animal.prototype.eat = function() {
console.log("nom nom nom");
};
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Bird;
除了从 Animal 构造函数继承的行为之外，还需要给 Bird 对象添加它独有的行为。 这里，我们给 Bird 对象添加一个 fly() 函数。 函数会以一种与其他构造函数相同的方式添加到 Bird's 的 prototype 中：
Bird.prototype.fly = function() {
console.log("I'm flying!");};

在上一个挑战中，我们学习了一个对象可以通过引用另一个对象的 prototype 来继承其属性和行为（或方法）：
ChildObject.prototype = Object.create(ParentObject.prototype);
然后，ChildObject 将自己的方法链接到它的 prototype中：
ChildObject.prototype.methodName = function() {...};

## 重写继承的方法
我们还可以重写继承的方法。 以同样的方式 - 通过使用一个与需要重写的方法相同的方法名，向ChildObject.prototype 中添加方法。 请看下面的举例：Bird 重写了从 Animal 继承来的 eat() 方法：
function Animal() { }Animal.prototype.eat = function() {
return "nom nom nom";};function Bird() { }

Bird.prototype = Object.create(Animal.prototype);

Bird.prototype.eat = function() {
return "peck peck peck";};
如果你有一个实例：let duck = new Bird();，然后你调用了 duck.eat()，以下就是 JavaScript 在 duck 的 prototype 链上寻找方法的过程：
1. duck => eat() 是定义在这里吗？ 不是。
2. Bird => eat() 是定义在这里吗？ => 是的。 执行它并停止往上搜索。
3. Animal => 这里也定义了 eat() 方法，但是 JavaScript 在到达这层原型链之前已停止了搜索。
4. Object => JavaScript 在到达这层原型链之前也已经停止了搜索。

## 使用 Mixin 在不相关对象之间添加共同行为
对于不相关的对象，更好的方法是使用 mixins。 mixin 允许其他对象使用函数集合。
let flyMixin = function(obj) {
obj.fly = function() {
console.log("Flying, wooosh!");
}};
flyMixin 能接受任何对象，并为其提供 fly 方法。
let bird = {
name: "Donald",
numLegs: 2};

let plane = {
model: "777",
numPassengers: 524};

flyMixin(bird);flyMixin(plane);

## 使用闭包保护对象内的属性不被外部修改
使属性私有化最简单的方法就是在构造函数中创建变量。 可以将该变量范围限定在构造函数中，而不是全局可用。 这样，属性只能由构造函数中的方法访问和更改。
function Bird() {
let hatchedEgg = 10;

this.getHatchedEggCount = function() {
return hatchedEgg;
};}let ducky = new Bird();
ducky.getHatchedEggCount();
这里的 getHatchedEggCount 是一种特权方法，因为它可以访问私有属性 hatchedEgg。 这是因为 hatchedEgg 是在与 getHatchedEggCount 相同的上下文中声明的。 在 JavaScript 中，函数总是可以访问创建它的上下文。 这就叫做 closure。

## 了解立即调用函数表达（IIFE）
JavaScript 中的一个常见模式就是，函数在声明后立刻执行：
(function () {
console.log("Chirp, chirp!");
})();
这是一个匿名函数表达式，立即执行并输出 Chirp, chirp!。
请注意，函数没有名称，也不存储在变量中。 函数表达式末尾的两个括号（）会让它被立即执行或调用。 这种模式被叫做立即调用函数表达式（immediately invoked function expression) 或者IIFE。

## 使用 IIFE 创建一个模块
一个立即调用函数表达式（IIFE）通常用于将相关功能分组到单个对象或者是 module 中。 例如，先前的挑战中定义了两个 mixins：
function glideMixin(obj) {
obj.glide = function() {
console.log("Gliding on the water");
};}function flyMixin(obj) {
obj.fly = function() {
console.log("Flying, wooosh!");
};}
我们可以将这些 mixins 分成以下模块：
let motionModule = (function () {
return {
glideMixin: function(obj) {
obj.glide = function() {
console.log("Gliding on the water");
};
},
flyMixin: function(obj) {
obj.fly = function() {
console.log("Flying, wooosh!");
};
}
}})();
注意：一个立即调用函数表达式（IIFE）返回了一个 motionModule 对象。 返回的这个对象包含了作为对象属性的所有 mixin 行为。 module 模式的优点是，所有的运动相关的行为都可以打包成一个对象，然后由代码的其他部分使用。 下面是一个使用它的例子：
motionModule.glideMixin(duck);
duck.glide();

# 正则表达式

## 使用测试方法
测试正则表达式的一种方法是使用 .test() 方法。 .test() 方法会把编写的正则表达式和字符串（即括号内的内容）匹配，如果成功匹配到字符，则返回 true，反之，返回 false。
let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr);
你还可以匹配多个规则，这可以通过添加更多的匹配模式来实现。 这些匹配模式将包含更多的 OR 操作符来分隔它们，比如/yes|no|maybe/。

## 提取匹配项
'string'.match(/regex/);
/regex/.test('string');

## 匹配时忽略大小写
/freeCodeCamp/i

## 全局匹配
若要多次搜寻或提取模式匹配，可以使用 g 标志。
let repeatRegex = /Repeat/g;
testStr.match(repeatRegex);
在正则表达式上可以有多个标志，比如 /search/gi

## 用通配符匹配任何内容
例如，如果想匹配 hug、huh、hut 和 hum，可以使用正则表达式 /hu./ 匹配以上四个单词。
let humStr = "I'll hum a song";let hugStr = "Bear hug";let huRegex = /hu./;
huRegex.test(humStr);
huRegex.test(hugStr);

## 将单个字符与多种可能性匹配
例如，如果想要匹配 bag、big 和 bug，但是不想匹配 bog。 可以创建正则表达式 /b[aiu]g/ 来执行此操作。 [aiu] 是只匹配字符 a、i 或者 u 的字符集。
let bgRegex = /b[aiu]g/;

## 匹配字母表中的数字和字母
在字符集中，可以使用连字符（-）来定义要匹配的字符范围。
例如，要匹配小写字母 a 到 e，你可以使用 [a-e]。
/[0-5]/ 匹配 0 和 5 之间的任意数字，包含 0 和 5。
let myRegex = /[a-z0-9]/ig;

## 匹配单个未指定的字符
要创建否定字符集，需要在开始括号后面和不想匹配的字符前面放置脱字符（即^）。
例如，/[^aeiou]/gi 匹配所有非元音字符。 注意，字符 .、!、[、@、/ 和空白字符等也会被匹配，该否定字符集仅排除元音字符。
let myRegex = /[^aeiou0-9]/ig;

## 匹配出现一次或多次的字符/a+/
可以使用 + 符号来检查情况是否如此。 记住，字符或匹配模式必须一个接一个地连续出现。 这就是说，字符必须一个接一个地重复。
例如，/a+/g 会在 abc 中匹配到一个匹配项，并且返回 ["a"]。 因为 + 的存在，它也会在 aabc 中匹配到一个匹配项，然后返回 ["aa"]。

## 匹配出现零次或多次的字符/go*/

## 用惰性匹配来查找字符
在正则表达式中，贪婪（greedy）匹配会匹配到符合正则表达式匹配模式的字符串的最长可能部分，并将其作为匹配项返回。 另一种方案称为懒惰（lazy）匹配，使用 ? 字符来变成懒惰匹配，它会匹配到满足正则表达式的字符串的最小可能部分。

## 匹配字符串的开头/^Ricky/ 匹配字符串的末尾/story$/

## 匹配所有的字母和数字/\w/ 匹配除了字母和数字的所有符号/\W/
\w， 这个缩写等同于[A-Za-z0-9_]。 此字符类匹配大写字母和小写字母以及数字。 注意，这个字符类也包含下划线字符 (_)。

## 匹配所有数字/\d/ 匹配所有非数字/\D/

## 匹配空白字符/\s/ 匹配非空白字符/\S/
可以使用 \s 搜寻空格，其中 s 是小写。 此匹配模式将匹配空格、回车符、制表符、换页符和换行符。 可以认为这类似于元字符 [ \r\t\f\n\v]。

## 指定匹配的确切数量/ha{3}h/ /a{3,5}h/
例如，要匹配出现 3 到 5 次字母 a 的在字符串 ah，正则表达式应为/a{3,5}h/。

## 检查全部或无/colou?r/

正向先行断言和负向先行断言
正向先行断言会查看并确保搜索匹配模式中的元素存在，但实际上并不匹配。 正向先行断言的用法是 (?=...)，其中 ... 就是需要存在但不会被匹配的部分。
另一方面，负向先行断言会查看并确保搜索匹配模式中的元素不存在。 负向先行断言的用法是 (?!...)，其中 ... 是希望不存在的匹配模式。 如果负向先行断言部分不存在，将返回匹配模式的其余部分。
先行断言的更实际用途是检查一个字符串中的两个或更多匹配模式。 这里有一个简单的密码检查器，密码规则是 3 到 6 个字符且至少包含一个数字：
let password = "abc123";
let checkPass = /(?=\w{3,6})(?=\D*\d)/;
checkPass.test(password);

检查混合字符组 /P(engu|umpk)in/

## 使用捕获组重用模式
let repeatStr = "row row row your boat";
下面的示例是匹配被空格隔开的两个相同单词：
let repeatRegex = /(\w+) \1 \1/;
repeatRegex.test(repeatStr); // Returns true
repeatStr.match(repeatRegex); // Returns ["row row row", "row"]

## 使用捕获组搜索和替换
可以在字符串上使用 .replace() 方法来搜索并替换字符串中的文本。
 .replace() 的输入首先是想要搜索的正则表达式匹配模式。 第二个参数是用于替换匹配的字符串或用于执行某些操作的函数。
let wrongText = "The sky is silver.";
let silverRegex = /silver/;
wrongText.replace(silverRegex, "blue");
replace 调用将返回字符串 The sky is blue.。
你还可以使用美元符号（$）访问替换字符串中的捕获组。
"Code Camp".replace(/(\w+)\s(\w+)/, '$2 $1');
调用 replace 将返回字符串 Camp Code。

## 删除开头和结尾的空白
let hello = "   Hello, World!  ";
let wsRegex = /^\s+|\s+$/g; 
let result =hello.replace(wsRegex, "");

# ES6

## 使用箭头函数编写简洁的匿名函数
const myFunc = () => {
const myVar = "value";
return myVar;}
当不需要函数体，只返回一个值的时候，箭头函数允许你省略 return 关键字和外面的大括号。 这样就可以将一个简单的函数简化成一个单行语句。
const myFunc = () => "value";

## 设置函数的默认参数
const greeting = (name = "Anonymous") => "Hello " + name;

console.log(greeting("John"));
console.log(greeting());

## 将 rest 操作符与函数参数一起使用
function howMany(...args) {
return "You have passed " + args.length + " arguments.";}

## 使用 spread 运算符展开数组项
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);
...arr 返回一个解压的数组。 也就是说，它展开数组。 然而，展开操作符只能够在函数的参数中或者数组中使用。


## 解构赋值：
const user = { name: 'John Doe', age: 34 };

const name = user.name;const age = user.age;

使用解构赋值来获取对象的值const { name, age } = user;

使用解构赋值从对象中分配变量const { name: userName, age: userAge } = user;

使用解构赋值从嵌套对象中分配变量const { johnDoe: { age: userAge, email: userEmail }} = user;

使用解构赋值从数组中分配变量
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c);

使用解构赋值配合 rest 操作符来重新分配数组元素
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b);
console.log(arr);

使用解构赋值将对象作为函数的参数传递
const profileUpdate = (profileData) => {
const { name, age, nationality, location } = profileData;

}
上面的操作解构了传给函数的对象。 这样的操作也可以直接在参数里完成：
const profileUpdate = ({ name, age, nationality, location }) => {

}

## 使用模板字面量创建字符串
const person = {
name: "Zodiac Hasbro",
age: 56};

const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`;

console.log(greeting);

## 使用简单字段编写简洁的对象字面量声明
const getMousePosition = (x, y) => ({
x: x,
y: y
});

const getMousePosition = (x, y) => ({ x, y });

## 用 ES6 编写简洁的函数声明
用 ES6 的语法在对象中定义函数的时候，可以删除 function 关键词和冒号。
const person = {
name: "Taylor",
sayHello() {
return `Hello! My name is ${this.name}.`;
}};

## 使用 class 语法定义构造函数
var SpaceShuttle = function(targetPlanet){
this.targetPlanet = targetPlanet;}var zeus = new SpaceShuttle('Jupiter');
class 语法只是简单地替换了构造函数 constructor 的写法：
class SpaceShuttle {
constructor(targetPlanet) {
this.targetPlanet = targetPlanet;
}}const zeus = new SpaceShuttle('Jupiter');

## 使用 getter 和 setter 来控制对象的访问
Getter 函数的作用是可以让对象返回一个私有变量，而不需要直接去访问私有变量。
Setter 函数的作用是可以基于传进的参数来修改对象中私有变量。 这些修改可以是计算，或者是直接替换之前的值。
class Book {
constructor(author) {
this._author = author;
}
// getter
get writer() {
return this._author;
}
// setter
set writer(updatedAuthor) {
this._author = updatedAuthor;
}}const novel = new Book('anonymous');
console.log(novel.writer);
novel.writer = 'newAuthor';
console.log(novel.writer);

## 创建一个模块脚本
<script type="module" src="filename.js"></script>

## 用 export 来重用代码块
export const add = (x, y) => {
return x + y;}
上面是导出单个函数常用方法，还可以这样导出：
const add = (x, y) => {
return x + y;}

export { add };
重复第一个例子的代码可以导出多个对象或函数，在第二个例子里面的导出语句中添加更多值也可以导出多项，例子如下：
export { add, subtract };

## 通过 import 复用 JavaScript 代码
import { add } from './math_functions.js';
在这里，import 会在 math_functions.js 里找到 add，只导入这个函数，忽略剩余的部分。
通过在 import 语句里添加项目，可以从文件里导入多个项目，如下：
import { add, subtract } from './math_functions.js';

## 用 * 从文件中导入所有内容
下面是一个从同目录下的 math_functions.js 文件中导入所有内容的例子：
import * as myMathModule from "./math_functions.js";
下面是使用导入的 add 和 subtract 函数的例子：
myMathModule.add(2,3);
myMathModule.subtract(5,3);

## 用 export default 创建一个默认导出
在文件中只有一个值需要导出的时候，通常会使用这种语法。 它也常常用于给文件或者模块创建返回值。
export default function add(x, y) {
return x + y;}

export default function(x, y) {
return x + y;}
第一个是命名函数，第二个是匿名函数。
export default 用于为模块或文件声明一个返回值，在每个文件或者模块中应当只默认导出一个值。 此外，你不能将 export default 与 var、let 或 const 同时使用。

## 导入一个默认的导出
import add from "./math_functions.js";

## 创建一个 JavaScript Promise
Promise 是构造器函数，需要通过 new 关键字来创建。 构造器参数是一个函数，该函数有两个参数 - resolve 和 reject。 通过它们来判断 promise 的执行结果。 用法如下：
const myPromise = new Promise((resolve, reject) => {

});

## 通过 resolve 和 reject 完成 Promise
Promise 有三个状态：pending、fulfilled 和 rejected。
Promise 成功时调用 resolve，promise 执行失败时调用 reject
const myPromise = new Promise((resolve, reject) => {
if(condition here) {
resolve("Promise was fulfilled");
} else {
reject("Promise was rejected");
}});

## 用 then 处理 Promise 完成的情况
当 promise 完成 resolve 时会触发 then 方法
myPromise.then(result => {

});
result 即传入 resolve 方法的参数。

## 使用 catch 处理 Promise 失败的情况
myPromise.catch(error => {

});
error 是传入 reject 方法的参数。




# JS项目

## 回文检查器
function palindrome(str) {
   var newStr=str.replace(/[^a-zA-Z0-9]/g,"").toLowerCase();
  var strReverse = newStr.split('').reverse().join("");
if (newStr===strReverse){
  return true;
}
  return false;
}


## 罗马数字转换器
function convertToRoman(num) {
  var rom1=['','I','II','III','IV','V','VI','VII','VIII','IX'];
  var rom2=['','X','XX','XXX','XL','L','LX','LXX','LXXX','XC'];
  var rom3=['','C','CC','CCC','CD','D','DC','DCC','DCCC','CM'];
  var rom4=['','M','MM','MMM'];
  var str='';
  str+=num;
  var arr=str.split('');
var result=[];
switch (arr.length){
  case 1:
  result.push(rom1[arr[0]]);
  break;
  case 2:
  result.push(rom2[arr[0]],rom1[arr[1]]);
  break;
  case 3:
  result.push(rom3[arr[0]],rom2[arr[1]],rom1[arr[2]]);
  break;
  case 4:
  result.push(rom4[arr[0]],rom3[arr[1]],rom2[arr[2]],rom1[arr[3]]);
  break;
}
return result.join('');
}

## 凯撒密码
function rot13(str) {
   return str.replace(/[A-Z]/g, L => String.fromCharCode((L.charCodeAt(0) % 26) + 65));
}


## 电话号码检查器
function telephoneCheck(str) {
    let regex = /^(1\s?)?\d{3}\s?\d{3}\s?\d{4}$|^(1\s?)?\d{3}-?\d{3}-?\d{4}$|^(1\s?)?\(\d{3}\)\s?\d{3}-\d{4}$/;
    if (regex.test(str)) {
        return true;
    }return false;
}

## 计算找零
function checkCashRegister(price, cash, cid) {
  var total=0; 
  var change=cash-price;
  var arr=[0.01,0.05,0.1,0.25,1,5,10,20,100];
  var result=[]; 
  for (let i=0;i<cid.length;i++){
    total+=cid[i][1];
  };
  if (total<change) {
    return {status: "INSUFFICIENT_FUNDS", change: []};
  };
  if(total===change){
    return {status: "CLOSED", change: [...cid]};
  };
  for (let i=arr.length-1;i>0;i--){
    if (arr[i-1]<change){
      if (change>=cid[i-1][1]){
        result.push(cid[i-1]);
        change = (change - cid[i-1][1]).toFixed(2);
      }else {
        result.push([cid[i-1][0],arr[i-1]*Math.floor(change/arr[i-1])]);
        change=(change-arr[i-1]*Math.floor(change/arr[i-1])).toFixed(2);
      };
      if (change==0){
        return {status: "OPEN", change: [...result]};
      }
    }
  }
 return {status: "INSUFFICIENT_FUNDS", change: []};
}

# 函数式编程

## 函数式编程
函数式编程是一种方案简单、功能独立、对作用域外没有任何副作用的编程范式：INPUT -> PROCESS -> OUTPUT。
函数式编程：
1）功能独立——不依赖于程序的状态（比如可能发生变化的全局变量）；
2）纯函数——同一个输入永远能得到同一个输出；
3）有限的副作用——可以严格地限制函数外部对状态的更改。

## 函数式编程术语
Callbacks 是被传递到另一个函数中调用的函数。 你应该已经在其他函数中看过这个写法，例如在 filter 中，回调函数告诉 JavaScript 以什么规则过滤数组。
函数就像其他正常值一样，可以赋值给变量、传递给另一个函数，或从其它函数返回，这种函数叫做头等 first class 函数。 在 JavaScript 中，所有函数都是头等函数。
将函数为参数或返回值的函数叫做高阶 ( higher order) 函数。
当函数被传递给另一个函数或从另一个函数返回时，那些传入或返回的函数可以叫做 lambda。

## 函数式编程的两个原则：
1. 不要更改变量或对象 - 创建新变量和对象，并在需要时从函数返回它们。 提示：使用类似 const newArr = arrVar 的东西，其中 arrVar 是一个数组，只会创建对现有变量的引用，而不是副本。 所以更改 newArr 中的值会同时更改 arrVar 中的值。
2. 声明函数参数 - 函数内的任何计算仅取决于参数，而不取决于任何全局对象或变量。

## 使用 map 方法从数组中提取数据Array.prototype.map()
请记住，map方法是迭代数组中每一项的方式之一。 在对每个元素应用回调函数后，它会创建一个新数组(不改变原来的数组)。 它这样做时没有改变原始数组。
当调用回调函数时，传入了三个参数。 第一个参数是当前正在处理的数组项。 第二个参数是当前数组项的索引值，第三个参数是在其上调用 map 方法的数组。
看下在 users 上使用 map 方法的例子，返回了一个新数组只包含了用户的名字。 为了简化，例子里只使用了回调函数的第一个参数。
const users = [
{ name: 'John', age: 34 },
{ name: 'Amy', age: 20 },
{ name: 'camperCat', age: 10 }];

const names = users.map(user => user.name);
console.log(names);
控制台将显示值 [ 'John', 'Amy', 'camperCat' ]。

## 使用 filter 方法从数组中提取数据Array.prototype.filter()
filter 接收一个回调函数，将回调函数内的逻辑应用于数组的每个元素，新数组包含根据回调函数内条件返回 true 的元素。 换言之，它根据传递给它的函数过滤数组。 和 map 一样，filter 不会改变原始数组。
回调函数接收三个参数。 第一个参数是当前正在被处理的元素。 第二个参数是这个元素的索引，第三个参数是在其上调用 filter 方法的数组。
看下在 users 上使用 filter 方法的例子，返回了一个包含了 30 岁以下的用户新数组。 为了简化，例子里只使用了回调函数的第一个参数。
const users = [
{ name: 'John', age: 34 },
{ name: 'Amy', age: 20 },
{ name: 'camperCat', age: 10 }];

const usersUnder30 = users.filter(user => user.age < 30);
console.log(usersUnder30);
控制台将显示值 [ { name: 'Amy', age: 20 }, { name: 'camperCat', age: 10 } ]

## 使用 slice 方法返回数组的一部分
slice 方法可以从已有数组中返回指定元素。 它接受两个参数，第一个规定从何处开始选取，第二个规定从何处结束选取（不包括该元素）。 如果没有传参，则默认为从数组的开头开始到结尾结束，这是复制整个数组的简单方式。 slice 返回一个新数组，不会修改原始数组。
举个例子：
const arr = ["Cat", "Dog", "Tiger", "Zebra"];
const newArray = arr.slice(1, 3);
newArray 值为 ["Dog", "Tiger"]

## 使用 concat 方法组合两个数组
对数组来说，在一个数组上调用 concat 方法，然后提供另一个数组作为参数添加到第一个数组末尾。 它返回一个新数组，不会改变任何一个原始数组。
[1, 2, 3].concat([4, 5, 6]);

## 使用 reduce 方法分析数据Array.prototype.reduce()
reduce方法遍历数组中的每个项目并返回单个值（即字符串、数字、对象、数组）。 这是通过在每次迭代中调用一个回调函数来实现的。
回调函数接受四个参数。 第一个参数称为叠加器，它是上一次迭代中回调函数的返回值，第二个参数是当前正在处理的数组元素，第三个参数是该参数的索引，第四个参数是在其上调用 reduce 方法的数组。
除了回调函数，reduce 还有一个额外的参数做为叠加器的初始值。 如果没有第二个参数，会跳过第一次迭代，第二次迭代给叠加器传入数组的第一个元素。
见下面的例子，给 users 数组使用 reduce 方法，返回所有用户数组的和。 为了简化，例子仅使用了回调函数的第一个参数和第二个参数。
const users = [
{ name: 'John', age: 34 },
{ name: 'Amy', age: 20 },
{ name: 'camperCat', age: 10 }];

const sumOfAges = users.reduce((sum, user) => sum + user.age, 0);
console.log(sumOfAges);
这里控制台将显示值 64。
在另一个例子里，查看如何返回一个包含用户名称做为属性，其年龄做为值的对象。
const users = [
{ name: 'John', age: 34 },
{ name: 'Amy', age: 20 },
{ name: 'camperCat', age: 10 }];

const usersObj = users.reduce((obj, user) => {
obj[user.name] = user.age;
return obj;}, {});
console.log(usersObj);
控制台将显示值 { John: 34, Amy: 20, camperCat: 10 }。

function getRating(watchList) {
  // 只修改这一行下面的代码
   const averageRating = watchList
    // Use filter to find films directed by Christopher Nolan
    .filter(film => film.Director === "Christopher Nolan")
    // Use map to convert their ratings from strings to numbers
    .map(film => Number(film.imdbRating))
    // Use reduce to add together their ratings
    .reduce((sumOfRatings, rating) => sumOfRatings + rating) /
  // Divide by the number of Nolan films to get the average rating
  watchList.filter(film => film.Director === "Christopher Nolan").length;
  // 只修改这一行上面的代码
  return averageRating;
}

## 使用 sort 方法按字母顺序给数组排序
function reverseAlpha(arr) {
return arr.sort(function(a, b) {
return a === b ? 0 : a < b ? 1 : -1;
});}

reverseAlpha(['l', 'h', 'z', 'b', 's']);
这将返回值 ['z', 's', 'l', 'h', 'b']。
JavaScript 的默认排序方法是 Unicode 值顺序排序，有时可能会得到意想不到的结果。 因此，建议提供一个回调函数来指定如何对数组项目排序。 这个回调函数通常叫做 compareFunction，它根据 compareFunction 的返回值决定数组元素的排序方式： 如果两个元素 a 和 b，compareFunction(a,b) 返回一个比 0 小的值，那么 a 会在 b 的前面。 如果两个元素 a 和 b，compareFunction(a,b) 返回一个比 0 大的值，那么 b 会在 a 的前面。 如果两个元素 a 和 b，compareFunction(a,b) 返回等于 0 的值，那么 a 和 b 的位置保持不变。

## 使用 split 方法将字符串拆分成数组
split 方法将一个字符串分割成一个字符串数组。 它需要一个参数作为分隔符，它可以是用于拆分字符串或正则表达式的一个字符。 举个例子，如果分隔符是空格，你会得到一个单词数组；如果分隔符是空字符串，你会得到一个由字符串中每个字符组成的数组。
下面是两个用空格分隔一个字符串的例子，另一个是用数字的正则表达式分隔：
const str = "Hello World";
const bySpace = str.split(" ");

const otherString = "How9are7you2today";
const byDigits = otherString.split(/\d/);
bySpace 将有值 ["Hello", "World"]，byDigits 将有值 ["How", "are", "you", "today"]。

## 使用 join 方法将数组组合成字符串
join 方法用来把数组中的所有元素放入一个字符串。 并通过指定的分隔符参数进行分隔。
const arr = ["Hello", "World"];
const str = arr.join(" ");
str 的值应该是字符串 Hello World。

## 使用 every 方法检查数组中的每个元素是否符合条件
every 方法用于检测数组中所有元素是否都符合指定条件。 如果所有元素满足条件，返回布尔值 true，反之返回 false。
举个例子，下面的代码检测数组 numbers 的所有元素是否都小于 10：
const numbers = [1, 5, 8, 0, 10, 11];

numbers.every(function(currentValue) {
return currentValue < 10;});
every 方法在这里会返回 false。

## 使用 some 方法检查数组中是否有元素是否符合条件
some 方法用于检测数组中任何元素是否满足指定条件。 如果有一个元素满足条件，返回布尔值 true，反之返回 false。
举个例子，下面的代码检测数组numbers中是否有元素小于 10：
const numbers = [10, 50, 8, 220, 110, 11];

numbers.some(function(currentValue) {
return currentValue < 10;});
some 方法将返回 true。

## 函数柯里化和局部调用
arity（参数个数）是函数所需的形参的数量。 函数柯里化（Currying）意思是把接受多个 arity 的函数变换成接受单一 arity 的函数。
换句话说，就是重构函数让它接收一个参数，然后返回接收下一个参数的函数，依此类推。
举个例子：
function unCurried(x, y) {
return x + y;}

function curried(x) {
return function(y) {
return x + y;
}}

const curried = x => y => x + y

curried(1)(2)
curried(1)(2) 会返回 3。
柯里化在不能一次为函数提供所有参数情况下很有用。 因为它可以将每个函数的调用保存到一个变量中，该变量将保存返回的函数引用，该引用在下一个参数可用时接受该参数。 下面是使用柯里化函数的例子：
const funcForY = curried(1);
console.log(funcForY(2)); // 3
类似地，局部调用（ partial application）的意思是一次对一个函数应用几个参数，然后返回另一个应用更多参数的函数。 这是一个示例：
function impartial(x, y, z) {
return x + y + z;}

const partialFn = impartial.bind(this, 1, 2);partialFn(10); // 13



