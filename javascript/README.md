### Tips
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
* [http://www.w3schools.com/jsref/default.asp](http://www.w3schools.com/jsref/default.asp)

* [Cheat Sheet mouseover/links](http://overapi.com/javascript)
* [Cheat Sheet](https://www.cheatography.com/davechild/cheat-sheets/javascript/)

---

### Best Practice
* __camelCase__ is standard for variables and functions
* __UpperCamelCase__ for built-in objects (Date, Math, etc)
* open __curly braces__ on same line
* define functions before you call them (you don't have to, but good practice)

---

### Tools
__Minify__ [Google Closure Compiler](http://closure-compiler.appspot.com) - Advanced

__Code Quality__ [JSLint](http://jslint.com)
super picky... check options:
* use browser
* tolerate type confusion
* tolerate 'use strict'
* tolerate messy white spice

---

### MDN additional info

* [built-in Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)

* [Expressions and Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)

---

### Info
* [String](string.md)
* [Numbers/Math/Arithmetic](math.md)
* [Date](date.md)
  
* [Comparisons !=](comparisons.md)
* [Switch](switch.md)
* [Ternary operators ?:](ternary.md)
  
* [Typeof](typeof.md)
* [RegEx](regex.md)
  
* [Object & Prototype](object.md)
* [Array](array.md)
  
* [For/Do/While](loop.md)
  
* [Function](function.md)

---

### Return
```javascript
return;        // stop the function from moving foward
return false;  // stop default browser behavior
```

---

### Undefined & null
__Null__ is for an object, __Undefined__ is for a property, method or variable
```
var myVariable;

console.log(myVariable);
// undefined

console.log(typeof(myVariable));
// "undefined"
```
  

To be null, your object has to be defined. If your object is not defined, and you test to see whether it is null, since it is not defined, it cannot test, and will throw an error.
  
```javascript
if (myObject !== null && typeof(myObject) !== 'undefined') {
	// if myObject is undefined, it cannot test for null, and will throw an error
}

if (typeof(myObject) !== 'undefined' && myObject !== null) {
	// code handling myObject')
}
```

---

### DOM

__document__: web page
__object__:   pieces
__model__:    agreed-upon set of terms/standards

to describe and interact with any page

---

### Modernizr
[http://www.modernizr.com](http://www.modernizr.com)
* feature __detection__ of HTML5 and CSS3 tags
* must load before body tag
  
you will have a Modernizer object to check what exists in user's browser
```javascript
if (Modernizr.video) {
    // yes - use HTML5 video
} else {
    // maybe replace with Flash video
}
```

```javascript
if (!Modernizr.svg) {
    $('img[src$=".svg"]').each(function() {
        $(this).attr('src', $(this).attr('src').replace('.svg', '.png'));
    });
}
```
