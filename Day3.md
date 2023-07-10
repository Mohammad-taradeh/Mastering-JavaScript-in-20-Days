# This Is My Third Day Of Mastering JavaScript In 20 Days


## Lessons Summary
- Comments is important in JS, it Help others (and yourself)understand your code.
-  Arrow function is unnamed function without much code.
- Scope determines where variables are "in play".
- There is a difference between "let" and "var" in their scope

## Coding Examples
```
// Example 1: declare the following functions :
//1. multiply: given 2 numbers, return their product
 function product(n1,n2)
 { return n1*n2;
 }
 //2.longerThan: given 2 arrays, return whether the first is 
 longer than the second
 function longerThan(a1, a2) {
 return a1.length>a2.length;
 }

 //Example 2 :declare function using arrow functions:

//divide: given 2 numbers, return the first divided by the second
 
 const divide=(n1,n2)=>n1/n2;

```


## coding Exercises
Return a Value from a Function with Return
```
function timesFive (n) {
  return n * 5;
};
```

Global Scope and Functions
```
let myGlobal = 10;
function fun1() {
  // Assign 5 to oopsGlobal here
myGlobal = 5;
console.log(myGlobal) // 5
}
console.log(myGlobal) // 10

// Only change code above this line
```

Local Scope and Functions
```
function myLocalScope() {
  // Only change code below this line
let myVar;
  console.log('inside myLocalScope', myVar); // inside myLocalScope undefined
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar); // ReferenceError: myVar is not defined
```

Global vs. Local Scope in Functions
```
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
let outerWear = "sweater";
  // Only change code above this line
  return outerWear;
}

console.log(myOutfit()); // sweater
```
stand in line
```
function nextInLine(arr, item) {
  // Only change code below this line
 
  arr.push(item);
  return arr.shift();
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr)); // [1,
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
