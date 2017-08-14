# Using Mustache.js

#### Mustache gets its name from the fact that there are many curly braces used in this method and they on to resemble a mustache.

## Why the need for Mustache?

#### When shaping HTML elements by making use of Javascript or jQuery can make the code look quite messy and way too complicated.
```
// JavaScript
newDiv = document.createElement('div');
newDiv.setAttribute('class', 'new');
order_list = document.createElement('ol');
newDiv.appendChild(order_list);
list_value = document.createElement('li');
list_value.innerHTML = 'Order list value';
order_list.appendChild(list_value);
```

#### With mustache.js we can get a solution that is far more feasible to understand and implement.
```
var view = {
    name: "Roy",
    say: function(){
        return "Hello!";
    }
}
var template = "{{name}} says {{say}}";
var html = Mustache.to_html(template, view);
alert(html);
```

So as we can see the code is simpler and provides us a dynamic template


#### Let's look at another mustache example that shows how the if and else statements, and for loops are not needed at all:

```
<!doctype html>
<!DOCTYPE html>
<html lang="en">
<head>
<title>Create a Methout with using of Mustache.js</title>
<script type="text/javascript" src="js/mustache.js" ></script>
<script>
var view = {
    title : "Mustache",
    rank : "Good"
};

function loadtemp(){
    var output = Mustache.render("{{rank}} rank of  {{title}}", view);
    document.getElementById('rank').innerHTML = output;
}
</script>
</head>
<body onload="loadtemp()">
    <div id="rank"></div>
</body>
</html>
```
The process has to begin with creating a mustache.js file and after that, we can proceed to creating the templates. The example I have provided has a view that stores the name and occupation of an individual and then the render() function contains the template. It also contains all the necessary tags and the presentation we need in terms of the required data.


## How the Template can be as snippets from outsite

This example will show how jQuery can be used for template leveraging certain functions like load ().

This method is essentially fetching the templates from external files and loads them dynamically. Example:

```
<div id="theme1" >
<h1>{{title}}</h1>
</div>

<div id="theme2" >
<div>{{title}}</div>
</div>

<div id="theme3" >
<p><span>{{title}}</span></p>
</div>
```

In order to ensure the compatibility with the jQuery, the <div> element is brought into action. Now, since we have different templates represented differently, we will have separate ids for each and now let’s put them into action by using them in a page:

```
<!doctype html>
<html lang="en">
<head>
<title>Template Can be As Snippets from Outside</title>
<script type="text/javascript" src="js/jquery-1.11.0.min.js" ></script>
<script type="text/javascript" src="js/mustache.js" ></script>
<script>
$(document).ready(function(){
    var view = {
        title : "Mustache",
        rank : "Good"
    };

    $("#rank").load("t2.php #theme1",function(){
        var theme1 = document.getElementById('theme1').innerHTML;
        var output = Mustache.render(theme1, view);
        $("#rank").html(output);
    });
});
</script>
</head>
<body>
    <div id="rank"></div>
</body>
</html>
```
