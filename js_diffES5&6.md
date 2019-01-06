<h1>Differences between ES5 and ES6</h1>
<ol>
<h2><li>Fat Arrow Functions</li></h2>
const example = (arg) => {};
<h2><li>this</li></h2>
something like python self.
current execution context of a function
function getType(){
  console.log(`Type is :${this.type}`)
};
var CRV = {
  type:'SUV',
  getType:getType
};
getType();

<h2><li>Objects literal</li></h2>
if key and value are same, you can ommit one of them.

function getCar(make, model, value){
  return {
    make,      // ES5 make:make,
    model,     // ES5 model:model,
    value      // ES5 value:value,
  }
}
<h2><li> <a href = 'https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes'>Classes </a></li></h2>
Classes are special functions. The class syntax has class expression and class declarations.
<h3>[1]class declarations </h3>
Use class keyword with the name of the class. Class declarations are not hoisted like function declarations. Hence, first declare class and then access it.
<h4>+++ ES6 +++</h4>
class Person {
  constructor(name, age, gender){
    this.name = name;
    this.age = age;
    this.gender = gender;
  }
  incrementAge(){
    this.age += 1;
  }
}

class Personal extends Person{
  constructor(name, age, gender, occupation, hobby){
    super(name, age, gender);
    this.occupation = occupation;
    this.hobby = hobby;
  }
  incrementAge(){
    super.incrementAge();
    this.age += 20;
    console.log(this.age);
  }
}

<h4>+++ ES5 +++</h4>
function Person (name, age, gender){
  this.name = name;
  this.age = age;
  this.gender = gender;
}
Person.prototype.incrementAge = function(){
  return this.age += 1;
}
function Personal(name, age, gender, occupation, hobby){
  Person.call(this, name, age, gender);
  this.occupation = occupation;
  this.hobby = hobby;
}
Personal.prototype = Object.create(Person.prototype);
Personal.prototype.constructor = Personal;
Personal.prototype.incrementAge = function(){
  Person.prototype.incrementAge.call(this);
  this.age += 20;
  console.log(this.age);
;}

<h3>[2]class expression</h3>
class expression can be named or unnabled. The name given to a named class expressionis local to class's body.
// unnamed
let Rectangle = class {  // class body start
  constructor(height, width){  // same as __init__ 1 constructor per class
    this.height = height;       // can use super keyword to call the super class
    this.width = width;         // constructor of the super class
  }
};
console.log(Rectangle.name);

//named
let Rectangle = class Rectangle2 {
  constructor (height, width){
    this.height = height;
    this.width = width;
  }
};
console.log(Rectangle.name);
<h2><li>Destructing assignment syntax</li></h2>
Destructuring allows us to extract values from arrays and objects(even deeply nested) and store them in variable with a more convenient syntax.
let [a,b,c,d] = [1,2,3,4];
let luke = {occupation:'jedi',father:'anakin'};
let {occupation, father} = luke; // console.log(occupation) //'jedi'


<h2><li>Template Literal / Interpolation(${name})</li></h2>
let text= `${name} said, "Hello" to me the other day.`

let text = (`cat
dog               // no need to put \n for new line
nickelodeon`
);

<h2><li> Default parameters </li></h2>
function multiply(a, b = 1) {
  return a * b;
}
<h2><li> Method definitinos </li></h2>
 //ES5
 var obj = {
     foo: foo(){ return 'bar'}
 };
 //ES6
 var obj = {    
     foo(){return 'bar'}
 }

<h2> <li>Rest parameters</li></h2>
 indefinite number of arguments
 function sum(...theArgs) {
  return theArgs.reduce((previous, current) => {
    return previous + current;
  });
}

<h2><li>Spread Syntax (...)</li></h2>
[reference] <a href='https://codeburst.io/javascript-es6-the-spread-syntax-f5c35525f754'>Medium blog by Brandon Morelli</a>
It allows an iterable to expand in places where 0+ arguments are expected.

<ul>
<h3><li>Inserting Arrays</li></h3>
* without spread syntax *
var mid = [3,4];
var arr = [1,2,mid,5,6] 
console.log(arr); // [1,2,[3,4],5,6] 

* with spread syntax *
var mid = [3,4];
var arr = [1,2,...mid,5,6] // 
console.log(arr); // [1,2,3,4,5,6] 

<h3><li>Math</li></h3>
var arr = [2,3,8,6,0]
* without spread syntax *
function max(arr){
    return Math.max.apply(null,arr);
} 

* with spread syntax *
var max = Math.max(...arr)

<h3><li>Copy an Array </li></h3>
By using spread syntax, you can copy an array without by Referencing.
* without spread syntax *
var arr = ['a', 'b', 'c'];
var arr2 = arr;
arr2.push('d')  // ['a','b','c','d'] 

* with spread syntax *
var arr = ['a', 'b', 'c'];
var arr2 = [...arr]; // ['a','b','c'] copied successfully

<h3><li> String to Array </li></h3>
var str = 'hello';
var chars = [...str]; // ['h','e','l','l','o'];
</ul>

<h2> Map</h2>
Still leaning
https://hackernoon.com/what-you-should-know-about-es6-maps-dc66af6b9a1e

<h2>others</h2>
Module Loaders
Weak set
New Library
Promises
Proxies