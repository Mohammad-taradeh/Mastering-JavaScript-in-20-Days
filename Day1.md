# This is my first day of mastering JavaScript
## I learn what is JavaScript and what it's used for.

**JavaScript:** it's a programming language used to build the logic of websites and to make the websites responsive and to make the website communicate with the server (build the server side code)

**Where we can typw JavaScript code?**
We can write JavaScript code on the browser, local text file editor like Vs code or using online playground like CodePen.

## Document Object Model (DOM)
We can write JavaScript code using the website's console to manipulate it and the changes that the code does will be rendered to the website.
we can use command like:
- document.title This will return the title of the page (document).
- document.boby This will return the body element
- document.body.children This will return the elements inside the body
- document.getElementById("tomato") This will return the element with id = "tomato"
- document.querySelector("#tomato") This is same as the previous one 
- document.getElementByClassName("potato") This will return the elements with className = "potato"
- document.querySelector(".potato") This is same as the previous one 
- document.getElementByTagName("button") This will return all the button elements
- document.querySelectorAll("h1") This will return all the h1 elements or return the elements that has a common class name 
- We can use (.length) to return the number of elements will be returned using one of the previous codes
- We can use (.textContent) to return the content of an element or to change the content of that element
- We can use (.append) to append something to a specific element

## Values and Data Types
**Values:** are chunks of information and it can be of different types
**Data Types:** the type of that chunks of information and there are two kindes of data
- primitive types like (String, Number, boolean, undefined, null)
- Objects like (document)
**We can use (typeof) to tell us the type of the value**
- String : like "Mohammad", 'Mohammad', \`Mohammad`.
- Number : like 1,2,3...
- Boolean: True or False.
- Undefined : accidental nothing
- Null : deliberate nothing

  **String**
  
- String's made of characters and each one has a number start from 0 which known as index so we can use the (.length) and we will have the number of characters the string is made of (number).
- We can use (.indexOf ("x")) and that will return the index of "x" in the given string and can be used for substring(number).
- We can use (.includes("abc:)) to know if that string contains "abc" or not (boolean).
- We can use (.startsWith("Mohammad")) to know if the string starts with mohammad or not (boolean).
- We can use (.toLowerCase()) to make all characters in lower case same as to (.toUpperCase()) (string).

## Operators
- **Binary Operators like**
  + **Arthmetic Operator**
    - \+ add
    - \- subtract
    - \* multiply
    - / divide

  + **Comparison Operator**
  This will return a boolean value all the time
    - \> greater than
    - < less than
    - \>= greater than or equal to
    - <= less than or equal to

  + **Equality Operator**
      - Strict (===), (!==)
      - Loosey-goosey (==), (!=)

   
- **Unary Operators**
    - Increment (++)
    - Decrement (--)
    - Logical Not (!)


**That how i solve Compound Assignment With Augmented Multiplication**

![image](https://github.com/Mohammad-taradeh/Mastering-JavaScript-in-20-Days/assets/98043145/e430b1ff-eb1e-4be5-a5f8-9be2de123fb7)


**That how i solve Concatenating Strings with the Plus Equals Operator**

![image](https://github.com/Mohammad-taradeh/Mastering-JavaScript-in-20-Days/assets/98043145/5145ca6a-5a4f-4d4e-b1cb-b1a0af814659)

**That how i solve Use Bracket Notation to Find the Nth-to-Last Character in a String**

![image](https://github.com/Mohammad-taradeh/Mastering-JavaScript-in-20-Days/assets/98043145/20e01844-abcb-47df-9223-7edd06b7ec33)
