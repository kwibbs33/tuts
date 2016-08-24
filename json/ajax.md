## AJAX with jQuery

* [http://api.jquery.com/jQuery.ajax](http://api.jquery.com/jQuery.ajax)
* [https://learn.jquery.com/ajax/jquery-ajax-methods](https://learn.jquery.com/ajax/jquery-ajax-methods)



```javascript
$.ajax({
    url: '/path/to/file',
    type: 'GET, POST',
    dataType: 'xml, json, script, html',
    //dataType: 'json', contentType: 'application/json; charset=utf-8',
    cache: false,
    data: {
        param1: 'value1',
        param2: 'value2'
    }
})
// Code to run if the request succeeds (is done)
// The response is passed to the function
.done(function() {
    console.log("success");
})
// Code to run if the request fails; the raw request and
// status codes are passed to the function
.fail(function( xhr, status, errorThrown ) {
    alert( "Sorry, there was a problem!" );
    console.log( "Error: " + errorThrown );
    console.log( "Status: " + status );
    console.dir( xhr );
})
// Code to run regardless of success or failure
.always(function() {
    console.log("complete");
});
```


simple jQuery AJAX done method:
```javascript
.done(function(data) {
    // no results
    if (data && data.length == 0) {
        $('#loading').hide();
        $('#none').text('No results');
        $('#content').show();
    }
    // results
    else {
        var output = '<ul>';
        $.each(data, function(i){
            output += '<li>' + this.Title + '</li>';
        });
        var output += '<ul>';

        // write to html file
        $('#content').html(output);


        $('#loading').hide();
        $('#none').hide();
        $('#content').show();
    }
})
```

^ is the same as:
```javascript
.done(function(data) {
    // no results
    if (data && data.length == 0) {
        $('#loading').hide();
        $('#none').text('No results');
        $('#content').show();
    }
    // results
    else {
        var output = '<ul>';
        $.each(data, function(key, val){
            output += '<li>' + val.Title + '</li>';
        });
        var output += '<ul>';

        // write to html file
        $('#content').empty();
        $('#content').append(output);


        $('#loading').hide();
        $('#none').hide();
        $('#content').show();
    }
})
```

