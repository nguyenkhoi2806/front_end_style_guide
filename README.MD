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

  
