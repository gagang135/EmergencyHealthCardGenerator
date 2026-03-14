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

| Page | Route | Status | Description |
|---|---|---|---|
| 🏠 Landing | `/index.html` | ✅ Complete | Hero + 3D scroll animation, features, how-it-works, CTA |
| 📝 Register | `/Register/register.html` | ✅ Complete | 4-step: identity, Aadhaar, phone OTP verify, health data |
| 🔐 Login | `/login/login.html` | ✅ Complete | Phone number + SMS OTP, 6-box UI, timer, resend |
| 📊 Dashboard | `/dashboard/dashboard.html` | ✅ Complete | Sidebar, health card, stats, QR code, activity feed |
| 🩺 Health Form | `/form/form.html` | ✅ Complete | Edit/update health card — live preview, pre-filled, unsaved changes warning |

> **`form/form.html`** is the only remaining frontend page. It is the **edit** page — reached from the dashboard's "Edit Card" button — and lets logged-in users update their health data without re-registering.

---

## ✨ Features

- **4-Step Registration** — Identity → Phone OTP → Health data → Redirect to login
- **Phone OTP Login** — No passwords. Verify identity via SMS OTP every session
- **Aadhaar Verification** — Split 4-4-4 input with auto-advance, hashed before DB storage
- **Blood Type Selector** — Clickable pill buttons (A+, B+, O−, etc.) — no dropdowns
- **Professional Dashboard** — Sidebar nav, live health card, stats, QR code, activity feed
- **3D Scroll Animation** — Landing page card reveal (vanilla JS, mirrors Framer Motion `ContainerScroll`)
- **Responsive Design** — Mobile hamburger menu, adaptive grid, all screen sizes
- **Java Servlet Ready** — Every form POSTs to a servlet endpoint with zero HTML changes needed
- **SMS OTP Architecture** — OTP generated server-side, delivered via MSG91 — API key never in HTML

---

## 🗂️ Project Structure

```
EmergencyHealthCardGenerator/
│
├── index.html                  ← ✅ Landing page (scroll animation, features, CTA)
│
├── Register/
│   └── register.html           ← ✅ 4-step registration (identity + OTP + health data)
│
├── login/
│   └── login.html              ← ✅ Phone OTP login (2-step verified flow)
│
├── form/
│   └── form.html               ← ⬜ Health data edit form (pending — last page)
│
├── dashboard/
│   └── dashboard.html          ← ✅ User dashboard with health card + sidebar
│
├── db.properties.example       ← ✅ Commit this (safe template, no real values)
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
| Markup | HTML5 (semantic, no frameworks) |
| Styling | CSS3 (Custom Properties, Grid, Flexbox, Keyframe Animations) |
| Interactivity | Vanilla JavaScript — OTP logic, step navigation, countdown timer, form validation |
| Fonts | Google Fonts — DM Serif Display, DM Sans, Space Mono |
| Deployment | Netlify (static hosting, auto-deploy from `main`) |
| Backend (planned) | Java Servlets + JDBC + MySQL + Apache Tomcat |
| SMS OTP (planned) | MSG91 — called server-side from `SendOtpServlet`, key never in HTML |

---

## 🔒 Security & Secrets

> ⚠️ **Never commit real credentials to a public repository.**

All sensitive configuration must stay off GitHub. Follow this pattern:

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
# db.properties.example  ← safe to commit, NO real values
db.url=jdbc:mysql://localhost:3306/YOUR_DB_NAME
db.user=YOUR_DB_USERNAME
db.password=YOUR_DB_PASSWORD
msg91.auth_key=YOUR_MSG91_AUTH_KEY
msg91.template_id=YOUR_MSG91_TEMPLATE_ID
```

**Keep the real file only on your local machine** (`db.properties`):
```properties
# db.properties  ← NEVER commit this
db.url=jdbc:mysql://localhost:3306/medicard
db.user=root
db.password=yourActualPassword
msg91.auth_key=your_real_key
msg91.template_id=your_real_template_id
```

> SMS API keys (MSG91 / Twilio) are also secrets. **Never put them in HTML or JS** — anyone can view source and steal them. They live only in `db.properties` and are read by the servlet at runtime.

---

## 🏗️ Architecture

### Current — Static Frontend (Phase 1)

```
Browser
   │
   ▼
┌──────────────────────────────────────────────┐
│               Netlify CDN                    │
│                                              │
│  index.html           ✅ landing page        │
│  Register/register.html ✅ 4-step signup     │
│  login/login.html       ✅ phone OTP login   │
│  dashboard/dashboard.html ✅ card view       │
│  form/form.html         ⬜ edit (pending)    │
└──────────────────────────────────────────────┘
```

