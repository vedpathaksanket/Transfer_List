#  React Transfer List

<div align="center">

![React](https://img.shields.io/badge/React-18%2B-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-5.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero-ff6b6b?style=for-the-badge)

**A sleek, fully interactive dual-panel Transfer List component built with React hooks.**  
Move items individually or in bulk between two lists — with smooth animations, dark mode support, and zero external dependencies.

[Live Demo](#) · [Installation](#installation) · [ Usage](#usage) · [ Contributing](#contributing)

</div>

---

##  Preview

> A dark-themed dual-panel UI where users can select items and transfer them between "Available" and "Selected" lists using directional controls.

```
┌─────────────────┐   ┌───┐   ┌─────────────────┐
│   Available  [6]│   │ ⇒ │   │   Selected   [4]│
│─────────────────│   │ → │   │─────────────────│
│ ☑ JavaScript   │   │ ← │   │ ☑ GraphQL       │
│ ☐ TypeScript   │   │ ⇐ │   │ ☐ Docker        │
│ ☐ React        │   └───┘   │ ☐ Node.js       │
│ ☐ Vue.js       │           │ ☐ Python        │
└─────────────────┘           └─────────────────┘
        Available: 4  ·  Selected: 4  ·  Total: 8
```

---

##  Features

| Feature | Description |
|---|---|
| ↔ Bidirectional transfer | Move items freely between left and right panels |
| Multi-select | Click any item to toggle selection; select multiple at once |
|  Move all | Bulk transfer every item in one click |
|  Staggered animations | Items animate in with a smooth CSS cascade on entry |
|  Dark mode ready | CSS variables auto-adapt to light/dark system theme |
|  Live stats bar | Real-time count of available, selected, and total items |
|  Empty state | Clean placeholder shown when a panel has no items |
|  Accessible | Keyboard-friendly, cursor interactions, visual feedback |

---

##  Tech Stack

| Technology | Purpose |
|---|---|
| **React 18+** | Component rendering and UI |
| **useState** | Panel item state management |
| **useCallback** | Optimized transfer handler functions |
| **CSS-in-JS** | Scoped styles via template literals — no stylesheet needed |
| **Google Fonts** | Syne (headings) + DM Mono (code items) |
| **Vite** | Lightning-fast dev server and bundler |
| **Zero libraries** | No MUI, no Tailwind, no external UI deps |

---

##  Project Structure

```
react-transfer-list/
│
├── public/
│   └── vite.svg
│
├── src/
│   ├── components/
│   │   └── TransferList.jsx     ← Main component (all logic + styles)
│   ├── App.jsx                  ← Root app — renders TransferList
│   └── main.jsx                 ← React DOM entry point
│
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

---

##  Installation

### Prerequisites

Make sure you have these installed:
- [Node.js](https://nodejs.org/) v18 or higher
- npm v9+ or yarn

### Clone & Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/react-transfer-list.git

# 2. Move into the project directory
cd react-transfer-list

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev
```

Then open [http://localhost:5173](http://localhost:5173) in your browser.

---

##  Build for Production

```bash
# Create an optimised production build
npm run build

# Preview the production build locally
npm run preview
```

Output will be in the `/dist` folder — ready to deploy anywhere.

---

## Usage

Drop the component anywhere in your React app:

```jsx
import TransferList from './components/TransferList';

export default function App() {
  return <TransferList />;
}
```

---

## Customizing Data

Each item uses a simple `{ id, label }` shape. Edit the two arrays at the top of `TransferList.jsx`:

```js
const initialLeft = [
  { id: 1, label: "JavaScript" },
  { id: 2, label: "TypeScript" },
  { id: 3, label: "React" },
  { id: 4, label: "Vue.js" },
  // Add as many as you need...
];

const initialRight = [
  { id: 9,  label: "GraphQL" },
  { id: 10, label: "Docker" },
];
```

>  Make sure every `id` is **unique** across both lists to avoid rendering bugs.

---

## ⌁ How the Controls Work

| Button | Action |
|---|---|
| `⇒` double arrow right | Move **all** items from left → right |
| `→` single arrow right | Move only **selected** items left → right |
| `←` single arrow left | Move only **selected** items right → left |
| `⇐` double arrow left | Move **all** items from right → left |

Click any item row to **select / deselect** it. Multiple items can be selected at once before transferring.

---

## Styling & Theming

All styles live inside a CSS template literal in `TransferList.jsx`. Key design tokens:

```css
/* Font families */
font-family: 'Syne', sans-serif;       /* headings & UI */
font-family: 'DM Mono', monospace;     /* item labels & badges */

/* Core color palette */
--accent:  #818cf8;   /* indigo  — selections, badges, borders */
--accent2: #ec4899;   /* pink    — move-all buttons & glow */
--bg:      #0a0a0f;   /* near-black background */
```

To retheme the component, change those values inside the `styles` constant at the top of `TransferList.jsx`.

---

##  Deployment

### Vercel (recommended — free)

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy with one command
vercel
```

### GitHub Pages

```bash
# Install gh-pages
npm install --save-dev gh-pages
```

Add to `package.json`:
```json
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
```

Then run:
```bash
npm run deploy
```

### Netlify

Drag and drop your `/dist` folder at [netlify.com/drop](https://app.netlify.com/drop) — live in 30 seconds, no account needed.

---

##  Roadmap

- [ ] Drag-and-drop reordering within panels
- [ ] Search / filter bar to find items quickly
- [ ] Full keyboard navigation (Tab, Space, Arrow keys)
- [ ] Export selected items as JSON / CSV
- [ ] Controlled mode — accept `value` + `onChange` props
- [ ] Virtualized list for 1000+ items (react-window)

---

##  Contributing

Contributions, issues, and feature requests are very welcome!

```bash
# 1. Fork the repository on GitHub

# 2. Clone your fork
git clone https://github.com/your-username/react-transfer-list.git

# 3. Create a feature branch
git checkout -b feature/my-awesome-feature

# 4. Make your changes and commit
git commit -m "feat: add my awesome feature"

# 5. Push your branch
git push origin feature/my-awesome-feature

# 6. Open a Pull Request on GitHub
```

Please follow [Conventional Commits](https://www.conventionalcommits.org/) format for commit messages:
- `feat:` — new feature
- `fix:` — bug fix
- `docs:` — documentation only
- `style:` — formatting, no logic change
- `refactor:` — code restructure

---

##  Reporting Bugs

Found something broken? [Open an issue](https://github.com/your-username/react-transfer-list/issues/new) and include:

1. Steps to reproduce the bug
2. What you expected to happen
3. What actually happened
4. Your browser name + version and OS

---

## ❓ FAQ

**Can I use this in a commercial project?**  
Yes — it's MIT licensed. Use it freely in any personal or commercial project.

**Does it work with TypeScript?**  
The component is plain JSX. Rename `TransferList.jsx` to `TransferList.tsx` and add prop types — it works out of the box.

**Can I pass in async data from an API?**  
Yes. Fetch your data and pass it to `useState` as the initial value, or update state after the fetch resolves.

**Does it support React 17?**  
It should work with React 17 since it uses only `useState` and `useCallback`, but it's tested against React 18+.

---

##  License

```
MIT License — Copyright (c) 2025 your-username

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

 Acknowledgements

- [Google Fonts](https://fonts.google.com/) — Syne & DM Mono typefaces
- [Vite](https://vitejs.dev/) — blazing-fast build tooling
- [React](https://react.dev/) — the UI library powering everything

---

<div align="center">

Made with  and React

** Star this repo if you found it helpful!**

</div>
