## JS Object

### JSON vs Javascript Object
__JSON__:
```javascript
{
    "full_name" : "Karen W",
    "location"  : "Napa, CA",
    "awesome"   : true
}
```

__JS Object__:
```javascript
var info = {
    full_name : "Karen W",
    location  : "Napa, CA",
    awesome   : true,
    getName   : function() {
        alert(this.full_name);
    }
};

info.full_name;      // Karen W
info['full_name'];   // Karen W
```

```javascript
var infoA = [
    {
        full_name : "Karen W",
        location  : "Napa, CA",
        awesome   : true,
        getName   : function() {
            alert(this.full_name);
        }
    }
];

infoA[0].full_name;   // Karen W
```

* key doesn't need quotes
* can be any data type (including function)


---

### Parse vs Stringify
JS Object has to be __parsed__ from string into Javascript
```javascript
var text = '{"name" : "Karen W", "location" : "Napa, CA", "skills" : ["HTML", "CSS", "Javascript"] }';

var info = JSON.parse(text);

info.skills[1];        // CSS
info['skills'][1];     // CSS
```

Take JS Object and convert into string with __stringify__
```javascript
var infostring = JSON.stringify(info);
```


---

### Looping

__for in__
* unordered

```javascript
var info = {
    "full_name" : "Karen W",
    "location"  : "Napa, CA",
    "animals"   : {
        "dog1" : "Sierra",
        "cat"  : "Booger",
        "dog"  : "Bosco"
    }
}
```
```javascript
for (key in info.animals) {
    if (info.animals.hasOwnProperty(key)) {   // if has key property
        console.log(key + ' = ' + info.animals[key]);
    }
}

// dog1 = Sierra
// cat = Booger
// dog = Bosco
```

__for__
* sequential order - use an array of objects

```javascript
var info = {
    "full_name" : "Karen W",
    "location"  : "Napa, CA",
    "animals"   : [
        { "cat"  : "Booger" },
        { "dog"  : "Bosco" },
        { "dog1" : "Sierra" }
    ]
}
```
```javascript
// for each object
for (var i = 0; i < info.animals.length ; i++) {
    // for each array element
    for (key in info.animals[i]) {
        if (info.animals.hasOwnProperty(key)) {
            console.log(key + ' = ' + info.animals[i][key]);
        }
    }
}

// cat = Booger
// dog = Bosco
// dog1 = Sierra
```



