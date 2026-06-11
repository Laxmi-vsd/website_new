# Laxmidhar Barik — VLSI Portfolio

Personal portfolio website for **Laxmidhar Barik**, M.Tech VLSI Design & Embedded Systems student at IIT Bhubaneswar. Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).

🌐 **Live site:** https://laxmi-vsd.github.io/portfolio/

---

## Folder Structure

```
portfolio/
├── mkdocs.yml                  ← Site configuration
├── docs/
│   ├── index.md                ← Home / About Me
│   ├── stylesheets/
│   │   └── extra.css           ← Custom styles
│   ├── assets/
│   │   ├── profile.png         ← Your profile photo (add this!)
│   │   ├── logo.png            ← Navbar logo (add this!)
│   │   ├── favicon.png         ← Browser tab icon (add this!)
│   │   └── resume/
│   │       └── Laxmidhar_Barik_Resume.pdf  ← Your resume (add this!)
│   ├── skills/
│   │   └── index.md
│   ├── projects/
│   │   └── index.md
│   ├── publications/
│   │   └── index.md
│   ├── resume/
│   │   └── index.md
│   └── contact/
│       └── index.md
└── README.md
```

---

## Deployment to GitHub Pages

### Step 1 — Create a GitHub repository

1. Go to https://github.com/new
2. Repository name: `portfolio`
3. Set to **Public**
4. Do NOT initialise with README
5. Click **Create repository**

### Step 2 — Upload all files

Option A — GitHub web interface:
1. Click **Add file → Upload files**
2. Drag the entire `portfolio/` folder contents
3. Commit with message: `Initial portfolio site`

Option B — Git command line:
```bash
cd portfolio/
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/laxmi-vsd/portfolio.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages with GitHub Actions

Create the file `.github/workflows/deploy.yml` in your repo:

```yaml
name: Deploy MkDocs to GitHub Pages
on:
  push:
    branches: [main]
permissions:
  contents: write
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: 3.x
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force
```

### Step 4 — Go live

1. After the workflow runs (2–3 minutes), go to:  
   **Settings → Pages → Source → Deploy from branch → gh-pages → /(root)**
2. Your site will be live at:  
   **https://laxmi-vsd.github.io/portfolio/**

---

## Adding Your Content

### Add your profile photo
- Place a square photo (400×400 px minimum) at `docs/assets/profile.png`

### Add your resume PDF
- Place your resume at `docs/assets/resume/Laxmidhar_Barik_Resume.pdf`

### Update your LinkedIn URL
- Edit `mkdocs.yml` → `extra.social` section
- Edit `docs/contact/index.md`

### Add a project
- Open `docs/projects/index.md`
- Copy an existing project block and fill in your details

### Update skills
- Edit `docs/skills/index.md` — add/remove rows in the tables or tabs

---

## Local Preview

```bash
pip install mkdocs-material
cd portfolio/
mkdocs serve
# Open http://127.0.0.1:8000
```

---

## Custom Domain (Optional)

1. Buy a domain (e.g., `laxmidharbarik.com`)
2. Add a `CNAME` file to `docs/` folder containing just your domain:
   ```
   laxmidharbarik.com
   ```
3. In your domain DNS, add a CNAME record pointing to `laxmi-vsd.github.io`
4. In GitHub → Settings → Pages → Custom domain, enter your domain
