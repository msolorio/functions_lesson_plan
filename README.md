# Lesson objectives

_After this lesson students will be able to:_

* Define a function
* Understand function parameters and arguments
* Define a function with a return value
* Combine functions with conditionals and loops

---

# FUNCTIONS

<!-- ### REVIEW

Conditions let us control whether or not a piece of code will inside a block of code. `{...}`

```javascript
const isSunny = false;

if (isSunny) {
	console.log('Lay out in the grass');
}
```

Loops let us _repeat_ lines of code within a block `{ ... }` according to our instructions:

```javascript
const num = 0;

while (num < 5) {
	console.log('Are we there yet?');
	num++;
}
```

```js
const fruits ['apple', 'banana', 'orange', 'pear'];

for (let i = 0; i <= 5; i++) {
	console.log(fruits[i]);
}
``` -->

## WHAT IS A FUNCTION?

Functions are a powerful construct in programming that allow us to organize our programs into chunks. We can think of a function like a black box that take in some input and returns an output.

![Function-Machine](./images/function_machine.png)

Say for example, we wanted a function that would tell us the first item on our grocery list. We could create a function that would take a grocery list as its input and return the first item on the list as its output.

## DEFINING A FUNCTION

We will start with the basic structure for now and not worry about inputs and output.

To define a function we include the `function` keyword followed by the function name, a set of parentheses and then the body of the function.
```javascript
function func() {
	console.log('This should be called later');
}
```
This code by itself will not run. To run this code we can call or **invoke** the function like so.

```js
func();
```
To call the function simply include the name of the function followed by a set of openning and closing parentheses.

### WHY FUNCTIONS?

Functions give the ability to organize our code into chunks and give those chunks names. This makes the code easier to understand and to reason about.

Functions allow us to store a line of code to be used as many times as we wish. This saves us from having to rewrite the same code many times and follows the DRY principle (Don't Repeat Yourself). 

<br>
<hr>

## CALLING A FUNCTION MANY TIMES

A function can be called many times and in this case will give us the same output every time.
```js
function logAlert() {
  console.log('Ah ah ah... you didn\'t say the magic word.');
}

logAlert();
logAlert();
logAlert();
logAlert();
logAlert();
```

## PARAMETERS

Functions can take in information and then act on that information in the form of **parameters**.

In this case the `printGreeting` function takes in a name **parameter** and prints out a custom message with the name inserted.
```js
function printGreeting(name) {
  console.log(`Welcome ${name}`);
}

const firstName = 'Yash';

printGreeting(firstName);
```
When calling `printGreeting(firstName)` the value we pass to it is refered to as an **argument**. When defining the function the values pass in are refered to as **parameters**.

## PASSING MULTIPLE PARAMETERS

We have the ability to pass many parameters to a function.

We've set up this function to take in 3 parameters and print out a longer greeting with the three values inserted.

```js
function printLongGreeting(name, numberOfMessages, dayOfWeek) {
  console.log(`Welcome ${name}. Today is ${dayOfWeek}. You have ${numberOfMessages} messages.`);
}

printLongGreeting('Sam', 12, 'Friday');
```

Often we will pass variables as the arguments to the function when we call it.
```js
const userName = 'Roberta';
const usersMessages = 30;
const currentDayOfWeek = 'Thursday';

printLongGreeting(userName, usersMessages, currentDayOfWeek);
```

## EXCERSIZE

Write a function that will log out a person's order at a restuarant, that takes in three **parameters**, the person's name, a menu item, and their table number.

<details>
  <summary>Solution:</summary>

  ```js
  function printOrder(orderName, menuItem, tableNumber) {
    console.log(`${menuItem} for ${orderName} at table #${tableNumber}`);
  }
  ```
</details>

## RETURNING A VALUE FROM A FUNCTION

A function can also return a value.
This function takes in 2 numbers and returns the sum of those numbers.
```js
function getTheSum(a, b) {
  return a + b;
}

const totalApples = 20;
const totalBananas = 10;

// Simply calling the function will not do anything in this case.
getTheSum(totalApples, totalBananas);

// Instead, that return value can be stored in a variable for later use, like so.
const sum = getTheSum(totalApples, totalBananas);

console.log(sum);
```

## MORE PRACTICE WITH RETURN

This function takes in 3 pieces of information, the itemName, the price, and the mustGoByDate, and prints out a message using those 3 pieces of information.
```js
function returnAdMessage(itemName, price, mustGoByDate) {
  return `I am selling ${itemName} for ${price}. It must go by ${mustGoByDate}.`;
}

const item = 'Lamp';
const price = 50;
const date = 'tomorrow';

const message = returnAdMessage(item, price, date);

