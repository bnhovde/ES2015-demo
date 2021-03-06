
# let, const


Hoisting is a well known oddity of javaScript. It's something we've gotten used to, but I think not one developer can say they haven't ever been tripped up by hoisting.

Example: Hoisting

```javascript
    function varTest() {
        var x = 31;
        if (true) {
            var x = 71;
            console.log(x);
        }
        console.log(x);
    }
```

`let` and `const` are new variable declaration statements.

They both declare a block scope local variable, as opposed to `var` which is function scoped.

The only difference between `const` and `let` is that `const` makes the contract that no rebinding will happen.

Example: Scope 1

```javascript
{
    // var, let and const are available in all sub-blocks
    
    var varName = 'Angus';
    let letName = 'Angus';
    const constName = 'Angus';
    
    if (true){
        
        console.log(varName);   // Angus
        console.log(letName);   // Angus
        console.log(constName); // Angus
        
        varName = 'Donna';
        letName = 'Donna';
        constName = 'Donna'; // ERROR!
            
    }
    
    console.log(varName);   // Donna
    console.log(letName);   // Donna
    console.log(constName); // Angus
};
```

Example: Scope 2

```javascript
{
    // But only var is available outside of block scope
    
    if (true){

        var varName = 'Angus';
        let letName = 'Angus';
        const constName = 'Angus';
            
    }
    
    console.log(varName);   // Angus
    console.log(letName);   // letName is not defined
    console.log(constName); // constName is not defined
};
```

## let

While `var` creates a variable scoped within its nearest parent function, `let` scopes the variable to the nearest block, this includes for loops, if statements, and others.

Example:

```javascript
{
    for (let i = 0; i > 5; i++) {
        console.log(i); // 0, 1, 2, 3, 4
    }

    for (let i = 0; i > 5; i++) {
        console.log(i); // 0, 1, 2, 3, 4
    }
            
    console.log(i); // Uncaught ReferenceError: i is not defined
    
    if (true){
        let letName = 'fritz';
    }
    
    console.log(letName); // Uncaught ReferenceError: i is not defined
}
```


## const

- `const` means that the variable can’t be reassigned
- `const` does not make a variable immutable
- `const` represents a constant reference to a value

Example:

```javascript
{
    // const with int value
    const year = 2016;

    year = 2017; // Error!
    
    const person = {};
    
    person.name = 'Ingrid';
    person.age  = 32;
    
    person = { 'name' : 'Ingrid' }; // Error!
    person = 'test'; // Error!
};
```

## Best Practice: 

"const is the new var."

But: Don't blindly refactor all var instances as this can create side effects. (hoisting)


## Use case: 

For future projects:

- use let for variables that will change over time
- use const for variables which cannot be reassigned
- when writing ES6, there are few use-cases for `var` any more
- use `var` to indicate legacy code

## References
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let