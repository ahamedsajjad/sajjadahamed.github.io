# How to Edit Your Site

## The basic loop

1. Go to your repo on GitHub
2. Click the file you want to change (e.g. `research.html`)
3. Click the **pencil icon** (top right of the file view)
4. Edit the text
5. Click **Preview** to sanity-check
6. Scroll down → **Commit changes**
7. Live in ~1 minute (hard-refresh to see it: Cmd+Shift+R / Ctrl+F5)

## Safe vs unsafe

- **SAFE to edit:** anything between `>` and `<` — that's your visible text
- **DO NOT touch:** the `<style>` block at the top of each file, or tag names themselves
- **Deleting a block:** remove the whole thing, opening tag through closing tag

## Formatting basics

| You want | Write this |
|----------|-----------|
| *Italics* (journal names, book titles) | `<em>Journal Name</em>` |
| A link | `<a href="https://example.com">link text</a>` |
| An ampersand | `&amp;` (not a bare `&`) |
| An em dash — | `&mdash;` |
| A middle dot · | `&middot;` |
| A curly apostrophe ’ | `&rsquo;` |

---

## index.html (Home)

Body text is plain paragraphs. Edit the words, keep the tags:

```html
<p>Your paragraph text goes here.</p>
```

To add a new paragraph, copy an existing `<p>...</p>` line and edit it.

The contact line near the bottom:

```html
<p>You can email me at <a href="mailto:REAL@wayne.edu">REAL@wayne.edu</a>
or find me on <a href="https://www.linkedin.com/in/YOUR-REAL-HANDLE/">LinkedIn</a>.</p>
```

---

## research.html (Publications)

**One publication block:**

```html
<div class="pub">
  <p class="title">Exact Article Title Here</p>
  <p class="venue"><em>Journal Name</em>, 2026. <a href="https://doi.org/XXXX">doi.org/XXXX</a></p>
</div>
```

**With a co-author:**

```html
<div class="pub">
  <p class="title">Exact Article Title Here (with M. Gallagher)</p>
  <p class="venue"><em>African Studies Quarterly</em>, 2025. <a href="URL">Link</a></p>
</div>
```

**A book chapter:**

```html
<div class="pub">
  <p class="title">Exact Chapter Title Here</p>
  <p class="venue">In <em>Book Title</em>, Publisher, 2023. <a href="URL">Link</a></p>
</div>
```

**No link yet?** Drop the `<a>` part entirely:

```html
<p class="venue"><em>Journal Name</em>, 2026.</p>
```

**Adding a whole new section heading:**

```html
<h2 class="label">Section Name</h2>
```

**To remove a publication:** delete from `<div class="pub">` through `</div>` inclusive.

---

## teaching.html (Courses)

```html
<div class="course">
  <p class="title">PS 1050: Understanding Political Science Statistics</p>
  <p class="meta">Graduate Teaching Assistant &middot; Fall 2025, Winter 2026</p>
</div>
```

Copy the block to add a course; delete the whole block to remove one.

---

## media.html

**Embedding a video** — replace the whole `<div class="video-placeholder">...</div>`
with the iframe you get from YouTube (Share → Embed). Keep it inside `.video-wrap`:

```html
<div class="video-wrap">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID" title="Talk title" allowfullscreen></iframe>
</div>
<p class="caption">Talk title &middot; Venue &middot; Date</p>
```

**Adding a photo** — upload the image to the `assets` folder, then:

```html
<img src="assets/your-photo.jpg" alt="Describe the photo" loading="lazy">
```

**A press link:**

```html
<li><a href="https://URL">Title of the piece</a> <span class="src">&mdash; Outlet, 2026</span></li>
```

---

## cv.html

Upload your PDF to the `assets` folder named exactly `cv.pdf`, then update the date:

```html
<p class="updated">Last updated: July 2026</p>
```

---

## Uploading files (photos, CV PDF)

1. In your repo, click into the `assets` folder
2. **Add file** → **Upload files**
3. Drag the file in → **Commit changes**
4. Reference it in HTML as `assets/filename.jpg`

## If you break something

Every commit is saved. Click the **History** link on any file, find the version
before your change, and restore it. Nothing is ever permanently lost.
