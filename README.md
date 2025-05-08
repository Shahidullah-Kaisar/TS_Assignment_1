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

Interface allows declaration merging, meaning if the same interface is declared multiple times, TypeScript will automatically combine them.

In the example above, User is declared twice, and TypeScript merges the two, resulting in a single interface with the properties name, age, and email.

On the other hand, type does not support declaration merging. Instead, multiple types can be combined using intersections (&), which results in a new type (UserProfile) that includes the properties from both BasicInfo and ContactInfo.


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


# How does TypeScript help in improving code quality and project maintainability?

1. Enhanced Tooling and IDE Support  

    TypeScript adds static typing to JavaScript, helping developers catch errors at compile-time. This improves code completion, refactoring, and navigation in IDEs.

    Modern ECMAScript features like async/await and decorators are transpiled to compatible JavaScript versions, ensuring broad compatibility.

2. Code Maintainability  

    TypeScript’s static typing helps detect errors early, improving readability and reducing bugs.

    Using custom types and interfaces makes complex data structures easier to understand, leading to more maintainable code.

3. Scalability

    TypeScript supports scalable projects by providing a clear contract between code components, ensuring bugs are minimized.

    The compiler guarantees that type dependencies are met, making refactoring and feature additions safer.

4. Strong Typing 

    TypeScript catches type mismatches early, making code more predictable. Developers can define types for variables, functions, and interfaces, reducing bugs.

5. Advanced Features

    TypeScript includes classes, interfaces, generics, and async/await, enabling clean and efficient code with faster development cycles.

6. Enhanced Readability

    TypeScript’s strong typing and modern syntax improve code clarity, making it easier to collaborate and maintain large projects.




