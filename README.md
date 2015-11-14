# Intro-To-Javascript

## Why JavaScript is Weird:

### Basics:

#### Data types:
 - Primatives: String, nums, booleans, null, undefined
 - Objects

| Ruby          | JavaScript    | Explanation |
| ------------- |:-------------:|:------------------------------------:|
|  "4" == 4 // false   | "4" == 4 // true | == is a type coersive, and a loose equality checker |
| falsys: nil, false    | falsys: null, undefined, 0, NaN, ""  | null == false, but undefined != false |
| "My name is #{name}." | "My name is " + name + "." | JS does not have string interpolation |
| p "this is ruby" | console.log("this is javascript") | |
| [1,2].push(4) // [1,2,4] | [1,2].push(4) // 3 | returns the length of the newly created array |
| a = 0 | var a = 0 | |
| a += 1 // returns 1, a == 1 | a++ // returns 0, a === 1 | (variable)++ adds one but returns the variable before |
| | ++a // returns 2, a === 2 | ++(variable) adds one to the variable then returns it |

#### Variables

Declaring a Variable:
```javascript
 $ var firstName = "Jane"

 $ var lastName = "Austen"

 $ var name = firstName + " " + lastName

 $ var names; // creates a variable to be defined. If called you get undefined

 $ var names = [];
 ```

#### Functions

Declaring a Function:

```javascript
 $ var combineName = function(firstName, lastName){
     return(firstName.concat(" ", lastName))
   }

 $ function sayHello(){
     return "Hello, World."
   }

 $ var x = (function(){
    var p = "password"
    return function(password){
      return p === password
    }
  })()    // IIFE -- immediately invoked function
  // cannot access var p from the console. It's more protected!
```
Calling a Function:
```javascript
 $ sayHello // function (){ return "Hello, World." }

 $ sayHello() // "Hello, World."

 $ x() // false

 $ x("password") // true
```
#### Objects:

Declaring Objects
```javascript
var ironMan = {
  firstName: "Tony",
  lastName: "Stark",
  company: "Stark Industries",
  greeting: function(name){
    return "Hello " + name
  }
}

ironMan.car = { make: "Tesla", year: 2015}

```

Calling Objects:

```javascript
ironMan.firstName // "Tony"

ironMan["company"] // "Stark Industries"

ironMan.greeting // function (name){
    return "Hello " + name
  }

ironMan.greeting("Stephanie") // "Hello Stephanie"

ironMan.car // Object {make: "Tesla", year: 2015}
ironMan.car.make // "Tesla"

```

#### Classes

 - by declaring with a capital letter, JS knows it's a class
```javascript

var Person = function(firstName, lastName, gender){
  this.firstName = firstName
  this.lastName = lastName
  this.gender = gender
}

Person.prototype.greeting = function(){
  return "Hello, my name is " + this.firstName
}

var jane = new Person("Jane", "Austen", "F")

jane.greeting() // "Hello, my name is Jane"
jane.profession = "Author"

var tony = new Person("Tony", "Stark", "M")
tony.profession // undefined
jane.profession // "Author"

```

#### What is this?

this is the object you are acting upon.

```javascript

var obj = {
  funct: function(){return this},
  variable: "x"
}

obj.funct() // Object {variable: "x"}

var Person = function(name){
  this.name = name;
  this.defineThis = this
}

var tony = new Person("Tony")
tony.defineThis // Person {name: "Tony", defineThis: Person}

var OtherTypeOfPerson = function(name){
  this.name = name;
  this.defineThis = function(){return this}
}

var jane = new OtherTypeOfPerson("Jane")
jane.defineThis() // Person {name: "Jane"}

```
##### This Tips:

use debugger in you code then console.log(this)

this ~ self

declare this to a variable so it cane be used later when this changes.



