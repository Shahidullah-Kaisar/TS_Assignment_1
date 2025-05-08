# Differences between interfaces and types in TypeScript

## Type in TypeScript:

A type in TypeScript is used to create custom data structures and ensure type correctness during development. It can represent primitives, unions, intersections, tuples, and other complex structures.

### Example:

```
type BasicInfo = {
  name: string;
  age: number;
};

type ContactInfo = {
  email: string;
};

type UserProfile = BasicInfo & ContactInfo;

const user: UserProfile = {
  name: "Sajib",
  age: 20,
  email: "shkaisar2002@gmail.com"
};
console.log(user);

Output:

{
  "name": "Sajib",
  "age": 20,
  "email": "shkaisar2002@gmail.com"
}
```
## Interface in TypeScript:

An interface is a contract that defines the structure that an object or class must follow. It is especially useful when working with object shapes and class implementations.

### Example: 
```
interface User {
  name: string;
  age: number;
}

interface User {
  email: string;
}

const person: User = {
  name: "Sajib",
  age: 20,
  email: "shkaisar2002@gmail.com"
};
console.log(person);

Output:

{
  "name": "Sajib",
  "age": 20,
  "email": "shkaisar2002@gmail.com"
}
```
## Difference Between Example 2:

Interface allows declaration merging, meaning if you declare the same interface multiple times, TypeScript will automatically combine them.

In the example above, User is declared twice, and TypeScript merges the two, resulting in a single interface with the properties name, age, and email.

On the other hand, type does not support declaration merging. Instead, you can combine multiple types using intersections (&), which results in a new type (UserProfile in this case) that includes the properties from both BasicInfo and ContactInfo.


## Type vs Interface Comparison

A type in TypeScript is more flexible than an interface. It can represent not only object shapes but also primitives, unions, intersections, and tuples. This makes it especially useful for defining custom types beyond just object structures. On the other hand, interface is specifically designed to describe the shape of an object and is ideal for class-based designs and object-oriented programming.

In terms of keyword usage, type uses the type keyword, while interface uses the interface keyword. Interfaces support declaration merging, which means you can define multiple interfaces with the same name and TypeScript will automatically combine them. This is not possible with types—redeclaring a type with the same name will throw an error.

When it comes to extending or implementing, interfaces are better suited for working with classes. They can be extended by other interfaces and implemented by classes. Types cannot be implemented or extended in the same way, although they support combining multiple types using intersections.


## When to Use Type vs Interface:

### Use interface when:

Defining the structure of objects or classes.
Declaration merging is needed.
Extending other interfaces is required.

### Use type when:

Representing primitives, unions, tuples, or intersections.
More versatility in combining types is desired.
Merging capabilities are not required.


