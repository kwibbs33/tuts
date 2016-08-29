## Comparisons

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)

---

### equality / inequality
(of the same type)
```javascript
1 == 1;            // true
1 == '1';          // true
0 == false;        // true
0 == null;         // false
0 == undefined;    // false
null == undefined; // true
1 != 2;            // true
1 != '1';          // false
1 != false;        // true
```
  
### strict equality / inequality
(identity with no type conversion)
```javascript
3 === 3;            // true
3 === '3';          // false
0 === false;        // false
0 === null;         // false
0 === undefined;    // false
null === undefined; // false
3 !== 3;            // false
3 !== '3';          // true
3 !== 4;            // true
```
  
### logical operators
```javascript
animal1 === 'monkey' && animal2 === 'bear';     // true
animal1 === 'monkey' || animal2 === 'bear';     // true
!(animal1 === 'monkey' && animal2 === 'bear');  // false
```
