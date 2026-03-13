<div align="center">

<br/>

```
███╗   ███╗███████╗██████╗ ██╗ ██████╗ █████╗ ██████╗ ██████╗
████╗ ████║██╔════╝██╔══██╗██║██╔════╝██╔══██╗██╔══██╗██╔══██╗
██╔████╔██║█████╗  ██║  ██║██║██║     ███████║██████╔╝██║  ██║
██║╚██╔╝██║██╔══╝  ██║  ██║██║██║     ██╔══██║██╔══██╗██║  ██║
██║ ╚═╝ ██║███████╗██████╔╝██║╚██████╗██║  ██║██║  ██║██████╔╝
╚═╝     ╚═╝╚══════╝╚═════╝ ╚═╝ ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═════╝
```

### Emergency Health Card Generator

**A static web application to generate portable emergency health cards — built with pure HTML & CSS, ready for a Java Servlet backend.**

<br/>

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-luminous--manatee-E63946?style=for-the-badge&logoColor=white)](https://luminous-manatee-5923e1.netlify.app/)
[![Netlify Status](https://img.shields.io/badge/Netlify-Deployed-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)](https://luminous-manatee-5923e1.netlify.app/)
[![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://github.com/gagang135/EmergencyHealthCardGenerator)
[![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://github.com/gagang135/EmergencyHealthCardGenerator)
[![Java Ready](https://img.shields.io/badge/Java_Servlet-Backend_Ready-ED8B00?style=for-the-badge&logo=java&logoColor=white)](https://github.com/gagang135/EmergencyHealthCardGenerator)

<br/>

> 🚨 **In an emergency, seconds matter.** MediCard generates a compact, printable health card with your critical medical information — instantly accessible to first responders.

<br/>

</div>

---

## 🔗 Live Preview

**→ [https://luminous-manatee-5923e1.netlify.app/](https://luminous-manatee-5923e1.netlify.app/)**

Deployed on Netlify from the `main` branch. No build step required — pure static HTML/CSS.

---

## 📸 Pages Overview

| Page | Route | Description |
|---|---|---|
| 🏠 Landing | `/index.html` | Hero landing page with scroll animation |
| 📝 Register | `/Register/register.html` | New user registration form |
| 🔐 Login | `/login/login.html` | User login page |
| 🩺 Health Form | `/form/form.html` | Fill in blood type, allergies, medications |
| 📊 Dashboard | `/dashboard/dashboard.html` | View & manage your emergency health card |

---

## ✨ Features

- **Instant Card Generation** — Fill a form, get a print-ready emergency health card
- **Critical Info Storage** — Blood type, allergies, conditions, medications, emergency contact
- **Scroll Animation** — Professional 3D card reveal animation on the landing page (CSS + vanilla JS, inspired by Framer Motion's `ContainerScroll`)
- **Responsive Design** — Works on all screen sizes, desktop to mobile
- **Print & Export Ready** — Card layout designed for real-world physical printing
- **Java Servlet Ready** — Every form and page is structured to wire up to a backend with zero HTML changes
- **Dark Medical Theme** — Professional UI using `DM Serif Display` + `Space Mono` typography

---

## 🗂️ Project Structure

```
EmergencyHealthCardGenerator/
│
├── index.html                  ← Landing page (scroll animation hero)
├── index.css                   ← Landing page styles
│
├── Register/
│   ├── register.html           ← Registration form
│   └── register.css            ← Registration styles
│
├── login/
│   ├── login.html              ← Login page
│   └── login.css               ← Login styles
│
├── form/
│   ├── form.html               ← Health data entry form
│   └── form.css                ← Form styles
│
├── dashboard/
│   ├── dashboard.html          ← User dashboard with health card preview
│   └── dashboard.css           ← Dashboard styles
│
├── db.properties.example       ← ✅ Commit this (template only, no real credentials)
├── db.properties               ← ❌ Never commit (add to .gitignore)
└── .gitignore
```

---

## 🚀 Getting Started

### Run Locally

No build tools needed. Just clone and open:

```bash
git clone https://github.com/gagang135/EmergencyHealthCardGenerator.git
cd EmergencyHealthCardGenerator

# Open directly in browser
open index.html
# or
start index.html   # Windows
```

Or serve with any static file server:

```bash
# Using Python
python -m http.server 3000

# Using Node.js (npx)
npx serve .
```

Then visit `http://localhost:3000`

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (Custom Properties, Grid, Flexbox, Animations) |
| Interactivity | Vanilla JavaScript (minimal) |
| Fonts | Google Fonts — DM Serif Display, DM Sans, Space Mono |
| Deployment | Netlify (static hosting) |
| Backend (planned) | Java Servlets + JDBC + MySQL + Apache Tomcat |

---

## 🔒 Security & Secrets

> ⚠️ **Never commit real credentials to a public repository.**

All sensitive configuration must stay off GitHub. Here's the pattern to follow:

**Add to `.gitignore`:**
```
# Secrets — never push these
db.properties
config.properties
*.env
WEB-INF/classes/config.properties
```

**Commit only the template** (`db.properties.example`):
```properties
# db.properties.example  ← safe to commit, contains NO real values
db.url=jdbc:mysql://localhost:3306/YOUR_DB_NAME
db.user=YOUR_DB_USERNAME
db.password=YOUR_DB_PASSWORD
```

**Keep the real file only on your local machine** (`db.properties`):
```properties
# db.properties  ← NEVER commit this file
db.url=jdbc:mysql://localhost:3306/medicard
db.user=root
db.password=yourActualPassword
```

This is standard practice on every real-world Java web project.

---

## 🏗️ Architecture

### Current — Static Frontend (Phase 1)

```
Browser
   │
   ▼
┌─────────────────────────────────────────────┐
│              Netlify CDN                    │
│                                             │
│  index.html  ──── index.css                 │
│  register.html ── register.css              │
│  login.html  ──── login.css                 │
│  form.html   ──── form.css                  │
│  dashboard.html ─ dashboard.css             │
└─────────────────────────────────────────────┘
```

No server. No database. Pure static files served from Netlify.

---

### Planned — Full Stack (Phase 2+)

```
┌──────────────────────────────────────────────────────────┐
│                        BROWSER                           │
│                                                          │
│  register.html  login.html  form.html  dashboard.html    │
│        │              │          │            │          │
└────────┼──────────────┼──────────┼────────────┼──────────┘
         │  HTTP POST   │ HTTP POST│ HTTP POST  │ HTTP GET
         ▼              ▼          ▼            ▼
┌──────────────────────────────────────────────────────────┐
│                  Apache Tomcat Server                    │
│                                                          │
│  ┌──────────────────┐   ┌────────────────────────────┐  │
│  │   web.xml         │   │        Servlets            │  │
│  │  URL Mappings     │──▶│                            │  │
│  │                   │   │  RegisterServlet.java       │  │
│  │  /register   ──▶ RS│  │  LoginServlet.java          │  │
│  │  /login      ──▶ LS│  │  FormServlet.java           │  │
│  │  /health-form ──▶ FS│ │  DashboardServlet.java      │  │
│  │  /dashboard  ──▶ DS│  │  LogoutServlet.java         │  │
│  └──────────────────┘   │  DownloadCardServlet.java   │  │
│                          └──────────────┬──────────────┘  │
└─────────────────────────────────────────┼────────────────┘
                                          │ JDBC
                                          ▼
┌──────────────────────────────────────────────────────────┐
│                     MySQL Database                       │
│                                                          │
│  ┌─────────────────────┐    ┌────────────────────────┐  │
│  │      users           │    │     health_cards        │  │
│  │─────────────────────│    │────────────────────────│  │
│  │ id (PK)             │◀───│ user_id (FK)            │  │
│  │ name                │    │ blood_type              │  │
│  │ email (UNIQUE)      │    │ conditions              │  │
│  │ password (hashed)   │    │ allergies               │  │
│  │ created_at          │    │ medications             │  │
│  └─────────────────────┘    │ emergency_contact       │  │
│                              │ emergency_phone         │  │
│                              └────────────────────────┘  │
└──────────────────────────────────────────────────────────┘
```

---

### Request Flow — Login Example

```
User fills login.html
        │
        │  POST /login  (email + password)
        ▼
  LoginServlet.java
        │
        ├── 1. Read email + password from request
        ├── 2. Query DB: SELECT * FROM users WHERE email = ?
        ├── 3. Verify BCrypt password hash
        ├── 4. Create HttpSession → session.setAttribute("user", userObj)
        │
        ├── ✅ Success → redirect to /dashboard
        └── ❌ Failure → redirect to login.html?error=1
```

---

### Data Flow — Health Card Generation

```
form.html  ──POST──▶  FormServlet
                           │
                    Check HttpSession
                           │
               ┌───────────┴───────────┐
          Not logged in           Logged in
               │                       │
        redirect to             INSERT / UPDATE
         login.html             health_cards table
                                       │
                               redirect to dashboard
                                       │
                           DashboardServlet fetches
                           card data from DB and
                           forwards to dashboard.html (JSP)
                                       │
                               User sees their card ✅
```

---

## 🗺️ Roadmap — Java Servlet Backend

The frontend is complete. The next phase is wiring up a Java backend:

```
Phase 1  ✅  Static HTML/CSS frontend
Phase 2  ⬜  Java Servlet project setup (Eclipse / IntelliJ + Tomcat)
Phase 3  ⬜  MySQL database schema (users + health_cards tables)
Phase 4  ⬜  RegisterServlet.java  — INSERT user into DB
Phase 5  ⬜  LoginServlet.java     — SELECT + HttpSession management
Phase 6  ⬜  FormServlet.java      — INSERT/UPDATE health card data
Phase 7  ⬜  DashboardServlet.java — GET data + forward to JSP
Phase 8  ⬜  PDF generation        — iText / OpenPDF download
Phase 9  ⬜  Convert pages to JSP  — Inject real user data dynamically
```

### Planned Database Schema

```sql
CREATE TABLE users (
  id       INT AUTO_INCREMENT PRIMARY KEY,
  name     VARCHAR(100) NOT NULL,
  email    VARCHAR(100) UNIQUE NOT NULL,
  password VARCHAR(255) NOT NULL,        -- BCrypt hashed
  created  TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE health_cards (
  id                INT AUTO_INCREMENT PRIMARY KEY,
  user_id           INT NOT NULL,
  blood_type        VARCHAR(5),
  conditions        TEXT,
  allergies         TEXT,
  medications       TEXT,
  emergency_contact VARCHAR(100),
  emergency_phone   VARCHAR(20),
  FOREIGN KEY (user_id) REFERENCES users(id)
);
```

### Servlet URL Mapping (planned `web.xml`)

```xml
<servlet-mapping>
  <servlet-name>RegisterServlet</servlet-name>
  <url-pattern>/register</url-pattern>
</servlet-mapping>

<servlet-mapping>
  <servlet-name>LoginServlet</servlet-name>
  <url-pattern>/login</url-pattern>
</servlet-mapping>

<servlet-mapping>
  <servlet-name>FormServlet</servlet-name>
  <url-pattern>/health-form</url-pattern>
</servlet-mapping>

<servlet-mapping>
  <servlet-name>DashboardServlet</servlet-name>
  <url-pattern>/dashboard</url-pattern>
</servlet-mapping>
```

---

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| `--red` | `#E63946` | Primary accent, emergency cross |
| `--bg` | `#0C0C0E` | Dashboard background |
| `--cream` | `#F8F4EF` | Landing page background |
| `--surface` | `#141416` | Card backgrounds |
| `--green` | `#22C55E` | Active / success states |
| Display font | `DM Serif Display` | Headings, card names |
| Body font | `DM Sans` | UI text |
| Mono font | `Space Mono` | Labels, IDs, code |

---

## 📱 Responsive Breakpoints

| Breakpoint | Behaviour |
|---|---|
| `> 1100px` | Full sidebar + 2-col dashboard grid |
| `768px – 1100px` | Sidebar visible, stacked grid |
| `< 768px` | Hamburger menu, single column |
| `< 480px` | Compact stats, simplified card |

---

## 🤝 Contributing

This is a learning project. Contributions are welcome!

```bash
# 1. Fork the repository
# 2. Create your feature branch
git checkout -b feature/add-servlet-backend

# 3. Commit your changes
git commit -m "feat: add RegisterServlet with JDBC"

# 4. Push and open a Pull Request
git push origin feature/add-servlet-backend
```

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

**Built with ❤️ by the MediCard team**

*Frontend complete · Java Servlet backend coming soon*

| | Contributor | GitHub |
|---|---|---|
| 👨‍💻 | gagang135 | [![GitHub](https://img.shields.io/badge/gagang135-181717?style=flat-square&logo=github)](https://github.com/gagang135) |
| 👨‍💻 | prashanthcoder | [![GitHub](https://img.shields.io/badge/prashanthcoder-181717?style=flat-square&logo=github)](https://github.com/prashanthcoder) |

[![Live](https://img.shields.io/badge/Live-netlify-00C7B7?style=flat-square&logo=netlify)](https://luminous-manatee-5923e1.netlify.app/)

</div>