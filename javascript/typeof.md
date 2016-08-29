## Type Checking

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)

---

### Basics
```javascript
typeof ''      // string
typeof 'asdf'  // string
```
  
```javascript
typeof 37        // number
typeof Infinity  // number
typeof NaN       // number
```
  
```javascript
typeof true   // boolean
typeof false  // boolean
```
  
```javascript
typeof undefined   // undefined
typeof blah        // undefined (an undefined variable)
```

---

### Objects / Arrays
```javascript
typeof {a:1}      // object
typeof [1, 2, 4]  // object   array (see below)

var myArray = [1,2,4];
Array.isArray(myArray);  // true
```
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)
  