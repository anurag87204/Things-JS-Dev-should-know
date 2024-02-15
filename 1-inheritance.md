# 🧬 Inheritance - Prototypal Inheritance

- It's mainly used to use code again. 🔄
- Other languages use classes for this, but JavaScript uses objects. 📦
- You can do it with or without classes in JavaScript. 🚫🏫
- It's about making a new class from an old one. 🆕➡️🆒

## 🏫 Classes

```javascript
const me = {
  talk() {
    return "Talking";
  },
};

const you = {
  talk() {
    return "Talking";
  },
};

// Problem 😕: If we have 100 objects, we must write the same code 100 times. If there's one bug, we have to fix it 100 times.

// Solution 🎉: Use inheritance.

class Person {
  talk() {
    return "Talking";
  }
}

const me = new Person();
const you = new Person();

// Now we write the code once and fix bugs once. ✅
```

```javascript
me.talk();

//output: "Talking"

me;
/*
Person {}
    __proto__: Object
        talk: function talk()
        constructor: class Person
        __proto__: Object
*/

Person.prototype;

/*
{talk: function, constructor: function}
    constructor: class Person
    talk: function talk()
    __proto__: Object
*/

Person.prototype === me.__proto__;

//output: true

// me.__proto__ is the same as Person.prototype.
// We can add a new method to Person.prototype, and all objects from Person will have it.
```

Now, if we need to fix a function because it has a bug:

```javascript
Person.prototype.talk = function () {
  return "New and improved talking";
};

me.talk();
// output: "New and improved talking" 🆕

you.talk();
// output: "New and improved talking" 🆕

// Fixing the function once updates it for all objects from Person. 🛠️
```

## 🧩 Pure Objects - Prototypal Inheritance

- It's about making a new object from an old one. 🔄
- You can do it with or without classes. 🚫🏫
- It's useful for reusing code and fixing bugs in one place. 🔧

```javascript
function Person() {}

Person.prototype.talk = function () {
  return "Talking";
};

const me = new Person();

me;

/*
Person {}
    __proto__: Object
        talk: function ()
        constructor: function Person()
        __proto__: Object
*/

me.talk();

//output: "Talking"

function Person() {
  this.talk = function () {
    return "Talking";
  };
}

const me = new Person();

me.talk();

//output: "Talking"

me;

/*
Person {talk: function}
    talk: function ()
    __proto__: Object
        constructor: function Person()
        __proto__: Object
*/

// This object is a 'Person' with a 'talk' function attached directly to it.
// '__proto__' is a special property pointing to the prototype of the object, which is where inherited features are found.
// The 'constructor' inside '__proto__' points back to the function that created the object.
```

### 🚀 Where would we use inheritance?

- When making objects that behave similarly. 👯
- When different things need the same features. 🛠️
- For a class that makes UI elements and adds them to the webpage. 🌐

Instead of writing the same steps over and over, we make a class or component that does it for us.
