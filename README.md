# Comprehensive-Angular-TypeScript-Interview-Questions-Your-Ultimate-Prep-Guide

## How do you define a variable in TypeScript with a specific type?

In TypeScript, you can define a variable with a specific type using type annotations. The syntax for this involves specifying the type of the variable after a colon `:` following the variable name. Here's the basic syntax:

```typescript
let variableName: type = value;
```

### Example 1: Defining a Number Variable

```typescript
let age: number = 25;
```
- Here, `age` is defined as a `number` type and is initialized with the value `25`. If you try to assign a value of a different type (e.g., a string) to `age`, TypeScript will throw a compile-time error.

### Example 2: Defining a String Variable

```typescript
let firstName: string = "John";
```
- In this example, `firstName` is defined as a `string` type with the value `"John"`. Assigning a non-string value will result in an error.

### Example 3: Defining a Boolean Variable

```typescript
let isActive: boolean = true;
```
- Here, `isActive` is of type `boolean`, and it's set to `true`.

### Example 4: Defining an Array of a Specific Type

```typescript
let scores: number[] = [90, 85, 88];
```
- `scores` is an array of numbers. You can only add number elements to this array.

### Example 5: Defining a Variable with a Union Type

```typescript
let identifier: number | string = 123;
```
- `identifier` can hold either a `number` or a `string`. In this case, it's initialized with a `number`, but you could later assign a `string` to it without causing an error.

### Example 6: Defining a Variable with a Custom Interface

```typescript
interface User {
    name: string;
    age: number;
}

let user: User = {
    name: "Alice",
    age: 30
};
```
- Here, `user` is defined with a custom type `User`, which is an interface with `name` and `age` properties.

### Example 7: Defining a Variable as `any` Type

```typescript
let data: any = "Hello";
```
- `data` can be of any type, and you can reassign it to any other type without causing a compile-time error. However, using `any` should generally be avoided as it negates the benefits of type checking.

### Example 8: Defining a Complex Type like: `let currentFilters: { [courseId: number]: string } = {};`

In TypeScript, you can declare a complex type using an index signature, which allows you to define an object where the keys are of one type (e.g., `number`) and the values are of another type (e.g., `string`). Here’s how you can declare and initialize such a variable:

```typescript
let currentFilters: { [courseId: number]: string } = {};
```

#### Breakdown

- `{ [courseId: number]: string }` is an index signature:
  - `courseId` is the key, which is of type `number`.
  - `string` is the type of the value associated with each key.
- `currentFilters` is the variable name.
- `= {}` initializes `currentFilters` as an empty object.

#### Usage Example

Now that you've declared `currentFilters`, you can add entries to it like this:

```typescript
currentFilters[101] = "Math";
currentFilters[102] = "Science";
```

Here, `101` and `102` are `number` keys, and `"Math"` and `"Science"` are `string` values.

#### Full Example

```typescript
let currentFilters: { [courseId: number]: string } = {};

// Adding filters
currentFilters[101] = "Math";
currentFilters[102] = "Science";

// Accessing a filter
console.log(currentFilters[101]); // Output: Math

// Removing a filter
delete currentFilters[101];
```

#### Key Points

- This type is particularly useful when you need to store dynamic keys (in this case, `courseId`s) with corresponding values (like filter names or descriptions).
- TypeScript ensures that the keys are numbers and the values are strings, providing type safety while working with such objects.

By explicitly defining types, TypeScript helps catch potential errors during development and makes the code more readable and maintainable.
