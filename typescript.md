# Typescript Notes

## AMD
* Asynchronous Module Definition ( AMD )
* cli command to compile multiple files
```
tsc --sourcemap --module amd filename.ts
```
* require.js will use the value of the **'data-main'** attribute in the following script tag to load 'app.js' after require.js itself loads. For e.g.,
```
    <script data-main="app" type="text/javascript" src="path/to/require.min.js"></script>
```

## Interface
* A simple interface that defines the interface for something that can drive.

## Class
* An implentation of a car
* Use **extends** to create sub classes.
* **super** : derived classes make super calls
```
class Animal {
    constructor(public name) { }
    move(meters) {
        console.log(this.name + " moved " + meters + "m.");
    }
}

class Snake extends Animal {
    move() {
        console.log("Slithering...");
        super.move(5);
    }
}
var sam = new Snake("Sammy the Python");
sam.move();
```


## Async
* Async functions are functions that can suspend their execution to wait for the completion of an asynchronous operation. This allows complex algorithms that require asynchronous control flow  to be written sequentially.

## Namespaces
* **namespaces** are also called as **internal modules** for versions <= 1.5
* **External modules** are now **modules**

## Modules
* 

## References

