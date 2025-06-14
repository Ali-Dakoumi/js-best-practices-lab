# 🔒 Closure Patterns

Closures are foundational for privacy, partial application, and custom behavior.

---

## 🧠 What’s a Closure?

- A function that “remembers” the scope it was created in—even after that scope leaves the stack.

```js
function secretHolder(secret) {
  return function () {
    return secret;
  };
}
const getSecret = secretHolder("🍪");
getSecret(); // '🍪'
```

---

## 🔐 Data Privacy

- Create private variables/functions, only exposing what’s needed.

```js
function createBankAccount() {
  let balance = 0;
  return {
    deposit: (amt) => (balance += amt),
    getBalance: () => balance,
  };
}
const acct = createBankAccount();
acct.deposit(100);
acct.getBalance(); // 100
```

---

## 🌀 Closures in Loops

- Use `let` in loops to preserve block scope:

```js
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Output: 0 1 2

// If you use var, all would be 3!
```

---

## 📚 Further Reading

- [MDN: Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
