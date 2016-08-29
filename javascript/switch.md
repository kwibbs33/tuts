## Switch

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

---

### Tips
* __break__ is used to stop executing when the case is met
* if no break, the next case is run regardless if met

---

```javascript
var answer = window.prompt('Type YES, NO, MAYBE, WORD, YO. Then click OK.');

switch (answer) {

    case 'YES' :
        document.write("You said YES");

    case 'NO' :
        document.write("You said NO");
        break;

    case 'MAYBE' :
        document.write("You said MAYBE");
        break;

    case 'WORD' :
    case 'YO' :
        document.write("You said WORD or YO");
        break;

    default :
        document.write("You're a rebel");
        break;
}
```
[view results on codepen](http://codepen.io/kwibbs33/pen/RRyNZE?editors=0010)
