# Embedding Video

The recommended way to add video to your site is to **embed from YouTube or Vimeo**. This keeps your repo small and fast — the video file itself lives on the external platform.

---

## Embedding a YouTube video

**Step 1 — Get the embed code from YouTube**

1. Go to the YouTube video you want to embed
2. Click **Share** below the video
3. Click **Embed**
4. Copy the `<iframe>` code

It will look something like this:

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
```

**Step 2 — Paste it into your markdown file**

MkDocs supports raw HTML in markdown files, so you can paste the iframe directly:

```markdown
## My Video Title

Some introductory text here.

<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
```

> Replace `VIDEO_ID` with the actual ID from your video's URL, e.g. for `https://www.youtube.com/watch?v=dQw4w9WgXcQ` the ID is `dQw4w9WgXcQ`.

---

## Making the video responsive

The default iframe has a fixed width and may not look great on smaller screens. Wrap it in a div to make it scale with the page:

```markdown
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID"
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
    frameborder="0"
    allowfullscreen>
  </iframe>
</div>
```

> `56.25%` maintains a standard 16:9 aspect ratio.

---

## Embedding a Vimeo video

The process is the same — go to the video on Vimeo, click **Share**, copy the embed code, and paste it into your markdown file.

---

## Linking to an externally hosted video file

If your video is hosted on a shared drive or institutional storage and you have a direct link, you can add it as a standard hyperlink:

```markdown
[Watch the demo video](https://your-institution.edu/path/to/video.mp4)
```

Or if the hosting platform supports it, you can use an HTML video player:

```markdown
<video width="560" controls>
  <source src="https://your-institution.edu/path/to/video.mp4" type="video/mp4">
</video>
```

---

## Tips

- Never commit large video files directly to your repo
- YouTube and Vimeo are the most reliable embedding options
- Make sure your YouTube video is set to **public** or **unlisted** — private videos will not embed
