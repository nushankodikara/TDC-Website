# AGENTS.md - Total Drive Care Website Architecture & Handoff

Welcome to the Total Drive Care (TDC) website repository. This document serves as the guide for any future AI agents or developer handoffs. It details the design system, technical choices, and structure.

---

## Project Overview

- **Business Name:** Total Drive Care Solutions (PVT) LTD
- **Domain:** www.totaldrivecare.lk
- **Hotline:** 071 114 4444 (Local) / +94 71 114 4444 (Intl)
- **Main Email:** info@totaldrivecare.lk
- **Facebook:** https://www.facebook.com/totaldrivecare.lk
- **Instagram:** https://www.instagram.com/totaldrivecare.lk
- **Location:** Athurugiriya, Sri Lanka (Next-generation auto repair specializing in major mechanical troubleshooting, structural bodywork, and advanced hydraulic suspension diagnostics)
- **Key Selling Proposition:** Smart tracking and clear communication (SMS and Email notifications on repair stages)

---

## Technical Stack & Architecture

- **Format:** Static Multi-Page Website
- **Frameworks:** Vanilla HTML5, CSS3, JavaScript (ES6+), and Tailwind CSS v3 via CDN.
- **Styling:**
  - Tailwind CDN for mobile-first layout and responsive utilities.
  - `styles.css` for custom industrial theme styles (light blueprint grid backgrounds, micro-animations, scroll-driven timelines, and white glassmorphism).
- **Fonts (Google Fonts):**
  - **Headings:** `Rajdhani` (600, 700) – Tech/industrial square-cut sans-serif.
  - **Body Text:** `Inter` – Clean, readable, and professional.
- **Entry Points:**
  - [index.html](file:///Users/nushan/Projects/TDC%20Website/index.html) - Landing page containing all primary client sections, contact form, services.
  - [track.html](file:///Users/nushan/Projects/TDC%20Website/track.html) - Dedicated repair tracking verification and progress page.
  - [blog.html](file:///Users/nushan/Projects/TDC%20Website/blog.html) - Blog listing and single-post container.
  - [careers.html](file:///Users/nushan/Projects/TDC%20Website/careers.html) - Join our Team, career listings, and job applications.
  - [success.html](file:///Users/nushan/Projects/TDC%20Website/success.html) & [failure.html](file:///Users/nushan/Projects/TDC%20Website/failure.html) - Redirect destinations for Formspark forms.
  - [privacy-policy.html](file:///Users/nushan/Projects/TDC%20Website/privacy-policy.html) & [terms-conditions.html](file:///Users/nushan/Projects/TDC%20Website/terms-conditions.html) - Standard compliance files.
  - [styles.css](file:///Users/nushan/Projects/TDC%20Website/styles.css) - Global stylesheets.

---

## Theme & Design System (Light Titanium Blue)

The layout uses a **Light Titanium Blue** color scheme that conveys a high-tech, clean engineering and mechanic garage aesthetic:

- **Primary Background:** Off-White / Slate 50 (`#f8fafc` / `#ffffff`) - Clean, light-mode base.
- **Card / Surface Background:** Solid White (`#ffffff`) with thin border lines and subtle drop shadows (`shadow-sm` or `shadow-md`).
- **Accent Highlighting:** Deep Cobalt Blue (`#2563eb` / `#0284c7`) - Represents precision, computer systems, and authority.
- **Primary Call to Actions (CTAs):** Safety Orange (`#f97316` / `#ea580c`) - High contrast industrial warning orange.
- **Grid Patterns:** Subtle CSS repeating linear gradients to simulate light coordinate sheets/blueprints (`rgba(14, 165, 233, 0.04)` grid).
- **Glassmorphism:** Frosted white borders (`rgba(14, 165, 233, 0.15)`) and background blur for dropdowns, overlays, and navigation panels.

---

## Form Submissions (Formspark & hCaptcha)

All form interactions are wired to Formspark endpoints and verified via hCaptcha:
- **Site Key:** `ccfac43a-a18c-4a38-acf0-c5560fecb8b2`
- **Redirects:** Formspark redirects to `success.html` or `failure.html` depending on submission verification.
- **Form Endpoints:**
  - **Appointment Form (index.html):** `https://submit-form.com/peO46DbpS`
  - **Contact Form (index.html):** `https://submit-form.com/DcAPdVeHz`
  - **Careers Form (careers.html):** `https://submit-form.com/oA04FVTKe`
    - Uses Uploadcare widget for file uploads with Public Key: `3b42138362a7c9f4a65f`. The resulting CDN URL is submitted to Formspark.
  - **Newsletter Form (index.html footer):** Submits to the main Contact form `https://submit-form.com/DcAPdVeHz` with an input attribute identifying it as a newsletter signup.

---

## Smart Repair Tracking Verification

To simulate TDC's real-time notifications, `track.html` implements a secure lookup:
- **Verification Parameters:** Both **Tracking ID** and **Mobile Number** (e.g. `0712345678`) must match a record.
- **Mock Data Index:**
  - `TDC-101` and `0711144444` -> Stage 1: Diagnostic & Inspection (Mitsubishi Lancer)
  - `TDC-202` and `0712222222` -> Stage 2: Sourcing Parts (Toyota Prado)
  - `TDC-303` and `0713333333` -> Stage 3: Active Repair & Calibration (Range Rover Sport)
  - `TDC-404` and `0714444444` -> Stage 4: Testing & Calibration (Honda Civic Si)
  - `TDC-505` and `0715555555` -> Stage 5: Ready for Delivery (Mercedes-Benz E300)

---

## SEO & Accessibility (a11y) Guidelines

- **Semantic HTML:** Structural elements (`<header>`, `<main>`, `<section>`, `<article>`, `<details>`, `<footer>`).
- **Heading Order:** Exactly one `<h1>` per page. Sub-sections must follow strict hierarchical orders.
- **Meta Tags:** Each page includes `<title>` (under 60 chars), `<meta name="description">` (under 160 chars), OpenGraph tags, and robots tags.
- **Interactive Identifiers:** Unique IDs for automated SEO and functional accessibility tests.
