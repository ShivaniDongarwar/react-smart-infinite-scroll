# react-smart-infinite-scroll

A lightweight and reusable **React Infinite Scroll Hook** built with TypeScript.
It helps you easily implement infinite scrolling behavior in scrollable containers without adding heavy dependencies.

---

## ✨ Features

* 🚀 Lightweight and simple
* ⚛️ Built for React
* 🧠 Prevents multiple API calls while loading
* 📦 TypeScript support
* 🔁 Customizable scroll threshold
* 🧩 Works with any list or grid

---

## 📦 Installation

```bash
npm install react-smart-infinite-scroll
```

or

```bash
yarn add react-smart-infinite-scroll
```

---

## 🚀 Usage

```tsx
import React from "react";
import { useInfiniteScroll } from "react-smart-infinite-scroll";

function App() {
  const { containerRef } = useInfiniteScroll({
    hasMore: true,
    isLoading: false,
    onLoadMore: () => {
      console.log("Load more data...");
    },
    threshold: 100,
  });

  return (
    <div
      ref={containerRef}
      style={{ height: "400px", overflowY: "auto", border: "1px solid #ccc" }}
    >
      {/* Your list items here */}
      <p>Scroll down to load more...</p>
    </div>
  );
}

export default App;
```

---

## ⚙️ API

| Option     | Type       | Required | Description                                      |
| ---------- | ---------- | -------- | ------------------------------------------------ |
| hasMore    | boolean    | ✅        | Indicates if more data is available              |
| isLoading  | boolean    | ✅        | Prevents multiple triggers while data is loading |
| onLoadMore | () => void | ✅        | Function called when scroll reaches bottom       |
| threshold  | number     | ❌        | Distance (in px) from bottom to trigger load     |

---

## 📘 Example Use Case

Ideal for:

* Infinite feed
* Chat applications
* Large datasets
* Product listings
* Activity timelines

---

## 🧠 How It Works

The hook listens to the **scroll event** on the container element and checks:

```
scrollHeight - scrollTop <= clientHeight + threshold
```

When the user reaches near the bottom, the **onLoadMore** callback triggers to fetch more data.

---

## 📦 Peer Dependencies

Make sure your project has **React installed**.

```
react >= 17
```

---

## 🛠 Development

Clone the repo and run:

```bash
npm install
npm run dev
```

To build the package:

```bash
npm run build
```

---

## 📄 License

MIT

---

## 👩‍💻 Author

Shivani
Frontend Developer (React)

---
