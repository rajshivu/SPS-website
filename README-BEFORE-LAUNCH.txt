SANJEEVANI POWER SOLUTIONS — WEBSITE HANDOFF NOTES
====================================================

FILES
  index.html    Home page (hero, about, services, process, testimonial, contact)
  service.html  Service detail page, one file drives all 3 services via ?service= in the URL
  style.css     All styling (single shared stylesheet, no build step, no framework)

No JS framework, no build tools, no external API calls — just static HTML/CSS/JS,
so it can be hosted directly from an S3 bucket / static hosting with no compute cost.

------------------------------------------------------
1. LOGO
   Replace: images/logo.png  (used in header on both pages)
   Recommended size: square, at least 84x84px, transparent background.

2. IMAGES (create an "images" folder next to index.html with these paths)
   images/design/cover.jpg          -> Services section, "Electrical System Design"
   images/design/g1.jpg ... g6.jpg  -> service.html gallery for that service
   images/consultancy/cover.jpg     -> Services section, "Power & Energy Consultancy"
   images/consultancy/g1.jpg ... g4.jpg
   images/sustainability/cover.jpg  -> Services section, "Automation & Sustainability"
   images/sustainability/g1.jpg ... g3.jpg

   You can add or remove gallery images freely — just edit the "gallery" array
   for each service inside the <script> block at the bottom of service.html.
   Until real photos are added, a placeholder pattern displays automatically
   (no broken-image icons).

3. TEXT PLACEHOLDERS TO UPDATE (search for square brackets "[ ]")
   - Hero stats: years in business, projects delivered
   - About section: founding story / company background
   - Stats strip: projects, years, clients served
   - Testimonial: replace with a real client quote and name
   - Contact section + footer: contact person, address, phone, email
   - Google Map: replace the iframe "src" in the Contact section with the
     client's real Google Maps embed link (Maps > Share > Embed a map)
   - WhatsApp link: replace 91XXXXXXXXXX with the real number. This number
     appears in TWO places on each page — the "Chat on WhatsApp" button in
     the Contact section, and the floating WhatsApp button (bottom-right,
     visible on every scroll position across the site) — update both.
   - Contact form: replace formspree.io/f/your_form_id with a real form
     endpoint (Formspree, Getform, or your own backend)

4. DESIGN SYSTEM (for future edits, all in style.css :root)
   Forest #0E3B2E / Forest-deep #082821 / Leaf #6FBE44 / Gold #E3A83B / Paper #F5F7F1
   (eco-friendly green palette, WhatsApp button keeps the standard WhatsApp green)
   Headings: Space Grotesk — Body: Inter (loaded from Google Fonts)

4b. NEW CONTENT SECTIONS (added on top of the original build)
   - "What electrical consultancy actually covers" — educational section on the home page
   - "Industries we serve" — sector grid
   - Certifications strip — replace the bracketed badges with real certifications/licenses
   - FAQ — plain HTML <details>/<summary> accordion, no JavaScript required
   All fully responsive down to small mobile widths (tested breakpoints at 900px, 700px, 480px).

5. ADDING A 4TH SERVICE (optional)
   Add a new entry to the "services" object in service.html, then add a
   matching .service-row block in index.html linking to
   service.html?service=yourkey
