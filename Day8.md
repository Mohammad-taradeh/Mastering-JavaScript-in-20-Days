## Lessons Summary
- JavScript is single threaded and synchronously executed
- The use of setTimeOut() function and JS dosn't has a timer but the web browser has and JS deals with it
- The job of JS to do when we call setTimeout(fun,value) is to set the value to the timer in the web browser and on completion of the timer JS call the function fun and push the callback(fun) to the callback queue
-  We use the command document in JavaScript to deal with the DOM of the web
-  We use fetch command in JavaScript to deal with network requests which it's not a part of JS
-  Event loop: when a callback queue has a function to run and keep checking the call stack if it's empty
-  As a solution of that we use two-pronged to
    + initiate background web browser word and
    + return a placeholder object(promise) immediatelly in JavaScript
- .then used to do something when the promise is fulfilled
- what function we will add to each one of call stack, callback queue and microtask queue and how they work
## Coding Examples
  ```
function printHello() {console.log("Hello");}
setTimeout(printHello, 1000);
console.log("Me first");
//This will print:
//Me first
//Hello 
```
```
function printHello() {
  console.log("Hello");
}
//this will tell the broweser to start timer with value = 0
//then the browser add printHello to callback queue
setTimeout(printHello, 0);
function block() {
  for (let i = 0; i < 3000000000; i++) {
    1 + 1;
  }
}
block();//Here we call block function
console.log("Me first");//This will be printed
//then we execute the printHello from callback queue
```
## coding Exercises
**Question 1**
```

const task1 = (cb) => setTimeout(() => {
    const message = "Task 1 has executed successfully!";
    cb(message);
  }, 3000)
  
  const task2 = (cb) => setTimeout(() => {
    const message = "Task 2 has executed successfully!";
    cb(message);
  }, 0)
  
  const task3 = (cb) => setTimeout(() => {
    const message = "Task 3 has executed successfully!";
    cb(message);
  }, 1000)
  
  const task4 = (cb) => setTimeout(() => {
    const message = "Task 4 has executed successfully!";
    cb(message);
  }, 2000)
  
  const task5 = (cb) => setTimeout(() => {
    const message = "Task 5 has executed successfully!";
    cb(message);
  }, 4000)
  
  const asyncTasks = [task1, task2, task3, task4, task5];
  
  const executeInSequenceWithCBs = (tasks, callback) => {
    if (tasks.length === 0) {
        callback([]);
        return;
      }
    
      const [currentTask, ...remainingTasks] = tasks;
      const results = [];
    
      function executeTask(index) {
        if (index === tasks.length) {
          callback(results);
          return;
        }
    
        currentTask(message => {
          results[index] = message;
          executeTask(index + 1);
        });
      }
    
      executeTask(0);
  };
  executeInSequenceWithCBs(asyncTasks, result => {
    console.log(result);
  })
  
```
**Question 2**
```
const apis = [
  {
    apiName: "products",
    apiUrl: "https://dummyjson.com/products",
  },
  {
    apiName: "users",
    apiUrl: "https://dummyjson.com/users",
  },
  {
    apiName: "posts",
    apiUrl: "https://dummyjson.com/posts",
  },
  {
    apiName: "comments",
    apiUrl: "https://dummyjson.com/comments",
  },
];

const executeInParallelWithPromises = (apis) => {
  const promises = apis.map((api) => {
    return fetch(api.apiUrl)
      .then((response) => response.json())
      .then((apiData) => ({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: apiData,
      }))
      .catch((error) => {
        console.error(`Error fetching data from ${api.apiUrl}:`, error);
        return {
          apiName: api.apiName,
          apiUrl: api.apiUrl,
          apiData: null,
        };
      });
  });
```
**Question 3**
```
import { response } from "express";

const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
]

//modify and write your code here
const executeInSequenceWithPromises = (apis) => {
    if (apis.length === 0) {
      return Promise.resolve([]);
    }
  
    const [currentApi, ...remainingApis] = apis;
  
    return fetch(currentApi.apiUrl)
      .then(response => response.json())
      .then(apiData => ({
        apiName: currentApi.apiName,
        apiUrl: currentApi.apiUrl,
        apiData: apiData
      }))
      .then(result => {
        return executeInSequenceWithPromises(remainingApis)
          .then(nextResults => [result, ...nextResults]);
      })
      .catch(error => {
        console.error(`Error fetching data from ${currentApi.apiUrl}:`, error);
        const result = {
          apiName: currentApi.apiName,
          apiUrl: currentApi.apiUrl,
          apiData: null
        };
        return executeInSequenceWithPromises(remainingApis)
          .then(nextResults => [result, ...nextResults]);
      });
  };
  
 ```


