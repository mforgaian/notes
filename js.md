# Important Concepts and Use cases in javascript

## How to modularize code
* Function Calling
```javascript
Trollbox = function(){};
Trollbox.prototype.foo = function(){
  alert('i can be called from other files too :');
}
```
* Function Definition
```javascript
var trollbox = new Trollbox();
trollbox.foo(); // ll show alert
```
## How to chain methods

* Defining Methods
```
function SimpleWidget(spec) {
    var instance = {}; // <-- A

    var headline, description; // <-- B

    instance.render = function () {
        var div = d3.select('body').append("div");

        div.append("h3").text(headline); // <-- C

        div.attr("class", "box")
           .attr("style", "color:" + spec.color) // <-- D
           .append("p")
               .text(description); // <-- E

        return instance; // <-- F
    };

    instance.headline = function (h) {
        if (!arguments.length) return headline; // <-- G
        headline = h;
        return instance; // <-- H
    };

    instance.description = function (d) {
        if (!arguments.length) return description;
        description = d;
        return instance;
    };

    return instance; // <-- I
}
```

* Chaining Methods
```javascript
var widget = SimpleWidget({color: "#6495ed"})
        .headline("Simple Widget")
        .description("This is a simple widget demonstrating functional javascript.");
widget.render();
```

## Comparing decimal fractions
While dealing with decimal input with that has fractional values upper bound error need to be taken into consideration. This upper bound is called as **machine epsilon**
```
0.1+0.2 === 0.3; // false
var epsEqu = function () { // IIFE, keeps EPSILON private
        var EPSILON = Math.pow(2, -53);
        return function epsEqu(x, y) {
            return Math.abs(x - y) < EPSILON;
        };
}();

epsEqu(0.1+0.2, 0.3); //true
```




## Reference

 
