# Blueprint: Legal Services Industry (Variant A)

## Meta
- **Industry**: Legal / Law Firm / Attorney Services
- **Style**: Professional, Authoritative, Trustworthy
- **Color Palette**: Dark Blue primary + Green secondary (success) + White/Light backgrounds
- **Target Pages**: 4-12 (vBronze to vGold)
- **Template Source**: Raven Law Firm

---

## Sections

### 1. Header
- **Layout**: Logo + Navigation with dropdowns
- **Logo**: Law firm logo/icon
- **Navigation**: Home, About, Services, Team, Testimonials, Contact
- **Top Bar**: Contact info (hidden on mobile)
- **Style**: Sticky navigation

### 2. Hero Section
- **Layout**: Full-width with overlay
- **Headline**: "Trusted Legal Counsel in {{city}}"
- **Badge**: "Ranked #1" or similar credibility badge
- **CTA**: "Schedule Consultation" + Video popup button
- **Video**: Fancybox video popup integration
- **ID**: `#hero`

### 3. Recognition/Awards Section
- **Layout**: Badge header + Description text
- **Content**: Awards and recognition description
- **Carousel**: Owl Carousel with award logos/ratings (Lead Counsel, Avvo, etc.)

### 4. About Us Section
- **Layout**: Text content + Image collage
- **Content**: "Who We Are" + Firm values
- **Checklist**: Key benefits (e.g., "No Fees Unless We Win")
- **Images**: Team/Office photo grid
- **ID**: `#about`

### 5. Services Section
- **Layout**: Icon list or grid
- **Service Items**:
  - Proven Track Record (fa-trophy)
  - No Win No Fee (fa-hand-holding-usd)
  - Multilingual Staff (fa-language)
  - 24/7 Availability (fa-phone)
  - 25+ Years Experience (fa-gavel)
  - Trial Attorneys (fa-balance-scale)
- **ID**: `#services`

### 6. Practice Areas
- **Layout**: Interactive map/graphic + List
- **Practice Areas**:
  - Personal Injury
  - Criminal Defense
  - Civil Litigation
  - Family Law
  - Business Law
- **Badge**: "Practice Areas" header
- **ID**: `#practice-areas`

### 7. Recent Results Carousel
- **Type**: Owl Carousel
- **Content**: Case study cards with results
- **Card Style**: Case type + Outcome + Hover details
- **Examples**: "Car Accident - $500,000 Settlement"

### 8. Consultation CTA
- **Layout**: Full-width banner with background image
- **Content**: "Need Legal Consultation?"
- **CTA**: "Call Us Now" button with phone number
- **Background**: Professional office/law image

### 9. Team Section
- **Type**: Carousel or grid
- **Content**: Attorney profiles
- **Card Style**: Photo + Name + Title + Bio excerpt + Social links
- **ID**: `#team`

### 10. Gallery Section (Optional - vSilver+)
- **Type**: Isotope filterable gallery
- **Filters**: All, Office, Events, Team
- **Lightbox**: Fancybox integration
- **ID**: `#gallery`

### 11. Career CTA (Optional)
- **Content**: "Want to Join Our Team?"
- **CTA**: "Apply Now" button

### 12. Footer
- **Layout**: 4-column with Google Maps
- **Columns**: About Links, Account, Resources, Newsletter
- **Map**: Embedded Google Maps
- **Back to Top**: Scroll button
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Lato, Nunito Sans
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --dark-blue: #1E3A5F; --success: #28A745; }
  .btn-primary { background: var(--primary); }
  ```
- Professional, authoritative aesthetic
- Mobile-first responsive design
- Smooth scroll + sticky navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Owl Carousel 2.3.4 for awards/team/results
- Fancybox 3.x for video popups and gallery lightbox
- Isotope/Packery for masonry gallery
- Google Maps API
- Semantic UI (accordion/transitions, optional)
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Scroll animations

---

## Variable Placeholders
- `{{business_name}}` - Law firm name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #1E3A5F)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- lawyer {{city}}
- attorney South Africa
- legal services {{city}}
- law firm Gauteng
- advocate near me

### Long-tail Keywords
- affordable lawyer {{city}}
- best attorneys South Africa
- family law near me
- criminal defense {{city}}
- divorce lawyer Gauteng

### Meta Tags
- **Title**: {{business_name}} | Trusted Legal Services in {{city}}
- **Description**: Expert legal representation in {{city}}, South Africa. Experienced attorneys, personal attention, proven results. Schedule your consultation today!
- **Keywords**: lawyer, attorney, legal, law firm, {{city}}, South Africa, advocate

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "LegalService",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "areaServed": "Gauteng, South Africa"
}
```

---

## Quality Standards

### Layout Consistency Rules
1. **Grid System**: Use Bootstrap 5 12-column grid exclusively
2. **Section Spacing**: Consistent `py-5` (padding-y: 3rem) for all sections
3. **Container Width**: `.container` max-width 1140px for content
4. **Heading Hierarchy**: H1 (hero only) → H2 (section titles) → H3 (card titles) → H4 (subtitles)
5. **Font Sizes**: H1: 3rem, H2: 2.25rem, H3: 1.5rem, Body: 1rem

### Accessibility Requirements
- All images must have `alt` attributes (descriptive text)
- Color contrast ratio minimum 4.5:1 for body text
- Focus states visible for all interactive elements
- Skip-to-content link at top of page
- ARIA labels on icons and buttons without text
- Form inputs must have associated `<label>` elements

### Performance Standards
- Critical CSS inlined in `<head>` for above-the-fold content
- Images lazy-loaded with `loading="lazy"` attribute
- External scripts loaded with `defer` or `async`
- Total page weight target: <500KB (excluding images)
- First Contentful Paint target: <2 seconds

### Brand Consistency
- Primary color must use CSS variable `var(--primary)`
- Mtronika attribution in footer: "Designed by Mtronika"
- WhatsApp button: green (#25D366), fixed bottom-right, 60px diameter
- Logo placement: top-left in navbar, centered in footer
