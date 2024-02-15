# 🧬 JavaScript Prototypes Explained

## 🤔 What are Prototypes?

In JavaScript, each object can get its features and actions from another object, called a "prototype". Think of a prototype as a model that objects use to get their own properties and methods.

### 🆚 The Difference between `__proto__` and `prototype`

- `__proto__`: This is the link that connects an object to the prototype it gets its features from. It's used to find methods and properties in the object.

- `prototype`: This is a feature on functions used to make new objects. It sets up the `__proto__` for any new object created by that function. Think of it as a plan or design for new objects.

## 🌲 Prototype Inheritance

When you try to use a feature or action of an object, JavaScript first checks the object itself. If it's not there, it checks the object's prototype, then the prototype's prototype, and keeps going like this until it finds what you're looking for or runs out of links to check.

### 🔗 Creating a Prototype Chain

You can create a line of inheritance, connecting objects through their prototypes. Here's a simpler example with an anime theme:

```javascript
const ninja = {
  stealthy: true,
};

const Boruto = Object.create(ninja);
Boruto.age = 15;

console.log(Boruto.age); // Outputs: 17
console.log(Boruto.stealthy); // Outputs: true
```

In this example, `Boruto` gets the `stealthy` feature from `ninja` because we set `ninja` as the prototype for `Boruto`. So even though we didn't directly tell `Boruto` it's stealthy, it knows this because it inherits from `ninja`.

### 💡 Practical Uses of Prototypes

- **Code Reusability**: Prototypes let you set up features and actions just once, and then other objects can use them too. This saves space and makes things run faster.

- **Dynamic Updates**: When you add a new feature or action to a prototype, all the objects linked to that prototype get it right away.
-

## 📚 `__proto__` and Arrays

When you make an array, it gets special abilities from `Array.prototype`, like adding or removing items with methods like `push()` and `pop()`. This happens because the array's `__proto__` is linked to `Array.prototype`.

## 🌟 Why Understanding Prototypes is Important

Knowing about prototypes is key to really getting JavaScript. It helps you make your code better, understand how JavaScript really works, and write code that's both fast and does what you want effectively.
