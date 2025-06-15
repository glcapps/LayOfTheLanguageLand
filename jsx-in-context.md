# 📘 JSX in Context

JSX (JavaScript XML) is often seen as synonymous with React, but it's more than a syntax trick — it's a statement about how you want to mix structure, logic, and data in your application. This article places JSX in historical and conceptual context.

---

## 🧾 What Is JSX?

JSX is a syntax extension for JavaScript that looks like HTML but compiles to `React.createElement()` calls (or their equivalents in other libraries).

Example:
```jsx
const button = <button onClick={save}>Save</button>;
```

Compiles to:
```js
const button = React.createElement("button", { onClick: save }, "Save");
```

---

## 🧬 JSX in the Lineage of Templating

JSX fits into a long lineage of “logic + markup” tools:

| Tool            | Primary Base   | Logic Injected Into    | Example                     |
|-----------------|----------------|-------------------------|-----------------------------|
| PHP             | HTML           | Embedded PHP tags       | `<?php echo $user; ?>`     |
| ERB (Rails)     | HTML           | Embedded Ruby           | `<%= user.name %>`         |
| Razor (.NET)    | HTML           | Embedded C#             | `@user.Name`               |
| Vue             | HTML + directives | JS methods, bindings | `{{ user.name }}`          |
| JSX             | JS             | HTML embedded as syntax | `<div>{user.name}</div>`   |

JSX reverses the flow: instead of logic inside markup, it puts markup inside logic.

---

## 🔄 HTML-in-JS vs JS-in-HTML

JSX is HTML-in-JS. It differs from traditional templating:

- You're writing logic-first code that returns structure
- All HTML is wrapped inside a JS expression
- You can use conditionals, loops, and composition like normal JS

Compare this to PHP or Vue templates, where structure dominates and logic is injected surgically.

---

## 🧠 What JSX Says About Your Mental Model

- "My UI is a function of state"
- "I want full JS control over structure"
- "I value co-location of logic and markup"

This aligns well with a component-based mental model and modern tooling like hot reload and static analysis.

---

## 🧱 But JSX Comes at a Cost

- It adds a build step (usually Babel)
- It requires devs to learn both JavaScript quirks and HTML semantics
- It breaks the mental separation between layout and behavior
- It leads to logic creep: conditionals and rendering logic pile up in the view

JSX can blur the line between application logic and interface glue — which may be a feature or a hazard depending on your team’s preferences.

---

## 🧩 JSX Outside React

JSX has spread beyond React:

- Preact, SolidJS, and Stencil use JSX
- Some libraries re-implement JSX-like syntax for composable elements
- TypeScript supports JSX natively with different modes (`react`, `preserve`, etc.)

This shows JSX isn’t owned by React — it’s a pattern that appeals to those who want JS-first component control.

---

## 🎯 When JSX Works Best

- In large apps with many components
- When your team is JS-centric
- When you want strong IDE and linting support
- When structure needs to be generated dynamically

---

## 📣 Takeaway

JSX isn’t “just syntax” — it’s a commitment to a mental model:

- Logic-first
- Component-based
- Embedded structure

Understanding JSX in context helps you decide when to embrace it — and when to reach for something simpler.