console.log(message);
```
The function returns a value. We can store this return value in a variable and then log out the variable.



This function takes in 3 pieces of information, breakfastItem, currentDayOfWeek and the rating and returns a message using those 3 pieces of information.

```js
function printBreakfast(breakfastItem, day, rating) {
  return `Today is ${day}. I ate ${breakfastItem}. I give a ${rating} out of 10`;
}

const todayBreakfast = 'Omelet';
const today = 'Monday';
const breakfastRating = 6;

const message = getMessage(todayBreakfast, today, breakfastRating);

console.log(message);
```


<!-- // REVIEW ON FOR LOOPS

This will add up all the numbers from 0 to 9 and log out the total.

```js
let numbersSum = 0;

for (let i = 0; i < 10; i++) {
  numbersSum += i;
}

console.log(numbersSum);
``` -->

## CONDITIONALS WITH FUNCTIONS

This function returns a message based on if the value passed in (hasFood) is true or false.

```js
const hasFoodInFridge = false;

function getFoodMessage(hasFood) {
  if (hasFood) {
    return 'You are good to go';
  } else {
    return 'Time to get some groceries';
  }
}

const foodMessage = getFoodMessage(hasFoodInFridge);

console.log(foodMessage);
```
Because the function returns a value, in order to get access to the value we store it in a variable with...
```js
const foodMessage = getFoodMessage(hasFoodInFridge);
```
After that we can log out the variable.

## MORE CONDITIONALS WITH FUNCTIONS

This function will return a message based on if isAdmin and isLoggedIn is true.

```js
function getLoginMessage(isAdmin, isLoggedIn) {
  if (isLoggedIn && isAdmin) {
    return 'Welcome admin user.';

  } else if (isLoggedIn && !isAdmin) {
    return 'Welcome website user.';
    
  } else {
    return 'You are not logged in.';

  }
}

const loginMessage = getLoginMessage(false);
console.log(loginMessage);
```

Hopefully we are starting to see how we can use functions to our advantage here. We can think of functions like a black box that take in some input and return an output. When we call our function we need to know about all the details happening inside. When calling the function we are just concerned with the information we give it, the **parameters** and the value that is outputed, the **return value**.

<details>
  <summary>Here is the visual again</summary>

  ![Function-Machine](./images/function_machine.png)
</details>


## BREIF REVIEW ON FOR LOOPS

Here we loop through each student in the list and log them out.

```js
const students = [
  'Shawna',
  'Sam',
  'Sri',
  'Simone'
];

for (let i = 0; i < students.length; i++) {
  console.log(students[i]);
}
```

## COMBINING LOOPS WITH FUNCTIONS

This function will loop through the list that is provided and if it finds an item that matches itemToCheck it will return true. If the itemToCheck is not found in the list, the function will return false.
```js
const groceryList = [
  'spanich',
  'beans',
  'eggs',
  'watermelon',
  'blueberries',
];

function listHasItem(list, itemToCheck) {
  for (let i = 0; i < list.length; i++) {
    if (list[i] === itemToCheck) {
      return true;
    }
  }

  return false;
}

const hasItem = listHasItem(groceryList, 'soup');

console.log(hasItem);
```

This function will loop through a list and return a formatted version of the list turned into a string.

```js
function getGroceryList(list) {
  let stringResult = '';

  for (let i = 0; i < list.length; i++) {
    stringResult += `${i + 1}. ${list[i]}\n`;
  }

  return stringResult;
}

const coolGroceryList = getGroceryList(groceryList);

