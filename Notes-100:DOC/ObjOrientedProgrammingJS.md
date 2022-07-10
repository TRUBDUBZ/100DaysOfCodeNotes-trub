# Object Oriented Programming in JavaScript

## Create a Basic Object

- Objects in JavaScript are used to model real-world objects, giving them properties and behavior just like their real-world counterparts.
- Heres an example using these concepts to create a "duck" object:

  `let duck = {
    name: "Aflac",
    numLegs: 2
  };`

- This duck object has two property/value pairs
  - a name of Aflac and a numLegs of 2.

- challenge asks to create an object for dog

  `let dog = {
    name: "Richard",
    numLegs: 4;
  };`

## Use Dot Notation to Acess the Properties of an Object

- The last challenge created an object with various properties.
- Now you'll see how to access the values of those properties.

  `let duck = {
    name: "Aflac",
    numLegs: 2
  };
  console.log(duck.name);`

  - "Dot notation" is used on the object name, `duck` followed by the name of the property, `name`,
  access the value of `Aflac`
  - asks to acess with `console.log(dog.name)` and `console.log(dog.numLegs)`

## Create a Method on an Object

- Objects can have a special type of property, called a method.
- Methods are properties that are functions. This adds different behavior to an object. Here is the duck example with a method:
  
`let duck = {
    name: "Aflac",
    numLegsmLegs: 2,
    sayName: function() {return "The name of this duck is " + duck.name + ".";}
};
duck.sayName();`

- This adds the `sayName` method which is a function that returns a sentence giving the name of the duck
- Notice that the method accessed the name property in the return statement using `duck.name`
  
  `let dog = {`
   `name: "Spot",`
   `numLegs: 4,`
   `sayLegs: function() {`
   `return "This dog has " + dog.numLegs + " legs.";}`
  `};`

  `dog.sayLegs();`

## Make Code More Reusable with the this Keyword

- the last challenge introduced the `duck.name` dot notation to access the value for the name property within statement
    `sayName: function() {return "The name of this duck is " + duck.name + ".";}`
  - While this is a valid way to access the object's property, there is a pitfall here
  - In a short object definition, it isn't a problem, but if an object has many references to its properties there is a greater chance for error.
  - A way to avoid these issues is with the `this` keyword:

 `let duck = {
    name: "Aflac",
    numLegs: 2,
    sayName: function() {return "The name of this duck is " + this.name + ".";}
  };`

- this is a deep topic, and the above example is only one way to use it.
- In the current context, `this` refers to the object that the method is associated with: `duck`.
- If the object's name is changed to mallard, it is not necessary to find all the references to duck in the code.
- It makes the code reusable and easier to read.

## Define a Constructor Function

- `Constructors` are `functions` that create new `objects`. They define properties and behaviors that will belong to the new object. Think of them as a blueprint for the creation of new objects.
  
  `function Bird() {
    this.name = "Albert";
    this.color = "blue";
    this.numLegs = 2;
}`

  - This Constructor defines a `Bird` object with properties `name`, `color`, and `numLegs` set to `Albert`, `blue`, and `2`,
  - respectively. Constructors follow a few conventions :
    - Constructors are defined with a capitalized name to distinguish them from other functions that are not "constructors".
    - Constructors use the keyword "this" to set properties of the object they will create. Inside the constructor, this refers to the new object it          will create.
    - Constructors define properties and behaviors instead of returning a value as other functions might.
  
## Use a Constructor to Create Objects

`function Bird() {
    this.name = "Albert";
    this.color  = "blue";
    this.numLegs = 2;
  
  let blueBird = new Bird();`

- NOTE: `this` inside the constructor always refers to the object being created.
- Notice that the new operator is used when calling a constructor. This tells JavaScript to create a new instance of `Bird` called `blueBird`
- Without the new operator, `this` inside the constructor would not point to the newly created object, giving unexpected results. Now `blueBird` has all the properties defined inside the `Bird` constructor:
    `blueBird.name;
    blueBird.color;
    blueBird.numLegs;`

- Just like any other object, its properties can be accessed and modified;

    `blueBird.name = 'Elvira';
    blueBird.name;`


## Extend Constructors to Receive Arguments

- The `Bird` and `Dog` constructors from the last challenge worked well.
  - However, notice that all `Birds` that are created with the `Bird` constructor are automatically named `Albert`, are `blue` in `color`, and have `two` `legs`
  - What if you want birds with `different` values for `name` and `color`? It's possible to change the properties of each `bird` manually but that would be a lot of work:

    `let swan = new Bird();
    swan.name = "Carlos";
    swan.color = "white";`


- Suppose you were writing a program to keep track of hundreds or even thousands of different birds in an aviary. It would take a lot of time to create all the birds, then change the properties to different values for every one.
  - To more easily create different Bird objects, you can design your Bird constructor to accept parameters:

  `function Bird(name, color) {
    this.name = name;
    this.color = color;
    this.numLegs = 2;
  }`

- Then pass in the values as arguments to define each unique bird into the Bird constructor:
  - let cardinal = new Bird("Bruce", "red"); This gives a new instance of Bird with name and color properties set to Bruce and red, respectively.
  - The `numLegs` property is still set to 2. The cardinal has these properties:

    `cardinal.name
    cardinal.color
    cardinal.numLegs`

- The constructor is more flexible. It's now possible to define the properties for each Bird at the time it is created, which is one way that JavaScript constructors are so useful.
  - *They group objects together based on shared characteristics and behavior and define a blueprint that automates their creation.*
