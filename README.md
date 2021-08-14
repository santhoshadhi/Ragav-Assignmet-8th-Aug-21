# Ragav-Assignmet-8th-Aug-21
**Bind( )**
**The bind method creates a new function and sets the this keyword to the specified object.**

Syntax:
function.bind(thisArg, optionalArguments)

For example:
Let’s suppose we have two person objects.
const john = {
  name: 'John',
  age: 24,
};
const jane = {
  name: 'Jane',
  age: 22,
};

Let’s add a greeting function:
function greeting() {
  console.log(`Hi, I am ${this.name} and I am ${this.age} years old`);
}

We can use the bind method on the greeting function to bind the this keyword to john and jane objects.
For example:
const greetingJohn = greeting.bind(john);
// Hi, I am John and I am 24 years old
greetingJohn();
const greetingJane = greeting.bind(jane);
// Hi, I am Jane and I am 22 years old
greetingJane();
Here greeting.bind(john) creates a new function with this set to john object, which we then assign to greetingJohn variable. Similarly for greetingJane.




**Call ( )**
The call method sets the this inside the function and immediately executes that function.

**The difference between call() and bind() is that the call() sets the this keyword and executes the function immediately and it does not create a new copy of the function, while the bind() creates a copy of that function and sets the this keyword.**

Syntax:
function.call(thisArg, arg1, agr2, ...)

For example:
function greeting() {
  console.log(`Hi, I am ${this.name} and I am ${this.age} years old`);
}
const john = {
  name: 'John',
  age: 24,
};
const jane = {
  name: 'Jane',
  age: 22,
};
// Hi, I am John and I am 24 years old
greeting.call(john);
// Hi, I am Jane and I am 22 years old
greeting.call(jane);
Above example is similar to the bind() example except that call() does not create a new function. We are directly setting the this keyword using call().





**Apply ( )**
The apply() method is similar to call(). The difference is that the apply() method accepts an array of arguments instead of comma separated values.

Syntax:
function.apply(thisArg, [argumentsArr])

For example:
function greet(greeting, lang) {
  console.log(lang);
  console.log(`${greeting}, I am ${this.name} and I am ${this.age} years old`);
}
const john = {
  name: 'John',
  age: 24,
};
const jane = {
  name: 'Jane',
  age: 22,
};
// Hi, I am John and I am 24 years old
greet.apply(john, ['Hi', 'en']);
// Hi, I am Jane and I am 22 years old
greet.apply(jane, ['Hola', 'es']);
