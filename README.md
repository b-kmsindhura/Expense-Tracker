# Personal Expense Tracker (PyScript & HTML)

A complete, modern **Personal Expense Tracker** web application featuring a premium fintech login page and client-side Python execution via **PyScript**.

---

## 🚀 Features

- **Premium Fintech Login Page (`login.html`)**:
  - Dark navy/obsidian glassmorphic interface with ambient radial glows (violet, indigo, cyan) and subtle floating financial elements (₹, %, 📈, 🪙).
  - Welcome branding with tagline *"Track smarter. Spend better."*
  - Interactive desktop spending analytics showcase with animated growth graph, savings indicator (`+32.4%`), and expense badges.
  - Complete form controls: Email validation, password visibility toggle, "Remember me" option, and loading state spinner.
  - Social login option: *"Continue with Google"*.
  - Functional *"Forgot Password?"* and *"Sign Up"* modal dialogs.
  - Ready-to-connect authentication hooks for Firebase, Supabase, Auth0, or custom REST APIs.
- **Client-Side Python Engine (`index.html`)**:
  - Entire frontend business logic runs client-side in Python with **PyScript** (no backend server required).
  - Indian Rupees (₹) formatting across all metrics, forms, and tables.
  - Minimalist Light & Dark mode toggle (`☀️` / `🌙`) with zero screen flicker and persistent storage.
  - User-settable Total Income / Monthly Budget directly on the card with one-click auto-calculate toggle.
  - Category filtering, real-time balance calculations, and transaction history management.
  - Seamless navigation between Login and Dashboard with user session state.

---

## 📁 Project Structure

```text
Expense Tracker/
├── index.html     # Main finance dashboard with PyScript runtime
├── login.html     # Premium fintech login & authentication page
└── README.md      # Setup, architecture, and deployment instructions
```

---

## 💻 How to Run Locally

### Option 1: VS Code Live Server (Recommended)
1. Install the **Live Server** extension in VS Code (`ritwickdey.LiveServer`).
2. Right-click `login.html` or `index.html`.
3. Click **"Open with Live Server"**.
4. The application will open in your default browser at `http://127.0.0.1:5500/login.html`.

### Option 2: Python Built-in HTTP Server
From the project folder in terminal or PowerShell:
```powershell
python -m http.server 8000
```
Then visit `http://localhost:8000/login.html` or `http://localhost:8000/index.html` in your browser.

---

## 🔐 Authentication Integration Notes

The login page (`login.html`) provides a complete, modern frontend authentication experience with form validation, loading states, and error messaging.

To attach a real backend provider (e.g., Firebase, Supabase, or custom JWT API):
1. Open [`login.html`](login.html).
2. Locate the `loginForm.addEventListener("submit", ...)` section.
3. Replace the simulated `setTimeout` transition with your API call:
```javascript
// Example Firebase / Supabase / REST API call:
const response = await fetch('/api/v1/auth/login', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email, password })
});
const data = await response.json();
if (response.ok) {
  localStorage.setItem("expense_tracker_user", data.user.email);
  window.location.href = "index.html";
} else {
  alert(data.message);
}
```

---

## 🌐 How to Deploy to GitHub Pages

1. Push your repository to GitHub:
```powershell
git init
git add index.html login.html README.md
git commit -m "Add premium fintech login page and user navigation"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

2. Enable GitHub Pages:
- Go to your repository on **GitHub.com**.
- Navigate to **Settings** -> **Pages**.
- Under **Source**, select **Deploy from a branch** -> branch **`main`** / **`/(root)`**, and click **Save**.
- In 1–2 minutes, your live site will be ready!
