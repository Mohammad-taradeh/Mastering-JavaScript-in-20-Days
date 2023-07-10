# This Is My Third Day Of Mastering JavaScript In 20 Days


## Lessons Summary
- Web browser fires many events when something hppend, so we need to handle this events , so the JS offers many methods to handle this events.
- Conditional statement like "if" statement let us run the code under certain conditions.
- JS can only do one task at a time ("single-threaded").
- Some actions needed a lot of time to run like "waiting from user events " ,so we use an asynchronus code for it .
- "setTimeout" method is used to delay action.

## Coding Examples
```
// loops Examples
const numbers = [1,2,3];

for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}

for (let n of numbers) {
    console.log(n);
}
-----------------------------------------------------
// map and filter Examples
//From the spices array, use map and filter to create a new array endInY with just the girls whose nickname ends in "y"
const spices = [
    {name: "Emma", nickname: "Baby"},
    {name: "Geri", nickname: "Ginger"},
    {name: "Mel B", nickname: "Scary"},
    {name: "Mel C", nickname: "Sporty"},
    {name: "Victoria", nickname: "Posh"}
];
let endInY=spices.filter(s=>s.nickname.endsWith("y"));

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
