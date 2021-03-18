Javascript 
==========

### 1. Variables 

-   1.1 Always use **const** or **let**

- Use **const** by default.

- Use **let** when a variable needs to be reassigned.

- Avoid using **var**

-   1.2 One variable per declaration, semicolons are required.

``` {#bkmrk-%2F%2F-bad-code-const-a-}
// Bad code
const a = 1, b = 2, c = 3; const $header = $('.header'), $footer = $('.footer'), $main = $('.main'); let car = {}, pet = {};

// Good code
const a = 1;
const b = 2;
const c = 3;
const $header = $('.header');
const $footer = $('.footer');
const $main = $('.main');
let car = {};
let pet = {};
```

-   1.3 Group all your `const`s and then group all your `let`s.

``` {#bkmrk-%2F%2F-bad-let-a%3B-const-}
// Bad
let a;
const const1 = 'const1';
let b;
const const2 = 'const2';
let c;

// Good
const const1 = 'const1';
const const2 = 'const2';
let a;
let b;
let c;
```

-   1.4 Assign variables where you **need** them

``` {#bkmrk-%2F%2F-bad---unnecessary}
// bad - unnecessary function call
function checkName(hasName) {
  const name = getName();
  
  if (hasName === 'test') {
    return false;
  }
  
  if (name === 'test') {
    this.setName('');
    return false;
  }
  
  return name;
}
// good
function checkName(hasName) {
  if (hasName === 'test') {
    return false;
  }
  
  const name = getName();
  if (name === 'test') {
    this.setName('');
    return false;
  }
  
  return name;
}
```

### 2. jQuery 

