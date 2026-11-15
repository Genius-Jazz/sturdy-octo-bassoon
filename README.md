# Shop Tracker

A single-page app for a small shop: sales (walk-in and online), pickup-point parcel revenue, partner capital and ownership %, expenses, and a profit dashboard.

It is one static file (`index.html`) with no build step and no dependencies.

## Run locally
Open `index.html` in a browser, or run `npx serve .` in this folder.

## Deploy: GitHub + Vercel
1. Create a new repository on GitHub (e.g. `shop-tracker`).
2. In this folder:
   ```
   git init
   git add .
   git commit -m "Shop tracker"
   git branch -M main
   git remote add origin https://github.com/<your-username>/shop-tracker.git
   git push -u origin main
   ```
3. Go to vercel.com, click **Add New > Project**, import the repository.
4. Framework preset: **Other**. Leave build command and output directory empty. Click **Deploy**.

Every push to `main` redeploys automatically.

## Where data is saved
Outside Claude, the app saves to the browser's `localStorage`. That means data stays on the device and browser where it was entered, and it is NOT shared between partners. Clearing browser data erases it.

To share data between two partners, connect a backend (for example Supabase or Firebase). The data layer is the small `store` object and the `connect()` function near the bottom of `index.html`; those are the only places to change.
