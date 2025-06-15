# Layers Upon Layers: Making Sense of Node, Next, Nuxt, and Their Peers

Modern JavaScript development can feel like spelunking through sedimentary layers of tooling. You start with JavaScript, find yourself installing Node.js, and suddenly you’re working in a world of frameworks like Next.js or Nuxt.js, each adding its own assumptions, structure, and deployment strategy.

This article is a map to those layers — where the runtime ends and the framework begins, and what responsibilities are handled at each tier.

## 🧱 Node.js: The Foundation
Node.js is the JavaScript runtime that enables server-side JS. It provides:
- Access to the file system
- An event loop
- Core modules (fs, http, etc.)

It doesn’t:
- Handle routing
- Serve HTML templates
- Provide a standard web framework

It is best thought of as the “C” layer of the JavaScript world — unopinionated and close to the metal.

## 🛣️ Express.js: A Simple Routing Layer
Express.js builds atop Node.js to provide routing and middleware composition. It's extremely lightweight and mostly concerned with shaping HTTP requests and responses.

## 🛤️ Next.js: Fullstack React Framework
Next.js builds atop Node (and optionally Express) to provide:
- File-based routing
- Server-side rendering (SSR)
- Static site generation (SSG)
- API routes
- React integration

It is “opinionated” but configurable. A fullstack React experience with sensible defaults.

## 🛤️ Nuxt.js: Vue’s Fullstack Equivalent
Much like Next.js but for Vue. It favors:
- SSR by default
- Config-over-code
- A monolithic feel, like Laravel

## 🔁 Bun and Deno: Alternatives and Counterpoints
- Bun aims to replace node, npm, esbuild, and Jest in a single fast binary.
- Deno reimagines Node with built-in TypeScript, browser-compatible modules, and better security.

## 🗺️ Visual Overview

| Tool      | Frontend Support | SSR | File Routing | Node-based | Opinion Level |
|-----------|------------------|-----|--------------|------------|----------------|
| Node.js   | ❌               | ❌  | ❌           | —          | 🔓 Low         |
| Express   | ❌               | ✅  | ❌           | ✅         | 🔓 Low         |
| Next.js   | ✅ (React)       | ✅  | ✅           | ✅         | 🔒 Medium      |
| Nuxt.js   | ✅ (Vue)         | ✅  | ✅           | ✅         | 🔒 High        |
| Deno      | ❌               | ❌  | ❌           | ❌         | 🔓 Medium      |
| Bun       | ❌               | ❌  | ❌           | ❌         | 🔓 Low         |