console.log(coolGroceryList);
```

## FUNCTIONS AND ARRAYS

We learned that arrays are a very handy way of storing related data. Let's take a look at combining them with functions.

### ACTIVITY 1

Write a function that takes in an array of grocery items as a **parameter** and returns just the first item in that list.

<details>
  <summary>Solution: </summary>

  ```js
  function getFirstItem(groceryList) {
    return groceryList[0];
  }

  const myList = ['spinach', 'tomato sauce', 'pickles'];

  const firstItem = getFirstItem(myList);

  console.log(firstItem);
  ```
</details>

### ACTIVITY 2

This time write a function that will take in an array of grocery items and return the array with the first item removed.

For example, our function should take this as a **parameter**
```js
const myList = ['spinach', 'tomato sauce', 'pickles'];
```
and return this.
```js
['tomato sauce', 'pickles'];
```

Do some research to see how you can remove the first item from an array.

Hint: Google `javascript remove first item from array`.

<details>
  <summary>Solution:</summary>

  Eventually you may come across the [shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) method with JavaScript.

  Read the [documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) take a moment to see if you can understand how it's working.

  ```js
  function removeFirstItem(groceryList) {
    groceryList.shift();

    return groceryList;
  }

  const myList = ['spinach', 'tomato sauce', 'pickles'];

  const updatedList = removeFirstItem(myList);

  console.log(updatedList);
  ```
</details>

### ACTIVITY 3

Write a function that takes an array of grocery items as its first **parameter** and a grocery item as its second **parameter**. This function should return true or false indicating whether or not the array includes the item.

Calling the function would look like this.

```js
const hasItem = doesListHaveItem(myGroceryList, item);
```

Do some research to see how to check if an array includes an item.

Hint: Google `javascript check if array has a particular item`.

<details>
  <summary>Solution:</summary>

  After googling you might eventually come across the [`.includes`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) method with JavaScript.

  Read the [documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) take a moment to see if you can understand how it's working.

  ```js
  function doesListHaveItem(groceryList, itemToCheck) {
    return groceryList.includes(itemToCheck);
  }

  const myList = ['spinach', 'tomato sauce', 'pickles'];

  const hasItem = doesListHaveItem(myList, 'cookies');

  console.log(hasItem);
  ```
</details>

## FUNCTION EXPRESSIONS

A function expression is another way to define a function. Here we define a function without a name and store it in a variable.

```js
const newFunction = function() {
  console.log('newFunction was called!');
}

newFunction();
```
Defining a function without a name, as we do on the right hand side of the equal sign is referred to as defining an anonymous function.

## ARROW FUNCTIONS

A newer version of JavaScript (ES6 / ES2015) allows us to write a function with the following syntax.

```js
const anotherFunction = (name) => {
  console.log(`Hey ${name}, anotherFunction was called!`);
}

anotherFunction('Lenny'); 
```

# Extra stuff: more on built-in methods

## String and array methods

**Refresher**

A method can be chained to a variable to perform an action. Example:

```javascript
const message = "hello there";

console.log(message.toUpperCase());
```

> => "HELLO THERE"

`.toUpperCase()` is a **method**.

<br>


## Datatypes

There are different methods for different **datatypes**.

Strings have different methods than arrays. In general, you can't use array methods on strings and vice versa.

Example of an **array** method:

```javascript
const letters = ['A', 'B', 'C', 'D'];

console.log(letters.join(''));
```

> => ABCD

`.join()` is a **method**, but it is only for arrays.


It will not work on a string:

```javascript
const letters = "ABCD";

console.log(letters.join(''));
```

![](https://i.imgur.com/Ire2ntQ.png)

> Here, `letters.join` is not a function because `.join` is not a method you can use on strings. See: TypeError


**.length is a method you can use on both strings and arrays**

<br>

## Methods can change the datatype

If we use `.join('')` on an array as intended:

```javascript
const letters = ['A', 'B', 'C', 'D'];

console.log(letters.join(''));
```

It will however output a **string**. Be mindful of this when it comes to **chaining methods**.

For example `.reverse()` is an **array** method.

```
console.log(letters.join.reverse());
```

![](https://i.imgur.com/NuPCUDB.png)

It will not work because the result of `letters.join('')` is a string.

<br>

## Chaining built-in methods

You can chain methods together:

```javascript
const str = "doodly doo";

console.log(str.split('').length);
```

> => 10

**Be mindful of datatypes**

This will not work:

```javascript
const str = "doodly doo";

console.log(str.split('').toUpperCase);
```

![](https://i.imgur.com/LDYjytH.png)

&#x1F535; **Why Not?**

Notice the error says `TypeError`. This is a big indicator as to what the problem is.

We are trying to use `.toUpperCase()` on the wrong type of data. In this case, we are trying to use it on an array, when it is not an array method. It is a string method.

&#x1F535; **Activity**

RESEARCH

How can you reverse a string?

* Try to use `.reverse()` on a **string**. Does it work?

* If it does not work, what is the error telling you?

* Try to use `.reverse()` on an array instead. Does it work?

There is no `.reverse()` method for strings, but there _is_ one for arrays.


&#x1F535; **Activity**

Using method chaining, figure out how to turn a string into an array, reverse the array, and turn the reversed array back into a string. This is one way to reverse a string. Chain the methods together on one line.

[Some string methods](https://www.w3schools.com/js/js_string_methods.asp)

[Some array methods](https://www.w3schools.com/js/js_array_methods.asp)

<br>

&#x1F535; **Extra**

Look into `regular expressions` and the [.match()](https://www.w3schools.com/jsref/jsref_match.asp) method. Use `.match()` only to select parts of a reversed string that match a pattern.

&#x1F535; **Extra**

Start in on this [regular expressions](https://regexone.com/) exercise.

<br>
<hr>

