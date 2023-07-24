## Lessons Summary
- when execution JavaScript executes the code line by line known as thread of execution
- execution context created to run code of a function and has two parts
  + Thread of execution
  + Memory
- call stack it's a data structure used in JavaScript we add to it the function to run and when we finish urnning of the function JS removes it from call stack, we are running the thing on the top of the stack
- i learn how the JavaScript code and functions executing
- we can pass a function to another one as an argument
- functions in JavaScript is first class object can be assigned to variables, properties, passed as arguments to other functions and returnde as values
- i learn what is the callback, arrow function and anonymous function
- what is pair programming 
## Coding Examples
```
//The declaration of a function that retrun 100
function temSquared()
{
  return 10*10;
}
tenSquared() //Calling the function
// not a good solution
```
 
## Coding Exercises
- Use higher-order functions map, filter or reduce to solve a complex problem
  
```
  const squareList = arr => {
  // Only change code below this line
  return arr
  .filter(s => s>0 && s%parseInt(s)===0)
  .map(s => s*s);
  // Only change code above this line
  };

  const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
  console.log(squaredIntegers);
```
- Apply functional programming to convert strings to URL slugs
  ```
    // Only change code below this line
    function urlSlug(title) {

    let temp = title.toLowerCase().trim().split(" ");
    temp = temp.filter(s => s.length > 0)

    temp = temp.join("-");
    return temp;


    }
    // Only change code above this line
    urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
    //a-mind-needs-books-like-a-sword-needs-a-whetstone
  ```

- Question 1: Functions and Callbacks

```

function mapAsync(array, callback) {
  return new Promise((resolve, reject) => {
    const mappedArray = [];
    let completedCount = 0;

    function processElement(index) {
      callback(array[index])
        .then((result) => {
          mappedArray[index] = result;
          completedCount++;

          if (completedCount === array.length) {
            resolve(mappedArray);
          }
        })
        .catch((error) => {
          reject(error);
        });
    }

    for (let i = 0; i < array.length; i++) {
      processElement(i);
    }
  });
}
const array = [1, 2, 3, 4, 5];

function asyncCallback(element) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(element * 2);
    }, 1000);
  });
}

mapAsync(array, asyncCallback)
  .then((result) => {
    console.log(result); // [2, 4, 6, 8, 10]
  })
  .catch((error) => {
    console.error(error);
  });

```

- Question 2: Call Stack and Recursion

```
let sum = 0;
const sumRange = (range) => {
  if (range > 0) {
    sum += range;
    sumRange(range - 1);
  }
};
sumRange(4);
console.log(sum); //This will print 10

```
