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

<code>$ node -v
Output: v7.3.0</code>
### YARN
* It was released in 2016 by Facebook, Google, and Tilde. 
* manage their dependencies more reliably
* installing their packages
* much faster than npm

<code>npm install -g yarn</code>
Instead of using 

<code>npm install --save [package-name]</code> 
you will use
<code>yarn add [package-name]</code>

To remove a dependency:
<code>yarn remove [package-name]</code>

To install all dependencies:
<code>yarn install</code> or <code>yarn</code> 
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
<code> var topic = "JavaScript"
if (topic) {
let topic = "React"
console.log('block', topic) // React
}
console.log('global', topic) // JavaScript
</code>
Another area where curly braces don’t block off a variable’s scope is in for loops:
<code> var div,
 container = document.getElementById('container')
 for (var i=0; i<5; i++) {
   div = document.createElement('div')
   div.onclick = function() {
     alert('This is box #' + i)
   }
 container.appendChild(div)
 }
</code>
La solution : 
<code>
var div, container = document.getElementById('container')
for (let i=0; i<5; i++) {
div = document.createElement('div')
div.onclick = function() {
alert('This is box #: ' + i)
}
container.appendChild(div)
}
</code>
* Template Strings


