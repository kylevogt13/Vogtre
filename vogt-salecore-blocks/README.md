# Vogt RE — SaleCORE Content Blocks

## How to Paste These Into SaleCORE

### Step 1: Website Settings (do this FIRST)
1. In SaleCORE editor, click "Website Options" or "Page Options"
2. Find the "Head HTML" field
3. Paste the ENTIRE contents of `00-website-settings/head-html.html` into that field
4. Save

### Step 2: Upload Images
1. Download team photos from the Astro site (https://dynamic-jalebi-53351b.netlify.app/images/)
2. Upload them to SaleCORE's media library
3. Note the new media URLs
4. In the team HTML files (06-team/02-team-grid.html), replace the placeholder `src="UPLOAD-TO-SALECORE-*.jpg"` values with the actual SaleCORE media URLs

### Step 3: Build Each Page
For each page folder (01-homepage, 02-search, etc.):

1. In SaleCORE, navigate to the page (or create via "Add Page")
2. For each numbered HTML file:
   - Right-click → "Add content" → Select "HTML"
   - Paste the contents of the HTML file
   - Save
3. For `.js` files:
   - Right-click → "Add content" → Select "Script"
   - Paste the JavaScript
   - Save
4. For `.txt` instruction files:
   - Follow the instructions (e.g., add SaleCORE's IDX widget or form widget)

### Block Order Matters!
Paste blocks in numbered order (01, 02, 03...) from top to bottom on each page. This determines the visual layout.

### Pages Overview
| Folder | Page | Blocks |
|--------|------|--------|
| 00-website-settings | N/A (global) | Head HTML (paste in Website Settings) |
| 01-homepage | Home | Hero video, stats, services, IDX, about, communities, testimonials, guides, home value CTA, join team, scripts |
| 02-search | Search | Page hero + IDX widget |
| 03-buyers-guide | Buyer's Guide | Page hero, 10 steps, CTA |
| 04-sellers-guide | Seller's Guide | Page hero, 8 steps, CTA |
| 05-communities | Communities | Page hero + 6 community sections |
| 06-team | Our Team | Page hero, team grid (8 members), CTA |
| 07-about | About Us | Page hero, about content, CTA |
| 08-testimonials | Testimonials | Page hero, 22 testimonials, CTA |
| 09-contact | Contact | Page hero, contact details, form widget |
| 10-join-our-team | Join Our Team | Page hero, content |
| 11-refer-a-friend | Refer a Friend | Page hero, content |
| 12-home-value | Home Value | Page hero, valuation widget |
| 13-pre-qualified | Pre-Qualified | Page hero, content |
| 14-articles | Articles | Page hero, articles widget |

### Contact Details
- Address: 13098 Apple Road, Wilton, California 95693
- Phone: (916) 801-4002
- Email: thevogts@thevogtregroup.com
- DRE: #02144449
- Facebook: https://facebook.com/Vogtrealestate/
- Instagram: https://instagram.com/kylevogt1/

### Design System
- **Typography:** Playfair Display (headings), DM Sans (body)
- **Colors:** Gold (#C5A46D), Espresso (#2B2118), Cream (#FAF7F2), Slate (#6B6259)
- **Aesthetic:** Warm luxury, editorial real estate
