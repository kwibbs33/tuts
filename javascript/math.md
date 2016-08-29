## Numbers/Math/Arithmetic

* [w3schools numbers info](http://www.w3schools.com/js/js_numbers.asp)

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)

---

### Numbers

string to number:
```javascript
x = "10";
Number(x);       // 10

x = "10.33";
Number(x);       // 10.33

x = "10 20";
Number(x);       // NaN

x = true;
Number(x);       // 1

x = false;     
Number(x);       // 0

x = new Date();
Number(x);       // 1404568027739


x = "10.33";
parseInt(x);       // 10
```

number to string:
```javascript
x = 10;
x.toString();       // 10
```
  
__NaN__ is not a number:
```javascript
var x = 100 / 'Apple';    // NaN

var x = 100 / '10';       // 10

var x = Number('10');
if ( !isNaN(x) ) {
    console.log('It IS a number');
}
// It IS a number
```

---

### Math

```javascript
Math.round(12.6);       // 13
Math.round(12.2);       // 12

Math.ceil(6.2);       // 7

Math.floor(4.7);       // 4

var biggest = Math.max(a,b,c);
var smallest = Math.min(a,b,c);
```
  
__Math.random()__ = integer between 0 and 1:
```javascript
// random number 0 to 10
Math.floor(Math.random() * 11);
```
---

### Arithmetic
```javascript
1 + 2;            // 3
true + 1;         // 2
5 + 'foo';        // 5foo
'foo' + false;    // foofalse
5 * 'foo';        // NaN
```
  
remainder:
```javascript
12 % 5;    // 2
12 % 2;    // 0
```
  
increment:
```javascript
var counter = 0;    // 0
counter++;          // 1
counter += 5;       // 6
counter--;          // 5
counter -= 3;       // 2
counter *= 4;       // 8
counter /= 2;       // 4
```
