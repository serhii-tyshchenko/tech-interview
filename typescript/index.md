**What is TypeScript, and how does it relate to JavaScript?**

- TypeScript is a statically typed superset of JavaScript. It adds static typing and other features to JavaScript.

**What are the benefits of using TypeScript?**

- Benefits include type checking, improved tooling, better code quality, and enhanced code maintainability.

**How do you declare a variable with a specific type in TypeScript?**

- You can declare a variable with a specific type using the colon (:) syntax. For example:

```typescript
let age: number = 30;
```

**What are TypeScript interfaces, and how are they used?**

- Interfaces define the shape of an object, specifying which properties and methods it should have. They help with type checking.

**How can you ensure that a variable in TypeScript can have multiple types?**

- You can use union types, such as `string | number`, to specify that a variable can have multiple types.

**What is type inference in TypeScript?**

- Type inference is TypeScript's ability to automatically deduce the type of a variable based on its initialization.

**Explain the concept of "type assertions" in TypeScript.**

- Type assertions are a way to tell the TypeScript compiler to treat a value as a specific type, even if TypeScript's static analysis cannot guarantee it.

**What are the different types of modules in TypeScript, and how do they differ?**

- TypeScript supports CommonJS, AMD, SystemJS, and ES6 modules. They differ in syntax and usage.

**How can you create and use decorators in TypeScript?**

- Decorators are used to modify the behavior of classes, methods, or properties. You can define decorators using the @ symbol.

**What are enums in TypeScript, and when would you use them?**

- Enums allow you to define a set of named constants. They are useful when you have a fixed set of values that a variable can take.

**Explain the difference between "interface" and "type" in TypeScript.**

- Interfaces are used for defining object shapes, while types can represent various data structures, including unions, intersections, and more.

**How does TypeScript handle optional properties in interfaces?**

- You can make properties optional in interfaces by using a ? symbol after the property name, like

```typescript
interface Person {
  name?: string;
}
```

**What is a generic type in TypeScript, and why is it useful?**

- Generic types allow you to create reusable components and functions that work with different data types while preserving type safety.

**What are type guards, and how do they work in TypeScript?**

- Type guards are conditional checks that refine the type of a variable within a specific code block, providing more precise type information.

**What is the "never" type in TypeScript, and when is it commonly used?**

- The never type represents values that never occur. It's often used to indicate functions that throw errors or never return.

**How can you enforce strict null checks in TypeScript?**

- By enabling the strictNullChecks compiler option, TypeScript ensures that null and undefined are only assignable to their respective types.

**Explain what "type alias" is in TypeScript and give an example.**

- Type aliases create custom type names for complex types. For example:
  `type Point = { x: number, y: number };`

**How can you create and use conditional types in TypeScript?**

- Conditional types use the `extends` keyword to create type branches based on existing types.

**What is the difference between "interface" and "class" in TypeScript?**

- An interface defines the shape of an object, while a class is a blueprint for creating objects.

**What is the purpose of the "readonly" modifier in TypeScript?**

- The `readonly` modifier indicates that a property or array cannot be modified after it's initialized.

**How do you handle asynchronous operations in TypeScript?**

- You can use promises, async/await, or observables (with libraries like RxJS) to handle asynchronous operations.

**What is an abstract class in TypeScript, and when would you use one?**

- An abstract class is a class that cannot be instantiated directly. It's used as a base class for other classes to inherit from.

**How can you define and use namespaces in TypeScript?**

- Namespaces provide a way to organize code into logical containers. You can define them using the `namespace` keyword.

**What is a "declaration file" in TypeScript, and when is it used?**

- Declaration files (.d.ts) describe the shape of JavaScript code in TypeScript, often used when working with external libraries.

**How does TypeScript handle type checking in classes and inheritance?**

- TypeScript performs type checking for class properties, methods, and constructors based on their defined types and access modifiers.

**Explain the "super" keyword in TypeScript when working with classes.**

- The `super` keyword is used to call methods or access properties of a parent class in a derived class.

**What is the purpose of the "private," "protected," and "public" access modifiers in TypeScript classes?**

- They control the visibility and accessibility of class members. private restricts access, protected allows access in derived classes, and public allows access from anywhere.

**How can you implement interface inheritance in TypeScript?**

- You can use the `extends` keyword to make one interface inherit the properties and methods of another.

**What is the "keyof" keyword in TypeScript, and how is it used?**

- keyof is used to get the keys (property names) of an object type. It's often used for creating mapped types.

**How can you use TypeScript with React for type safety?**

- You can use TypeScript with React by using TypeScript's .tsx extension, defining prop types, and using generic types for components.

**What are "discriminated unions" in TypeScript, and how are they useful?**

- Discriminated unions are union types with a common property (discriminator) that helps TypeScript narrow down the specific type in a union.

**How can you define and use type guards with discriminated unions?**

- You can use type guards to check the discriminator property and narrow down the type in a discriminated union.

