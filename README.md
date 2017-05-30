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
** console.log(lastName + ", " + firstName + " " + middleName)
** insert the variable values: console.log(`${lastName}, ${firstName} ${middleName}`)
### Default Parameters
* Languages including C++ and Python allow developers to declare default values for function arguments
```javascript
function logActivity(name="Shane McConkey", activity="skiing") {
console.log( `${name} loves ${activity}` )
}
```
