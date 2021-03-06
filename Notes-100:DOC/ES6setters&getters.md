# ES6 Setters & Getters

<https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-export-to-share-a-code-block>

- Getter functions are meant to simply return (get) the value of an object's private variable to the user without the user directly accessing the private variable
- Setter functions are meant to modify (set) the value of an object's private variable based on the value passed into the setter function. This change could involve calculations, or even overwriting the previous value completely
- Note: It is convention to precede the name of a private variable with an underscore (_). However, the practice itself does not make a variable private.
- Getters and setters are critical parts of a class/object. They allow you to control their attributes from the outside. They will become more prominent when you get started with the Object-Oriented Programming unit (coming up!). For now, this exercise shows you how to manipulate them with ES6

## Create a Module Script

- in javascript you can import scripts straight into html files by using <script type="module" src=index.js"></script>

- imagine a file called math_functions.js that contains several functions related to mathematical operations. One of them is stored in a variable, add, that takes in two numbers and returns their sum. You want to use this function in several different JavaScript files. In order to share it with these other files, you first need to export it.

     `const add = (x, y) => { return x + y }`
`export { add };`

- When you export a variable or function, you can import it in another file and use it without having to rewrite the code. You can export multiple things by repeating the first example for each thing you want to export, or by placing them all in the export statement of the second example, like this:

  `export { add, functions, here };`

## Reuse JavaScript Code Using Import

- import allows you to choose which parts of a file or module to load. In the previous lesson, the examples exported

- add from the math_functions.js Here's how you can import it to use in another file:

`import { add } from './math_functions.js';`

- import find math_functions.js just that function and ignore the rest. the tells the import to look for the math_functions.js files in the same folder as the current file the relative file path (./) and file extension (.js) are required when using import this way.

- You can import more than one item from the file by adding them in the import statement like this:
  
  `import { add, subtract } from './math_functions.js'`
  