 ```js
console.log(1);
setTimeout(() => console.log(2), 0);
Promise.resolve().then(() => console.log(3));
setTimeout(() => console.log(4), 1);
console.log(5);
```
---
 ```js
function Person() {
  this.name = 'jack'
  this.age = 25
  this.sayHello = function () {
      console.log('Hello', this.name)
      function innerFunction() {
          console.log(this.age)
      }
      innerFunction();
  }
}
let x = new Person();
x.sayHello()
```
---


 ```js

const obj1= {name: "John Doe", age: "24"};
const obj2  = obj1;
obj2.name = "Jane Miller";
obj1.age  = 36
console.log(obj1, obj2);
```
---

 ```js
['Dubai', 'UAE', 'United Arab Emirates']


stm1 =  'I live in Dubai'
stm2 = 'I want to visit United States of America'
```
---

---

 ```js
const passengerNames = [2,6];
passengerNames.forEach((passenger) => {
    passengerNames.push(1);
})

console.log(passengerNames)
```
---

 ```js

console.log(1);
setTimeout(() => console.log(2), 0);
Promise.resolve().then(() => console.log(3));
setTimeout(() => console.log(4), 1);
console.log(5);
// Scenario 1:
process.nextTick(() => console.log(6));
// Scenario 2:
const syncOperation = () => {
  for (let i = 0; i < 1e9; i++) {
    // Some blocking operation
  }
};
syncOperation();
console.log(7);
// Scenario 3:
const fetchFromNetwork = () => {
  setTimeout(() => console.log(8), 500);
};
fetchFromNetwork();
// Scenario 4:
Promise.resolve().then(() => {
  console.log(9);
  Promise.resolve().then(() => console.log(10));
});


// Scenario 5:
setImmediate(() => console.log(11));


// Scenario 7:
const someAsyncFunction = async () => {
  console.log(13);
  await Promise.resolve();
  console.log(14);
};
someAsyncFunction();
// Scenario 8:
const complexPromiseChain = () => {
  Promise.resolve()
    .then(() => console.log(15))
    .then(() => console.log(16))
    .then(() => setImmediate(() => console.log(17)))
    .then(() => console.log(18))
    .then(() => process.nextTick(() => console.log(19)));
};
complexPromiseChain();
// Scenario 9:
setTimeout(() => {
  console.log(20);
  Promise.resolve().then(() => console.log(21));
  setImmediate(() => console.log(22));
}, 1000);
```
---
