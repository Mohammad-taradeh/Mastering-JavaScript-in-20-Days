## Lessons Summary:
- how (x++) works and how realy the value will be changed
- there are two ways for that prefix (++x) and postfix (x++) and what each one does
- when we add string and number the result will be as a string
- when we use the plus plus way JavaScript parse the value to number first
- in JavaScript everything isn't an object they could act like objects
- Primitive Types in JS: undefined, string, number, boolean, object, symbol
- functions and arrays are objects but what listed above isn't
- in Js variables don't have types, values do
- bight isn't an IEEE number
- undefined vs. undeclared vs. uninitialized
- special balues: NAN ("not a number"),
- the variables with NAN value dosn't equal itself
- Negative Zero
## Coding Examples

```
var x = 40;

x++;   //40
console.log(x);     //41

++x;  //42
console.log(x);     //42
```

```
var x;
typeof x;  //"undefined"
x ="5";
typeof x;  //"string"
x = x + 1;  //"51"
typeof x;  //"number"

x++;        //51
console.log(x) //52
```

```
typeof tomato;  //"undefined"

var v = null;
typdof v;    //"object"

v= function(){};
typdof v;    //"function"

v = [1, 2, 3];
typdof v;    //"object"
```
## Coding Exercises

**Question 1**

```
function convertStringToNumber(input) {
  if (typeof input === "string") {
    const convertedValue = +input;
    if (!Number.isNaN(convertedValue)) {
      return convertedValue;
    }
  }
  return { value: input, type: typeof input };
}

```

**Question 2:**
```
const checkNaN = (value) => {
  return Number.isNaN(value);
};

```
**Question 3:**
```
function isEmptyValue(value) {
  return value === undefined || value === null || value === "";
}


```
**Question 4**
```
function compareObjects(input1, input2) {
  if (typeof input1 !== "object" || typeof input2 !== "object") {
    return [input1, input2];
  }

  const keys1 = Object.keys(input1);
  const keys2 = Object.keys(input2);

  if (keys1.length !== keys2.length) {
    return false;
  }

  for (const key of keys1) {
    if (!keys2.includes(key) || input1[key] !== input2[key]) {
      return false;
    }
  }

  return true;
}
```
**Question 5**
```
const complexCoercion = (input) => {
  // Check if the input is a primitive type
  if (typeof input !== "object" && typeof input !== "function") {
    if (typeof input === "number") {
      // Convert number to string and then return as a boolean
      return Boolean(input.toString());
    } else if (typeof input === "string") {
      // Return the boolean representation of the string
      return Boolean(input);
    } else if (input === null || input === undefined) {
      // Return false for null or undefined values
      return false;
    }
  }

  // If input is not a primitive type, return the argument as is
  return input;
};
```
