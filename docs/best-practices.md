# 🧠 JavaScript Best Practices

Solid JavaScript code is readable, robust, and efficient. Here are essential best practices for writing high-quality JS!

---

## 🔧 Variable Declarations

- Prefer `const` for values that don’t change.
- Use `let` for changeable bindings.
- Avoid `var` to prevent hoisting and scope confusion.

```js
// ✅ Good
const MAX_USERS = 5;
let userCount = 0;

// 🔴 Avoid
var isLoggedIn = false; // var is function-scoped, use let/const instead.
```

---

## 🧩 Functions

- Keep functions small and focused on a single responsibility.
- Use arrow functions for concise syntax, but name functions for recursion or debugging.
- Prefer default parameters over manual checks.

```js
// ✅ Good
function sum(a, b = 0) {
  return a + b;
}

const double = (x) => x * 2;

// 🔴 Avoid
function process(a, b, c, d, e) {
  /* ... */
} // Too many params
```

---

## 🗃️ Modules & Structure

- Use ES Modules (`import` & `export`) for structure and maintainability.
- Group related functions into files/modules by feature.
- Export only what’s needed.

```js
// math.js
export function add(a, b) {
  return a + b;
}
export function subtract(a, b) {
  return a - b;
}

// index.js
import { add } from "./math.js";
```

---

## 🧠 Error Handling

- Use `try/catch` for operations that may fail.
- Throw errors with informative messages.
- Avoid catching errors you can’t handle.

```js
try {
  fetchUser();
} catch (error) {
  console.error("Failed to fetch user:", error);
}
```

---

## 📝 Code Style

- Use consistent formatting (indent, spaces, naming).
- Stick to one style guide (Airbnb, Google, or your own).
- Comment "why", not "what".

---

## 🧪 Testing

- Write automated tests (unit, integration).
- Use a test framework like Jest or Mocha.

```js
test("sum adds numbers", () => {
  expect(sum(2, 3)).toBe(5);
});
```

---

## 🚀 Performance Tips

- Minimize DOM access and updates.
- Debounce or throttle expensive operations.
- Prefer modern array methods (`map`, `filter`, `reduce`).

```js
// Debounce example
let timeout;
window.addEventListener("resize", () => {
  clearTimeout(timeout);
  timeout = setTimeout(() => {
    console.log("Resized!");
  }, 200);
});
```

---

## 📝 Further Reading

- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [Airbnb JavaScript Style Guide](https://airbnb.io/javascript/)
