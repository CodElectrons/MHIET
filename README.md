# منظومة إدارة التدريب والبحث العلمي — معهد المدينة العالي للهندسة والتكنولوجيا

## Files
- `index.html` — the whole application
- `logo.png` — the institute logo (**you must add this file**, see below)
- `data.json` — optional, generated from the admin dashboard to publish data to all visitors

## Deploy on GitHub Pages
1. Create a repository and upload `index.html`, `logo.png` (and `data.json` later).
2. Repository **Settings → Pages → Build and deployment → Deploy from a branch → `main` / root → Save**.
3. Open `https://<username>.github.io/<repo>/`.

## Logo
Save the logo image you sent as `logo.png` next to `index.html`. It is hard-wired in the code
(header, letter header, watermark, seal) and there is no upload button, so it cannot be replaced from the site.

## How data is saved
- Everything is saved in the browser's `localStorage` on the device where it was entered.
- Admin dashboard (default password `1234`, change it after first login) → **تصدير Excel** downloads an `.xlsx` with 4 sheets.
- To show your data to all students: admin dashboard → **ملف النشر data.json**, then upload that file to the repo (replace the old one).
  Visitors load it automatically. National IDs are published as one-way hashes, and student requests are never published.
- **نسخة احتياطية / استرجاع** saves and restores the full data as JSON.

## Limits of a static site
GitHub Pages has no server, so student requests stay on the student's own device and the admin password is only a client-side gate.
For a shared live system (requests reaching the admin, real login), a backend such as Firebase or Supabase is needed.
