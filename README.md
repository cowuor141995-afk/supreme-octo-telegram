
# MarkNet - Vite React E-commerce Starter

This project is a ready-to-deploy Vite + React + Tailwind starter for **MarkNet** with:
- Example product catalog (Accessories, Personal Care, Baby & Child, Catering).
- Admin panel (localStorage) protected by default credentials.
- PayPal client-side Smart Buttons.
- Stripe Checkout integration via a Vercel serverless function.

---

## What's included

- `src/MarkNetApp.jsx` — Main single-file app (products, cart, admin, PayPal + Stripe hooks).
- `api/create-stripe-session.js` — Vercel serverless function to create Stripe Checkout sessions.
- Tailwind CSS configured (`tailwind.config.cjs`, `postcss.config.cjs`).
- Example product images and data.

---

## Setup (local)

1. Install dependencies:

```bash
npm install
```

2. Create a `.env` file in the project root for local dev (Vite expects `VITE_` prefix for client keys):

```
VITE_PAYPAL_CLIENT_ID=your_paypal_client_id
VITE_STRIPE_PUBLISHABLE_KEY=pk_test_...
VITE_ADMIN_USERNAME=admin
VITE_ADMIN_PASSWORD=Godloves@1
VITE_BASE_URL=http://localhost:5173
```

3. Run dev server:

```bash
npm run dev
```

4. Visit `http://localhost:5173`.

---

## Deploy to Vercel

1. Push the project to GitHub.
2. In Vercel, import the repo.
3. Add Environment Variables in Vercel dashboard (Project Settings):
   - `PAYPAL_CLIENT_ID` = your PayPal client id
   - `STRIPE_PUBLISHABLE_KEY` = your Stripe publishable key (pk_...)
   - `STRIPE_SECRET_KEY` = your Stripe secret key (sk_...) **server-side only**
   - `ADMIN_USERNAME` = admin
   - `ADMIN_PASSWORD` = Godloves@1
   - `NEXT_PUBLIC_BASE_URL` = https://your-site-url.vercel.app

4. Deploy. The serverless function will be available at `/api/create-stripe-session`.

---

## Notes & Security

- **Do not** commit secret keys to source control.
- Stripe secret key must be set only in Vercel environment variables.
- Admin in this starter is simple (suitable for early testing). For production, use a real auth system and database.
- Orders/messages are stored in localStorage for demo — replace with a backend for production.

---

If you'd like, I can:
- Push this code to a GitHub repo for you.
- Deploy to Vercel and connect environment variables (you'll need to provide the keys).
- Add order persistence and a proper admin user system.

Contact: cowuor141995@gmail.com
