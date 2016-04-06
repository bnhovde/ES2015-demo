
# destructuring


Imagine javaScript without JSON, having to set key values on objects.

The same has been true for taking values out of JSON/objects.

Destructuring is like the reverse of this

Example:

    {
        const person = {
            name: 'Tim Samson',
            features: {
                face: 'round',
                arms: 'sort',
                hair: false
            }
        }
        
        // Imagine if you had to do this instead:
        const person = {};
        
        person.name = 'Tim Samson';
        person.features = {};
        person.features.face = 'round';
        person.features.arms = 'sort';
        person.features.hair = false;
    };

Destructuring is like the reverse of this!

Example:

    {
        const person = {
            name: 'Tim Samson',
            features: {
                face: 'round',
                arms: 'sort',
                hair: false
            }
        }
        
        // To get values out, you got to dig!
        const name = person.name;
        const face = person.features.face;
        const arms = person.features.arms;
        const hair = person.features.hair;
        
        // Not anymore!
        const { name, features: { face, arms, hair } } = person;

    };

You can use destructuring for other things too.


## Function parameter destructuring

Useful when you only care about certain parameters

Example:

    {
        const menu = {
            appetiser: 'flea soup'
            mains: 'locust eggs'
            dessert: 'goblin sorbet'
        }
        
        function orderDessert({dessert}){
            console.log('Can I please have a bucket of ' + dessert + ', please?');
        }
        
        orderDessert(menu); // Can I please have a bucket of goblin sorbet, please?
        
    };


## Default values

Provide a fallback value if property doesn't exist

Example:

    {
        const person = {
            name: 'Draco',
            age: 673
        }
        
        const { name = 'Ricardo', height = '180cm' } = person;
        
        console.log(name);      // Draco
        console.log(height);    // 180cm
    };



## Use case: 

For future projects:

- get data from JSON/objects
- provide default variable values
- destructure function arguments