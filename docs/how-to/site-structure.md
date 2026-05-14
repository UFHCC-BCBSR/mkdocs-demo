# Site Structure & Navigation

Your MkDocs site is controlled by two things: the **files** in your `docs/` folder and the **`mkdocs.yml`** file at the root of your repo. This page explains how they work together.

---

## How it works

Every page on your site is a markdown file (`.md`) inside the `docs/` folder. The `mkdocs.yml` file tells MkDocs what to call each page and how to organize them in the navigation menu.

```
your-repo/
├── mkdocs.yml        ← controls site settings and navigation
├── docs/
│   ├── index.md      ← your home page (required)
│   ├── about.md
│   └── 01_section/
│       └── page.md
```

---

## The nav section in mkdocs.yml

The `nav:` block in `mkdocs.yml` defines your site's menu. Each entry is a label and a path to a file in `docs/`.

```yaml
# mkdocs.yml — located at the root of your repo

nav:
  - Home: index.md
  - About: about.md
  - My Section:
    - First Page: 01_section/first-page.md
    - Second Page: 01_section/second-page.md
```

> The label on the left (e.g. `Home`, `About`) is what appears in the menu. The path on the right is relative to the `docs/` folder.

---

## Adding a new page

**Step 1 — Create the file**

<details>
<summary>On GitHub.com (no terminal)</summary>

1. Navigate to your `docs/` folder on GitHub.com
2. Click **Add file → Create new file**
3. Name your file, e.g. `my-new-page.md` or `01_section/my-new-page.md`
4. Add some content and click **Commit changes**

</details>

<details>
<summary>Locally (terminal)</summary>

```bash
# from the root of your repo
touch docs/my-new-page.md
```

</details>

**Step 2 — Add it to the nav**

Open `mkdocs.yml` and add a line under `nav:`:

```yaml
nav:
  - Home: index.md
  - My New Page: my-new-page.md  # ← add this
```

---

## Adding a new section

To group pages under a section heading in the menu, indent them under a label with no file path:

```yaml
nav:
  - Home: index.md
  - My Section:             # ← section label, no file path
    - Page One: 01_section/page-one.md
    - Page Two: 01_section/page-two.md
```

It helps to organize your files into matching folders inside `docs/`, but it is not required — the folder structure and the nav are independent.

---

## Changing the site name and description

At the top of `mkdocs.yml`:

```yaml
# mkdocs.yml — located at the root of your repo

site_name: My Project Documentation   # ← appears in the browser tab and header
site_description: A short description # ← used for search and SEO
```

---

## Tips

- The file `docs/index.md` is your home page and is required
- File and folder names cannot contain spaces — use hyphens or underscores
- The order of items in `nav:` controls the order they appear in the menu
- After editing `mkdocs.yml` on GitHub.com, your site will redeploy automatically in ~2 minutes
