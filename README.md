# Rubi Client UI

**Modern Vue 3 Frontend • Component-Driven • Scalable Architecture**

Rubi Client UI is a **Vue 3 + Vite + Vuetify** front-end application designed for scalability, reusability, and long-term maintainability.  
The project follows a **component-driven architecture** with clear separation of concerns across layouts, views, state management, plugins, and styles.

This repository is ideal for teams building **production-ready dashboards, marketing pages, and user-facing platforms** with Vue 3.

---

## ✨ Key Highlights

- ⚡ Lightning-fast dev experience with **Vite**
- 🧱 Component-driven structure (Atoms / Molecules / Organisms)
- 🎨 **Vuetify 3** with SCSS-based theming
- 🧭 **Vue Router 4** with layout-based routing
- 🗂️ **Pinia** for predictable global state
- ♻️ Reusable composables for shared logic
- 🧩 Clean plugin registration system
- 🚀 Optimized for scalability and team collaboration

---

## 🛠 Tech Stack

| Category  | Tools                                      |
| --------- | ------------------------------------------ |
| Framework | Vue 3                                      |
| Bundler   | Vite                                       |
| UI        | Vuetify 3, Material Design Icons           |
| Routing   | Vue Router 4 (History Mode)                |
| State     | Pinia                                      |
| Styling   | SCSS, custom fonts                         |
| Utilities | Swiper, Bootstrap 5, v-mask, WebFontLoader |

---

## 📦 Prerequisites

Make sure you have the following installed:

- **Node.js** ≥ 16
- **npm** ≥ 8

Check versions:

```bash
node -v
npm -v
```

````

---

## 🚀 Getting Started

### 1️⃣ Install dependencies

```bash
npm install
```

### 2️⃣ Run development server

```bash
npm run dev
```

App runs at:
👉 **[http://localhost:3000](http://localhost:3000)**

### 3️⃣ Build for production

```bash
npm run build
```

### 4️⃣ Preview production build

```bash
npm run preview
```

### 5️⃣ Lint & auto-fix

```bash
npm run lint
```

---

## 🗂 Project Structure (High Level)

```
src/
├── main.js                 # App entry point
├── plugins/                # Vuetify, Router, Pinia, Fonts
├── router/                 # Route definitions
├── store/                  # Pinia stores
├── layouts/                # App layouts (Default, etc.)
├── views/                  # Route-level pages
├── components/             # Reusable UI components
├── composables/            # Shared logic hooks
├── styles/                 # Global SCSS & themes
├── assets/                 # App assets
public/                     # Static files
```

> 🔹 `@` alias points to `src/` (configured in `vite.config.js`)

---

## 🧩 App Bootstrap Flow

1. `createApp(App)` → `src/main.js`
2. Load global SCSS (theme, typography)
3. Register plugins via `registerPlugins(app)`
4. Mount app to `#app`

---

## 🧭 Routing System

- Centralized in `src/router/index.js`
- Uses `createWebHistory`
- Default layout wraps all child routes
- Pages are **lazy-loaded** for performance

### Example Route

```js
{
  path: 'my-feature',
  name: 'my-feature',
  component: () => import('@/views/MyFeature.vue'),
}
```

### Navigation

```vue
<router-link :to="{ name: 'my-feature' }" />
```

---

## 🧱 Layout System

**Default Layout**

- Header (AppBar)
- Footer
- `<router-view />` for pages

Location:

```
src/layouts/default/
├── Default.vue
├── AppBar.vue
├── Footer.vue
└── View.vue
```

### Creating a New Layout

1. Create a layout component under `src/layouts/`
2. Assign it to a route
3. Place `<router-view />` inside the layout

---

## 🗂 State Management (Pinia)

- Global Pinia instance registered via plugins
- Stores live in `src/store/`

### Example Store

```js
import { defineStore } from "pinia";

export const useUserStore = defineStore("user", {
  state: () => ({
    profile: null,
  }),
  actions: {
    setProfile(data) {
      this.profile = data;
    },
  },
});
```

Usage:

```js
const userStore = useUserStore();
userStore.setProfile(profile);
```

---

## 🔌 Plugin System

All plugins are registered in **one place**:

```
src/plugins/index.js
```

Includes:

- Vuetify
- Vue Router
- Pinia
- WebFontLoader

### Adding a New Plugin

```bash
npm install v-mask
```

```js
import VueMask from "v-mask";

app.use(VueMask);
```

---

## 🔁 Composables (Reusable Logic)

Located in:

```
src/composables/
```

Examples:

- Modal state handling
- Dynamic script injection
- UI helpers (size, color mapping)

### Usage Example

```js
import useClubrubiModal from "@/composables/use-clubrubi-modal";

const { openClubSignModal, setClubSignState } = useClubrubiModal();
setClubSignState(true);
```

---

## 🎨 Styling & Assets

- Global SCSS lives in `src/styles/`
- Vuetify theme variables defined in `settings.scss`
- Icons loaded via Material Design Icons
- Public assets served from `/public`

---

## 📌 Best Practices

- Keep **views thin**
- Move logic to **composables**
- Share state via **Pinia**
- Reuse UI components aggressively
- Use `@` alias for clean imports
- Run lint before commits

---

## 🧪 Troubleshooting

| Issue             | Fix                                      |
| ----------------- | ---------------------------------------- |
| App not loading   | Check Node version                       |
| Icons missing     | Run `npm install`                        |
| Port conflict     | Change `server.port` in `vite.config.js` |
| Fonts not loading | Update WebFontLoader config              |

---

## 📄 License

This project is proprietary / internal (update if open-source).

---

## 🤝 Contributing

Feel free to submit issues or improvements.
Clean code, meaningful commits, and consistency are expected.

```

```
````
