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

