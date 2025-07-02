---
# 🚀 Advanced React Learning Guide

Welcome to the **Advanced React Roadmap**, your go-to resource for writing modern, production-grade React applications.

---

## 📚 Table of Contents

- [React Fundamentals](#react-fundamentals)
- [JSX Deep Dive](#jsx-deep-dive)
- [Components & Props](#components--props)
- [State & Lifecycle](#state--lifecycle)
- [Handling Events](#handling-events)
- [Conditional Rendering](#conditional-rendering)
- [Lists & Keys](#lists--keys)
- [Forms](#forms)
- [Lifting State Up](#lifting-state-up)
- [Composition vs Inheritance](#composition-vs-inheritance)
- [React Router](#react-router)
- [Context API](#context-api)
- [Hooks](#hooks)
- [Custom Hooks](#custom-hooks)
- [Portals](#portals)
- [Error Boundaries](#error-boundaries)
- [Code Splitting](#code-splitting)
- [Suspense & Lazy Loading](#suspense--lazy-loading)
- [Performance Optimization](#performance-optimization)
- [Accessibility (a11y)](#accessibility-a11y)
- [Testing](#testing)
- [Styling Strategies](#styling-strategies)
- [TypeScript with React](#typescript-with-react)
- [Best Practices](#best-practices)
- [Advanced Project Ideas](#advanced-project-ideas)
- [Recommended Stack](#recommended-stack)
- [Folder Structure](#folder-structure)
- [Resources](#resources)

---

## 🚀 React Fundamentals

React is a **component-based** JavaScript library for building user interfaces:

- Declarative
- Component-driven
- Virtual DOM
- One-way data flow

```jsx
function Welcome({ name }) {
  return <h1>Hello, {name}!</h1>;
}
````

---

## ⚛️ JSX Deep Dive

JSX combines HTML + JS in a single syntax:

```jsx
const heading = <h1>React Rocks</h1>;
```

* use `{}` to embed expressions
* use `className` instead of `class`
* camelCase props (`onClick`, `htmlFor`)

---

## ⚛️ Components & Props

**Functional components** are the modern standard.

```jsx
function Profile({ name, age }) {
  return <p>{name} is {age} years old.</p>;
}
```

Props are read-only and passed top-down.

---

## ⚛️ State & Lifecycle

React manages local data in **state**:

```jsx
const [count, setCount] = useState(0);
```

Use `useEffect` for side effects:

```jsx
useEffect(() => {
  console.log('Runs on mount or count change');
}, [count]);
```

---

## ⚛️ Handling Events

```jsx
<button onClick={() => console.log("Clicked")}>Click Me</button>
```

✅ events use camelCase
✅ functions passed as handlers

---

## ⚛️ Conditional Rendering

```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

or

```jsx
isLoading && <Spinner />
```

---

## ⚛️ Lists & Keys

```jsx
{users.map(user => (
  <li key={user.id}>{user.name}</li>
))}
```

✅ **always** use a stable `key`
✅ never use array indexes if avoidable

---

## ⚛️ Forms

```jsx
<form onSubmit={handleSubmit}>
  <input value={name} onChange={e => setName(e.target.value)} />
</form>
```

✅ Controlled inputs
✅ Validate on submit
✅ Store form state in parent if needed

---

## ⚛️ Lifting State Up

When two sibling components share data, lift it to their closest common parent.

---

## ⚛️ Composition vs Inheritance

React recommends **composition**:

```jsx
function Card({ children }) {
  return <div className="card">{children}</div>;
}
```

---

## ⚛️ React Router

Modern routing with react-router:

```jsx
import { BrowserRouter, Routes, Route } from "react-router-dom";

<BrowserRouter>
  <Routes>
    <Route path="/" element={<Home />} />
    <Route path="/about" element={<About />} />
  </Routes>
</BrowserRouter>
```

✅ nested routes
✅ route parameters

---

## ⚛️ Context API

Global state made easy:

```jsx
const ThemeContext = createContext('light');
```

✅ wrap app in `<Provider>`
✅ consume with `useContext`

---

## ⚛️ Hooks

The modern standard:

* `useState`
* `useEffect`
* `useContext`
* `useReducer`
* `useRef`

---

## ⚛️ Custom Hooks

Reuse logic cleanly:

```jsx
function useCounter() {
  const [count, setCount] = useState(0);
  return { count, increment: () => setCount(c => c + 1) };
}
```

---

## ⚛️ Portals

Render a component outside the normal DOM tree:

```jsx
ReactDOM.createPortal(<Modal />, document.getElementById('modal-root'));
```

✅ perfect for modals and overlays

---

## ⚛️ Error Boundaries

Catch errors in the render tree:

```jsx
class ErrorBoundary extends React.Component {
  componentDidCatch(error, info) {
    console.error(error);
  }
  render() {
    return this.props.children;
  }
}
```

---

## ⚛️ Code Splitting

Lazy-load heavy components:

```jsx
const Heavy = React.lazy(() => import('./Heavy'));
```

---

## ⚛️ Suspense & Lazy Loading

Combine with Suspense:

```jsx
<Suspense fallback={<Spinner />}>
  <Heavy />
</Suspense>
```

---

## ⚛️ Performance Optimization

* use `React.memo`
* use `useMemo` / `useCallback`
* virtualize lists
* split bundles
* measure with React DevTools Profiler

---

## ⚛️ Accessibility (a11y)

✅ semantic elements
✅ correct `aria-*`
✅ focus management
✅ screen-reader testing

Tools:

* axe
* Lighthouse
* eslint-plugin-jsx-a11y

---

## ⚛️ Testing

React Testing Library + Jest:

```jsx
import { render, screen } from '@testing-library/react';

test('renders title', () => {
  render(<App />);
  expect(screen.getByText(/hello/i)).toBeInTheDocument();
});
```

✅ test user behavior, not internals

---

## ⚛️ Styling Strategies

✅ CSS Modules
✅ Tailwind CSS
✅ Styled Components
✅ SCSS
✅ Utility classes

---

## ⚛️ TypeScript with React

```tsx
type Props = { name: string; };

const Welcome: React.FC<Props> = ({ name }) => (
  <h1>Hello, {name}</h1>
);
```

✅ prevents runtime errors
✅ improves teamwork

---

## ⚛️ Best Practices

* keep components small and focused
* use prop drilling carefully
* organize by feature or domain
* consistent naming
* break logic into hooks
* comment complex code
* test!

---

## 🚀 Advanced Project Ideas

| Project                  | Skills Practiced                 |
| ------------------------ | -------------------------------- |
| E-commerce SPA           | Routing, context, payments       |
| Chat App                 | WebSockets, state management     |
| Analytics Dashboard      | Charts, Grid, advanced forms     |
| Form Wizard              | validation, multi-step logic     |
| Markdown Blog            | dynamic routes, markdown parsing |
| Portfolio with Dark Mode | theming, context, accessibility  |

---

## ✅ Recommended Stack

* **React**
* **Vite** or **CRA**
* **React Router**
* **TypeScript**
* **Tailwind**
* **React Testing Library**
* **Prettier + ESLint**

---

## 📁 Folder Structure

```
src/
  components/
  hooks/
  context/
  pages/
  assets/
  utils/
  App.tsx
  main.tsx
```

---

## 🔗 Resources

* [React Docs](https://react.dev/)
* [React Router](https://reactrouter.com/)
* [TypeScript Handbook](https://www.typescriptlang.org/docs/)
* [Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
* [MDN JSX](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/JSX)

---
✅ **To create a React app for the first time**, follow these steps (assuming you already have **Node.js** installed — if not, I can guide you through that too):

---

## **1️⃣ Install Node.js (if you haven’t)**

* Go to [https://nodejs.org](https://nodejs.org)
* Download and install the **LTS version**

---

## **2️⃣ Create a React app**

React has a handy command-line tool called **Create React App**, which sets everything up for you.

Open your terminal or command prompt and run:

```bash
npx create-react-app my-app
```

➡️ *This creates a folder called `my-app` with all the React boilerplate.*

---

## **3️⃣ Navigate to your project folder**

```bash
cd my-app
```

---

## **4️⃣ Start the development server**

```bash
npm start
```

➡️ This will open your new React app in your browser at [http://localhost:3000](http://localhost:3000).

---

## **5️⃣ Start coding!**

* Go to the `src` folder
* Edit `App.js` to change your first React component
* The browser will live-reload as you save changes

---

**In short:**
✅ Install Node.js
✅ `npx create-react-app my-app`
✅ `cd my-app`
✅ `npm start`

---
**Happy Reacting!** ⚛️
