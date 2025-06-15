# 🧱 Component vs Web Component

The word “component” is one of the most overloaded in frontend development. When someone says "component," they might mean:

- a reusable UI unit in React, Vue, or Svelte
- a browser-native custom element
- or simply "a chunk of interface with logic and style"

This article breaks down the two dominant meanings: framework components and Web Components.

---

## 🧠 What Is a Component?

In modern frontend frameworks like React or Vue:

- A component is a JavaScript function or class
- It outputs markup (often via JSX or templates)
- It manages its own state and props
- It's usually not truly encapsulated at the browser level

They’re mental and structural units of UI, but they don't directly create new HTML elements.

Example:
```jsx
function Alert({ message }) {
  return <div className="alert">{message}</div>
}
```

This is a "component" in the framework sense — but the browser just sees a <div>.

---

## 🌐 What Is a Web Component?

Web Components are a browser standard that lets you create your own HTML elements:

- Built using custom elements and the Shadow DOM
- Truly encapsulated styles and structure
- Framework-agnostic
- Registered with `customElements.define()`

Example:
```js
class MyAlert extends HTMLElement {
  connectedCallback() {
    this.innerHTML = `<div class="alert">${this.getAttribute('message')}</div>`;
  }
}
customElements.define('my-alert', MyAlert);
```

Used like:
```html
<my-alert message="Danger!"></my-alert>
```

The browser understands this as a real custom element — no framework required.

---

## 🔍 Key Differences

| Feature               | Framework Component               | Web Component                      |
|-----------------------|-----------------------------------|-------------------------------------|
| Syntax                | JSX or template syntax            | HTML + JavaScript class             |
| Encapsulation         | Logical, not enforced             | Enforced via Shadow DOM             |
| Browser-native        | ❌ Requires framework              | ✅ Yes                              |
| Reusability across stacks | ❌ Often framework-specific      | ✅ Fully portable                    |
| Style isolation       | Scoped via CSS modules or hacks   | Shadow DOM + encapsulated styles    |
| Learning curve        | Simpler within framework          | More verbose, lower-level API       |

---

## 🤝 Can They Work Together?

Yes — with caveats.

- Framework components can wrap or embed Web Components
- Web Components can be used inside React/Vue/Svelte (with some quirks)
- Some design systems (like Salesforce Lightning or Shoelace) are Web Component-based for portability

---

## 🎯 When to Use Which?

Use a framework component when:

- You're working entirely within a single app or stack
- You need fast iteration and developer tooling
- You're already in a React/Vue/Svelte ecosystem

Use a Web Component when:

- You want to share UI across frameworks or platforms
- You’re building a design system
- You need native encapsulation without framework buy-in

---

## 🧩 Takeaway

“Component” is a flexible term. Framework components help you think in chunks. Web Components help you publish real, reusable browser-native chunks.

Just make sure when someone says “component,” you know which one they mean.