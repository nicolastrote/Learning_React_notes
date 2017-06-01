# Learning_React_notes
Notes during my reading of :
  Learning React
  Functional Web Development
  with React and Redux
  Alex Banks and Eve Porcello
Some usefull source for this reading:
* https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
## CHAPTER 1 - Welcome to React
### ERRATUM
http://oreilly.com/catalog/errata.csp?isbn=9781491954621 for release details.
### GIT
https://github.com/moonhighway/learning-react
### TOOLS
https://jsbin.com (online code editor similar to CodePen and JSFiddle)
### BROWSER EXTENSIONS
* react-detector is a Chrome extension
* show-me-the-react (same as precedent)
* React Developer Tools (this ONE is the BEST)
### NODE.JS
https://nodejs.org/en/download/ : for npm tool

```
$ node -v
Output: v7.3.0
```
### YARN
* It was released in 2016 by Facebook, Google, and Tilde. 
* manage their dependencies more reliably
* installing their packages
* much faster than npm
```
npm install -g yarn
```
Instead of using 
```
npm install --save [package-name]
```
you will use
```
yarn add [package-name]
```
To remove a dependency:
```
yarn remove [package-name]
```
To install all dependencies:
`yarn install` or `yarn`
An optional alternative for npm is Yarn
## CHAPTER 2 - Emerging JavaScript
### JavaScript
* Node.js et JavaScript donnent full-stack applications
* ECMA committee=> last update has many names: ECMAScript 6, ES6, ES2015, and ES6Harmony, Next is ES2017.
* Latest JavaScript features : http://kangax.github.io/compat-table/esnext/
### Declaring Variables in ES6
* VAR : var pizza = true  [retour] pizza=false;
* CONST : Connot be reset : const pizza = true [retour] pizza=false;  //Uncaught type error
* LET : lexical variable scoping
```javascript 
var topic = "JavaScript"
if (topic) {
let topic = "React"
console.log('block', topic) // React
}
console.log('global', topic) // JavaScript
```
Another area where curly braces don’t block off a variable’s scope is in for loops:
```javascript  
var div,
 container = document.getElementById('container')
 for (var i=0; i<5; i++) {
   div = document.createElement('div')
   div.onclick = function() {
     alert('This is box #' + i)
   }
 container.appendChild(div)
 }
```
La solution : 
```javascript
var div, container = document.getElementById('container')
for (let i=0; i<5; i++) {
  div = document.createElement('div')
  div.onclick = function() {
    alert('This is box #: ' + i)
  }
  container.appendChild(div)
}
```
* Template Strings
    * console.log(lastName + ", " + firstName + " " + middleName)
    * insert the variable values: console.log(`${lastName}, ${firstName} ${middleName}`)
### Default Parameters
* Languages including C++ and Python allow developers to declare default values for function arguments
```javascript
function logActivity(name="Shane McConkey", activity="skiing") {
console.log( `${name} loves ${activity}` )
}
```
### Arrow Functions
* ```var lordify = firstname => `${firstname} of Canterbury` ```
* ```var lordify = (firstName, land) => `${firstName} of ${land}` ```
### Transpiling ES6
* For compatibility with all browser ES6 code is convert to ES5 with Babel.
* You just include the browser.js file, and any scripts with type="text/babel".
### ES6 Objects and Arrays
#### Destructuring Assignement
* destructure incoming function arguments:
``` 
var sandwich = {
bread: "dutch crunch",
meat: "tuna",
cheese: "swiss",
toppings: ["lettuce", "tomato", "mustard"]
}
var {bread, meat} = sandwich
console.log(bread, meat) // dutch crunch tuna 
```
* destructured from arrays:
``` 
var [,,thirdResort] = ["Kirkwood", "Squaw", "Alpine"] 
console.log(thirdResort) // Alpine 
```
``` 
var [firstResort] = ["Kirkwood", "Squaw", "Alpine"]
console.log(firstResort) // Kirkwood 
```
### Object Literal Enhancement
* Object literal enhancement is the opposite of destructuring
``` 
var name = "Tallac"
var elevation = 9738
var funHike = {name,elevation}
console.log(funHike) // {name: "Tallac", elevation: 9738} 
``` 
* We can also create object methods with object literal enhancement or restructuring
``` 
var name = "Tallac"
var elevation = 9738
20 | Chapter 2: Emerging JavaScript
var print = function() {
console.log(`Mt. ${this.name} is ${this.elevation} feet tall`)
}
var funHike = {name,elevation,print}
funHike.print() // Mt. Tallac is 9738 feet tall 
```
* Object literal enhancement allows us to pull global variables into objects and reduces typing by making the function keyword unnecessary.
* OLD
```
var skier = {
name: name,
sound: sound,
powderYell: function() {
var yell = this.sound.toUpperCase()
console.log(`${yell} ${yell} ${yell}!!!`)
},
speed: function(mph) {
this.speed = mph
console.log('speed:', mph)
}
} ```
* NEW
```
const skier = {
name,
sound,
powderYell() {
_let_ yell = this.sound.toUpperCase()
console.log(`${yell} ${yell} ${yell}!!!`)
},
speed(mph) {
this.speed = mph
console.log('speed:', mph)
}
}
```
### The Spread Operator
The spread operator is three dots (...) for
* combine array
``` var first = ["a", "b", "c"]
var last = ["d", "e"]
var alphabet = [...first, ...last]
console.log(alphabet.join(', ')) // a,b,c,d,e,f
var [reversing] = peaks.reverse()  // can be write: var [reversing] = [...alphabet].reverse()
console.log(reversing) // f
console.log(peaks.join(', ')) //f,e,d,c,b,a
```
* A part of array
```
var alphabet = ["a", "b", "c", "d"]
var [first, ...apart] = alphabet
console.log(apart.join(", ")) // "a, b, c"
```






