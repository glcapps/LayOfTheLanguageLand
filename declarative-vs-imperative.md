# 🧾 Declarative vs Imperative

One of the most foundational distinctions in programming style is between declarative and imperative paradigms — yet the line between them is often blurry, especially in modern frontend tools. This article explores how they differ, how they mix, and what that means in practice.

---

## 🧠 Core Distinction

| Imperative                        | Declarative                            |
|----------------------------------|----------------------------------------|
| You specify how to do it         | You specify what you want              |
| Step-by-step instructions        | Desired end state                      |
| Mutates state as it progresses   | Often uses immutable descriptions      |
| More control                     | More abstraction                       |

Example:

Imperative:
```js
const result = [];
for (let i = 0; i < nums.length; i++) {
  if (nums[i] % 2 === 0) result.push(nums[i] * 2);
}
```

Declarative:
```js
const result = nums.filter(n => n % 2 === 0).map(n => n * 2);
```

---

## 🧰 Tools and Frameworks: Where It Shows Up

| Tool / Feature         | Imperative Style Example             | Declarative Style Example                 |
|------------------------|--------------------------------------|-------------------------------------------|
| DOM Manipulation       | `document.createElement()`           | JSX / template rendering                  |
| UI Animation           | `setInterval`, manual style updates  | CSS transitions, Framer Motion            |
| Routing                | Manual `window.location` change      | Declarative route trees                   |
| State Updates          | `count++` in a handler               | `setCount(n => n + 1)`                    |

---

## 🧬 React as a Case Study

React claims to be declarative: “You describe what the UI should look like for a given state.”

But in practice:

- You still write `useEffect()` imperatively to perform side effects
- JSX may look declarative but is compiled into imperative React calls
- State updates are abstracted, but async behavior and batching are deeply imperative under the hood

So it’s more accurate to say:

> React encourages declarative descriptions, but requires imperative escapes.

---

## 🧠 Why It Matters

- Declarative code tends to be more concise and composable
- Imperative code gives you precision and often better performance
- Teams should agree on where to lean into abstraction and where to be explicit

---

## ⚖️ How to Choose

| If you want...                      | Prefer...       |
|------------------------------------|-----------------|
| Readability and intent clarity     | Declarative     |
| Fine-grained performance tuning    | Imperative      |
| Rapid development with guardrails  | Declarative     |
| Full control over flow and timing  | Imperative      |

Often, the best solutions blend both — but knowing where your tool falls on the spectrum helps you reason about it better.

---

## 🧩 Takeaway

Declarative and imperative aren't binary categories — they're a spectrum. Most tools mix both. The key is to understand the tradeoffs and make them visible to your team and to your future self.