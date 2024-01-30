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



