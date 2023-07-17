
## Lessons Summary
- closure (scope and execution eontext)
- we use closure to not re-execute the entire function every time i want a specific thing in that function
- we can call the 'backpack' as :
    + Closed Over 'Variable Environment' (C.O.V.E)
    + Persistent Lexical Scope Referenced Data (P.L.S.R.D)
    + 'Backpack'
    + 'Closure'
- the closure of live data is attached addTwo (then to generatedFunction) though a hidden property known as [[scope]] which persists when the inner function is returned out
## Coding Examples
```
function createFunction() {
  function addTwo(num) {
    return num * 2;
  }
  return addTwo;
}

const generatedFunction = createFunction();
const result = generatedFunction(5);
console.log(result);//This will print 10
```
## coding Exercises
**Question 1:**
```
function createCounter(start) {
  let counter = start;
  return function increment() {
    return counter++;
  };
}
const myincrement = createCounter(5);
myincrement();
console.log(myincrement());
```

**Question 2:**
```
function calculateAverage(nums) {
  let sum = 0;
  let count = 0;
  function average() {
    nums.forEach((element) => {
      sum += element;
      count++;
    });
    return sum / count;
  }
  return average;
}

const numbers = [1, 2, 3, 4, 5];
const avrageFunction = calculateAverage(numbers);
const averageResult = avrageFunction();
console.log(averageResult);//This will print 3
```

**Question 3:**
```
function powerOf(base) {
  function calculate(exp) {
    return Math.pow(base, exp);
  }
  return calculate;
}

const myFunction = powerOf(2);
const result = myFunction(4);
console.log(result);//This will pring 2^4 which equals 16
```

**Question 4:**
```
function compose(...functions) {
  return function (value) {
    return functions.reduceRight((result, fn) => {
      return fn(result);
    }, value);
  };
}
function addOne(num) {
  return num + 1;
}
function double(num) {
  return num * 2;
}
function square(num) {
  return num * num;
}

const composedFunction = compose(square, double, addOne);
console.log(composedFunction(2));
```
