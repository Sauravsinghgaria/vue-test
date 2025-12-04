# Vue Internals & Concepts

## Core Concepts

**Reactivity System**: Vue tracks data changes and automatically updates the DOM when reactive data changes.

**Virtual DOM**: In-memory representation of the actual DOM that Vue uses to efficiently compute and apply updates.

**Components**: Reusable, encapsulated units of UI logic that manage their own state and lifecycle.

**Directives**: Special HTML attributes (like `v-if`, `v-for`) that add dynamic behavior to templates.

**Composables**: Reusable logic functions that encapsulate and share stateful behavior across components.

## Lifecycle Hooks

**setup()**: Runs before component creation; used for composition API setup.

**beforeCreate**: Called before instance initialization.

**created**: Instance is created; data and methods are available but DOM is not mounted.

**beforeMount**: Component is ready to mount but hasn't been added to DOM yet.

**mounted**: Component is mounted to DOM and can interact with it.

**beforeUpdate**: Triggered before reactive data change causes re-render.

**updated**: Component has been updated after data change.

**beforeUnmount**: Called before component is removed from DOM.

**unmounted**: Component is completely removed from DOM.

## Hydration Lifecycle (SSR)

**beforeHydrate**: Prepares component before server-rendered HTML is hydrated.

**hydrated**: Server-rendered HTML is connected with client-side reactivity.

Ensures client-side app matches server-rendered markup without re-rendering.

## Nuxt-Specific Concepts

**Auto-imports**: Components, composables, and utilities are automatically imported without explicit imports.

**File-based routing**: Routes are automatically generated from files in `/pages` directory.

**Middleware**: Functions that run before navigating to a page for authentication or validation.

**Layouts**: Wrapper components that provide consistent structure across multiple pages.

**Plugins**: Initialize app-wide functionality, inject helpers, or register components globally.

**Server Routes**: API routes created in `/server/routes` for backend logic.