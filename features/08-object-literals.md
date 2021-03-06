
# Enhanced Object Literals

Object literals have been given more functionality with ES6.

- Shorthands for defining methods
- Dynamic property names


## Method shorthands

- Object methods now look like methods
- The keyword "function" is no longer necessary.

Example:

```javascript
{

    // ES5
    var person = {
        name: 'Doyle',
        poke: function() { console.log('Stop that!'); },
        greet: function() { console.log('Ahoi-hoi!'); }
    };

    // ES6
    var person = {
        name: 'Doyle',
        poke() { console.log('Stop that!'); },
        greet() { console.log('Ahoi-hoi!'); }
    };

};```


## Computed property names

- Allows you to put an expression in brackets [], that will be computed as the property name

Example:

```javascript
{

   // Computed property names (ES6)
    const prefix = 'half';
    const people = {
        [prefix + 'man']: 'Tyrion',
        [prefix + 'hand']: 'Qhorin',
        [prefix + 'mast']: true
    };
    
    console.log(people.halfman);    // → Tyrion
    console.log(people.halfhand);   // → Qhorin
    console.log(people.halfmast);   // → true

};
```


## Sources

https://github.com/lukehoban/es6features#enhanced-object-literals
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer
