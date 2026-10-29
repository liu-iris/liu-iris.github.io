# liu-iris.github.io

Iris Liu's portfolio. Plain HTML and one CSS file: no build step, no dependencies.

## Deploying

The site deploys from the `main` branch with GitHub Pages (Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`). Push to `main` and the site at https://liu-iris.github.io updates within a minute or two.

## Files

```
index.html                  Home: intro + case-study cards
about.html                  About: bio, photo, links
graphic-design.html         Graphic design gallery
work/esme.html              ESME case study
work/dont-let-them-in.html  Don't Let Them In case study
css/style.css               All styles (colors and sizes are variables at the top)
images/esme/  images/dlti/  images/graphics/
resume.pdf                  Linked from the nav on every page
```

## Updating content

- **Text:** edit the HTML directly. Each page is self-contained, so the header and footer are repeated on every page. If you change the nav or footer, change it in all five files.
- **Replace the resume:** overwrite `resume.pdf` with the new file, keeping the same name.
- **Add a case study card to Home:** in `index.html`, copy one `<li>` inside `<ul class="card-list">` and change the link, image, title, description, and tags.
- **Add a case study page:** copy `work/esme.html`, then change the title, meta description, metadata row, and sections. Update the "Next case study" links so they form a loop.
- **Add a graphic design piece:** in `graphic-design.html`, copy one `<section>` and change its contents.

### Images

- Always include `width` and `height` (the image's real pixel size) so the page doesn't jump while loading, plus `loading="lazy"` and an `alt` that says what the image shows.
- Every image needs a one-line `<figcaption>` below it.
- To lay out several screenshots side by side, wrap them in `<div class="grid grid-2">` (or `grid-3` / `grid-4`). They stack into one column on phones. Add `panels` (`class="grid grid-3 panels"`) for narrow chat-panel screenshots.
- Wide images use `<figure class="wide">`, which can extend up to 1100px.
- **Images not ready yet** show as a gray placeholder box with the filename inside, for example:
  ```html
  <div class="placeholder" style="aspect-ratio: 4 / 3" role="img" aria-label="Placeholder for ...">images/dlti/map.png</div>
  ```
  When the file exists, replace the `div` with an `<img>`.
- Keep images under ~1MB where possible. Export at about 2000px wide at most; JPG works well for art and photos.

### After changing the stylesheet

Every page loads `css/style.css?v=2`. Browsers keep an old copy of the stylesheet, so after editing `css/style.css`, bump the number on all six pages (for example, change `?v=2` to `?v=3` everywhere). Otherwise you and visitors may keep seeing the old styles.

### Unfinished text

Text still to be written is wrapped in `<span class="todo">[...]</span>`, which shows as a purple note. Search for `class="todo"` to find what's left.

## Previewing locally

```
python -m http.server 8123
```

Then open http://localhost:8123.
