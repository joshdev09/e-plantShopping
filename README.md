# 🌿 Paradise Nursery — E-Plant Shopping

A single-page plant e-commerce app built with React and Redux Toolkit. Browse plants across five curated categories, add them to a cart, and manage quantities in real time — all with a smooth landing page → catalog → cart flow.

**Where Green Meets Serenity**

## Features

- **Landing page** with an "About Us" section and a "Get Started" call-to-action that transitions into the product catalog
- **Product catalog** organized into five categories:
  - Air Purifying Plants
  - Aromatic Fragrant Plants
  - Insect Repellent Plants
  - Medicinal Plants
  - Low Maintenance Plants
- **Shopping cart** powered by Redux Toolkit, with:
  - Add to cart (button disables per item once added)
  - Increment / decrement quantity
  - Remove item
  - Live cart badge showing total item count in the navbar
  - Running total cost calculation
- **Client-side navigation** between Home, Plants, and Cart views without a router — all state-driven within `App.jsx`

## Tech Stack

- [React 18](https://react.dev/)
- [Redux Toolkit](https://redux-toolkit.js.org/) + [React Redux](https://react-redux.js.org/)
- [Vite](https://vitejs.dev/) — dev server and build tool
- [ESLint](https://eslint.org/) — linting
- [gh-pages](https://www.npmjs.com/package/gh-pages) — deployment to GitHub Pages

## Project Structure

```
e-plantShopping-main/
├── public/
│   └── vite.svg
├── src/
│   ├── assets/
│   │   └── react.svg
│   ├── App.jsx              # Root component; toggles landing page vs. catalog
│   ├── App.css
│   ├── AboutUs.jsx           # About section on the landing page
│   ├── AboutUs.css
│   ├── ProductList.jsx       # Navbar, category grid, product cards
│   ├── ProductList.css
│   ├── CartItem.jsx          # Cart view: quantities, totals, checkout stub
│   ├── CartItem.css
│   ├── CartSlice.jsx         # Redux slice: addItem, removeItem, updateQuantity
│   ├── store.js               # Redux store configuration
│   ├── index.css
│   └── main.jsx               # App entry point, wraps App in Redux Provider
├── index.html
├── vite.config.js
└── package.json
```

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or later recommended)
- npm

### Installation

```bash
# Clone the repository
git clone https://github.com/joshdev09/e-plantShopping.git
cd e-plantShopping

# Install dependencies
npm install
```

### Development

```bash
npm run dev
```

This starts the Vite dev server. Open the printed local URL in your browser to view the app.

### Build

```bash
npm run build
```

Produces a production build in the `dist/` folder.

### Preview Production Build

```bash
npm run preview
```

### Lint

```bash
npm run lint
```

## How It Works

- **Landing → Catalog transition:** `App.jsx` holds a `showProductList` boolean that controls a CSS fade between the landing page and the product grid — no routing library needed.
- **State management:** Cart state lives in a single Redux slice (`CartSlice.jsx`). Adding a plant that's already in the cart increments its quantity instead of duplicating the entry.
- **Cart totals:** `CartItem.jsx` parses each plant's `cost` string (e.g. `"$15"`) to compute per-item and overall totals on the fly.
- **Checkout:** The checkout button is currently a placeholder (`alert('Functionality to be added for future reference')`) — a natural next step for future development.

## Roadmap Ideas

- [ ] Implement real checkout / payment flow
- [ ] Add persistent cart storage (e.g. localStorage or a backend)
- [ ] Add product search and filtering
- [ ] Add unit tests for cart reducer logic
- [ ] Migrate to React Router for real URL-based navigation

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](./LICENSE) file for details.
