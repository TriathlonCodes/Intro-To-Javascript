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

 $ var firstName = "Jane"

 $ var lastName = "Austen"

 $ var name = firstName + " " + lastName

 $ var names; // creates a variable to be defined. If called you get undefined

 $ var names = [];

#### Functions

Declaring a Function:

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

Calling a Function:

 $ sayHello // function (){ return "Hello, World." }

 $ sayHello() // "Hello, World."

 $ x() // false

 $ x("password") // true

#### Objects:
