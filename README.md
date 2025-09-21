# React + Tailwind CSS Configuration Guide

A step-by-step guide to set up **Tailwind CSS** in a **React** project, including configuration tips, common issues, and best practices.

---

## Table of Contents

* [Prerequisites](#prerequisites)
* [Project Setup](#project-setup)
* [Installing Tailwind CSS](#installing-tailwind-css)
* [Configuring Tailwind CSS](#configuring-tailwind-css)
* [Using Tailwind CSS in React](#using-tailwind-css-in-react)
* [Customizing Tailwind](#customizing-tailwind)
* [Best Practices](#best-practices)
* [Troubleshooting](#troubleshooting)
* [References](#references)

---

## Prerequisites

* Node.js (v14 or above)
* npm or yarn
* Basic knowledge of React

---

## Project Setup

**Using Vite (recommended):**

```bash
npm create vite@latest my-app
cd my-app
npm install
```

**Or Using Create React App:**

```bash
npx create-react-app my-app
cd my-app
```

---

## Installing Tailwind CSS

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

This will create:

* `tailwind.config.js`
* `postcss.config.js`

---

## Configuring Tailwind CSS

Edit `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Add Tailwind directives to `src/index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Import CSS in `src/main.jsx` or `src/index.js`:

```javascript
import './index.css';
```

---

## Using Tailwind CSS in React

```jsx
function App() {
  return (
    <div className="flex items-center justify-center h-screen bg-gray-100">
      <h1 className="text-4xl font-bold text-blue-600">Hello, Tailwind!</h1>
    </div>
  );
}
export default App;
```

---

## Customizing Tailwind

Extend theme in `tailwind.config.js`:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#1D4ED8',
        secondary: '#9333EA',
      },
      spacing: {
        128: '32rem',
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
}
```

---

## Best Practices

* Use meaningful class combinations.
* Use `@apply` for repetitive classes.
* Use responsive utilities like `sm:`, `md:`, `lg:`.

---

## Troubleshooting

* **Tailwind classes not working:**

  * Check `content` paths in `tailwind.config.js`
  * Restart dev server

* **Custom theme not applied:**

  * Ensure Tailwind CSS is imported correctly

---

## References

* [Tailwind CSS Documentation](https://tailwindcss.com/docs)
* [React Documentation](https://reactjs.org/docs/getting-started.html)
* [Vite Documentation](https://vitejs.dev/guide/)

---

**Happy Coding! 🚀**
