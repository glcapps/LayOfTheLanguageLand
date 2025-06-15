# ✂️ Logic and Markup Boundaries

Every tool that outputs HTML — from React to Rails to HTMX — takes a stance on how logic and markup should be interwoven. This stance shapes how code reads, how easily it can be maintained, and who on the team can touch it.

This article explores where different tools draw that boundary, and what those choices mean.

---

## 🧱 The Spectrum: Separation vs Integration

Some tools keep logic and markup separate:

- Handlebars, Mustache, Smarty
- Rails with ERB templates
- Classic ASP/PHP with includes

Others integrate logic into structure:

- React with JSX
- Svelte with `{#if}`, `{#each}`
- Vue with `v-if`, `v-for` directives

Each has tradeoffs:

| Approach             | Pros                                         | Cons                                       |
|----------------------|----------------------------------------------|--------------------------------------------|
| Strict separation    | Easy to reason about, approachable to non-devs | Can feel limiting, hard to debug          |
| Full integration     | Highly expressive, fewer files               | Blurs concerns, harder to test             |
| DSL directives       | Clean syntax, good balance                   | Learning curve, magic behavior             |

---

## 🔄 Mixing Styles in Practice

Most teams end up mixing:

- Templates for static layouts
- Embedded expressions for dynamic fields
- Function calls or helper tags for business logic

This hybrid style can work well — if boundaries are clear and consistent.

---

## 🧠 Who Gets to Touch the File?

The more tightly logic and markup are coupled, the more technical experience is required to edit them.

- Can a designer safely modify layout?
- Can a junior dev trace data flow?
- Can an interviewee reason about execution order?

Tools like HTMX or ERB keep HTML sacred. JSX or Svelte let you wire behavior inline — powerful, but potentially exclusive.

---

## 🧩 Philosophy Shines Through

- React: “UI is a function of state” → logic leads
- HTMX: “HTML is enough” → markup leads
- Vue: tries to balance — expressive but constrained
- Svelte: compiler bridges both — logic feels built-in

Every tool sends a message about who it’s for, and how it wants you to think.

---

## 🎯 Takeaway

The boundary between logic and markup isn’t just a technical detail — it’s a design choice that affects team velocity, clarity, and who gets to participate in building the product.

Knowing where your tools draw that line helps you use them with more intention.