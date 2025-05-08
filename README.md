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

Also, when a project grows bigger, and we have lots of files and functions, TypeScript helps us with **auto-completion** and **refactoring**.  
I noticed how easy it became to understand what each function is expecting and returning just by hovering over them.  
It’s like having **documentation built into the code!**

Another great thing is when we make changes—like **renaming a property** or **refactoring a function**—TypeScript shows where it’s used and if it will break anything.  
This makes big projects **way easier to maintain**.
