# The Vogt Real Estate Group — Website

A modern, fast, SEO-optimized real estate website built with [Astro](https://astro.build) and deployed to [Netlify](https://netlify.com).

## Quick Start

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Project Structure

```
vogt-real-estate-group/
├── public/
│   ├── favicon.svg
│   └── images/          ← Drop your own images here
├── src/
│   ├── components/
│   │   ├── Nav.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── BaseLayout.astro
│   ├── pages/
│   │   ├── index.astro         ← Homepage
│   │   ├── search.astro        ← IDX search (embed your feed here)
│   │   ├── buyers-guide.astro
│   │   ├── sellers-guide.astro
│   │   ├── communities.astro
│   │   ├── team.astro
│   │   ├── about.astro
│   │   ├── testimonials.astro
│   │   └── contact.astro       ← Netlify Forms enabled
│   └── styles/
│       └── global.css
├── astro.config.mjs
├── netlify.toml
└── package.json
```

## Deploy to Netlify via GitHub

### 1. Create a GitHub Repository

```bash
cd ~/Desktop/vogt-real-estate-group
git init
git add .
git commit -m "Initial commit — Vogt Real Estate Group site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/vogt-real-estate-group.git
git push -u origin main
```

### 2. Connect to Netlify

1. Go to [app.netlify.com](https://app.netlify.com)
2. Click **"Add new site"** → **"Import an existing project"**
3. Select **GitHub** and authorize access
4. Choose `vogt-real-estate-group` repo
5. Build settings should auto-detect from `netlify.toml`:
   - Build command: `npm run build`
   - Publish directory: `dist`
6. Click **Deploy site**
7. Once deployed, go to **Domain settings** → **Add custom domain** → enter `thevogtregroup.com`
8. Update your DNS to point to Netlify (they'll provide the records)

## IDX / MLS Feed Setup

Your Sacramento MLS is **MetroList** (MetroList Services, Inc.). Here are your best options for adding IDX search to this Astro site:

### Recommended: IDX Broker

**Why:** Most popular, excellent MetroList support, works with any site via JS embeds.

**Setup Steps:**

1. **Sign up** at [idxbroker.com](https://www.idxbroker.com) ($50-80/mo for Core plan)
2. **Apply for MetroList IDX feed** — IDX Broker will guide you through the MLS approval process. You'll need:
   - Your MetroList subscriber/Matrix ID
   - Your Office ID
   - Completed CRMLS IDX Request Form (or MetroList equivalent)
   - Broker permission (Kris can approve as broker)
3. **Get your widget code** from IDX Broker dashboard
4. **Embed in your site** — Open `src/pages/search.astro` and `src/pages/index.astro`, find the `search-embed` placeholder, and replace with your widget:

```html
<!-- Example IDX Broker widget embed -->
<script charset="UTF-8" type="text/javascript"
  id="idxwidgetsrc-XXXXX"
  src="//your-subdomain.idxbroker.com/idx/search.php?widgetid=XXXXX">
</script>
```

Or use an iframe for the full search page:

```html
<iframe
  src="https://your-subdomain.idxbroker.com/idx/search/advanced"
  style="width:100%;min-height:800px;border:none;"
  title="MLS Property Search">
</iframe>
```

### Alternative: Buying Buddy

Embeddable widget components, good CRM, works on any site.

1. Sign up at [buyingbuddy.com](https://buyingbuddy.com)
2. They'll handle MetroList IDX licensing
3. Paste their widget `<div>` + `<script>` in the search embed areas

### Alternative: MetroList Frameable Link

Free option through your MetroList subscription. Less customizable but zero cost.

1. Log in to your MetroList account
2. Get your frameable search URL
3. Embed via iframe in `search.astro`

### MetroList IDX Data License

Regardless of provider, you'll need an IDX data license from MetroList. The $5/month data access fee is typical. Your IDX vendor will usually walk you through this process.

## Replacing Placeholder Images

The site currently uses Unsplash stock photos. Replace them with your own:

1. **Hero image** (`index.astro`): Wide landscape or luxury home shot
2. **Service cards** (`index.astro`): Buy/Sell/Valuation themed photos
3. **Team photos** (`team.astro`): Professional headshots of Kris, Kellie, Kyle
4. **Community photos** (`communities.astro`): Neighborhood-specific images
5. **About photo** (`index.astro`, `about.astro`): Team group photo

Drop images in `public/images/` and reference as `/images/your-photo.jpg`.

## Contact Form

The contact page uses **Netlify Forms** — forms are automatically detected during build and submissions go to your Netlify dashboard. You can set up email notifications in Netlify: Site settings → Forms → Form notifications.

## Customization

### Colors
Edit CSS variables in `src/styles/global.css`:
- `--c-gold`: Primary accent (currently warm gold)
- `--c-espresso`: Dark text/backgrounds
- `--c-cream`: Light section backgrounds

### Fonts
Currently using Playfair Display (headings) + DM Sans (body) from Google Fonts.

### Adding Pages
Create a new `.astro` file in `src/pages/` — Astro auto-generates routes from the file name.

## Tech Stack

- **Astro** — Static site generator, zero JS by default
- **Netlify** — Hosting, forms, CDN
- **Google Fonts** — Playfair Display + DM Sans
- **IDX Broker** (recommended) — MLS listing search
