# JavaScript Notes
## Introductory Info


### What is JavaScript?
- High level interpreted programming language
- Conforms to the **ECMAScript** specification
- Multi-paradigm
- Runs on the client/browser as well as on the server (Node.js)

### Why learn JavaScript?
- It is the programming language of the browser
    - If you want to run code on a user's machine, you need JS. Other languages like Python and PHP run on another machine.
- Build very interactive user interfaces with frameworks like React
- Used in building very fast server side and full-stack applications
- Used in mobile development (React Native Native Script, Ionic)
- Used in desktop application development (Electron JS)

---

## Course Contents
1. Variables & Data Types
2. Arrays
3. Object Literals
4. Methods for strings, arrays, objects, etc.
5. Loops - for, while, for…of, forEach, map
6. Conditionals (if, ternary & switch)
7. Functions (normal & arrow)
8. OOP (prototypes & classes)
9. DOM Selection
10. DOM Manipulation
11. Events
12. Basic Form Validation

---

## Basics

JS is inserted into an HTML document using the `<script>` tag.

JS should be added within the `<body>` element but after all other content (*this is to ensure all content loads before the script runs*).

While JS can be added directly into the `<script>` tag, it is best practice to link a reference file, like this:

```HTML 
<script>src="main.js"</script>
```
### The Console

To see what your JS is outputting, you can view the **console**.

In Firefox, the console is accessible through the shortcut `ctrl + shift + k`.

You can display to the console directly with the command: 

```javascript
console.log();
```
---
## Variables

### Types of Variables

In JS, we have three ways to set variables:
1. `var`
2. `let`
3. `const`

### 1. ```var```

You don't want to use `var` anymore because it's global in scope.

Now `let` and `const` are the new standards.

### 2. ```let```

The `let` variable can be changed and reassigned.

### 3. ```const```

The `const` variable stays constant once it is set. Any attempts to change it will produce an error.

*Good rule of thumb: unless you know you'll be changing a variable down the line, use `const` instead of `let`.*

---

### Data Types for Variables

In JS, primitive data types refer to things written directly to the computer. They include:
1. `String`
2. `Numbers`
3. `Boolean`
4. `null`
5. `undefined`

### 1. `String`

**Strings** are a series of characters enclosed in either double or single quotes.

For example:
```javascript
const name = 'John';
```

### 2. `Numbers`

**Numbers** are any number without any quotes.

For example:
```javascript
const name = 30;
```

### 3. `Boolean`

**Booleans** are variables with either a `true` or `false` value.

For example:
```javascript
const name = true;
```

### 4. `null`

**Null** only includes the quoteless value `null`, and essentially indicates that a field is empty.

For example:
```javascript
const x = null;
```

### 5. `undefined`
**Undefined** is a variable similar to `null`, but if we use `let` we don't need to explicitly define it.

For example:
```javascript
const y = undefined;
```
or:
```javascript
let z;
```
Typingng any of these variables to the console using `console.log()` will return their variable type.

For example:
```javascript
console.log(z);
```
will return:
```javascript
undefined
```
---
## Strings

### Concatenation
If we want to mix other variable types (or even other strings) in with astring, we can use a method called "concatenation."

There are two ways to do this.

Concatenation is the older, more tedious method and uses quotes and plus signs, like this:

```javascript
const name = 'John';
const age = 30;

console.log('My name is' + name + ' and I am' + age);
```

which would output:

```
My name is John and I am 30
```

### Template String
The more modern method is to use "Template Literals", which employ backticks, dollar signs and curly braces, like this:

```javascript
const name = 'John';
const age = 30;

console.log(`My name is ${name} and I am ${age}`);
```

which also outputs:

```
My name is John and I am 30
```

---
## String Properties & Methods
Properties and Methods are ways to evaluate or manipulate strings. They are denoted by a name, and appended to string variables with a period.

