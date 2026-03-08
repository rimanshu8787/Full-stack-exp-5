# Full-stack-exp-5
 React Advanced State Management

A full-stack React project demonstrating Redux Toolkit, Context API, React Router, and useMemo optimization.

## 🚀 Features Implemented

### ✅ Redux Toolkit (State Management)

- **Store Configuration**: Configured Redux store with `configureStore`
- **Cart Slice**: Created `cartSlice` with 3 core actions:
  - `addItem`: Add products to cart
  - `removeItem`: Remove items from cart
  - `updateQuantity`: Update item quantity
- **Usage**: Cart page dispatches actions and selects state using `useDispatch` and `useSelector`

### ✅ Context API (Global State)

- **AppContext**: Manages global state for:
  - `theme`: Light/dark mode toggle
  - `user`: Mock user profile data
- **Provider**: `AppContextProvider` wraps the entire app
- **Components Using Context**:
  - Navbar: Displays user name and theme toggle
  - Analytics: Displays personalized welcome message
  - Cart: Displays user information

### ✅ useMemo (Performance Optimization)

- **Analytics Page**: Calculates derived analytics stats (total views, clicks, conversions, conversion rate)
- **Cart Page**: Computes cart summary (total price, tax, final total, item count) - recalculates only when cartItems change
- Both implementations prevent unnecessary recalculations

### ✅ React Router (Multi-page Navigation)

- **Pages**: 4 total pages with navigation
  - Home: Landing page with feature overview
  - Projects: Portfolio showcase (from Exp 4)
  - Analytics: Dashboard with statistics and useMemo (from Exp 4)
  - Cart: Shopping cart with Redux and useMemo (NEW - Exp 5)
- **Navbar**: Links to all pages, integrated with router

### ✅ UI/UX Design

- Clean, modern interface with consistent styling
- Dark mode toggle functionality
- Responsive design (mobile, tablet, desktop)
- Smooth transitions and hover effects
- Professional color scheme

## 📁 Project Structure

```
src/
├── components/
│   ├── Navbar.jsx
│   └── Navbar.css
│
├── context/
│   └── AppContext.jsx
│
├── redux/
│   ├── store.js
│   └── slices/
│       └── cartSlice.js
│
├── pages/
│   ├── Home.jsx
│   ├── Home.css
│   ├── Projects.jsx
│   ├── Projects.css
│   ├── Analytics.jsx
│   ├── Analytics.css
│   ├── Cart.jsx
│   └── Cart.css
│
├── App.jsx
├── App.css
├── main.jsx
└── index.css
```

## 🔧 Installation & Setup

1. **Install Dependencies**

   ```bash
   npm install
   ```

2. **Run Development Server**

   ```bash
   npm run dev
   ```

   The app will open at `http://localhost:5173`

3. **Build for Production**
   ```bash
   npm run build
   ```

## 📚 Technologies Used

- **React 18**: UI library
- **Redux Toolkit**: State management
- **React Router v6**: Client-side routing
- **Vite**: Build tool and dev server

## 🎯 Key Implementation Details

### Redux Flow

```
User adds product → dispatch(addItem) → cartSlice reducer → store updated
→ useSelector reads updated state → Component re-renders with new cart
```

### Context API Flow

```
AppContextProvider wraps App → AppContext.Provider with value prop
→ Components consume using useContext(AppContext)
→ Theme toggle updates context → Dark mode applied via CSS classes
```

### useMemo Optimization

```
Dependency array [cartItems] → Memorized cartSummary calculated
→ If cartItems unchanged → Return cached value (no recalculation)
```

## 📸 Screenshots

Screenshots are located in the `/screenshots` folder:

- `home.png` - Home page
- `cart.png` - Cart page with Redux and useMemo
- `analytics.png` - Analytics page with useMemo optimization

## 🌐 Deployment

Deployed on Vercel: `[your-deployment-link].vercel.app`

## ✨ Experiment 5 Enhancements

- ✅ Replaced useReducer with Redux Toolkit
- ✅ Implemented Context API for theme management
- ✅ Added useMemo for performance optimization
- ✅ Created new Cart page demonstrating all advanced features
- ✅ Maintained responsive and modern design
- ✅ 4 interconnected pages with smooth navigation

## 📋 Checklist Verification

- ✅ App runs without errors (`npm run dev`)
- ✅ React Router works with 3+ pages
- ✅ Context Provider wraps app and used in 2+ components
- ✅ Redux Toolkit store with slice + 3 actions
- ✅ Redux state used in 2+ components (Cart, Analytics pages)
- ✅ useMemo used for derived data (Analytics, Cart)
- ✅ New Experiment 5 page created (Cart)
- ✅ README updated with all features
- ✅ Screenshots added in /screenshots folder

---

**Created**: March 2026  
**Assignment**: Experiment 5 - Advanced React State Management  
**Status**: ✅ Complete