No server. No database. All OTPs are demo-mode (`console.log` only).

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
│  │                   │   │  SendOtpServlet.java        │  │
│  │  /send-otp   ──▶ SO│  │  VerifyOtpServlet.java      │  │
│  │  /verify-otp ──▶ VO│  │  RegisterServlet.java       │  │
│  │  /register   ──▶ RS│  │  LoginServlet.java          │  │
│  │  /login      ──▶ LS│  │  FormServlet.java           │  │
│  │  /health-form ──▶ FS│ │  DashboardServlet.java      │  │
│  │  /dashboard  ──▶ DS│  │  LogoutServlet.java         │  │
│  │  /logout     ──▶ LO│  │  DownloadCardServlet.java   │  │
│  └──────────────────┘   └──────────────┬───────────────┘  │
│                                        │ MSG91 SMS API     │
└────────────────────────────────────────┼──────────────────┘
                                         │ JDBC
                                         ▼
┌──────────────────────────────────────────────────────────┐
│                     MySQL Database                       │
│                                                          │
│  ┌──────────────────────┐    ┌────────────────────────┐  │
│  │        users          │    │     health_cards        │  │
│  │──────────────────────│    │────────────────────────│  │
│  │ id (PK)              │◀───│ user_id (FK)            │  │
│  │ name                 │    │ blood_type              │  │
│  │ phone (UNIQUE) ←key  │    │ conditions              │  │
│  │ aadhaar_hash         │    │ allergies               │  │
│  │ dob                  │    │ medications             │  │
│  │ gender               │    │ emergency_contact       │  │
│  │ created_at           │    │ emergency_phone         │  │
│  └──────────────────────┘    │ updated_at              │  │
│                               └────────────────────────┘  │
└──────────────────────────────────────────────────────────┘
```

> No `password` or `email` column — authentication is **phone + SMS OTP only**. Aadhaar is stored as a SHA-256 hash, never plain text.

---

### Request Flow — Registration

```
register.html  (4 steps)
        │
        ├── Step 1: Name, Phone, Aadhaar, DOB, Gender → validate
        │
        ├── Step 2: POST /send-otp { phone }
        │               ↓
        │          SendOtpServlet → OTP stored in session
        │               ↓ MSG91 API → SMS to user's phone
        │
        │           Enter OTP → POST /verify-otp { otp }
        │               ↓
        │          VerifyOtpServlet → checks session OTP + expiry
        │               ↓ ✅ phone verified
        │
        └── Step 3: POST /register { all fields }
                        ↓
                   RegisterServlet
                   INSERT INTO users (name, phone, aadhaar_hash, dob, gender)
                   INSERT INTO health_cards (user_id, blood_type, allergies...)
                        ↓
                   redirect → login.html?registered=1
```

---

### Request Flow — Login (Phone OTP, No Password)

```
login.html
        │
        │  Enter phone number
        │  POST /send-otp { phone }
        │       ↓
        │  SendOtpServlet
        │  ├── phone NOT in users table → error "No account. Please register."
        │  └── phone found → generate OTP → session → MSG91 SMS
        │
        │  Enter 6-digit OTP
        │  POST /verify-otp { otp }
        │       ↓
        │  VerifyOtpServlet
        │  ├── OTP correct + not expired
        │  ├── HttpSession created → session.setAttribute("user", userObj)
        │  │
        │  ✅ → redirect to /dashboard
        └── ❌ → inline error, clear boxes, retry
```

---

### Data Flow — Health Card on Dashboard

```
/dashboard  ──GET──▶  DashboardServlet
                            │
                     Check HttpSession
                            │
               ┌────────────┴────────────┐
          No session                Session valid
               │                         │
       redirect to               SELECT health_cards
        login.html               WHERE user_id = session.id
                                          │
                                 Forward to dashboard.jsp
                                 with card data as attributes
                                          │
                                User sees their real card ✅
                                          │
                         "Download PDF" → DownloadCardServlet → PDF
                         "Edit Card"    → form.html → FormServlet → UPDATE
                         "Print"        → window.print()
```

---

## ✅ Frontend Completion Checklist

```
✅  index.html            — Landing page, 3D scroll animation, nav, footer
✅  Register/register.html — 4-step signup: identity + Aadhaar + phone OTP + health
✅  login/login.html       — Phone + 6-box OTP, timer, resend, masked display
✅  dashboard/dashboard.html — Sidebar, health card, stats, QR, activity, profile
✅  form/form.html         — Edit health card (live preview, pre-fill, unsaved warning)
```

### What `form/form.html` needs

A single-page form pre-filled with existing health data (blood type, allergies, conditions, medications, emergency contact) and an **"Update Card"** submit button. No OTP — user is already in a valid session. Simpler than register step 3, same design system.

---

## 🗺️ Roadmap

```
── FRONTEND ────────────────────────────────────────────────
Phase 1  ✅  index.html            Landing page
Phase 1  ✅  Register/register.html 4-step registration UI
Phase 1  ✅  login/login.html       Phone OTP login UI
Phase 1  ✅  dashboard/dashboard.html Health card dashboard
Phase 1  ⬜  form/form.html         Health data edit page

