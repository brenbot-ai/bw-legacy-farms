# B&W Legacy Farms — Website

Clean, single-page informational site for B&W Legacy Farms, New Haven, Indiana.

## Structure

```
bw-legacy-farms/
├── index.html        # Main single-page site
├── thank-you.html    # Contact form success page
├── css/
│   └── style.css     # All styles
└── images/           # Drop logo + photos here
    └── (logo.png, hero.jpg, etc.)
```

## Sections

1. **Hero** — Full-screen, tagline, CTA
2. **About** — Family story, multi-gen values
3. **Operations** — Grain farming, cash rent, grain storage
4. **Contact** — Form with Netlify Forms integration

## Adding the Logo

Replace the text logo placeholder in `index.html`:
```html
<!-- Find this: -->
<span class="logo-text">B&W Legacy Farms</span>

<!-- Replace with: -->
<img src="images/logo.png" alt="B&W Legacy Farms" style="height:44px;" />
```

## Adding a Hero Background Photo

In `css/style.css`, find `.hero` and add a background image:
```css
.hero {
  background-image: url('../images/hero.jpg');
  background-size: cover;
  background-position: center;
  /* keep the rest... */
}
```

## Running Locally

```bash
cd bw-legacy-farms
python3 -m http.server 8080
```
Open http://localhost:8080

## Deploying to Cloudflare Pages

1. Push this folder to a GitHub repo
2. Go to Cloudflare Dashboard → Pages → Create a project
3. Connect the repo, set build output to `/` (no build step)
4. Add your custom domain in the Pages settings
5. Update DNS at your registrar to point to Cloudflare

## Contact Form

The form uses **Netlify Forms** (`data-netlify="true"`).  
If hosting on Cloudflare Pages instead, swap to **Formspree**:
1. Sign up at formspree.io (free tier: 50 submissions/month)
2. Create a form, get your endpoint URL
3. Replace `action="/thank-you.html"` with `action="https://formspree.io/f/YOUR_ID"`
4. Remove `data-netlify="true"` and the hidden input

## Domain & DNS

- Register domain at Cloudflare Registrar (cheapest, at-cost)
- Use Cloudflare DNS (free, fast)
- SSL is automatic via Cloudflare Pages
- Total cost: ~$10-15/year (domain only)
