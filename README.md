# Kigali Data Explorer

- **Student Name:** Imanishimwe Kersy Merissa
- **API Used:** [DummyJSON Products API](https://dummyjson.com/docs/products)
- **Live Deployed Link:** [View Live App](#)
- **Video Walkthrough Link:** [Watch Video Demonstration](#)

## Features Included
1. **Fetch on Load:** Automatically loads 100 products using `async/await`.
2. **Reusable Helper:** `getJSON(url)` in `src/api.js` checks `response.ok` and throws clear errors.
3. **UI States:** Fully handles Loading (animate-pulse), Error (+ working Retry button), Empty state, and Success.
4. **Responsive Grid:** Product cards rendered with `map` and destructuring using Tailwind CSS.
5. **Search & Filter:** Live case-insensitive search and category filtering built from data.
6. **Sorting:** Multiple sort options (price ascending/descending, name A-Z) using `toSorted` (no mutation).
7. **Details View & Stats:** Click a card to open a `<dialog>` modal with details; computed average price and item counts using `reduce`.
8. **Parallel Requests:** Uses `Promise.all` in `api.js` to fetch categories and products simultaneously.

## State Shape & Flow
```javascript
const state = {
  items: [],
  categories: [],
  status: "loading", // loading, success, error
  error: null,
  query: "",
  filter: "all",
  sort: "default",
  visibleItems: [],
  visibleCount: 0,
  avgPrice: "0.00",
  selectedProduct: null
};