*Properties do not have parentheses. If it's something that looks like a property and has parentheses it's a method.*

### 1. `.length`
The **.length** property counts the number of characters in a given string.

For example:

```js
const s = 'Hello World!';

console.log(s.length);
```

will output:

```js
12
```

### 2. `.toUpperCase` & `.toLowerCase`
The **.toUpperCase** & **.toLowerCase** methods convert a given string to either all upper or all lowercase characters.

For example:

```js
const s = 'Hello World!';

console.log(s.toUpperCase());
console.log(s.toLowerCase());
```

will output:

```js
HELLO WORLD!
hello world!
```

### 3. `.subString`

The **.subString** method will isolate a specific range of characters from the larger string, and output it as a separate sub-string.

Within the method parentheses you need to specify the starting and ending index, which is separated by a comma.

For example:

```js
const s = 'Hello World!';

console.log(s.subString(0, 5));
```

will output:

```
Hello
```

### 4. `.split`

The **.split** method will split a given string into an array (more on those later).

Within the inner parentheses, you can specify how you'd like to split the string.

For example, to split by each letter, you would use empty quotes.

Meaning:
```js
const s = 'Hello World!';

console.log(s.split(''));
```

will output:

```js
["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!"]
```
You can also define any kind of separator.

For example, if you wanted to create an array out of tags within a blog post, all separated by commas, you could define your separator as `.split(', ')`, which would break up each of the tags into separate array elements.

Let's say you had:

```js
const s = 'technology, computers, it, code';

console.log(s.split(', '));
```

It would output:

```js
["technology", "computers", "it", "code"]
```
---
## Arrays

Arrays are variables that hold multiple values.

There are a few ways to make arrays.

The first is not so common, but we'll review it anyways.

### Array Constructor
This uses the `new` keyword, which lets us know what comes agter is a constructor.

In this case we have:

```js
const numbers = new Array(1,2,3,4,5);
```

Now if we go:
```js
console.log(numbers);
```
Then we get an array with 5 values:
```js
[1, 2, 3, 4, 5]
```
### Set Brackets
For the most part, you're going to create an array by just setting the brackets and populating it with items.

For example:

```js
const fruits = ['apples', 'oranges', 'pears'];
```

One important thing is that you can mix data types within the same array.

For example:

```js
const fruits = ['apples', 'oranges', 'pears', true, 2];
```

This is also a perfectly valid array.

---
## Manipulating Arrays

### Isolating Array Items

Now, let's say we want to pull out just one item from our list of fruits.

We can do this as follows:

```js
const fruits = ['apples', 'oranges', 'pears'];

console.log(fruits[1]);
```

Which would output:

```js
oranges
```

Two important things to note here. 

1. The number we chose to call was wrapped in brackets. This is how arrays work.
2. Even though we chose 1, we got the second item in the list. This is because arrays (and everything in JS) count from 0 up.

### Adding Array Items (general method)

Another thing we can do is add an item to an array.

The way we would do this is as follows:

```js
const fruits = ['apples', 'oranges', 'pears'];

fruits[3] = 'grapes';
```

Now when we call `fruits` back up…

```js
console.log(fruits);
```

We get:
```js
["apples", "oranges", "pears", "grapes"]
```

### Adding Array Items (`.push` and `.unshift` methods)

The previous method works fine if you know how many items are in your array, but what if you don't? Or what if you want to add to the beginning of an array?

In that case, you can use the `.push` and `.unshift` methods to append a new array item to the end or beginning of a string respectively. All without needing to specify a number.

For example:

```js
const fruits = ['apples', 'oranges', 'pears'];

fruits.push('mangoes');

fruits.unshift('strawberries');
```

Now when we call `fruits` back up…

```js
console.log(fruits);
```

We get:

```js
["strawberries", "apples", "oranges", "pears", "mangoes"]
```

### Additional Array Methods

What if we want to knock the last item off a list?

