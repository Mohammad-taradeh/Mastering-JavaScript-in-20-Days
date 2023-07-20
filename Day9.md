## Lessons Summary
- The Object Oriented Programming allows us write easy ro reason about, easy to add features and nevertheless efficient and performant
- Understandinig the difference between \_\_proto_\_ and prototype
- The new and class keywords as tools to automate our object and method creation
- store function with their associated data
- we can create empty object and assign properties to that object (using dot notation)
- object.create(null) return us an empty object
- the prototype chain is used to store the functions of objects to one object and all other ones can use that function
- each object has a _\_\_proto_\_  and by default it's linked with object.prototype
- new keyword used either to create a new object
## Coding Examples
```
const user = {
  name: "Mohammad",
  age: 21,
  increment: function () {
    this.age++;
    return this.age;
  },
};

console.log(user.increment()); // 22
```
this is using object.create() method

```
function userConstructor(name, score) {
  const newUser = Object.create(null);
  newUser.name = name;
  newUser.score = score;
  newUser.increment = function () {
    newUser.score++;
  };
  return newUser;
}
const user1 = userConstructor("Mohammad", 1);
const user2 = userConstructor("Ahmad", 2);
user1.increment();
console.log(user1, user2); //this will pring the two objects user1 and user2
```
## coding Exercises

**I used this email to solve the exercise on freecodecamp: 201160@ppu.edu.ps**

