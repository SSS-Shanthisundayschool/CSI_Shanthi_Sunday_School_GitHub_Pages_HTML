# CSI Shanthi Church Sunday School Attendance — GitHub Pages edition

This is a static **HTML/CSS/JavaScript** attendance system for CSI Shanthi Church Sunday School, Wilson Garden.

## What is included
- `index.html` — the website entry point
- `styles.css` — aesthetic responsive styling
- `app.js` — dashboard, attendance, reports, people, accounts and backup logic
- `config.js` — add your Supabase project URL + publishable/anon key here
- `seed-data.js` — imported 104-person roster for local preview
- `supabase-setup.sql` — creates the secure shared database + RLS policies
- `import-current-roster.sql` — imports the existing 104 people and 21 June 2026 attendance

## 1) Preview immediately
Open `index.html` in a browser. Because `config.js` is blank, the page offers **Open admin preview**. Preview data is stored only in that browser via localStorage.

## 2) Create the real shared database
1. Create a Supabase project.
2. Open **SQL Editor** and run `supabase-setup.sql`.
3. Run `import-current-roster.sql`.
4. In Supabase project settings, copy the **Project URL** and **publishable/anon key**.
5. Put them into `config.js`.
6. Open the site, create your first account from **Teacher registration**.
7. In Supabase SQL Editor run the admin promotion line shown at the bottom of `supabase-setup.sql`, replacing `YOUR_ADMIN_EMAIL` with your own email.
8. Sign out and back in. You now have the full admin dashboard.

### Teacher access
Teachers use **Create an account request** on the sign-in page. New accounts default to `teacher` and have no class access. The admin opens **Accounts** and assigns one or more classes. Database RLS enforces those restrictions.

## 3) Put the HTML site on GitHub
Create a GitHub repository, then put all files from this folder in the repository root.

Using Terminal from this folder:
```bash
git init
git add .
git commit -m "CSI Sunday School attendance site"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## 4) Enable GitHub Pages
In the repository:
1. **Settings** → **Pages**
2. Under **Build and deployment**, choose **Deploy from a branch**
3. Branch: `main`
4. Folder: `/ (root)`
5. Save

Your URL normally becomes `https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY/`.

## Security
- Do **not** put a Supabase `service_role`/secret key in `config.js` or GitHub.
- The browser should contain only the project URL and publishable/anon key.
- `supabase-setup.sql` enables Row Level Security so database access is restricted by the signed-in account.

## Features
Admin: dashboard, all classes, roster add/edit/archive, teacher access assignment, reports/CSV/JSON, full backup, student profiles.
Teacher: only assigned classes, Sunday attendance, class reports, student profiles.
Analytics: academic-year percentage, latest Sunday, class comparison, monthly trend, current/best streaks and chronic-absence alerts (default 3 consecutive recorded absences).

## Academic year
Default is **June to May**. Change `academicYearStartMonth` in `config.js` if required.

## Backups
The **Backup** screen downloads a complete JSON export and keeps a last-known browser snapshot after sync/save. For disaster recovery, also enable/use your Supabase/Postgres backup options and periodically store downloaded copies safely.
