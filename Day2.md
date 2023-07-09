# This Is My Second Day Of Mastering JavaScript In 20 Days

## Expressions
An equation that will be evaluated to a value (True or False)


## Variables
We should use camelCase to declare variables

- **Decalring a variable:** like (let myVar) here the initial value of myVar is undefined.
- **Assigning a variable:** like (myVar = "Mohammad").
- **We can do it both in the same line of code:** like (let var = 123).

**Note** we can declare a variable using const keyword but we will be able to assign it a value just one time.

**There ara different types of variables**
1- var: we can dclare a variable using var like 
```var x;
x =10;```
it's known as function scoop variable

2- let: thst's how we can delcare a variable using let
``` let myName = "Mohammad```
it's a block scooped variable

3- const: it's same as let but the difference is it can be assigning just one time
```const y = 10;
y = 5 //This will raise an error
```

variables dosen't containg a value it points to values which means it's a pointer containg the address where that value exists in memory

### What is the difference between expressions and statements 
statement tells JavaScript to do something like (declare or assign a variable).
expression is like question we ask JavaScript and it will tell us the answer.


## Array
it's a way to keep multiple values togather in a single collection like
``` let names = ["Mohammad", "Ahmad", "Ibrahim"]; ```
and it has a length and each value has an index.
we can check if the array contains a certin vlue using our previous example we want to check if the array names contain a value called Mohammad.
```names.includes("Mohammad"); // in this example it will return True;```
but unlike strings we can modify an arras
```
let firstNameInTheArray = names.pop(); // this will return the value with index 0  delete the first element in the array names
names.push("Mostafa") // this will add "Mohstafa" to the array names
```
The array could be empty or have a single value or multiple values and with different types like:
``` let array = ["Mohammad", 5, {name: "Ahmad", age: 25}, True]```

we can sort the array elements using .sort() ``` names.sort();```.
.concat() used to cantinate two arrays like: ```[1, 2, 3].concat([4, 5, 6]);```
.join() usen to join all the values in the array usnig some string between each value 
```["lions", "tigers", "bears oh my!"].join(" & ") // the output: lions & tigers & bears oh my!```

- Mutable data can be edited like arrays
- Immutable data always stays the same like strings and other primitives

some actions mutate an array like 
``` oldArray.push(newValue)```
change the array in-place

other actions don't mutate the original array but instead create a new copy like:
```oldArray.concat(otherArray)```
dosn't change the oldArray.

note that variables also could be immutable like const

## objects
objects collect multiple values togather to describe more complex data also let us point at related values using properties in the object.
```const js = {
    name: "JavaScript",
    abbreviation: "JS",
    isAwesome: true,
    officialSpec: "ECMAScript",
    birthYear: 1995,
    creator: "Brendan Eich"
};```
we can use property values like this
``` js.name.startsWith("Java"); // this will return ture
let age = 2023 - js.birthYear; // age = 28
````
**Exercise:** Create an object representing you
```const mohammad = {
    name: "Mohammad",
    home: "Hebron",
    languages: ["English", "Arabic"],
    pet: null,
    vehicle: null,
    hobbies: ["travel", "programming", "gaming"]
};```

Properties can point to functions too We call function-properties "methods" on objects

we have already worked with objects which is the document object
**note:** Strings are primitive values (not objects) but JS automatically wraps them in String objects 

**That is my solution for Profile Lookup**

![image](https://github.com/Mohammad-taradeh/Mastering-JavaScript-in-20-Days/assets/98043145/0791253c-0b67-4ccd-a67b-a6502b5a3884)

**That is my solution for Copy Array Items Using slice()**
![image](https://github.com/Mohammad-taradeh/Mastering-JavaScript-in-20-Days/assets/98043145/b696d01c-1149-4e21-a523-4cba06d40cab)

**That is my solution for Combine Arrays with the Spread Operator**
![image](https://github.com/Mohammad-taradeh/Mastering-JavaScript-in-20-Days/assets/98043145/ae4c0cd1-c511-4638-8f24-0ce5088e9288)