- The `.pop` method does exactly that.

What if we want to find what number within an array a certain value is?

- The `.indexOf` method allows you to input any value and returns its index.

What if we want to squeeze new elements in to an existing array, and/or cut out other elements in the process?
- The `.splice` element does just that. The first two parameters are numbers, which define the **position** where the new elements are to be inserted and **how many** elements should be removed. The rest of the parameters define the new elements **to be added**.

*Even more array methods can be found [here](https://www.w3schools.com/js/js_array_methods.asp).*

---

## Object Literals

Object literals are essentially key value pairs grouped under a single constant.

So let's do something simple like a person:

```js
const person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 30,
    hobbies: ['music', 'movies', 'sports'],
    address: {
        street: '50 main st',
        city: 'Boston',
        state: 'MA'
    }
};
```

Now, if we log the variable `person`, it will return all of these things.

Meaning:

```js
console.log(person);
```

Outputs the following object:

```js
{ firstName: 'John', lastName: 'Doe', age: 30, hobbies: ['music', 'movies', 'sports'], address: {street: '50 main st', city: 'Boston', state: 'MA'}};
```

An important thing to note about the above object, is that it can contain any variable type (and can even include other objects within it!)

### Applying Methods to Objects

Let's say we want to just pull a single value from a given object.

In our case we can simply append another property to the given object name, like this:

```js
console.log(person.firstName);
```

Which will output:

```js
John
```

You can also output multiple values this way, by separating them with a comma.

For example:

```js
console.log(person.firstName, person.lastName);
```

Which will output:

```js
John Doe
```

Another thing you can do is nab a single item from an array that is within an object.

For example:

```js
console.log(person.hobbies[1]);
```

Will output:

```js
movies
```

*That's because `'movies'` was the second item in the `hobbies` array, meaning it had an index of `1`.*

You can also freely add new properties to an existing object.

Just append a new property to the existing object with a period, then define it with an equal sign.

For example:

```js
person.email = 'john@gmail.com';
```

Will add the new value of `email` to the existing object `person`.

---

## Arrays of Objects

Alot of the time, we'll be dealing with arrays of objects, and these are simple to create.

Take the following 'todo' array:

```js
const todos = [
    {
        id: 1,
        text: 'Take out trash',
        isCompleted: true
    },
    {
        id: 2,
        text: 'Meeting with boss',
        isCompleted: true
    },
    {
        id: 3,
        text: 'Dentist appt',
        isCompleted: false
    },
];
```
Now, let's say you wanted to grab the text from todo item number two.

Easy enough:

```js
console.log(todos[1].text);
```

Will output:

```
Meeting with boss
```

---

>### **A quick aside about JSON**
>
>**JSON** is a very popular for full-stack development and using APIs.
>  
>When you're sending data to a server, you usually send it in JSON.
>
>The thing is, it's very similar to object literals, and you can convert between the tools using free tools like [these](https://www.freeformatter.com/json-formatter.html). 
>
>When you do this conversion, you'll see the syntax between a JS object array and JSON is very similar (only difference is only double quotes in JSON). 
> 
>So, what if you want to convert your JS object to JSON directly in your script?
>  
>Turns out it's very easy.
>  
>The way you do it is as follows:
>```js
> const todoJSON = JSON.stringify(todos);
>```
>Outputting this to a `console.log` will produce a fully JSON version of the original JS object array.
>  
>And this is how you would send that data to a server.  
>.

---

## Loops

### For Loops

For Loops are structured as follows:

- **`for()`** : declares that a for loop is starting.
- **`let i = 0;`** : defines a variable and establishes a starting condition (in this case of 0),
- **`i < 10;`** : sets up a condition to check against after each iteration of the loop. As soon as this expression comes up false, the loop will stop.
- **`i++`** : this establishes an iterator that will change the variable after each loop (in this case `++` = add 1). Without an iterator, the loop will run forever.
- **`console.log(i);`** : this will print out the value for our variable after each loop. We can choose to have it print a variety of things to console.

Now here it is all together:

```js
for(let i = 0; i < 10; i++) {
    console.log(i);
}
```
### While Loops

While Loops are structured as follows:

- **`let i = 0;`** : similar to a for loop, here we are setting up a variable for a starting point. Only in this case, we set it up outside the loop itself.
- **`while(i < 10){}`** : here we are establishing the condition under which the loop will run. The second this statement becomes false, the loop will stop.
- **`console.log(i);`** : this instructs what the loop will output to console.
- **`i++;`** : much like the for loop, it's key to include an iterator within the while loop, otherwise it will run endlessly.

Now here it is all together:

```js
let i=0;
while(i < 10) {
    console.log(i);
    i++;
}
```

### For of Loop

For of loops are a much more efficient way of looping through object arrays, like this:

```js
const todos = [
    {
        id: 1,
        text: 'Take out trash',
        isCompleted: true
    },
    {
        id: 2,
        text: 'Meeting with boss',
        isCompleted: true
    },
    {
        id: 3,
        text: 'Dentist appt',
        isCompleted: false
    },
];
```

For of loops are structured as follows:

- **`for()`** : this indicates that a for loop is starting.
- **`let todo`** : this creates a new variable we will iterate on.
- **`of todos`** : this allows our iterator to reference our existing object array.
- **`{console.log(todo.text);}`** : this will cause our console to print the text variable from each object in the array.

Now here it is all together:

```js
for(let todo of todos) {
    console.log(todo.text);
}
```
---
## High Order Array Methods

These are the best methods to use when trying to iterate on arrays.

### 1. `.forEach`

The `.forEach` method is structured as follows:

- **`todos.forEach()`** : this targets a specific array and declares the method.
- **`(function(todo))`** : all higher order array methods take in a function as a parameter, so we pass in a function. This callback function can take in multiple parameters, but the first one is going to be the variable that you want to use as each item, (or in this case each todo).
- **`{console.log(todo.text);}`** : then this will output the text for each todo.

Now here it is all together:

```js
todos.forEach(function(todo) {
    console.log(todo.text);
});
```

### 2. `.map`

The `.map` method is structured as follows:

- **`const todoText =`** : this method actually returns an array, so you need to assign a new variable. Because what we're doing is looping through and the return an array of just the text values.

- **`todos.map`** : this declares the method for the given object.

- **`(function(todo)`** : this establishes the function we'll take in as our first parameter.

- **`{return todo.text;});`** : this returns the text for each instance of the todo function that is mapping to the todos array.

Now here it is all together:

```js
const todoText = todos.map(function(todo) {
    return todo.text;
});
```

### 3. `.filter`

The `.filter` method is structured as follows:

- **`const todoCompleted =`** : this method actually returns an array, so you need to assign a new variable. Because what we're doing is looping through and the return an array of just the values that meet a certain condition.

- **`todos.filter`** : this declares the method for the given object.

- **`(function(todo)`** : this establishes the function we'll take in as our first parameter.

- **`{return todo.isCompleted === true;});`** : this returns the values for each instance object in the todos array that meets our filter criteria.
 
Now here it is all together:

```js
const todoCompleted = todos.filter(function(todo) {
    return todo.isCompleted === true;
});
```

We can also chain these methods together.

For example, if I just wanted the text of the array items we filtered as true, we could add `.map` to the end of the entire `.filter` function above:

```js
const todoCompleted = todos.filter(function(todo) {
    return todo.isCompleted === true;
}).map (function(todo) {
    return todo.text;
});
```

### 4. `.sort`

This is similar to the above, but is meant explicitly meant to take a function and sort it by two variables at a time, iterating with a value of 1 or -1 to sort it within the array.

For example, imagine we want to sort the following array by start date:

```js
const companies = [
  {name: "Company One", category: "Finance", start: 1981, end: 2003},
  {name: "Company Two", category: "Retail", start: 1992, end: 2008},
  {name: "Company Three", category: "Auto", start: 1999, end: 2007},
  {name: "Company Four", category: "Retail", start: 1989, end: 2010},
  {name: "Company Five", category: "Technology", start: 2009, end: 2014},
  {name: "Company Six", category: "Finance", start: 1987, end: 2010},
  {name: "Company Seven", category: "Auto", start: 1986, end: 1996},
  {name: "Company Eight", category: "Technology", start: 2011, end: 2016},
  {name: "Company Nine", category: "Retail", start: 1981, end: 1989}
];
```

Then we could run the following `.sort` function:



```js
const sortedCompanies = companies.sort(function(c1, c2){
    if(c1.start > c2.start) {
        return 1;
    }   else {
        return -1;
    }
});
```

We could use ternary operators and the arrow function syntax (more on that later) to make this even simpler.

```js
const sortedCompanies = companies.sort((c1, c2) => (c1.start > c2.start ? 1 : -1));
```

### 5. `.reduce`

Reduce can be used to combine all the items in an array into one value.

For example, let's say we wanted to calculate the total years for all companies, we could run the following `.reduce` function:

```js
const totalYears = companies.reduce((total, company) => total + (company.end - company.start), 0);
```

This function is actually performing a similar function to a `for` loop. It is iterating from a set starting point (the `0` in the `company` variable) and then iterating through and racking up a total.

---
>### **Example of how we can simplify existing functions using higher order functions**
>---
>Imagine we have the following array:
>```js
>const ages = [33, 12, 20, 16, 5, 54, 21, 44, 61, 13, 15, 45, 25, 64, 32];
>```
>Now, what if we want to just fetch the ages where drinking is legal?
>
>There are three options:
>
>The first is to use a `for` loop:
>
>```js
>const canDrink = []; 
>     for(let i = 0; i < ages.length; i++) {
    >       if(ages[i] >= 21) {
        >           canDrink.push(ages[i]);
    >   }
>};
>```
>Messy, right?
>
>The second way is to use a basic `.filter` function:
>```js
>const canDrink = ages.filter(function(age)) {
    >   if(age >= 21) {
        >       return true;
    >   }
>};
>```
>
>Much, better. But we can go one step further by using the arrow function syntax on the `.filter` function from before.
>
>```js
>const canDrink = ages.filter(age => age >= 21);
>```
>
>Wow! Now the whole function fits on  single line, but outputs the same thing.
>
>.

---

## Conditionals

Conditionals allow us to set certain logical conditions for our functions.

### 1. `else if`

For example, let's say:

```js
const x = 10;
```

So…

```js
if(x === 10) {
    console.log('x is 10');
}
```
>*(the difference between the `===` and the `==` is that the double equal just measures equal value whereas triple equal also measures data type)*

We can also account for the counterfactual with

```js
else {
    console.log('x is NOT 10');
}
```

These statements can be strung together to account for multiple contingencies by using `else if`.

For example: 

```js
if(x === 10) {
    console.log('x is 10');
} else if(x > 10) {
    console.log('x is greater than 10');
} else {
    console.log('x is less than 10');
}
```

### 2. Ternary Operators

Ternary operators are a shorthand for the `else if` conditional.

They are structured as follows:

```js
const x = 11;

const color = x > 10 ? 'red' : 'blue';
```

In this case, logging the console will return `red`, because the variable `x` meets the condition `> 10`.

### 3. `switch` conditionals

Switches are another way to evaluate a condition, which unlike ternaries are more suited to evaluating multiple cases.

They are structured as follows:

```js
switch(color) {
    case 'red':
        console.log('color is red');
        break;
    case 'blue':
        console.log('color is blue');
        break;
    default:
        console.log('color is NOT red or blue');
        break;
}
```

---

## Functions