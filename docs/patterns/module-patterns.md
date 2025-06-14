# 📦 Module Patterns

Encapsulate code, prevent global leaks, and organize functionality with module patterns.

---

## 🚀 ES6 Modules

- Modules use `export` and `import` statements.
- Better encapsulation, tooling, and readability.

```js
// lib/math.js
export function add(a, b) {
  return a + b;
}
export const PI = 3.14;

// app.js
import { add, PI } from "./lib/math.js";
console.log(add(2, PI));
```

---

## 🧩 Revealing Module Pattern

- Common before ES6 modules, especially in browsers.

```js
const UserModule = (function () {
  let name = "Anonymous";
  function setName(newName) {
    name = newName;
  }
  function getName() {
    return name;
  }
  return { setName, getName };
})();

UserModule.setName("Ada");
console.log(UserModule.getName()); // 'Ada'
```

---

## ⚠️ When to Use

- Prefer ES6 modules in modern projects.
- Revealing module helps in legacy code or IIFEs.

---

## 📚 Further Reading

- [MDN: ES6 Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
