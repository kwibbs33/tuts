## Using getJSON to parse JSON data

* use __callback=?__ to treat as JSONP from remote site

```javascript
var requestURL = 'https://api.instagram.com/v1/users/{user-id}/media/recent?callback=?';

$.getJSON(requestURL, {
    count: '100',
    access_token: 'ACCESSTOKEN'
}, function(json, textStatus) {
    // do something with the data
});
```

^ is the same as:
```javascript
var requestURL = 'https://api.instagram.com/v1/users/{user-id}/media/recent?count=100&access_token=ACCESSTOKEN&callback=?';

$.getJSON(requestURL, function(json, textStatus) {
    // do something with the data
});
```

data:
```javascript
$.getJSON(requestURL, function(json, textStatus) {
    $.each(json.data, function(i) {
        var theLink = this.link;
        var theImage = this.images.standard_resolution.url;

        var theFilter = 'Filter: ';
        if (this.filter.toLowerCase() === 'normal') {
            theFilter += 'none';
        } else {
            theFilter += this.filter;
        }
    });
});
```


[View a city, state lookup JSON call to Ziptastic on Codepen](http://codepen.io/kwibbs33/pen/vKwvyJ?editors=1011)


