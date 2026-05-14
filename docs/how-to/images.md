# Adding Images

Images can be added to any page. There are two steps: **uploading the image file** to your repo and **referencing it** in your markdown.

---

## Step 1 — Upload your image

We recommend keeping all images in `docs/assets/images/` to stay organized.

<details>
<summary>On GitHub.com (no terminal)</summary>

1. Navigate to `docs/assets/` in your repo
2. Click **Add file → Upload files**
3. Drag and drop your image or click to browse
4. Click **Commit changes**

> If the `images/` subfolder doesn't exist yet, you can create it by naming your file `images/my-image.png` in the file name field — GitHub will create the folder automatically.

</details>

<details>
<summary>Locally (terminal)</summary>

```bash
# from the root of your repo
cp ~/Downloads/my-image.png docs/assets/images/my-image.png
git add .
git commit -m "Add image"
git push
```

</details>

---

## Step 2 — Add the image to your page

Open the `.md` file where you want the image to appear and use this syntax:

```markdown
![A description of the image](../assets/images/my-image.png)
```

> The text in square brackets is the **alt text** — a short description of the image. It is important for accessibility and should always be filled in.

---

## Getting the path right

The path to your image is **relative to the markdown file** you are editing. Use the table below:

| Your markdown file | Path to use |
|--------------------|-------------|
| `docs/index.md` | `assets/images/my-image.png` |
| `docs/how-to/page.md` | `../assets/images/my-image.png` |
| `docs/how-to/sub/page.md` | `../../assets/images/my-image.png` |

> Each `../` moves up one folder level toward `docs/`.

---

## Controlling image size

Add a width attribute after the path:

```markdown
![My image](../assets/images/my-image.png){ width="400" }
```

Or as a percentage of the page width:

```markdown
![My image](../assets/images/my-image.png){ width="60%" }
```

---

## Adding a caption

```markdown
<figure markdown>
  ![A bar chart showing gene expression levels](../assets/images/my-image.png)
  <figcaption>Figure 1. Gene expression levels across conditions.</figcaption>
</figure>
```

---

## Tips

- Supported formats: PNG, JPG, GIF, SVG, WebP
- PNG is recommended for screenshots and diagrams
- Avoid spaces in file names — use hyphens or underscores: `my-figure.png` ✅  `my figure.png` ❌
- Keep images reasonably sized before uploading — large images slow down page load
