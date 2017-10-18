# Using TypeScript

> These exercises require you to use the TypeScript compiler, `tsc`. Either use the one in your Angular project folder (in `node_modules/.bin/tsc`), or install the compiler globally (`npm install typescript -g`).

## JavaScript is TypeScript

Place the following JavaScript code in a file `hello.ts` (use any folder - it's just temporary):

      let myname = 'Pete';
      console.log(`My name is ${myname}`);

Now compile it:

      $ tsc hello.ts

And run it:

      $ node hello.js


## Type Inference

TypeScript uses _type inference_ to infer types that aren't specified explicitly.

1. Add a line of code to your `hello.ts` script which attempts to replace `myname`'s string with a number.

2. Try to compile it and verify that an error is displayed.


## Adding Type Annotations

You can also specify types explicitly.

1. Modify your script so that it now contains:

        let myname: string = 'Pete';
        console.log(`My name is ${myname}`);

     The `:string` is a _type annotation_.

2. Write a function that accepts a `string` parameter. This function should display a message on the console. Check that this function can only be called with a `string`.

3. __Return Value__ Change this function so that it now _returns_ a string value. How might you specify the return type? Check with the [function documentation](http://www.typescriptlang.org/docs/handbook/functions.html).

4. Examine the compiled `.js` file. How does it compare to the source `.ts` file?

## Using an Interface

1. Copy this code into a TypeScript file:

        let car = {
            make: 'Nissan',
            model: 'Note',
            year: 2011,
            hasRoofRack: true,
        };

        function displayCar(car: Car) {
            console.log(`A ${car.year} ${car.make} ${car.model} with${car.hasRoofRack ? '' : 'out'} a roof rack`);
        }

2. At the moment, this is pure JavaScript. Call the function and run the script to ensure that it works.

3. Add a TypeScript [interface](http://www.typescriptlang.org/docs/handbook/interfaces.html) at the top of the file. Name the interface `Car`, and ensure that the property types reflect the types of the Nissan Note above.

4. Add a type annotation to `displayCar`'s parameter.

5. Compile and run the script again to ensure that it works.

6. Check that if you change a property type (eg the `year` to a string), the compiler generates an error.


## Creating a Class

1. Refactor your code to use a TypeScript [class](http://www.typescriptlang.org/docs/handbook/classes.html) for the `car` instead of an `interface`. Your `Car` class should have a constructor that takes the properties as parameters and instantiates a new car. It should also have a `display()` method.

2. Create a new Car object and call its `display()` method.

3. Ensure that creating a Car object with incorrect parameters generates a compiler error.
