### Is JavaScript OOP?
It is prototype based language. In ES6, class was implemented, but that is to implement prototype-based classes.

### What is prototype?
Every object has prototype which makes inheritance possible. 

### What is syntactic sugar in ES6.
構文Sugar

### <a href='https://www.youtube.com/watch?v=PFmuCDHHpwk'>What is OOP?</a>
A programing model based around the idea of objects
https://www.quora.com/What-do-the-4-principles-of-OOP-mean

(1)Abstraction
Abstraction means hiding unessential details from user. And providing only essential information.
Data Abstraction: suppose you wanna make a call to your mom. What you need?
Just valid number!
To make a call, you never need to know the background details how calling is being done. (Like connecting to network whichever your mom is using either airtel or idea etc)

(2)Encapsulation
 In technical terms, it means wrapping up of data and code in to a single unit(i.e Class) and also protecting the data from outside world. There is also another term related with encapsulation is data hiding. Data hiding means hiding the data from world. Data can not be accessed directly.

(3)Inheritance
Inheriting the properties of super class in subclass. Basically subclass is more specialized one and it provides re usability.
Inheritance: Suppose you are using android phone version suppose lollypop. So basically lollypop version has inherited all functionality of previous versions i.e kitkat

(4)Polymorphism
It means having same name but different functionality. In technical terms, function overloading, function overriding etc
Now let see how polymorphism is implemented in your mobile.Every mobile has inbuilt camera. But still there are another apps which let us take photos like Retrica.
Retrica which has different functionality but does the same work(clicking photos).


## What is closure?
A closure is a function that makes use of variables defined in outer functions that have previously returned.

## What is callback?
functions that can be passed as argument. When using, check typeof myFunc === 'function' because you forget what is this arguement is 
(1) Event Handling => callback
(2) AJAX
(3) Array

Asyncroness = non-blocking = single threded;

## <a href='https://developer.mozilla.org/en-US/docs/Glossary/Mutable'>Mutable/immutable:</a>
Mutable: Can Change Object and Array (Pass by Ref) Referring the same memory.
Immutable: String, Numbers (Pass by Val) Passing the value instead of memory location.

<a href='https://www.sitepoint.com/event-bubbling-javascript/'##>Event bubbling</a>
Nested tag. When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.
stopPropagation()

## primitives
Not object and has no method.
type: undefined, null, boolean, string and number

## Promise
A Promise is an object representing the eventual completion or failure of an asynchronous operation.

## Compiler/Interpreter
JS is interpreted language. C is Compiler

##<a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions'>Regular Expression</a>
Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. 

splice and slice
slice create new array

how to delete object property
http://perfectionkills.com/understanding-delete/
delete only returns false when a property can not be deleted    
var myObject = {
    "ircEvent": "PRIVMSG",
    "method": "newURI",
    "regex": "^http://.*"
};
delete myObject.regex;

## function declarations and function expressions and self invoking function
<ol>
<li> function expression</li>
https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/
function func(ele){  // function declarations
    return
}
The function name is visible within it’s scope and the scope of it’s parent (which is good because otherwise it would be unreachable)
Officially prohibited within non-function blocks such as (if statement)

<li> function declaration</li>
const func = () => {} // function declaration
Functions defined via Functions Expressions can be named or anonymous. Does not start with function

<li> self invoking function</li>
function expression will execute automatically if the execution is followed by (). Can't self invoke function declarations
(function () {
  var x = "Hello!!";      // I will invoke myself
})();
</ol>
### Application Programming Interfaces (APIs)

###Differences between ES5 and ES6
<ol>
<li>Fat Arrow Functions</li>
const example = (arg) => {};

<li> Default parameters </li>
function multiply(a, b = 1) {
  return a * b;
}
<li> Method definitinos </li>
 //ES5
 var obj = {
     foo: foo(){ return 'bar'}
 };
 //ES6
 var obj = {    
     foo(){return 'bar'}
 }

 <li>rest parameters</li>
 indefinite number of arguments
 function sum(...theArgs) {
  return theArgs.reduce((previous, current) => {
    return previous + current;
  });
}
(5)
