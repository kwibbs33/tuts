## Ternary (Conditional) Operator

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

---

### Tips
* not used often because is too terse
* typically used to __set variables__

---

```javascript
var wine = 'Grenache';

wine === 'Grenache' ? document.write('a favorite') : document.write('nope');
// a favorite

var blend = (wine === 'Grenache' ? 'GSM' : 'Bordeaux');
document.write(blend);
// GSM
```
