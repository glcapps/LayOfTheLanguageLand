# 🧱 Framework Boundary Contracts

Every UI framework draws a line — often implicitly — between what it handles and what it expects you to handle. This "boundary contract" shapes how data, logic, and markup flow through your application, and it can vary wildly between tools.

Understanding this boundary helps you choose the right framework for your project, avoid misuse, and communicate expectations clearly within teams.

---

## 📐 What Is a Boundary Contract?

A framework’s boundary contract defines:

- What parts of your app it controls (state, DOM, data flow, rendering)
- What it delegates to you (event wiring, lifecycle, routing, styling)
- How tightly it couples logic and presentation
- Whether you code “around it” or “inside it”

---

## 🧭 Example Contracts by Framework

| Framework    | Structure Origin | Data Flow Style       | Who Owns Logic?         | Common Boundary Shift       |
|--------------|------------------|------------------------|--------------------------|-----------------------------|
| React        | JS (via JSX)     | Props down, events up  | You via hooks            | State handling + side effects |
| Vue          | HTML + directives| Template-driven        | You via script           | Logic inside template        |
| Svelte       | HTML + script    | Auto-reactive          | Compiler-lifted logic    | Precompile to imperative     |
| Angular      | HTML + TS        | Two-way binding        | Framework + decorators   | Routing and service layer    |
| HTMX         | HTML             | Server-triggered       | Server mostly            | Minimal JS client-side       |
| Qwik         | Resumable HTML   | Fine-grained hydration | Compiler + you           | Serialization logic          |
| SolidJS      | JSX              | Signals (fine-grained) | You + reactivity engine  | Effect tracking              |

---

## 🧠 Why This Matters

- Helps avoid “fighting the framework”
- Shapes testing strategy and mental model
- Influences onboarding and handoff ease
- Determines what “performance” optimization even means

When teams misunderstand a boundary, they:
- misuse hooks or lifecycle events
- duplicate state or confuse source-of-truth
- get lost during server/client transitions

---

## 🔍 Framework Fit Depends on Contract

You’re not just choosing a syntax or community — you're agreeing to the framework’s opinion about:

- How logic should flow
- Where state lives
- Who renders what, and when

Examples:

- HTMX assumes the server owns logic; React assumes the client does
- Svelte hides reactivity behind the compiler; Vue makes it explicit
- Angular expects you to architect your app “the Angular way”

---

## 📣 Takeaway

Frameworks aren't neutral. Each comes with an invisible contract — a set of promises and assumptions about boundaries.

Understanding and respecting that contract is the key to long-term maintainability, scalability, and sanity.