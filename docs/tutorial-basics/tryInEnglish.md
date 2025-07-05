---
sidebar_position: 7
---

# Getting Started with Custom React Hooks

Custom hooks are a powerful feature of React that help you **encapsulate reusable logic** across your components.

They make your code **cleaner**, **more modular**, and **easier to maintain**.

If you’re comfortable with React’s `useState` and `useEffect`, custom hooks are your next step!

## Why use custom hooks?

- Eliminate code duplication across components
- Extract complex logic into separate files
- Improve readability and testability

## Example: useWindowWidth Hook

```jsx
import { useState, useEffect } from "react";

function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener("resize", handleResize);
    return () => window.removeEventListener("resize", handleResize);
  }, []);

  return width;
}
```
