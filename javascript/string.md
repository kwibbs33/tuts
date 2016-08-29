## String

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

---

```javascript
var longString = 'This is a very long string which needs ' +
                 'to wrap across multiple lines because ' +
                 'otherwise my code is unreadable.';

var longString = 'This is a very long string which needs \
to wrap across multiple lines because \
otherwise my code is unreadable.';
```

---

### string Methods
```javascript
var phrase = 'This is a simple phrase though';
```
  
__length__:
```javascript
var lng = phrase.length;
// 30
```
  
__split()__ forms an array:
```javascript
var words = phrase.split(' ');
// [This,is,a,simple,phrase,though]
```
  
__indexOf()__ & __lastIndexOf()__ index of occurrence & last occurence (returns -1 if not found):
```javascript
var position = phrase.indexOf('simple');
// 10
var position = phrase.lastIndexOf('p');
// 17

var occurrence = phrase.indexOf('whatsup') == -1 ? 'no' : 'yes';
// no
var nope = phrase.indexOf('whatsup') == -1;
// true
```

__search()__ results same as indexOf(), but can take much more powerful search values (regex)
  
__replace()__ (/g for global, /i for case-insensitive, [regex](regex.md) for multiples):
```javascript
phrase.replace('th', 'TH');
// This is a simple phrase THough

phrase.replace(/th/i, 'TH');
// THis is a simple phrase though

phrase.replace(/is/g, 'IS');
// ThIS IS a simple phrase though

var regEx = new RegExp('th', 'ig');
phrase.replace(regEx, 'TH');
// THis is a simple phrase THough
```
  
others:
```javascript
.slice(start, end)
.substring(start, end)
.substr(start, length)
.toUpperCase()
.toLowerCase()
```
