## Object

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
* [http://javascriptissexy.com/javascript-objects-in-detail](http://javascriptissexy.com/javascript-objects-in-detail)

---

### Tips
* Unordered list of 5 basic data types: __Number, String, Boolean, Undefined, and Null__
* can also contain: __Arrays, Objects__
* good for info when not worried about indexes
* __parent.child__ and __parent['child']__ are same

---

### empty object

```javascript
var emptyObject = {};
```

---

### basic object

```javascript
var animal = { 'color' : 'black' , 'deadly' : false , 'maxOffspring' : 5 };

/*
animal = {
    "color": "black",
    "deadly": false,
    "maxOffspring": 5
}
*/
```

---

### add / delete
__add__:
```javascript
animal['whereItLives'] = 'in a tree';
```
  
__delete__:
```javascript
delete animal['color'];

/*
animal = {
    "deadly": false,
    "maxOffspring": 5,
    "whereItLives": "in a tree"
}
*/
```
  
---

### associating Behaviors with objects
```javascript
for (var eachItem in animal) {
    document.write(eachItem);
}

// deadlymaxOffspringwhereItLives
```
  

```javascript
// create objects
var player1 = { name: 'Fred', score: 10000, rank: 1 };
var player2 = { name: 'Sam', score: 100, rank: 5 };

// associate behavior with objects
function playerDetails() {
    // display info about each player
    document.write(this.name + ' has a rank of: ' + this.rank + ' and a score of: ' + this.score);
}

// create "logDetails" method of objects and associate function with objects
player1.logDetails = playerDetails;
player2.logDetails = playerDetails;

// call function
player1.logDetails();

// Fred has a rank of: 1 and a score of: 10000
```
  
---

### Prototypes
* every object has a prototype property
* using multiple objects that share the same description
* (closest thing to Object Oriented Programming and classes that javascript has)
  
```javascript
// create constructor function to make new objects (UpperCamelCase)
function Player(n,s,r) {
    this.name = n;
    this.score = s;
    this.rank = r;
}

// use prototype to tie new functions to Player object with logInfo method
Player.prototype.logInfo = function() {
    console.log('I am', this.name);
}
Player.prototype.promote = function() {
    this.rank++;
    console.log('My new rank is', this.rank);
}

// create variable from the constructor
var fred = new Player("Fred", 10000, 5);

fred.logInfo();  // I am Fred
fred.promote();  // My new rank is 6

var bob = new Player("Bob", 50, 1);
bob.logInfo();  // I am Bob
bob.promote();  // My new rank is 2
```
