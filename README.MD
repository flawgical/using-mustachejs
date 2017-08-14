# Using Mustache.js

#### Mustache gets its name from the fact that there are many curly braces used in this method and they on to resemble a mustache.

## Why the need for Mustache?

#### When shaping HTML elements by making use of Javascript or jQuery can make the code look quite messy and way too complicated.

// JavaScript
newDiv = document.createElement('div');
newDiv.setAttribute('class', 'new');
order_list = document.createElement('ol');
newDiv.appendChild(order_list);
list_value = document.createElement('li');
list_value.innerHTML = 'Order list value';
order_list.appendChild(list_value);

#### With mustache.js we can get a solution that is far more feasible to understand and implement.

var view = {
    name: "Roy",
    say: function(){
        return "Hello!";
    }
}
var template = "{{name}} says {{say}}";
var html = Mustache.to_html(template, view);
alert(html);

```So as we can see the code is simpler and provides us a dynamic template
```

#### Let's look at another mustache example that shows how the if and else statements, and for loops are not needed at all:

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
