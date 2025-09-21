# React + Tailwind CSS with Vite Guide

A step-by-step guide to set up **Tailwind CSS** in a **React** project using **Vite**, including configuration tips, plugin integration, and best practices.

---

## Table of Contents

* [Prerequisites](#prerequisites)
* [Project Setup](#project-setup)
* [Installing React DOM](#installing-react-dom)
* [Installing React Router](#installing-react-router)
* [Installing Tailwind CSS with Vite Plugin](#installing-tailwind-css-with-vite-plugin)
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

**Create a new Vite React project:**

```bash
npm create vite@latest my-project
cd my-project
npm install
```

---

## Installing React DOM

Install `react-dom` to enable React rendering in the browser:

```bash
npm install react-dom
```

---

## Installing React Router

Install `react-router-dom` for routing support in your React project:

```bash
npm install react-router-dom
```

---

## Installing Tailwind CSS with Vite Plugin

1. **Install Tailwind CSS and Vite plugin**

```bash
npm install tailwindcss @tailwindcss/vite
```

2. **Configure the Vite plugin**

```typescript
// vite.config.ts
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [
    tailwindcss(),
  ],
})
```

3. **Import Tailwind CSS**

```css
/* src/style.css */
@import "tailwindcss";
```

4. **Start your build process**

```bash
npm run dev
```

5. **Use Tailwind in your HTML/JSX**

```html
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/src/style.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```

Or in React JSX:

```jsx
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
      </Routes>
    </Router>
  );
}

function Home() {
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
* [React Router Documentation](https://reactrouter.com/)
* [Vite Documentation](https://vitejs.dev/guide/)

---

**Happy Coding! 🚀**
