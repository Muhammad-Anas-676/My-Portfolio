<div align="center">

<img src="https://i.ibb.co/5hdGHmDt/circle-image-1.png" alt="Anas" width="120" style="border-radius:50%"/>

# ✦ Anas Dev — AI Portfolio

**Production-grade personal portfolio with Firebase-powered Admin Panel**

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-Visit_Portfolio-3b82f6?style=for-the-badge&logo=vercel&logoColor=white)](https://resumepro-pk.vercel.app)
[![Admin Panel](https://img.shields.io/badge/🔐_Admin_Panel-admin.html-6366f1?style=for-the-badge&logo=firebase&logoColor=white)](#)
[![Firebase](https://img.shields.io/badge/Firebase-Connected-ffca28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)](LICENSE)

<br/>

> *"I Build Intelligent & Beautiful Web Experiences."*
>
> — Anas · AI Prompt Engineer & Front-End Developer · Karachi, Pakistan 🇵🇰

</div>

---

## 📸 Preview

| User Portfolio | Admin Dashboard |
|:-:|:-:|
| Dark mode hero with animated ring photo | Sidebar-based admin with live charts |
| Firebase real-time projects & skills | Card / List view for project management |
| Services section with numbered cards | Full CRUD — Projects, Skills, Messages |

---

## ✨ Features

### 🖥️ User Portfolio (`index.html`)

- **Hero Section** — Animated conic-gradient photo ring, floating badges, desktop visual panel with quick-info cards & tech stack strip
- **About Section** — Clean single-column layout, info grid (Location · Speciality · Languages · Availability)
- **Skills Section** — Firebase-driven skill chips with icon, color & level — no dummy data
- **Projects Section** — Firebase-driven cards with 16/9 thumbnails, filter by category (AI Tools · Web Apps · Landing Pages · Utilities), real-time project count in hero stat
- **Services Section** — Numbered cards (01–06), hover accent bar, service chips — 3-column desktop grid
- **Contact Section** — Contact links + form saved to Firestore
- **Footer** — GitHub & WhatsApp icons only, links auto-updated from Firebase Settings
- **Dark / Light Mode** — Persisted via `localStorage`
- **60fps Optimized** — `will-change: transform`, `translate3d`, GPU-accelerated animations

### 🔐 Admin Panel (`admin.html`)

- **Firebase Auth** — Email/password login, protected routes via `onAuthStateChanged`
- **Sidebar Navigation** — Dashboard · Projects · Skills · Messages · Settings — with collapse support
- **Sidebar Controls** — Dark/Light toggle · View Portfolio · Logout — all inside sidebar
- **Dashboard** — 4 stat cards (Total Projects · Live Projects · Skills Listed · Messages) + **2 live Chart.js charts** (Projects by Category doughnut + Skills by Level bar) + Recent Projects table
- **Projects Manager** — **Card view & List view toggle** — Full CRUD with Add / Edit / Delete
- **Skills Manager** — Icon grid with hover actions — Full CRUD
- **Messages** — Incoming contact form submissions from Firestore
- **Settings** — Profile · Contact Info · WhatsApp · GitHub · LinkedIn · Photo URL · Hero Stats · Availability · Hire Me link

---

## 🗂️ Project Structure

```
my-portfolio/
│
├── index.html          # 🌐 Main user-facing portfolio
├── admin.html          # 🔐 Admin panel (Firebase Auth protected)
└── README.md           # 📖 You are here
```

> Single-file architecture — no build tools, no npm, no dependencies to install.
> Both files are fully self-contained with all CSS, JS, and Firebase SDK loaded via CDN.

---

## 🚀 Getting Started

### Prerequisites
- A Firebase project (Firestore + Authentication enabled)
- A GitHub account (to host via Pages / Vercel)

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/my-portfolio.git
cd my-portfolio
```

### 2. Firebase is Already Configured ✅

The Firebase config is already embedded in both files. No `.env` needed.

```js
// Already inside index.html & admin.html
const firebaseConfig = {
  apiKey: "...",
  authDomain: "my-portfolio-b5d90.firebaseapp.com",
  projectId: "my-portfolio-b5d90",
  ...
};
```

### 3. Enable Firebase Authentication

1. Go to [Firebase Console](https://console.firebase.google.com) → your project
2. **Authentication** → Sign-in method → Enable **Email/Password**
3. **Authentication** → Users → **Add User** → enter your admin email + password

### 4. Set Up Firestore Collections

The admin panel auto-creates documents. Required collections:

| Collection | Description |
|---|---|
| `projects` | Portfolio projects added via admin |
| `skills` | Tech skills added via admin |
| `contacts` | Form submissions from visitors |
| `settings` | Profile settings saved from admin |

> No manual setup needed — just add data through the Admin Panel.

### 5. Deploy

**Option A — Vercel (Recommended)**
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

**Option B — GitHub Pages**
1. Push to `main` branch
2. Go to repo **Settings → Pages**
3. Source: `main` branch, `/ (root)`
4. Your site: `https://YOUR_USERNAME.github.io/my-portfolio`

**Option C — Local**
```bash
# Just open in browser — no server needed
open index.html
```

---

## 🔑 Admin Panel Usage

### Login
Navigate to `admin.html` → enter your Firebase Auth credentials

### Managing Projects
1. Go to **Projects** section
2. Click **Add Project**
3. Fill in all fields:

| Field | Description | Example |
|---|---|---|
| **Project Name** | Display name | `ResumePro` |
| **Category** | Used for filtering | `webapp` / `ai` / `tool` |
| **Description** | Short project summary | `Firebase-backed CV platform` |
| **Live URL** | Deployed URL | `https://project.vercel.app` |
| **GitHub URL** | Optional repo link | `https://github.com/user/repo` |
| **Thumbnail URL** | Project preview image | `https://i.ibb.co/...` (16:9 ratio) |
| **Icon Class (FA)** | FontAwesome icon fallback | `fas fa-brain` / `fab fa-react` |
| **Tech Stack** | Comma-separated langs | `HTML, CSS, JS, Firebase` |
| **Tags** | Filter categories | `webapp, firebase, ai` |
| **Display Order** | Sort position (1 = first) | `1` |

> **Thumbnail**: Use a 16:9 image (e.g. 1280×720px). Host on [imgbb.com](https://imgbb.com) for free.
>
> **Icon Class**: Visit [fontawesome.com/icons](https://fontawesome.com/icons) → search → copy the class e.g. `fas fa-rocket`
>
> **Display Order**: Lower number appears first. Set `1` for most important project.

### Managing Skills
| Field | Description | Example |
|---|---|---|
| **Skill Name** | Technology name | `JavaScript` |
| **Level** | Proficiency | `Expert` / `Advanced` / `Intermediate` / `Beginner` |
| **Icon Class (FA)** | FontAwesome icon | `fab fa-js-square` |
| **Icon Color** | Brand hex color | `#f7df1e` (JS yellow) |
| **Display Order** | Sort position | `1` |

**Common Icon Classes & Colors:**

| Skill | Icon Class | Color |
|---|---|---|
| HTML5 | `fab fa-html5` | `#e34f26` |
| CSS3 | `fab fa-css3-alt` | `#1572b6` |
| JavaScript | `fab fa-js-square` | `#f7df1e` |
| React | `fab fa-react` | `#61dafb` |
| Firebase | `fas fa-fire` | `#ffca28` |
| Python | `fab fa-python` | `#3776ab` |
| Node.js | `fab fa-node-js` | `#339933` |
| Git | `fab fa-git-alt` | `#f05032` |
| Figma | `fab fa-figma` | `#f24e1e` |
| AI/Prompting | `fas fa-brain` | `#6366f1` |
| Vercel | `fas fa-cloud` | `#3b82f6` |

### Settings Panel
Configure your portfolio content from **Settings**:

| Field | Effect |
|---|---|
| **WhatsApp Number** | Updates footer & contact WhatsApp link |
| **GitHub URL** | Updates footer GitHub icon link |
| **Photo URL** | Changes hero & about section photo |
| **Display Name** | Your name shown on portfolio |
| **Tagline** | Role text below name |
| **Years of Experience** | Hero stat counter |
| **Availability** | Open to Work / Busy / Unavailable |

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| **HTML5** | Markup structure |
| **CSS3** | Glassmorphism, custom properties, animations |
| **Vanilla JavaScript** | All interactivity, DOM manipulation |
| **Firebase Firestore** | Real-time database for projects, skills, contacts, settings |
| **Firebase Authentication** | Admin panel login security |
| **Font Awesome 6** | Icons throughout UI |
| **Google Fonts** | Outfit · Playfair Display · Dancing Script |
| **Chart.js 4** | Dashboard analytics charts |

---

## ⚡ Performance

- **60fps animations** — GPU-accelerated via `will-change: transform` and `translate3d()`
- **DocumentFragment** batch DOM rendering — zero layout thrashing
- **IntersectionObserver** — fade-up animations triggered only when visible
- **Lazy loading** — project thumbnails load on demand
- **No framework overhead** — pure HTML/CSS/JS, instant load

---

## 📱 Responsive Design

| Breakpoint | Layout |
|---|---|
| `> 1024px` | Desktop — 2-col hero, 3-col services, sidebar admin |
| `768px – 1024px` | Tablet — stacked hero, 2-col services |
| `< 768px` | Mobile — single column, hamburger menu, bottom sidebar |

---

## 🔒 Security Notes

- Admin panel is protected by **Firebase Authentication** — no one can access without credentials
- Firebase API keys in this repo are **client-side safe** — they are restricted by Firebase Security Rules
- Configure Firestore Rules to allow only authenticated writes:

```js
// Firestore Security Rules (recommended)
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /projects/{doc} { allow read; allow write: if request.auth != null; }
    match /skills/{doc}   { allow read; allow write: if request.auth != null; }
    match /settings/{doc} { allow read; allow write: if request.auth != null; }
    match /contacts/{doc} { allow create; allow read, write: if request.auth != null; }
  }
}
```

---

## 📄 License

MIT License — free to use, modify and distribute.

---

<div align="center">

**Built with ❤️ by Anas**

*AI Prompt Engineer & Front-End Developer · Karachi, Pakistan*

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-Visit-3b82f6?style=flat-square)](https://resumepro-pk.vercel.app)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-24292e?style=flat-square&logo=github)](https://github.com)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-Contact-25d366?style=flat-square&logo=whatsapp&logoColor=white)](https://wa.me/923001234567)

<sub>Made By Anas · <em>Turning Ideas into Digital Reality</em></sub>

</div>
