# ⚠️ JavaScript Anti-Patterns

These are common pitfalls and mistakes that cause bugs, maintenance nightmares, or performance issues. Avoid them!

---

## 🌎 Global Variables

> Declaring variables outside of any scope pollutes the global namespace and causes conflicts.

```js
// 🔴 Don't do this!
userCount = 42;

// ✅ Instead, use:
const userCount = 42;
```

---

## ⚡️ The `eval()` Function

> `eval()` is dangerous and slow. Never use it.

```js
// 🔴 Don't do this!
eval("console.log('Hi!')");

// ✅ Instead:
console.log("Hi!");
```

---

## 🌲 Callback Hell

> Deeply-nested callbacks make code unreadable and hard to maintain.

```js
// 🔴 Don't do this!
login(user, pass, function (token) {
  fetchProfile(token, function (profile) {
    fetchSettings(profile, function (settings) {
      // ...
    });
  });
});

// ✅ Use Promises or async/await:
async function loadUser() {
  const token = await login(user, pass);
  const profile = await fetchProfile(token);
  const settings = await fetchSettings(profile);
}
```

---

## 🛠️ Modifying Prototypes

> Changing built-in prototypes (like `Array.prototype`) can break other code.

```js
// 🔴 Don't do this!
Array.prototype.shuffle = function () {
  /* ... */
};
```

---

## 🔄 Implicit Coercion

> Relying on JS to implicitly convert types can lead to bugs.

```js
// 🔴 Don't do this!
if (count == "0") {
  /* ... */
} // == does type coercion

// ✅ Instead:
if (count === 0) {
  /* ... */
}
```

---

## 🏃 Forgotten `break`

> Missing `break` in switch statements causes unintended fall-through.

```js
// 🔴 Don't do this!
switch (value) {
  case 1:
  // ...
  case 2:
  // ...
}

// ✅ Always add break:
switch (value) {
  case 1:
    // ...
    break;
  case 2:
    // ...
    break;
}
```

---

## 📝 Further Reading

- [Anti-Patterns in JavaScript (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Anti-pattern)
- [JavaScript Anti-Patterns — Addy Osmani](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#antipatterns)
