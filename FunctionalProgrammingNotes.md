# Understand the Hazards of Using Imperative Code

  - Functional programming is a good habit. It keeps your code easy to manage, and saves you from sneaky bugs. But before we get there, let's look at an imperative approach to programming to highlight where you may have issues.
    - Often the statements change the state of the program, like updating global variables. A classic example is writing a `for` loop that gives exact directions to iterate over the indices of an array.
    - In contrast, functional programming is a form of declarative programming. You tell the computer what you want done by calling a method or function.
  
  - JavaScript offers many predefined methods that handle common tasks so you don't need to write out how the computer should perform them. 
    - For example, instead of using the `for` loop mentioned above, you could call the `map` method which handles the details of iterating over an array.
    - This helps to avoid semantic errors, like the "Off By One Errors" that were covered in the Debugging section.
  
  - Consider the scenario: you are browsing the web in your browser, and want to track the tabs you have opened. Let's try to model this using some simple object-oriented code.
    
  - A Window object is made up of tabs, and you usually have more than one Window open. The titles of each open site in each Window object is held in an array
    - After working in the browser (opening new tabs, merging windows, and closing tabs), you want to print the tabs that are still open. Closed tabs are removed from the array and new tabs (for simplicity) get added to the end of it.
 
  - The code editor shows an implementation of this functionality with functions for `tabOpen()`, `tabClose()`, and `join()`. The array `tabs` is part of the Window object that stores the name of the open pages.

# Avoid Mutations and Side Effects Using Functional Programming

  - the issue in the previous challenge was with the `splice` call in the `tabClose()` function. Unfortunately, `splice` changes the original array it is called on, so the second call to it used a modified array, and gave unexpected results.
  
  - This is a small example of a much larger pattern - you call a function on a variable, array, or an object, and the function changes the variable or something in the object.
    - *Functional programming sounds to me a lot more like the kind of programming that is done in Solidity*
  
  - The previous example didn't have any complicated operations but the `splice` method changed the original array, and resulted in a bug.
  
  - Recall that in functional programming, changing or altering things is called *mutation*, and the outcome is called a *side effect*. A function, ideally, should be a *pure function*, meaning that it does not cause any side effects.
 

# Pass Arguments to Avoid External Dependence in a Function

  - The last challenge was a step closer to functional programming principles, but there is still something missing.
    - We didn't alter the global variable value, but the function `incrementer` would not work without the global variable `fixedValue` being there.
 
  - Another principle of functional programming is to always declare your dependencies explicitly. This means if a function depends on a variable or object being present, then pass that variable or object directly into the function as an argument.
  
  - There are several good consequences from this principle. The function is easier to test, you know exactly what input it takes, and it won't depend on anything else in your program.
    - This can give you more confidence when you alter, remove, or add new code. You would know what you can or cannot change and you can see where the potential traps are.
    - Finally, the function would always produce the same output for the same set of inputs, no matter what part of the code executes it. 


# Refactor Global Variables Out of Functions

  - So far, we have seen two distinct principles for functional programming:  
    
  1. Don't alter a variable or object - create new variables and objects and return them if need be from a function. Hint: using something like `const newArr = arrVar`, where `arrVar` is an array will simply create a reference to the existing variable and not a copy.
    
    - So changing a value in `newArr` would change the value in `arrVar`.

  2. Declare function parameters - any computation inside a function depends only on the arguments passed to the function, and not on any global object or variable.

    - Adding one to a number is not very exciting, but we can apply these principles when working with arrays or more complex objects.


# Use the Map Method to Extract Data From an Array

- So far we have learned to use pure functions to avoid side effects in a program. Also, we have seen the value in having a function only depend on its input arguments.
- This is only the beginning. As its name suggests, functional programming is centered around a theory of functions.

- It would make sense to be able to pass them as arguments to other functions, and return a function from another function. 
- Functions are considered *first class objects* in JavaScript, which means they can be used like any other object. They can be saved in variables, stored in an object, or passed as function arguments.

- Let's start with some simple array functions, which are methods on the array object prototype. In this exercise we are looking at `Array.prototype.map()`, or more simply `map`.
  - The `map` method iterates over each item in an array and returns a new array containing the results of calling the callback function on each element. It does this without mutating the original array.

- When the callback is used, it is passed three arguments. 
  
  1. The first argument is the current element being processed. 
  2. The second is the index of that element
  3. the third is the array upon which the `map` method was called.

- See below for an example using the `map` method on the `users` array to return a new array containing only the names of the users as elements. For simplicity, the example only uses the first argument of the callback.

  `const users = [
    { name: 'John', age: 34 },
    { name: 'Amy', age: 20 },
    { name: 'camperCat', age: 10 }
  ];

  const names = users.map(user => user.name);
  console.log(names);`
  
  - The console would display the value `[ 'John', 'Amy', 'camperCat' ]`
   
    `const ratings = watchList.map(({ Title: title, imdbRating: rating }) => ({title, rating}));`
  
    - use this instead of a for loop to use `map` on `watchList` to assign a new array of objects to the `ratings` var


# Implement map on a Prototype 

- As you have seen from applying `Array.prototype.map()`, or simply `map()` earlier, **the `map` method returns an array of the same length as the one it was called on. It also doesn't alter the original array, as long as its callback function doesn't.**
- In other words, `map` is a pure function, and its output depends solely on its inputs. Plus, it takes another function as its argument.
- You might learn a lot about the `map` method if you implement your own version of it. It is recommended you use a `for loop` or `Array.prototype.forEach()`.


# Implement the fileter Method on a  Prototype

- You might learn a lot about the `filter` method if you implement your own version of it. It is recommended you use a `for` loop or `Array.prototype.forEach()`.
- Write your own `Array.prototype.myFilter()`, which should behave exactly like `Array.prototype.filter()`. You should not use the built-in `filter` method. The `Array` instance can be accessed in the `myFilter` method using `this`.
 

