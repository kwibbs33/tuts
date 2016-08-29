## For Loops

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)

---

### For
(Very common to loop over arrays)

```javascript
var pageNames = ['Home', 'About', 'Contact'];
var thisPage = 'About';

for (var i = 0; i < pageNames.length; i++) {
    var currentPageTitle = pageNames[i];

    if (thisPage === currentPageTitle)
        console.log('We ARE here: ' + currentPageTitle);
    else
        console.log('We are not here: ' + currentPageTitle);
}

// We are not here: Home
// We ARE here: About
// We are not here: Contact
```

---

### For Enumerative
(Better to use with objects, not arrays)

```javascript
var pages = {
    'first' : 'Home',
    'second' : 'About',
    'third' : 'Contact'
};

for (var p in pages) {
    if (pages.hasOwnProperty(p)) {
        console.log(p + ' is ' + pages[p]);
    }
}

// first is Home
// second is About
// third is Contact

```

---

### While
(When you don't know how many times to iterate over, there's no particular counter or you don't know the end point. Be careful not to create infinite loop.)

```javascript
var myArray = [true, true, true, false, true, true];

var myItem = null;
while (myItem !== false) {
    document.write('myArray has ' + myArray.length + ' items now. Loop until we pop a false.');
    myItem = myArray.pop();
}

// myArray has 6 items now. Loop until we pop a false.
// myArray has 5 items now. Loop until we pop a false.
// myArray has 4 items now. Loop until we pop a false.
```