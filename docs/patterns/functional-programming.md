# 🧩 Functional Programming

Adopt these patterns for safer, more declarative, reusable code!

---

## ⚡️ Core Principles

- **Pure functions:** Output only depends on inputs, no side effects.
- **Immutability:** Don’t change state; return new values.
- **First-class, higher-order functions:** Pass/return functions as values.

---

## 🍃 Examples

```js
// Pure function
function add(a, b) {
  return a + b; // No external state used or changed
}

// Higher-order function
function filter(arr, fn) {
  const result = [];
  for (let v of arr) if (fn(v)) result.push(v);
  return result;
}

const nums = [1, 2, 3, 4];
const evens = filter(nums, (x) => x % 2 === 0); // [2, 4]

// Immutability
const moreNums = [...nums, 5];
```

---

## 🏆 Benefits

- Easier to reason about and test.
- Fewer bugs (no hidden state).
- Composable logic (e.g., via `.map`, `.filter`, `.reduce`).

---

## 📚 Further Reading

- [MDN: Functional Programming](https://developer.mozilla.org/en-US/docs/Glossary/Functional_programming)
