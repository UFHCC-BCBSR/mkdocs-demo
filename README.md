# MkDocs Demo — Reusable Site Template

A ready-to-use MkDocs site template with automatic deployment to GitHub Pages via GitHub Actions. Every time a file is edited — including directly on GitHub.com — the site rebuilds and deploys automatically.

> **This repo is a template.** Click the green "Use this template" button above to create your own copy.

---

## Which workflow is right for you?

There are two ways to use this template. Choose based on your comfort level:

<details>
<summary>✅ <strong>No terminal needed — Edit everything on GitHub.com</strong></summary>

This workflow requires no command line, no Git, and no local setup.
You only need a GitHub account and permission to use the org.

**You can:**
- Create your repo from this template in a few clicks
- Edit any `.md` file directly on GitHub.com
- Add images by uploading files through the GitHub interface
- See your site update automatically within ~2 minutes of saving

**You cannot (without the terminal):**
- Preview the site before it goes live
- Add new MkDocs plugins or change `requirements.txt`
- Restructure the nav in `mkdocs.yml` and test it locally first

> If all you need to do is write and edit documentation, this workflow is all you need.

</details>

<details>
<summary>💻 <strong>Terminal workflow — Full local development</strong></summary>

This workflow lets you preview the site locally before pushing, install plugins, and make structural changes with confidence.

**You will need:**

| Tool | Install |
|------|---------|
| Python 3 | [python.org](https://www.python.org/downloads/) |
| GitHub CLI (`gh`) | [cli.github.com](https://cli.github.com/) |
| MkDocs + Material | Installed automatically via `requirements.txt` |

</details>

---

## Quickstart

### ☁️ GitHub.com only (no terminal)

**1. Create your repo from this template**

Click the green **"Use this template"** button at the top of this repo, then select **"Create a new repository"**. Choose the `UFHCC-BCBSR` org as the owner and give it a name.

**2. Enable GitHub Pages (one-time setup)**

After your repo is created, the GitHub Actions workflow will run automatically and create a `gh-pages` branch.

<details>
<summary>How to enable GitHub Pages</summary>

1. Go to your new repo on GitHub.com
2. Click **Settings** (top menu) → **Pages** (left sidebar)
3. Under **Branch**, select `gh-pages` and click **Save**
4. Your site will be live at `https://ufhcc-bcbsr.github.io/your-repo-name/`

> It may take 1–2 minutes to appear the first time.

</details>

**3. Edit your site**

- Navigate to any `.md` file in the `docs/` folder
- Click the ✏️ pencil icon to edit
- Make your changes and click **"Commit changes"**
- Your site will automatically rebuild and deploy

**4. Change your site name and description**

- Open `mkdocs.yml` at the root of your repo
- Click the ✏️ pencil icon
- Edit the `site_name` and `site_description` fields at the top
- Commit — the site will redeploy with your new title

---

### 💻 Local development (terminal)

**1. Authenticate the GitHub CLI**

```bash
gh auth login
```

**2. Clone your repo**

```bash
git clone https://github.com/UFHCC-BCBSR/your-repo-name.git
cd your-repo-name
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

**4. Preview locally**

```bash
mkdocs serve
```

Open [http://127.0.0.1:8000](http://127.0.0.1:8000) — the site live-reloads as you edit files.

**5. Push your changes**

```bash
git add .
git commit -m "Your message here"
git push
```

GitHub Actions will automatically build and deploy your site to GitHub Pages.

---

## Customizing Your Site

Edit `mkdocs.yml` to change your site name, navigation, colors, and more.
This can be done directly on GitHub.com — no terminal needed.

<details>
<summary>Changing the site name and description</summary>

```yaml
site_name: My Project Documentation   # ← change this
site_description: A short description # ← change this
```

</details>

<details>
<summary>Changing the theme color</summary>

```yaml
theme:
  palette:
    primary: blue  # ← change this
```

See all available colors at [squidfunk.github.io/mkdocs-material/setup/changing-the-colors](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/).

</details>

<details>
<summary>Adding a new page to the nav</summary>

1. Create a new `.md` file in the `docs/` folder (you can do this on GitHub.com via **Add file → Create new file**)
2. Add it to the `nav:` section of `mkdocs.yml`:

```yaml
nav:
  - Home: index.md
  - My New Page: my-new-page.md
```

</details>

<details>
<summary>Replacing the logo</summary>

1. Go to `docs/assets/` in your repo on GitHub.com
2. Click **Add file → Upload files**
3. Upload your logo (PNG recommended)
4. In `mkdocs.yml`, update:

```yaml
theme:
  logo: assets/your-logo-filename.png
  favicon: assets/your-logo-filename.png
```

</details>

---

## Example Pages

The `docs/` folder includes example pages demonstrating common MkDocs features.
Use them as copy-paste references when building your own content.

| Page | What it demonstrates |
|------|----------------------|
| Images | Adding and sizing images |
| Admonitions | Note, warning, tip, and danger boxes |
| Video | Embedding a YouTube video |
| Code blocks | Syntax highlighting and copy button |

---

## Resources

| Resource | Link |
|----------|------|
| MkDocs documentation | [mkdocs.org](https://www.mkdocs.org) |
| Material theme documentation | [squidfunk.github.io/mkdocs-material](https://squidfunk.github.io/mkdocs-material/) |
| Material color palette | [Changing the colors](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/) |
| Material icon browser | [Icons and emojis](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/) |
| Markdown cheatsheet | [markdownguide.org](https://www.markdownguide.org/cheat-sheet/) |

---

## Repo Structure

```
your-repo/
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions workflow — do not edit
├── docs/
│   ├── assets/
│   │   ├── logo.png          # Replace with your logo
│   │   └── css/
│   │       └── custom.css    # Add custom styles here
│   ├── index.md              # Home page
│   ├── 01_section-one/
│   │   ├── page-one.md
│   │   └── page-two.md
│   └── 02_section-two/
│       └── page-three.md
├── mkdocs.yml                # Site configuration
├── requirements.txt          # Python dependencies
└── README.md                 # You are here
```

---

## Questions?

Open an issue in this repo or contact the UFHCI Biostatistics and Computational Biology Shared Resource.
