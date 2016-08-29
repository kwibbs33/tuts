## Object

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/regexp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/regexp)
* [http://www.w3schools.com/jsref/jsref_obj_regexp.asp](http://www.w3schools.com/jsref/jsref_obj_regexp.asp)

---

```javascript
var string1 = 'This is the longest string in this sentence ever.';
var string2 = 'This is a shortest string ever';
var string3 = 'Is this the thing which is the string?';
var string4 = 'This is the thing in the string';
```
  
### basic patterns

```javascript
var regex = /this/;

regex.test(string1);    // true
regex.test(string2);    // false
regex.test(string3);    // true
regex.test(string4);    // false
```
  
```javascript
var regex = /this/i;         // i case-insensitive
          = /thi./i;         // . any character
          = /he..o/;         // . any char
          = /^thing/;        // ^ at the start
          = /thin$/;         // $ at the end
          = /this/g;         // g global - all instances
          = /hello|goodbye/; // either | or

          = /\bthi/;         // \b word boundary ('thi' starts a word)
          = /ing\b/;         // \b word boundary ('ing' ends a word)

          = /[cld]ope/;      // [] range of chars (cope, lope, dope)
          = /[^cld]ope/;     // [^] NOT any range of chars (rope, nope)

          = /hel+o/;         // + prev character once or more (helo, hello, hellllllllo, etc)
          = /hel*o/;         // * prev char zero or more (heo, helo, helllo, hellllllllllo, etc)
          = /hel?o/;         // ? prev char zero or one (heo, helo)
          = /[0-9]{4};       // {} exact number of chars (4 numbers 0-9)
          = /[0-9]{4,10};    // {} range of chars (4-10 numbers 0-9)
```

```javascript
var regEx = new RegExp('th', 'ig');
string1.replace(regEx, 'TH');

// That is the longest string in that sentence ever.
// That is a shortest string ever
// Is that the thing which is the string?
// That is the thing in the string
```
  
### complex patterns
[common patterns](http://geniuscarrier.com/common-regular-expressions-in-javascript)
```javascript
/^[a-z0-9_-]{3,16}$/          // username
/^[a-z0-9_-]{6,18}$/          // password
/^[0-9]{5}(?:-[0-9]{4})?$/    // zip code
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/    // url
```

  
