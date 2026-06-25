# 🎁 Birthday Gift Registry — Shobhit's Wishlist

A sleek, single-page birthday gift registry website with real-time claim syncing via **Supabase**. Friends can browse a curated wishlist, claim gifts with their name, and prevent duplicates — all without any login required.

> **Live for:** Shobhit's 23rd Birthday · June 28, 2026

---

## ✨ Features

- 🎉 **Live countdown timer** to the birthday (days, hours, minutes, seconds)
- 🛍️ **Gift cards** with images, prices, priority tags, and direct buy links
- ✅ **Claim system** — enter your name to lock in a gift
- 🔄 **Real-time sync** via Supabase — claims update across all visitors every 5 seconds
- 🔐 **Undo protection** — must re-enter your name to unclaim a gift
- 🗂️ **Category tabs** — filter by Gaming, Tech, Lifestyle, or Books
- ✨ **Polished UI** — glassmorphism cards, animated particles, mouse spotlight effect, typewriter tagline, and a loading screen
- 📱 **Fully responsive** — works great on mobile and desktop

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| HTML / CSS / Vanilla JS | Entire frontend — no frameworks |
| [Supabase](https://supabase.com) | Backend database for real-time claim storage |
| Google Fonts (Inter + Bebas Neue) | Typography |
| CSS Glassmorphism + Animations | Visual effects |

---

## 📁 Project Structure

```
├── index.html      # Everything — HTML, CSS, and JS in one file
```

This is a self-contained single-file app. No build tools, no npm, no dependencies to install.

---

## ⚙️ Setup & Configuration

### 1. Clone or download the project

```bash
git clone https://github.com/your-username/birthday-registry.git
cd birthday-registry
```

### 2. Configure Supabase (for real-time sync)

Create a free project at [supabase.com](https://supabase.com), then create a `claims` table:

```sql
create table claims (
  item_name text primary key,
  claimer   text
);
```

Then update these two constants near the top of the `<script>` tag in `index.html`:

```js
const SUPABASE_URL  = 'your-supabase-project-url';
const SUPABASE_ANON = 'your-supabase-anon-key';
```

> Without Supabase configured, the app still works locally — claims just won't persist across devices.

### 3. Customize the wishlist

Edit the `items` array in the `<script>` section:

```js
const items = [
  {
    name: 'Item Name',
    cat: 'gaming',          // gaming | tech | lifestyle | books
    priority: 'high',       // high | medium | '' (blank)
    note: 'A short note',
    price: '₹999',
    type: 'link',           // 'link' for direct URL, 'ref' for Amazon search
    url: 'https://...',     // used when type is 'link'
    refs: ['search term'],  // used when type is 'ref'
    img: 'https://...'      // product image URL
  },
  // ...
];
```

### 4. Update birthday details

In the HTML and JS, update the birthday date and name as needed:

```js
// Countdown target date (IST)
new Date('2026-06-28T00:00:00+05:30')
```

---

## 🚀 Deployment

Since it's a single HTML file, you can host it anywhere for free:

- **[GitHub Pages](https://pages.github.com/)** — push to a repo, enable Pages
- **[Netlify Drop](https://app.netlify.com/drop)** — drag and drop the file
- **[Vercel](https://vercel.com/)** — import the repo and deploy instantly

---

## 🎨 Wishlist Categories

| Category | Items include |
|---|---|
| 🎮 Gaming | RGB strips, controller, microphone, grip tape, puzzles, RC car |
| 💻 Tech | Laptop stand, multiport connector, cable organizer |
| 👕 Lifestyle | F1 merch, jerseys, hats, balisong |
| 📚 Books | Mystery, fiction, and self-help titles |

---

## 🤝 Contributing

Have a suggestion for the wishlist or a UI improvement? Open an issue or submit a PR!

---

## 📄 License

MIT — use it, fork it, make your own birthday registry!