**What are "module augmentation" and "declaration merging" in TypeScript?**

- Module augmentation allows you to add new declarations to existing modules. Declaration merging is TypeScript's way of combining declarations with the same name.

**How can you configure TypeScript options in a tsconfig.json file?**

- You can create a tsconfig.json file and specify compiler options to configure TypeScript for your project.

**Explain the "tsc" command and how to use it to compile TypeScript files.**

- The tsc command is used to compile TypeScript files. You can run it with the filename or specify a tsconfig.json file.

**What is the purpose of the "any" type in TypeScript?**

- The any type allows you to opt out of TypeScript's static type checking, effectively making a variable of any type.

**How can you define and use type assertions in TypeScript?**

- Type assertions allow you to tell TypeScript to treat a value as a specific type, using the `as` keyword or angle brackets.

**Explain the role of "tsconfig.json" in a TypeScript project.**

- tsconfig.json is a configuration file that specifies TypeScript compiler options and settings for a project.

**What is a "namespace import" and a "default import" in TypeScript module systems?**

- A namespace import brings all exported members into a single object. A default import imports the default export of a module.

**How can you create and use decorators with class methods in TypeScript?**

- You can create method decorators by prefixing a function with @ and applying it to a class method.

**What is the "this" type in TypeScript, and how does it help with type checking?**

- The `this` type is used to represent the type of this within a function. It helps with type checking in functions that rely on this.

**Explain the "strict" mode in TypeScript and its advantages.**

- Enabling the "strict" mode in TypeScript enables a set of strict type checking options, which helps catch more type-related errors.

**How can you handle external dependencies in TypeScript, such as third-party libraries?**

- You can use declaration files (.d.ts) to provide type information for external libraries or use type definitions from DefinitelyTyped.

**What is the purpose of "template literal types" in TypeScript, and how do they work?**

- Template literal types allow you to create mapped types using template strings and placeholders.

**Explain the concept of "tsconfig.json" inheritance and how it works.**

- Inheritance allows you to extend or override settings from a base tsconfig.json file in a child project-specific tsconfig.json.

**How do you ensure type safety when working with third-party JavaScript libraries in TypeScript?**

- You can use type definitions (.d.ts files), type assertion, or type casting to ensure type safety with third-party libraries.

**What is the "as const" assertion in TypeScript, and how does it work?**

- `as const` is used to infer literal types from object literals, making all properties read-only and preserving their exact values.

**Explain the use of "mapped types" in TypeScript and provide an example.**

- Mapped types are used to create new types by iterating over the properties of an existing type and transforming them. For example: { [K in keyof T]: string }.

**How can you use TypeScript with popular build tools like Webpack or Babel?**

- You can configure Webpack or Babel to process TypeScript files using appropriate loaders and plugins, ensuring TypeScript is transpiled correctly.

**What is the difference between `any`, `unknown` and `never`?
- In TypeScript, `any`, `unknown`, and `never` are three distinct types that serve different purposes in the type system.

1. **`any`**:
   - **Description**: The `any` type is the most permissive type in TypeScript. It essentially disables static type checking for a particular value or expression.
   - **Use Cases**: Use `any` when you want to opt out of TypeScript's type checking for a specific variable or value. It is often used when migrating JavaScript code to TypeScript or when dealing with dynamic or uncertain types.

   ```typescript
   let someValue: any = "Hello, World!";
   console.log(someValue.length); // No type checking errors, even though length is not a property of all values
   ```

   While `any` provides flexibility, it comes at the cost of losing the benefits of static type checking.

2. **`unknown`**:
   - **Description**: The `unknown` type is a safer alternative to `any`. Variables of type `unknown` require a type assertion or a type check before they can be used.
   - **Use Cases**: Use `unknown` when the type of a value is not known at compile time, and you want to enforce type checking before performing operations on that value.

   ```typescript
   let userInput: unknown = getUserInput();
   
   // Type assertion
   let userName: string = userInput as string;

   // Type check
   if (typeof userInput === "string") {
       let userName: string = userInput;
   }
   ```

   `unknown` encourages you to perform type checking before using values, making the code more robust.

3. **`never`**:
   - **Description**: The `never` type represents values that will never occur. It is often used to indicate functions that throw exceptions, enter infinite loops, or have unreachable endpoints.
   - **Use Cases**: Use `never` when you have a function that never returns (e.g., throws an error or enters an infinite loop).

   ```typescript
   function throwError(message: string): never {
       throw new Error(message);
   }

   function infiniteLoop(): never {
       while (true) {
           // code that never exits
       }
   }
   ```

   `never` is useful in scenarios where the function is not expected to complete normally.

- In summary, `any` provides maximum flexibility but sacrifices type safety, `unknown` adds a layer of type safety by requiring explicit type checks, and `never` is used to indicate values or functions that will never occur or complete. The choice between them depends on the specific requirements and design goals of your code.