── BACKEND ─────────────────────────────────────────────────
Phase 2  ⬜  Java project setup     Eclipse/IntelliJ + Tomcat
Phase 2  ⬜  MySQL schema           users + health_cards tables
Phase 3  ⬜  SendOtpServlet         Generate OTP + MSG91 SMS API
Phase 3  ⬜  VerifyOtpServlet       Validate OTP from session
Phase 4  ⬜  RegisterServlet        INSERT users + health_cards
Phase 5  ⬜  LoginServlet           Check phone exists + HttpSession
Phase 6  ⬜  FormServlet            UPDATE health_cards for session user
Phase 7  ⬜  DashboardServlet       SELECT card + forward to JSP
Phase 8  ⬜  LogoutServlet          session.invalidate() + redirect
Phase 9  ⬜  DownloadCardServlet    OpenPDF generation + stream to browser
Phase 10 ⬜  Convert to JSP         Inject real DB data into pages
```

---

### Planned Database Schema

```sql
-- No password column — phone + OTP is the only auth method
CREATE TABLE users (
  id            INT AUTO_INCREMENT PRIMARY KEY,
  name          VARCHAR(100) NOT NULL,
  phone         VARCHAR(15)  UNIQUE NOT NULL,  -- login identifier
  aadhaar_hash  VARCHAR(255) NOT NULL,          -- SHA-256 hash, never plain text
  dob           DATE,
  gender        ENUM('Male','Female','Other','Prefer not to say'),
  created_at    TIMESTAMP DEFAULT CURRENT_TIMESTAMP
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
  updated_at        TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  FOREIGN KEY (user_id) REFERENCES users(id)
);
```

---

### Servlet URL Mapping (`web.xml`)

```xml
<servlet-mapping>
  <servlet-name>SendOtpServlet</servlet-name>
  <url-pattern>/send-otp</url-pattern>
</servlet-mapping>

<servlet-mapping>
  <servlet-name>VerifyOtpServlet</servlet-name>
  <url-pattern>/verify-otp</url-pattern>
</servlet-mapping>

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

<servlet-mapping>
  <servlet-name>LogoutServlet</servlet-name>
  <url-pattern>/logout</url-pattern>
</servlet-mapping>

<servlet-mapping>
  <servlet-name>DownloadCardServlet</servlet-name>
  <url-pattern>/download-card</url-pattern>
</servlet-mapping>
```

---

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| `--red` | `#E63946` | Primary accent, cross icon, buttons, OTP active |
| `--red-deep` | `#B5202D` | Hover states on all red elements |
| `--cream` | `#F8F4EF` | Landing + auth pages background |
| `--ink` | `#0D0D0D` | Card headers (dark strip), body text |
| `--bg` | `#0C0C0E` | Dashboard dark background |
| `--surface` | `#141416` | Dashboard panel / card surfaces |
| `--pulse-green` | `#22C55E` | Success states, verified badge, progress done |
| Display font | `DM Serif Display` | Page titles, card names, hero headings |
| Body font | `DM Sans` | All UI text, labels, buttons, inputs |
| Mono font | `Space Mono` | OTP boxes, Aadhaar, IDs, code labels, badges |

---

## 📱 Responsive Breakpoints

| Breakpoint | Behaviour |
|---|---|
| `> 1100px` | Full sidebar + 2-col dashboard grid |
| `768px – 1100px` | Sidebar visible, stacked grid |
| `< 768px` | Hamburger menu, nav links hidden, single column |
| `< 480px` | Compact stats, OTP boxes narrower, simplified card |

---

## 🤝 Contributing

This is a learning project. Contributions are welcome!

```bash
# 1. Fork the repository
# 2. Create your feature branch
git checkout -b feature/add-servlet-backend

# 3. Commit your changes
git commit -m "feat: add SendOtpServlet with MSG91 integration"

# 4. Push and open a Pull Request
git push origin feature/add-servlet-backend
```

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

**Built with ❤️ by the MediCard team**

*Frontend complete ✅ · Java Servlet backend coming soon**

| | Contributor | GitHub |
|---|---|---|
| 👨‍💻 | prashanthcoder | [![GitHub](https://img.shields.io/badge/prashanthcoder-181717?style=flat-square&logo=github)](https://github.com/prashanthcoder) |
| 👨‍💻 | gagang135 | [![GitHub](https://img.shields.io/badge/gagang135-181717?style=flat-square&logo=github)](https://github.com/gagang135) |

[![Live](https://img.shields.io/badge/Live-netlify-00C7B7?style=flat-square&logo=netlify)](https://luminous-manatee-5923e1.netlify.app/)

</div>