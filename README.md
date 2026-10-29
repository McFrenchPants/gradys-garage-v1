# Grady's Garage — High-Converting Auto Repair Landing Page (`gradysgarage.com`)

A modern, mobile-first, ultra-fast static landing page built for **Grady's Garage**, an ASE-Certified and NAPA Auto Care Center located in Owosso, Michigan. Hosted on **Cloudflare Pages** at [`https://gradysgarage.com`](https://gradysgarage.com).

---

## 📖 Project Overview

This repository contains the official, lightweight business website for **Grady's Garage**, an independent ASE-Certified and NAPA Auto Care Center located in Owosso, Michigan.

The website is designed to provide customers with a clean, fast, and mobile-friendly experience to learn about shop services, find operating hours and location details, and easily contact the team for vehicle service appointments.

### Key Highlights
- **Simple & Fast:** Pure static HTML5 and CSS with sub-second load times and zero heavy runtime dependencies.
- **Mobile-First & Accessible:** Fully responsive layout with intuitive click-to-call actions, clear navigation, and accessible semantic markup.
- **Local Business Essentials:** Clear overview of auto repair services, ASE/NAPA certifications, shop hours, 24/7 key drop, and location directions.
- **Production-Ready Hosting:** Structured for direct deployment via Cloudflare Pages or any modern static web host.

---

## 🏢 Business Source of Truth (NAP)

| Field | Value |
| :--- | :--- |
| **Business Name** | Grady's Garage |
| **Owner / Lead Contact** | Jim Grady |
| **Address** | 1107 E Main Street, Owosso, MI 48867 |
| **Phone** | `(989) 725-3800` (`tel:9897253800`) |
| **Email** | `gradysgarage@gmail.com` |
| **Primary Domain** | `https://gradysgarage.com` |
| **Hours** | Monday – Friday: 8:00 AM – 5:00 PM (Closed Sat–Sun) |
| **Accreditations** | Certified NAPA Auto Care Center • ASE-Certified Technicians • Shiawassee Regional Chamber of Commerce Member • ~4.9★ Customer Rating |

---

## 📁 Repository Structure

```text
Gradys-Garage/
├── README.md                  # Project overview, architecture, and deployment guide
├── .gitignore                 # Standard Git ignore rules
├── docs/                      # Reference specifications & operational runbooks
│   ├── business_profile.md    # Core business details, accreditations, and service menu
│   ├── fix_ads_disapproval.md # Step-by-step Google Ads phone verification runbook
│   ├── operations_runbook.md  # Git, Cloudflare Pages, and GoDaddy DNS setup guide
│   └── website_requirements.md# Landing page architecture, CRO, and SEO specs
├── images/                    # Original source photography from Grady's Garage
└── website/                   # Production-ready static site root (Cloudflare Pages root)
    ├── index.html             # Complete semantic HTML5 landing page + JSON-LD schema
    ├── styles.css             # Pre-compiled, minified Tailwind CSS & custom utilities
    ├── favicon.svg            # Vector gear/shield favicon matching Grady's Garage branding
    ├── robots.txt             # Search & Google Ads crawler permissions
    ├── sitemap.xml            # XML sitemap for gradysgarage.com
    ├── _headers               # Cloudflare Pages caching & security headers
    └── images/                # SEO-named production image assets
```

---

## 🚀 Deployment Instructions (Cloudflare Pages)

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "feat: initial release of Grady's Garage landing page"
git branch -M main
git remote add origin https://github.com/<your-username>/gradys-garage-web.git
git push -u origin main
```

### 2. Configure Cloudflare Pages
1. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com/) and navigate to **Compute (Workers & Pages)** > **Create application** > **Pages** > **Connect to Git**.
2. Select the `gradys-garage-web` repository.
3. Configure the build settings:
   - **Project name:** `gradys-garage`
   - **Production branch:** `main`
   - **Framework preset:** `None`
   - **Build command:** *(Leave blank)*
   - **Build output directory:** `/website`
4. Click **Save and Deploy**.

### 3. Connect Custom Domain (`gradysgarage.com`) & Verify Google Ads
- Follow [`docs/operations_runbook.md`](docs/operations_runbook.md) to point GoDaddy DNS (`@` and `www`) to Cloudflare Pages.
- Once `https://gradysgarage.com` is live with SSL, follow [`docs/fix_ads_disapproval.md`](docs/fix_ads_disapproval.md) to set `https://gradysgarage.com` as the **Verification URL** for `(989) 725-3800` in Google Ads.
