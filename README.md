 
# Menu Flipbook (100% Free Hosting)

This folder is a drop-in starter to host your PDF **flipbooks for free** on any static host (GitHub Pages, Cloudflare Pages, Netlify Free).
It uses [StPageFlip] and [PDF.js] from public CDNs.

## Quick Start (GitHub Pages — free)
1. Create a GitHub account (free) and a new **public** repository named `menus-flipbook`.
2. Upload the **contents** of this folder (index.html, multi.html, and the `menus/` folder).
3. Put your PDFs into the `menus/` folder: `dinner.pdf`, `drinks.pdf`, `brunch.pdf` (you can change names).
4. Enable Pages: Settings → Pages → **Deploy from a branch**. Select `main` and root `/`.
5. Your site will be live at: `https://<your-username>.github.io/menus-flipbook/`

- Single menu URL:
  `https://<your-username>.github.io/menus-flipbook/index.html?pdf=/menus/dinner.pdf`

- Tabs page (multiple menus):
  `https://<your-username>.github.io/menus-flipbook/multi.html`

## Quick Start (Cloudflare Pages — free)
1. Go to Cloudflare Pages, create a new project **from Git** and connect this repo.
2. Build settings: Framework **None**, Build command **(leave empty)**, Output directory **/**.
3. Deploy. You’ll get a URL like `https://menus-flipbook.pages.dev/`

## Embed in your website (iframe)
Copy this snippet into your site where you want the flipbook to appear:
```html
<div style="position:relative;padding-top:65%;width:100%;max-width:1100px;margin:auto;">
  <iframe
    src="https://<your-domain>/index.html?pdf=/menus/dinner.pdf"
    style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"
    loading="lazy"
    allowfullscreen>
  </iframe>
</div>
```
Replace `src=` with your actual GitHub Pages or Cloudflare Pages URL. Use `multi.html` if you want tabs for multiple menus.

## Tips
- Keep PDFs under ~5–8 MB for faster mobile loading. Export to **A4 portrait**, 150–200 DPI.
- If a PDF is slow, export images and we can switch to a pure-image version.
- Host the PDFs **in the same repo/domain** as the HTML to avoid CORS issues.
- You can rename or add menus by editing `MENUS` in `multi.html`.

## Files
- `index.html` – Single PDF flipbook (pass `?pdf=` or edit `data-pdf`). 
- `multi.html` – Tabs UI for multiple menus (edit the `MENUS` array).
- `menus/` – Put your PDF files here.
- `menus/README.md` – Placeholder to keep the folder.

---
CDNs:
- StPageFlip: https://unpkg.com/page-flip/
- PDF.js: https://cdnjs.com/libraries/pdf.js
