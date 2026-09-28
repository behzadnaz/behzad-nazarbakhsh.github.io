# Behzad Nazarbakhsh — Professional Portfolio

Personal professional portfolio and career hub for **Behzad Nazarbakhsh**.

**Software Craftsmanship · Product Coaching · Agile · IT Management**

The site brings together professional experience, selected work, knowledge articles, services, CV, and contact options.

## 🌐 Portfolio

**Live site:**  
https://behzadnaz.github.io/behzad-nazarbakhsh.github.io/

**GitHub repository:**  
https://github.com/behzadnaz/behzad-nazarbakhsh.github.io

---

## 📊 Analytics & Shared Counters

The portfolio uses two complementary analytics mechanisms:

### 1. Cloudflare — Shared Portfolio Counters

Cloudflare Workers + Cloudflare KV provide shared counters that work across browsers and devices.

Tracked events include:

- **Page visitors**
- **CV views**
- **Article views**

Architecture:

```text
Visitor
   ↓
GitHub Pages
   ↓
Cloudflare Worker
   ↓
Cloudflare KV
   ↓
Shared Counter
   ↓
Private Analytics Dashboard
```

**Counter API:**

https://behzad-portfolio-counters.bmbvm5.workers.dev/counter

**Page visitor counter:**

https://behzad-portfolio-counters.bmbvm5.workers.dev/counter?key=page_visits

**Private analytics dashboard:**

https://behzad-portfolio-counters.bmbvm5.workers.dev/dashboard

The dashboard is protected and should not be publicly exposed with credentials.

> **Security:** Dashboard credentials and passwords are stored in Cloudflare Worker secrets. They are intentionally **not** stored in this repository or README.

The Cloudflare Worker uses the secret named `DASHBOARD_PASSWORD` for dashboard authentication. The secret value must remain private.

### 2. GoatCounter — Website Analytics

The portfolio also uses **GoatCounter** for privacy-friendly website analytics and event tracking.

GoatCounter complements the Cloudflare counters:

- **Cloudflare KV** → shared, application-level counters for visitors, CV views, and article views.
- **GoatCounter** → website analytics, page/event activity, and traffic analysis.

This separation keeps the portfolio's visible counters independent from broader website analytics.

---

## 🧩 Portfolio Structure

The website is organized around:

- **Home** — professional positioning and overview
- **Contribution** — selected work and professional contributions
- **Knowledge Base** — AI Engineering, Organizational Change, Product Management, Software Engineering, Agile Teams, and Lean
- **Services** — ways organizations and teams can engage
- **About** — experience, achievements, CV, and contact

### Selected Work

Current featured reports include:

- **IT Portfolio Management**
- **Organizational Change Management**

---

## 📈 Counter Flow

### Page visitor

When the portfolio is opened:

1. The page requests the current shared visitor count.
2. The page sends a `POST` event to the Cloudflare Worker.
3. The Worker increments the `page_visits` counter in Cloudflare KV.
4. The updated total is returned to the portfolio.
5. The same cumulative value is available from any browser or device.

### CV view

Clicking **View My CV** increments the shared `cv_views` counter.

### Article view

Opening an article card increments an article-specific counter such as:

```text
article_<article-slug>
```

This allows the private dashboard to show article-level performance.

---

## 🔐 Security Notes

- Never commit the Cloudflare dashboard password to GitHub.
- Never place Worker secrets inside `index.html`.
- Keep `DASHBOARD_PASSWORD` configured as a Cloudflare Worker secret.
- The public counter endpoint exposes counter values only; dashboard access remains protected.
- If the dashboard password is ever exposed, rotate the Cloudflare Worker secret immediately.

---

## 🛠️ Technology

- HTML5
- CSS3
- JavaScript
- GitHub Pages
- Cloudflare Workers
- Cloudflare KV
- GoatCounter
- Responsive design for desktop and mobile

---

## 📁 Repository Highlights

```text
/
├── index.html
├── style.css
├── IT-Portfolio-Management.html
├── Organization-Change-Management.html
├── report-bundles/
├── favicon.svg
└── README.md
```

---

## 👤 Contact

**Behzad Nazarbakhsh**

- LinkedIn: https://www.linkedin.com/in/behzad-nazarbakhsh/
- GitHub: https://github.com/behzadnaz
- Portfolio: https://behzadnaz.github.io/behzad-nazarbakhsh.github.io/

---

## License

Personal portfolio and professional content of Behzad Nazarbakhsh.
