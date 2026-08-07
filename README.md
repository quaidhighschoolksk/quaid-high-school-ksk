# Quaid High School KSK — Website

This is a **single-file website**: everything (HTML, CSS, and JavaScript) lives inside `index.html`. There are no other files the site depends on — all backend data (students, results, notices, etc.) is stored in **Firebase** (project: `quaid-high-school-ksk`), not in this repo, so moving the file to a new host does not affect your saved data.

## Move from Netlify to GitHub Pages

### 1. Create the GitHub repository
1. Go to [github.com/new](https://github.com/new)
2. Repository name: e.g. `quaid-high-school-ksk` (or reuse your existing `Sial-Pigeon-Club`-style repo if you prefer one repo per project — but a separate repo for the school is cleaner)
3. Set it to **Public** (GitHub Pages free tier requires a public repo, unless you have GitHub Pro/Team)
4. Click **Create repository**

### 2. Upload the file
**Easiest way (no coding tools needed):**
1. Open your new repository on GitHub
2. Click **Add file → Upload files**
3. Drag in `index.html` (rename it to exactly `index.html` if it isn't already)
4. Click **Commit changes**

### 3. Turn on GitHub Pages
1. In the repository, go to **Settings → Pages**
2. Under **Branch**, choose `main` and folder `/ (root)`
3. Click **Save**
4. Wait 1–2 minutes — GitHub will give you a live link like:
   `https://<your-github-username>.github.io/<repo-name>/`

### 4. Point your domain (optional)
If you have a custom domain (or want a free one — see below), add it under **Settings → Pages → Custom domain**, and add a `CNAME` record at your domain registrar pointing to `<your-github-username>.github.io`.

### 5. Turn off / delete the Netlify site
Once the GitHub Pages link is working and you've tested it, you can delete the old Netlify site so people aren't confused by two live copies.

## Free custom domain (to remove "github.io" from the URL)
A few options that give a free subdomain you can point at GitHub Pages:
- **is-a.dev** — free `yourschool.is-a.dev` style subdomains for personal/small projects (GitHub-based signup)
- **js.org** — free for JavaScript-related projects
- A fully custom domain (`quaidhighschoolksk.com`) still costs money yearly from any registrar (Namecheap, GoDaddy, etc.) — GitHub Pages itself is free, only the domain name has a cost if you want your own `.com`.

## Notes for admin login / Firebase
Nothing needs to change in Firebase when you switch hosts — the config inside `index.html` already points to your Firebase project, and Firebase Authentication/Firestore/Storage don't care which domain serves the HTML file. Just make sure, if you use Google Sign-In for the admin panel, that your new GitHub Pages domain is added under:
**Firebase Console → Authentication → Settings → Authorized domains**
(add `<your-github-username>.github.io`).
