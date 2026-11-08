# Saree Skill and Re-Polish Center - Website

A static, fully responsive website built with HTML5, CSS3 and vanilla JavaScript.
No backend, no database, no build tools, no dependencies. Ready for Netlify.

## Folder structure

```
saree-skill-website/
├── index.html       Home
├── about.html       About Us
├── services.html    All 10 service cards + a detailed section for each service
├── gallery.html     Before/after sliders, filterable gallery, image preview popup
├── contact.html     Contact details, map, Netlify enquiry form
├── css/style.css    All styles (palette is defined as variables at the top)
├── js/script.js     All interactivity + the BUSINESS details block
└── images/          banner/, services/, gallery/, logo/
```

## Before you publish: 3 things to fill in

1. **Business details** - open `js/script.js` and edit the `BUSINESS` block at the top:
   phone display text, phone digits, WhatsApp number (country code + number, digits only,
   e.g. `919876543210`) and the address. One edit updates every page (header, footer,
   buttons, map). While these are empty, the site shows `[Add your phone number]` /
   `[Add your business address]`, call and WhatsApp buttons lead to the enquiry form,
   and the map shows a notice. No contact details have been invented.
2. **Images** - the pictures included are simple generated illustrations used as
   placeholders (SVG). Replace them with real photos of your work (see below).
3. **Testimonials** - the three on the home page are clearly marked samples. Replace them
   with real customer feedback (with permission) in `index.html`.

## Replacing the images

Keep the same file names and the site updates automatically, or change the `src` paths.

- `images/banner/hero.svg` - home hero background (use a wide image, about 1600x900)
- `images/services/<service>.svg` - one per service (about 800x600)
- `images/gallery/g1..g8.svg` - gallery photos
- `images/gallery/ba1..ba3-before/after.svg` - before/after pairs (keep each pair the same size)
- `images/logo/logo.svg` - logo and browser icon

If you switch to JPG/PNG/WebP files, update the extensions in the HTML (search for `.svg`).
For speed, resize photos to roughly 1200px wide and compress them (WebP or JPG, under 200 KB each).
Always keep meaningful `alt` text.

## Deploying to Netlify

**Option A: drag and drop (easiest)**
1. Sign in at https://app.netlify.com
2. Go to **Sites** and drag the `saree-skill-website` folder onto the deploy area.
3. Netlify publishes it and gives you a URL. You can rename it or add your own domain under *Domain settings*.

**Option B: Git**
1. Push this folder to a GitHub repository.
2. In Netlify choose **Add new site > Import an existing project** and pick the repository.
3. Leave the build command empty and set the publish directory to `/` (the repository root, or the folder containing `index.html`).

No server configuration is needed.

## Enquiry form (Netlify Forms)

The form on `contact.html` uses `data-netlify="true"`, so Netlify detects it when the site is deployed.
Submissions appear in your Netlify dashboard under **Forms**. To receive an email for each enquiry:
**Site configuration > Forms > Form notifications > Add notification > Email notification**.

Notes:
- The form only works on the deployed Netlify site. Opening the file locally shows a friendly
  error and suggests WhatsApp instead.
- A hidden honeypot field (`bot-field`) is included for basic spam protection.
- The form is validated in the browser first (name, phone, optional email, service, message).
- Netlify must detect the form at deploy time. It is plain HTML in `contact.html`, so this happens automatically.

## Features

Responsive mobile menu, smooth scrolling, service quick-navigation with scroll highlighting,
Read More toggles, gallery filter and lightbox (keyboard: Esc, left/right arrows), before/after slider
(mouse, touch and keyboard), FAQ accordion, form validation, WhatsApp enquiries with pre-filled messages,
back-to-top button, active navigation highlighting (works with Netlify's extension-less URLs),
scroll animations (disabled for people who prefer reduced motion), and lazy loading of images.

## Customising

- **Colours**: edit the variables at the top of `css/style.css` (`--maroon`, `--gold`, `--cream`, `--pink`, `--brown`).
- **Service text**: each service has its own section in `services.html` (id such as `#darning`).
- **Fonts**: Playfair Display and Poppins load from Google Fonts, with serif/sans-serif fallbacks if offline.
- **Social sharing image**: `og:image` uses a relative path. After you have a domain, change it to the full
  URL (for example `https://yourdomain.com/images/banner/hero.jpg`) and use a JPG/PNG, since many
  platforms do not show SVG previews.

## Notes on content

Service descriptions use plain language and avoid technical promises. Each service says that results depend on the
age, fabric and condition of the saree, and that the team inspects first. Please review the wording and adjust it
so it matches how your business actually works (for example, the process steps, timings and fabrics you handle).
