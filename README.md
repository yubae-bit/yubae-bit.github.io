# Yubo Zhou Rasmussen — personal site

Plain HTML and CSS single-page portfolio. No build step, no framework. Hosts on GitHub Pages for free.

---

## What's in the folder

```
index.html        – the page itself
style.css         – styling
README.md         – this file
figures/          – create this folder and drop your headshot in as figures/headshot.jpg
cv.pdf            – drop your CV PDF here at the repo root (matches the link in index.html)
```

---

## Before you push — two quick things

1. **Headshot.** Create a `figures/` folder and save your photo as `figures/headshot.jpg`. Square, ~400×400 px or larger. If the file isn't there, the page shows a dashed placeholder instead of breaking.
2. **CV.** Save your CV as `cv.pdf` at the repo root. If you'd rather call it something else, update the two `cv.pdf` links inside `index.html`.

Optional polish:
- Add a `favicon.ico` at the root and browsers will pick it up.
- Update the Publications section when your submitted paper is accepted.
- If you create a Google Scholar profile, add a link in the Contact section.

---

## Deploying to GitHub Pages

### 1. Create the repo

1. On GitHub, click **New repository**.
2. Name it **exactly** `YOURUSERNAME.github.io` (lowercase, using your actual GitHub handle). This gives you the clean URL `https://YOURUSERNAME.github.io`.
3. Set to **Public**.
4. Don't tick "Add a README" — you already have one.
5. Click **Create repository**.

If the `username.github.io` name is taken or you prefer a project-style URL, call the repo something else (e.g. `portfolio`). The site will then live at `https://YOURUSERNAME.github.io/portfolio/`.

### 2. Push the files

From a terminal, in the folder containing `index.html`:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/REPO-NAME.git
git push -u origin main
```

Replace `YOURUSERNAME` and `REPO-NAME` with your values.

First-time git setup (only once, ever):

```bash
git config --global user.name  "Yubo Zhou Rasmussen"
git config --global user.email "yubosej@gmail.com"
```

The easiest auth path is [GitHub CLI](https://cli.github.com/) — install it, run `gh auth login`, and credentials are handled automatically.

### 3. Turn on Pages

1. Repo → **Settings** → **Pages** (left sidebar).
2. **Source**: "Deploy from a branch".
3. **Branch**: `main`, folder `/ (root)`. Save.
4. Wait ~30 seconds, refresh. The Pages panel shows your URL.

### 4. Preview locally (optional)

Just double-click `index.html` — it opens in your browser and everything works. For hot-reload:

```bash
python3 -m http.server 8000    # or:  npx serve .
```

Then open <http://localhost:8000>.

### 5. Updating the site

```bash
git add .
git commit -m "Add new publication"
git push
```

GitHub rebuilds automatically within a minute or two.

---

## Tweaking the design

All the design tokens live at the top of `style.css`:

```css
:root {
    --paper: #faf7f0;       /* background — swap for #ffffff for pure white */
    --ink:   #1b1a17;       /* body text */
    --accent: #1e3a5f;      /* navy — try #7a1e3b wine, #2d4a2b forest, #a8421a terracotta */
    --max-width: 44rem;     /* content column width; widen to 52rem for roomier layout */
}
```

To swap fonts, change the Google Fonts `<link>` in `index.html` and the `--font-*` variables in `style.css`.

---

## A few editorial notes on what I did with your CV

- **"Vibe coding"** from your CV skills list is not on the site — insurance/actuarial hiring tends to be conservative and the term reads as informal. Add it back as a chip in the Skills section if you'd prefer.
- Canada Life bullet said "CIFRS" on the CV — I've treated that as a typo for IFRS. Change in `index.html` if wrong.
- The accent colour is navy, which fits insurance/finance. Swap the `--accent` variable for any of the alternatives listed above.
- Brand Ambassador (Times Top 100) and Mathematics Project Assistant roles from the CV aren't in the Experience timeline — for industry reviewers, a tighter list of the most load-bearing roles tends to land better than a complete work history, and your CV covers the fuller picture. Easy to add them back by duplicating a `<li class="timeline-item">` in `index.html`.
- Publications are listed in reverse-chronological order with you in bold when you're an author. The 2025 submitted paper shows "Submitted to …" — change to the venue once it's accepted.

---

## Licence

MIT. Reuse, fork, remix — attribution appreciated.
