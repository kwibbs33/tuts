## Date

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
* [http://www.w3schools.com/jsref/jsref_obj_date.asp](http://www.w3schools.com/jsref/jsref_obj_date.asp)

---

### date Methods

```javascript
var today = new Date();
var y2k = new Date(2000, 0, 1);

today.getMonth();     // returns 0-11
today.getFullYear();  // YYYY (not zero-based)
today.getYear();      // DEPRECATED
today.getDate();      // 1-31 day of month
today.getDay();       // 0-6 day of week. 0 = sunday.
today.getHours();     // 0-23
today.getTime();      // milliseconds since 1/1/1970
```
[view results on codepen](http://codepen.io/kwibbs33/pen/pbdYyv?editors=0010)
  
```javascript
var bdayWeekday = new Date(1975, 0, 22);    // Wed Jan 22 1975 00:00:00 GMT-0800 (PST)

bdayWeekday.getDay();  // 3
```

---

### Comparing dates

```javascript
var date1 = new Date(2000, 0, 1);
var date2 = new Date(2000, 0, 2);

var diff = (date1.getTime() < date2.getTime()) ? 'after' : 'before';
// after
```

---

### Uses

```javascript
var d = new Date();
```

```javascript
var monthNames = [ "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec" ];
var monthFull = [ "January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December" ];

console.log(monthNames[d.getMonth()]);
// Jul
console.log(monthFull[d.getMonth()]);
// July
```
  
```javascript
var days = [ "Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"];

console.log(days[d.getDay()]);
// Wednesday
```
  
Wordpress ajax
```javascript
function ISOdate(d) {
    MM = monthFull;
    date = new Date(d);
    return MM[date.getMonth()] + ' ' + date.getDate() + ', ' + date.getFullYear();
}
var thedate = ISOdate(this.date);
```

Facebook/Twitter ajax
```javascript
function goTime(h,m) {
    var hour, am;
    if (h > 12) {
        hour = h - 12;
        am = 'pm';
    } else {
        hour = h;
        am = 'am';
    }
    return hour + ':' + pad(m) + am;
}
function goDate(d) {
    return monthNames[d.getMonth()] + ' ' + d.getDate() + ', ' + d.getFullYear() + ' ' + goTime(d.getHours(), d.getMinutes());
}
function pad(n) { return n < 10 ? '0' + n : n }

var thedate = goDate(new Date(this.created_time));  // Facebook
var thedate = goDate(new Date(this.created_at));    // Twitter
```
