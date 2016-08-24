### JSON / JS Objects

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)
* [http://www.w3schools.com/json/](http://www.w3schools.com/json/)


---

### Tools
* [__JSON Editor Online__](http://jsoneditoronline.org)
* [__JSONLint__ to check for JSON errors](http://jsonlint.com)
* [__JSHint__ to check for JS Object errors](http://jshint.com)


---

### Info
* [JS Objects](objects.md)
* [getJSON](getjson.md)
* [AJAX](ajax.md)


---

### Tips
* __key__ and __value__ pairs
    * key must be wrapped in double quotes
        * underscores = best practice (full_name)
    * value: strings, numbers, objects, arrays, booleans or null

* __objects__: {} curly brackets / __arrays__: [] square brackets
    * objects use .key or ['key']
    * arrays use index [0]

* __JSON__ for local data / __JSONP__ for remote data


---

JSON file:
```javascript
{
    "full_name" : "Karen W",
    "location"  : "Napa, CA",
    "awesome"   : true,
    "dogs"      : 1,
    "animals"   : [
        {
            "type" : "dog",
            "name" : "Bosco"
        },
        {
            "type" : "cat",
            "name" : "Booger"
        }
    ]
}
```
