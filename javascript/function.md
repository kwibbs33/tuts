## Function

* [https://developer.mozilla.org/en-US/docs/Glossary/Function](https://developer.mozilla.org/en-US/docs/Glossary/Function)

---

### Arguments
```javascript
function speakSomething(what, howMany) {
    // check if argument is defined, and if not, provide default value
    var what = (typeof what !== 'undefined' ? what : 'Default speech');
    var howMany = (typeof howMany !== 'undefined' ? howMany : 3);

    for (var i = 0; i < howMany; i++) {
        return what + ' (' + i + ')';
    };
}

speakSomething('Hey', 2);
// Hey (0)
// Hey (1)

speakSomething('Hey');
// Hey (0)
// Hey (1)
// Hey (2)

speakSomething();
// Default speech (0)
// Default speech (1)
// Default speech (2)
```
  
```javascript
function addingMachine() {
    // initialize the total we'll be returning
    var total = 0;

    for (var i = 0; i < arguments.length; i++) {
        // grab the next number
        var number = arguments[i];

        // check the argument is a number. if so, add it to the total.
        if (typeof number === 'number')
            total += number;

    };
    // return the total
    return total;
}

addingMachine(1,2,3);
// 6

addingMachine(3,4,33);
// 40

addingMachine(3,'12',33);
// 36
```

---

### As Objects
^ same as above
```javascript
var saySomething = function(what, howMany) {
    // check if argument is defined, and if not, provide default value
    var what = (typeof what !== 'undefined' ? what : 'Default speech');
    var howMany = (typeof howMany !== 'undefined' ? howMany : 4);

    for (var i = 0; i < howMany; i++) {
        return what + ' (' + i + ')';
    };
}
```

invoke immediately (__instantiate__):
```javascript
var saySomething = function(what, howMany) {
    // code goes here
}('Yo', 2);

// Yo (0)
// Yo (1)
```

```javascript
var obj = {
    'gofunction' : function() {
        console.log('Hello');
    }
}

obj.gofunction();
// Hello
```