-   jQuery object must be cached and have prefix \`\$\`.

``` {#bkmrk-%2F%2F-bad-const-sidebar}
// Bad
const sidebar = $('.sidebar');
$('.popup').show();
...
$('.popup').show();

// Good
const $sidebar = $('.sidebar');
const $popup = $('.popup');
$popup.hide();
...
$popup.show();
```

 

### 3. String 

- Use single quotes, not double quotes.

``` {#bkmrk-%2F%2F-bad-let-directive}
// Bad
let directive = "No identification of self or mission.";
let saying = 'Say it ain\u0027t so.';

// Good
let directive = 'No identification of self or mission.';
let saying = `Say it ain't so`;
```

- Use template strings instead of concatenation.

``` {#bkmrk-%2F%2F-bad-function-sayh}
// Bad
function sayHi(name) {
    return 'Hi ' + name + ' , how are you ?';
}

// Good
function sayHi(name) {
    return `Hi ${name}, how are you ?`;
}
```

 

### 4. Naming  

- Meaningful names, prefer camelCase, avoid underscores.

``` {#bkmrk-%2F%2F-bade-const-a-%3D-20}
// Bade
const a = 20;
const nErr = 'number error';
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';
this._firstName = 'Panda';

// Good
const age = 20;
const numErrors = 'number error';
this.firstName = 'Panda';
```

 

- Use ALL\_UPPERCASE when naming constant variables.

``` {#bkmrk-%2F%2F-bad-const-pi-%3D-3.}
// Bad
const pi = 3.1416;
const logo_name = 'Sunbytes';

// Good
const PI = 3.1416;
const LOG_NAME = 'Sunbytes';
```

 

- Use
[camelCase]([https://eslint.org/docs/rules/camelcase.html](https://eslint.org/docs/rules/camelcase.html))
when naming objects, functions, and instances.

``` {#bkmrk-%2F%2F-bad-const-newobje}
// Bad
const NEWObject = {};
const my_function = () => {};
const NewPerson = new PerSon();

// Good
const newObject = {};
const myFunction = () => {};
const newPerson = new Person();
```

 

- Use
[PascalCase]([https://eslint.org/docs/rules/new-cap.html](https://eslint.org/docs/rules/new-cap.html))
only when naming constructors or classes.

``` {#bkmrk-%2F%2F-bad-function-pet%28}
// Bad
function pet(options) {
    this.name = options.name;
}

const kiki = new pet({
    name: 'Ki Ki',
});

// Good
class Pet {
  constructor(options) {
    this.name = options.name;
  }
}

const kiki = new Pet({
    name: 'Ki Ki',
});
```

 

- Don't save references to \`this\`. Use arrow functions or [Function
bind]([https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)).

``` {#bkmrk-%2F%2F-bad-function-show}
// Bad
function showPlace() {
  const that = this;
  return function () {
    console.log(that);
  }
}

// Good
function showPlace() {
  return () => {
    console.log(this);
  }
}
```

 

### 5. Whitespace  

Bad code

``` {#bkmrk-const-y%3Dx%2B5%3B-functio}
const y=x+5;
function getContent(){
    ...
}
    
function getContent( options ) {
    ...
}
    
$button.on('click',{
    ...
})
```

Good code

``` {#bkmrk-const-y-%3D-x-%2B-5%3B-fun}
const y = x + 5;
function getContent() {
    ...
}
    
function getContent(options) {
    ...
}
    
$button.on('click', {
    ...
})
```

### 6. End of file (EOF), end of object declaration (JSON)  

Bad code

``` {#bkmrk-import-%7B-es6-%7D-from-}
import { es6 } from './javascript';
    ...
export es6;
```

Good code

``` {#bkmrk-import-%7B-es6-%7D-from--0}
import { es6 } from './javascript';
    ...
export es6;↵
```

- End json properties with a single comma\
\
Bad code

``` {#bkmrk-const-object-%3D-%7B-nam}
const object = {
  name: 'Bob',
  age: 20
}
```

Good code

``` {#bkmrk-const-object-%3D-%7B-nam-0}
const object = {
  name: 'Bob',
  age: 20,
}
```

  Css  
===

### 1. Prefixing  

- To minimise conflict potential all

- Example: Wordpress plugin WooCommerce use classes \`.woocommerce-\`

### 2. Class name  

- Use a more traditional [BEM](http://getbem.com/naming/) approach to
naming classes.

- Document: [http://getbem.com](http://getbem.com/)

- \*\***Block**\*\*: being independent allows for their re-use\
- \*\***Element**\*\*: A constituent part of a block that can not be
used outside of it.\
- \*\***Modifier**\*\*: Flags on blocks or elements. Use them to change
appearance or behaviour.

- Example:

- modifier: \`.woocommerce-loop-product\_sale\`\
- element: \`.woocommerce-loop-product\_\_link\`\
- element: \`.woocommerce-loop-product\_\_title\`\
- element: \`.woocommerce-loop-product\_\_price\`\
- element: \`.woocommerce-loop-product\_\_rating\`\
- element: \`.woocommerce-loop-product\_\_button-add-to-cart\`\
- modifier: \`.woocommerce-loop-product\_\_button-add-to-cart\_added\`

Bad code

``` {#bkmrk-datasetlist%2C-dataset}
datasetlist,
dataset_list,
datasetList
```

good code

``` {#bkmrk-dataset-list}
dataset-list
```

- Choose semantic names.

- Choosing great variable names.

### 3. Rules  

- Avoid the \`\*\` wildcard selector.

- Do not use external link (google font, css of framework, ...).

- Use display: flex instead of float and display: inline-block.

- Avoid extra selectors.

Bad code:

``` {#bkmrk-body-%23container-.som}
body #container .someclass ul li {....}
```

Good code:

``` {#bkmrk-.someclass-li-%7B...%7D}
.someclass li {...}
```

- Use only lowercase.

Bad code:

``` {#bkmrk-color%3A-%23acefd1%3B-disp}
color: #ACEFD1;
display: BLOCK;
<DIV></DIV>
```

Good code:

``` {#bkmrk-color%3A-%23acefd1%3B-disp-0}
    color: #acefd1;
    display: block;
    <div></div>
```

- Always end in a semicolon.

Bad code:

``` {#bkmrk-color%3A-%23fff}
color: #fff
```

Good code:

``` {#bkmrk-color%3A-%23fff%3B}
color: #fff;
```

- Make it \`readable\`: easier to re-use, maintain and develop in the
future

Bad code

``` {#bkmrk-.example%7Bbackground%3A}
.example{background:red;padding:2em;border:1px solid black;}
```

Good code

``` {#bkmrk-.example-%7B-backgroun}
.example {
  background: red;
  padding: 2em;
  border: 1px solid black;
}
```

- Do not put “0”s in front of values or lengths between -1 and 1.

Bad code:

``` {#bkmrk-font-size%3A-0.8em%3B}
font-size: 0.8em;
```

Good code:

``` {#bkmrk-font-size%3A-.8em%3B}
font-size: .8em;
```

- Avoid units on zero values.

Bad code:

``` {#bkmrk-margin%3A-0px-0px-2px-}
margin: 0px 0px 2px 0px;
```

Good code:

``` {#bkmrk-margin%3A-0-0-20px-0%3B}
margin: 0 0 20px 0;
```

- Avoid using tag names with ID or class name.

Bad code:

``` {#bkmrk-ul.example-%7B%7D-p%23cont}
ul.example {}
p#container {}
```

Good code:

``` {#bkmrk-.example-%7B%7D-%23contain}
.example {}
#container {}
```

- Avoid use IDs in selectors.

Bad code:

``` {#bkmrk-btn%23download}
btn#download
```

Good code:

``` {#bkmrk-.download}
.download
```

 

- Avoid duplicate properties.

- Caps lock for meaning, text-transform for style \`***text-transform:
uppercase***\`.

- Use absolute \`position\` only when you have to, \`no choice\`.

### 4. Fonts 

- Always specify a fallback generic font.

Bad code:

``` {#bkmrk-font-family%3A-%22helvet}
font-family: "Helvetica Neue";
```

Good code:

``` {#bkmrk-font-family%3A-%22helvet-0}
font-family: "Helvetica Neue", Tahoma, sans-serif;
```

\
- Font names with spaces must surrounded by double-quotes.

Bad code:

``` {#bkmrk-font-family%3A-helveti}
font-family: Helvetica Neue, Tahoma, sans-serif;
```

Good code:

``` {#bkmrk-font-family%3A-%22helvet-1}
font-family: "Helvetica Neue", Tahoma, sans-serif;
```

\
- Font weights should be defined using numeric values.

Bad code:

``` {#bkmrk-font-weight%3A-bold%3B}
font-weight: bold;
```

 Good code:

``` {#bkmrk-font-weight%3A-700%3B}
font-weight: 700;
```

### 5. Color 

- All color values are written in the hexadecimal format and using
lowercase.

 Bad code:

``` {#bkmrk-color%3A-%23acefd1%3B-colo}
color: #ACEFD1;
color: white;
```

 Good code:

``` {#bkmrk-color%3A-%23acefd1%3B-colo-0}
color: #acefd1;
color: #fff;
```

- Use 3 character hexadecimal notation where possible.

Bad code:

``` {#bkmrk-color%3A-%23eebbcc%3B-colo}
color: #eebbcc;
color: #ffffff;
```

Good code:

``` {#bkmrk-color%3A-%23ebc%3B-color%3A-}
color: #ebc;
color: #fff;
```

- If you need transparency, use rgba.

Good code:

``` {#bkmrk-color%3A-rgba%280%2C-0%2C-0%2C}
 color: rgba(0, 0, 0, .6);
 bacground: rgba(0, 0, 0, .6);
```

### 6. Shorthand properties 

- Use shorthand properties where possible

Bad code:

``` {#bkmrk-img-%7B-margin-top%3A-5p}
img {
 margin-top: 5px;
 margin-right: 10px;
 margin-bottom: 5px;
 margin-left: 10px;
}

button {
 padding: 0 0 0 20px;
}
```

Good code:

``` {#bkmrk-img-%7B-margin%3A-5px-10}
img {
 margin: 5px 10px;
}

button {
 padding-left: 20px;
}
```

### 7. Property ordering 

- Place @extends and @includes at the top of your declaration list.

- Place concatenate selectors second.

- Place pseudo states and elements third.

- Place nested selectors last.

- Place pseudo-class/ nested selectors after an empty line.

Good code:

``` {#bkmrk-.element-%7B-%40extend-.}
.element {
  @extend .other-element;
  background: #000;
 
  &:hover {
   background: #333;
  }
 }
```

### 8. Units 

- Use pixel (px) unit – corresponds to actual pixels on the screen – for
margin, padding

- Use rem (rem) unit – corresponds to the specified point size of the
font – for text

- Use percentage (%) unit for full width content

- Use unitless values when you can. Favor rem if you use relative units.
Prefer seconds over milliseconds.

Bad code:

``` {#bkmrk-div-%7B-margin%3A-0px%3B-f}
div {
 margin: 0px;
 font-size: .9em;
 line-height: 22px;
 transition: 500ms;
}
```

Good code:

``` {#bkmrk-div-%7B-margin%3A-0%3B-fon}
div {
 margin: 0; 
 font-size: 1rem;
 line-height: 1.5;
 transition: .5s;
}
```

### 9. Combine CSS elements  

Bad code:

``` {#bkmrk-h1-%7B-font-family%3A-ve}
h1 {
 font-family: verdana; 
 color: #e1e1e1;
}

h2 {
 font-family: verdana; 
 color: #e1e1e1;
}
```

Good code:

``` {#bkmrk-h1%2C-h2-%7B-font-family}
h1,
h2 {
 font-family: verdana;
 color: #e1e1e1;
}
```

### 10. Caniuse is your friend  

Use caniuse or a similar service to check if what you are using is
widely supported, if it needs prefixes, or if it causes any bugs in a
certain platform. ([https://caniuse.com/](https://caniuse.com/))

### 11. CSS animation with transform  

Bad code:

``` {#bkmrk-.ball-%7B-left%3A-50px%3B-}
.ball {
 left: 50px;
 transition: 0.4s ease-out;
}

.ball.slide-out {
 left: 500px;
}
```

Good code:

``` {#bkmrk-.ball-%7B-left%3A-50px%3B--0}
.ball {
 left: 50px;
 transition: left 0.4s ease-out;
}

.ball.slide-out {
 transform: translateX(450px);
}
```

[https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/)

### 12. Overriding 

Bad code:

``` {#bkmrk-li-%7B-visibility%3A-hid}
li {
 visibility: hidden;
}

li:first-child {
 visibility: visible;
}
```

Good code:

``` {#bkmrk-li-%2B-li-%7B-visibility}
li + li {
 visibility: hidden;
}
```

### 13. Inheritance  

- Do not duplicate style declarations that can be inherited.

Bad code:

``` {#bkmrk-div-h1%2C-div-p-%7B-text}
div h1, 
div p {
  text-shadow: 0 1px 0 #fff;
}
```

Good code:

``` {#bkmrk-div-%7B-text-shadow%3A-0}
div {
  text-shadow: 0 1px 0 #fff;
}
```

### 14. Language 

- Prefer English over math

Bad code:

``` {#bkmrk-%3Anth-child%282n-%2B-1%29-%7B}
:nth-child(2n + 1) {
  transform: rotate(360deg);
}
```

Good code:

``` {#bkmrk-%3Anth-child%28odd%29-%7B-tr}
:nth-child(odd) {
  transform: rotate(360deg);
}
```

### 15. Modularize styles for reuse  

Bad code:

``` {#bkmrk-.news-%7B-background%3A-}
.news {
  background: #eee;
  border: 1px solid #ccc;
  border-radius: 6px;
}
.events {
  background: #eee;
  border: 1px solid #ccc;
  border-radius: 6px;
}
```

Good code:

``` {#bkmrk-.feat-box-%7B-backgrou}
.feat-box {
  background: #eee;
  border: 1px solid #ccc;
  border-radius: 6px;
}
```

### 16. Comment 

- One of the best practices for writing CSS is placing a comment on each
group of elements.

- Comments should be used liberally to explain anything that may be
unclear at first glance, especially IE workarounds or hacks.

- Explain code as needed where possible.

### 17. Understand the difference between block vs inline elements 

- List of elements are inline: span, a, strong, em, img, br, input,
abbr, acronym

- List of elements are block: div, h1 … h6, p, ul, li, table,
blockquote, pre, form

### 18. Hack  

- Avoid using as little browser-specific hacks if at all possible.

- Avoid user agent detection as well as CSS “hack” -- try a different
approach first.

### 19. Validate our CSS and XHTML with the W3C validator  

https://jigsaw.w3.org/css-validator/

### 20. Avoid long stylesheets {#bkmrk-20.-avoid-long-style}

- When you break your styles into smaller and more focused stylesheets
it’s easier to document them.

- You can also save time by not having to document what becomes
self-explanatory.

``` {#bkmrk-header.scss-button.s}
 header.scss
 button.scss
 main.scss
 form.scss
```

### 21. Document CSS with a style guide in mind {#bkmrk-21.-document-css-wit}

- Some simple comments are all it takes to organize a style sheet and
make it more accessible to your colleagues or your future self.

- Style guide can help you determine a good structure for your CSS
because to create one you will need to distinguish between:

-   the baseline styles that define the look and feel of your
    application.
-   the customizations that are done to specific components.
-   the customizations that are done to specific pages.

### 22. Do not repeat yourself {#bkmrk-22.-do-not-repeat-yo}

Bad code:

``` {#bkmrk-.message-error-%7B-bor}
.message-error {

  border: 1px solid red;

  color: red;

  background: #fff;

  font-weight: bold;

}

.message-ok {

  border: 1px solid green;

  color: green;

  background: #fff;

  font-weight: bold;

}

.message-warn {

  border: 1px solid orange;

  color: orange;

  background: #fff;

  font-weight: bold;

}
```

Good code:

``` {#bkmrk-.message-error%2C-.mes}
.message-error,

.message-ok,

.message-warn {

  border: 1px solid;

  font-weight: bold;

  background: #fff;

}

.message-error {

  border-color: red;

  color: red;

}

.message-ok {

  border-color: green;

  color: green;

}

.message-warn {

  border-color: orange;

  color: orange;

}
```

 

 

 

 

 

* * * * * 
