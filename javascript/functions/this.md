# this

`this` is **a reference** to **an object**. The binding \(i.e. value\) of `this` has nothing to do with where a function is declared, but has instead everything to do with the context in which the function is called.

Example:

```javascript
// Example 1: value of this in a method
var cat = {
  sound: 'meow!',
  whatIsThis: function() {
    console.log(this)
  }
}

cat.whatIsThis() // this === cat object

// Example 2: value of this in a function
function whatIsThis() {
  console.log(this)
}
whatIsThis() // this === global, when run in node
whatIsThis() // this === window, when run in browser
// go ahead and try it in node or in your browser console (e.g. this === window)
```

## Dynamic Scoping vs Lexical Scoping

Except the case in arrow-functions, `this` is not an author-time binding but a runtime binding \(i.e. lexical scope doesn't apply, since lexical scope is determined by author-time binding\). In [arrow-functions, `this` follows lexical scope rules](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4).

## Common gotchas with `this`

`this` is **not assigned a value until an object invokes the function \(or the function is bound to an object via** `bind`**\)**. `this` can lose its reference.

Here are 3 typical scenarios where `this` will lose its reference:

* when used inside callback functions
* when a method is assigned to a function
* when used inside closures

When this happens, there are strategies \(e.g. [bind, apply, call](https://github.com/thoughtworks-jumpstart/jumpstart/tree/e9e6f724f6a404a7ef165f66abc22b3debc74dc1/01_programming_fundamentals/javascript/es5/bind_apply_call.html)\) for binding `this` to a specific object of your choice

## Resources

* [http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/](http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)
