## Array

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
* [w3schools array sort](http://www.w3schools.com/jsref/jsref_obj_date.asp)

---

### Tips
* Effectively the same as objects except:
    - order is preserved
    - keys are automatically assigned (index)

---

### empty array

```javascript
var myArray = [];
```

---

### basic array

```javascript
var daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
// Sunday,Monday,Tuesday,Wednesday,Thursday,Friday,Saturday
```

---

### array containing objects and arrays

```javascript
var arrayOfStuff = [
    {'name' : 'value'},
    [1, 2, 3],
    true,
    'yes'
];
// [object Object],1,2,3,true,yes;
```
  
```javascript
var lng = arrayOfStuff.length;      // 4
var lng = arrayOfStuff[1].length;   // 3
```

---

### array Methods
```javascript
var wineCities = ['Napa', 'Sonoma', 'Healdsburg', 'Yountville'];
// Napa,Sonoma,Healdsburg,Yountville
```
__replace__:
```javascript
wineCities[1] = 'Calistoga';
// Napa,Calistoga,Healdsburg,Yountville
```
__add__ - end:
```javascript
wineCities[wineCities.length] = 'Sonoma';
// Napa,Calistoga,Healdsburg,Yountville,Sonoma
```
__add__ - end:
```javascript
wineCities.push('Oakville');
// Napa,Calistoga,Healdsburg,Yountville,Sonoma,Oakville
```
__add__ - middle (start before 3rd item, 0 = no items removed, items added):
```javascript
wineCities.splice(2, 0, 'St Helena', 'Rutherford');
// Napa,Calistoga,St Helena,Rutherford,Healdsburg,Yountville,Sonoma,Oakville
```
__remove__ - end:
```javascript
wineCities.pop();
// Napa,Calistoga,St Helena,Rutherford,Healdsburg,Yountville,Sonoma
```
__remove__ (start before 2nd item, 3 items removed):
```javascript
wineCities.splice(1, 3);
// Napa,Healdsburg,Yountville,Sonoma
```
