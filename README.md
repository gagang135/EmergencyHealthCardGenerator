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
| 📝 Register | `/Register/index.html` | New user registration form |
| 🔐 Login | `/login/index.html` | User login page |
| 🩺 Health Form | `/form/index.html` | Fill in blood type, allergies, medications |
| 📊 Dashboard | `/dashboard/index.html` | View & manage your emergency health card |

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
│
├── Register/
│   └── index.html              ← Registration form
│
├── login/
│   └── index.html              ← Login page
│
├── form/
│   └── index.html              ← Health data entry form
│
└── dashboard/
    └── index.html              ← User dashboard with health card preview
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

*Frontend complete · Java Servlet backend coming soon*

| | Contributor | GitHub |
|---|---|---|
| 👨‍💻 | gagang135 | [![GitHub](https://img.shields.io/badge/gagang135-181717?style=flat-square&logo=github)](https://github.com/gagang135) |
| 👨‍💻 | prashanthcoder | [![GitHub](https://img.shields.io/badge/prashanthcoder-181717?style=flat-square&logo=github)](https://github.com/prashanthcoder) |

[![Live](https://img.shields.io/badge/Live-netlify-00C7B7?style=flat-square&logo=netlify)](https://luminous-manatee-5923e1.netlify.app/)

</div>