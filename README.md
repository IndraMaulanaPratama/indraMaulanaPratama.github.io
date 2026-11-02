# indramaulana.com — personal site

Static single-page portfolio. No build step, no dependencies, no framework.
Everything lives in `index.html` (markup, CSS and the theme toggle script).

## Deploying

1. Create a **public** repository named exactly `indraMaulanaPratama.github.io`.
   The name matters: this is a GitHub *user site*, which serves the root domain
   without a subpath. Any other repo name serves from `/<repo-name>/` instead.
2. Push `index.html`, `CNAME` and this file to the `main` branch.
3. Repo → **Settings → Pages** → Source: `main`, folder `/ (root)`.
4. In **Custom domain**, enter `indramaulana.com`. GitHub reads the `CNAME` file
   automatically, so this should already be filled in.
5. Wait for DNS to resolve, then tick **Enforce HTTPS** once it becomes available.

## DNS records

At your domain registrar, for host `@` create four A records:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

And one CNAME: host `www` → `indraMaulanaPratama.github.io`

Verify these against GitHub's current documentation on apex domains before saving —
the addresses are stable but not permanent.

## Files in this bundle

| File | Purpose |
|---|---|
| `index.html` | The whole site — markup, CSS, and the theme/language scripts |
| `cv.pdf` | Served by the **Download CV** button. Replace this whenever the CV changes |
| `photo.jpg` | Profile photo, 640×640. If you delete it the site falls back to an "IMP" monogram |
| `CNAME` | Tells GitHub Pages which custom domain to serve |

## Bilingual content

Every block of prose exists twice: once as `class="lang-en"`, once as `class="lang-id"`.
Two CSS rules on `:root[data-lang=...]` hide whichever set is inactive, and the EN/ID
button flips the attribute and remembers the choice in `localStorage`.

When you edit text, **edit both copies**. A block that exists in only one language will
simply vanish when the reader switches — which looks like a bug, not a translation gap.

## Editing content

Projects are plain `<article class="card">` blocks inside `<section id="work">`.
Copy one, change the text, done. Technology chips are `<span class="tag">`.

Colours are CSS custom properties on `:root`, with a dark-mode block below them.
Change a value once and it applies everywhere.

## Notes

- GitHub Pages' free tier requires a **public** repository, so treat everything
  here as world-readable. No phone number, no internal screenshots, no client data.
- The two NDA projects are described without naming the clients. Keep it that way
  unless you have written clearance.
