## 1. How TypeScript Helps Improve Code Quality and Maintainability

One of the biggest reasons of choosing TypeScript is as it has a **type system**.  
TypeScript allows us to define the types of variables, function arguments, and return values.  
This sounds small, but it actually makes a huge difference in **catching errors early** and **making the code easier to understand**.

---

### For example, in JavaScript, we can do this:

```js
function add(i, j) {
  return i + j;
}
```

If someone passes a string by mistake, it might behave weirdly:

```js
add(5, "10"); // Output: "510"
```

---

### In TypeScript, we can define the types clearly:

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

Now, if someone passes a string, TypeScript will show an error **before even running the code**.  
This saves a lot of time debugging.

---


## 2.What is the use of the `keyof` keyword in TypeScript?

The `keyof` keyword in TypeScript is used to get the **keys of an object type** as a union of string literal types.  
It helps us make our code more type-safe, especially when we are working with object properties dynamically.

The `keyof` keyword helps us build more flexible and reusable functions while still keeping everything type-safe.  
It’s especially useful when working with object properties dynamically, like in form handling, API responses, or utility functions.

---

### 🔍 Example:

```ts
type User = {
  id: number;
  name: string;
  email: string;
};

type UserKeys = keyof User;
// UserKeys is now: "id" | "name" | "email"
```

Now, we can use `UserKeys` in a function to safely access values from a `User` object:

```ts
function getValue(obj: User, key: keyof User) {
  return obj[key];
}

const user = { id: 1, name: "Alice", email: "alice@example.com" };

console.log(getValue(user, "email")); // Output: "alice@example.com"
```

If we try to use a key that doesn’t exist, TypeScript will show an error:

```ts
// Error: Argument of type '"age"' is not assignable to parameter of type 'keyof User'
// getValue(user, "age");
```

---



Another great thing is when we make changes—like **renaming a property** or **refactoring a function**—TypeScript shows where it’s used and if it will break anything.  
This makes big projects **way easier to maintain**.
