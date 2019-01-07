<h1>Differences between ES5 and ES6</h1>
<ol>
<h2><li>Fat Arrow Functions</li></h2>
const example = (arg) => {};
<h2><li>this</li></h2>
<p>something like python self.current execution context of a function </p>

&nbsp function getType(){<br>
&nbsp&nbsp  console.log(`Type is :${this.type}`)<br>
&nbsp };<br>

var CRV = {<br>
&nbsp  type:'SUV',<br>
&nbsp  getType:getType<br>
};<br>

getType();<br>

<h2><li>Objects literal</li></h2>
if key and value are same, you can ommit one of them.

function getCar(make, model, value){<br>
&nbsp  return {<br>
&nbsp&nbsp    make,      // ES5 make:make,<br>
&nbsp&nbsp    model,     // ES5 model:model,<br>
&nbsp&nbsp    value      // ES5 value:value,<br>
&nbsp  }<br>
}<br>
<h2><li> <a href = 'https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes'>Classes </a></li></h2>
Classes are special functions. The class syntax has class expression and class declarations.
<h3>[1]class declarations </h3>
Use class keyword with the name of the class. Class declarations are not hoisted like function declarations. Hence, first declare class and then access it.
<h4>+++ ES6 +++</h4>
class Person {<br>
&nbsp  constructor(name, age, gender){<br>
&nbsp&nbsp    this.name = name;<br>
&nbsp&nbsp    this.age = age;<br>
&nbsp&nbsp    this.gender = gender;<br>
  }<br>
&nbsp  incrementAge(){<br>
&nbsp&nbsp    this.age += 1;<br>
  }<br>
}<br>

class Personal extends Person{<br>
&nbsp  constructor(name, age, gender, occupation, hobby){<br>
&nbsp&nbsp    super(name, age, gender);<br>
&nbsp&nbsp    this.occupation = occupation;<br>
&nbsp&nbsp    this.hobby = hobby;<br>
&nbsp  }<br>
&nbsp  incrementAge(){<br>
&nbsp&nbsp    super.incrementAge();<br>
&nbsp&nbsp    this.age += 20;<br>
&nbsp&nbsp    console.log(this.age);<br>
&nbsp  }<br>
}<br>

<h4>+++ ES5 +++</h4>
function Person (name, age, gender){<br>
&nbsp  this.name = name;<br>
&nbsp  this.age = age;<br>
&nbsp  this.gender = gender;<br>
}<br>
Person.prototype.incrementAge = function(){<br>
&nbsp  return this.age += 1;<br>
}<br>
function Personal(name, age, gender, occupation, hobby){<br>
&nbsp  Person.call(this, name, age, gender);<br>
&nbsp  this.occupation = occupation;<br>
&nbsp  this.hobby = hobby;<br>
}<br>
Personal.prototype = Object.create(Person.prototype);<br>
Personal.prototype.constructor = Personal;<br>
Personal.prototype.incrementAge = function(){<br>
&nbsp  Person.prototype.incrementAge.call(this);<br>
&nbsp  this.age += 20;<br>
&nbsp  console.log(this.age);<br>
;}<br>

<h3>[2]class expression</h3>
class expression can be named or unnabled. The name given to a named class expressionis local to class's body.<br>
// unnamed<br>
let Rectangle = class {  // class body start<br>
&nbsp  constructor(height, width){  // same as __init__ 1 constructor per class<br>
&nbsp&nbsp    this.height = height;       // can use super keyword to call the super class<br>
&nbsp&nbsp    this.width = width;         // constructor of the super class<br>
&nbsp  }<br>
};<br>
console.log(Rectangle.name);<br>

//named<br>
let Rectangle = class Rectangle2 {<br>
&nbsp  constructor (height, width){<br>
&nbsp&nbsp    this.height = height;<br>
&nbsp&nbsp    this.width = width;<br>
&nbsp  }<br>
};<br>
console.log(Rectangle.name);<br>
<h2><li>Destructing assignment syntax</li></h2>
Destructuring allows us to extract values from arrays and objects(even deeply nested) and store them in variable with a more convenient syntax.
let [a,b,c,d] = [1,2,3,4];<br>
let luke = {occupation:'jedi',father:'anakin'};<br>
let {occupation, father} = luke; // console.log(occupation) //'jedi'<br>


<h2><li>Template Literal / Interpolation(${name})</li></h2>
let text= `${name} said, "Hello" to me the other day.`<br>

let text = (`cat<br>
dog               // no need to put \n for new line<br>
nickelodeon`<br>
);<br>

<h2><li> Default parameters </li></h2>
function multiply(a, b = 1) {<br>
&nbsp  return a * b;<br>
}<br>
<h2><li> Method definitinos </li></h2>
//ES5<br>
var obj = {<br>
&nbsp     foo: foo(){ return 'bar'}<br>
 };<br>

 //ES6<br>
 var obj = {    <br>
&nbsp     foo(){return 'bar'}<br>
 }<br>

<h2> <li>Rest parameters</li></h2>
 <p>indefinite number of arguments</p>
 function sum(...theArgs) {<br>
&nbsp  return theArgs.reduce((previous, current) => {<br>
&nbsp&nbsp    return previous + current;<br>
&nbsp&nbsp  });<br>
}<br>

<h2><li>Spread Syntax (...)</li></h2>
[reference] <a href='https://codeburst.io/javascript-es6-the-spread-syntax-f5c35525f754'>Medium blog by Brandon Morelli</a><br>
It allows an iterable to expand in places where 0+ arguments are expected.

<ul>
<h3><li>Inserting Arrays</li></h3>
* without spread syntax *<br>
var mid = [3,4];<br>
var arr = [1,2,mid,5,6] <br>
console.log(arr); // [1,2,[3,4],5,6] <br>

* with spread syntax *<br>
var mid = [3,4];<br>
var arr = [1,2,...mid,5,6] // <br>
console.log(arr); // [1,2,3,4,5,6] <br>

<h3><li>Math</li></h3>
var arr = [2,3,8,6,0]<br>
* without spread syntax *<br>
function max(arr){<br>
&nbsp    return Math.max.apply(null,arr);<br>
} <br>

* with spread syntax *<br>
var max = Math.max(...arr)<br>

<h3><li>Copy an Array </li></h3>
By using spread syntax, you can copy an array without by Referencing.<br>
* without spread syntax *<br>
var arr = ['a', 'b', 'c'];<br>
var arr2 = arr;<br>
arr2.push('d')  // ['a','b','c','d'] <br>

* with spread syntax *<br>
var arr = ['a', 'b', 'c'];<br>
var arr2 = [...arr]; // ['a','b','c'] copied successfully<br>

<h3><li> String to Array </li></h3>
var str = 'hello';<br>
var chars = [...str]; // ['h','e','l','l','o'];<br>
</ul>

<h2> Map</h2>
Still leaning<br>
https://hackernoon.com/what-you-should-know-about-es6-maps-dc66af6b9a1e

<h2>others</h2>
<p>Module Loaders</p>
<p>Weak set</p>
<p>New Library</p>
<p>Promises</p>
<p>Proxies</p>