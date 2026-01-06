# Blueprint: Healthcare/Medical Industry (Variant B - Dental)

## Meta
- **Industry**: Healthcare / Dental Clinic
- **Style**: Modern, Clean, Professional with Rounded Elements
- **Color Palette**: Dental blue primary + White + Light accents
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: DentCare

---

## Sections

### 1. Topbar
- **Layout**: Opening hours + Email ({{email}}) + Phone ({{phone}})
- **Accent**: Primary color shape on right side
- **Background**: Light

### 2. Navbar
- **Logo**: Tooth icon + Clinic name
- **Navigation**: Home, About, Services, Pricing, Team, Contact
- **Features**: Search modal trigger
- **CTA**: "Book Appointment" button
- **Style**: Sticky on scroll

### 3. Full Screen Search Modal (Optional)
- **Type**: Overlay search input
- **Style**: Dark overlay with centered search field

### 4. Hero Carousel
- **Type**: Owl Carousel or Bootstrap Carousel
- **Content**: Dental clinic images with headlines
- **Headline**: "Quality Dental Care in {{city}}"
- **CTAs**: "Book Appointment" + "Contact Us"
- **ID**: `#hero`

### 5. Banner Cards
- **Layout**: 3-column quick action cards
- **Cards**:
  - Opening Hours (with schedule)
  - Find a Dentist (search/link)
  - Book Appointment (form link)
- **Style**: Colored backgrounds with icons

### 6. About Section
- **Layout**: Text content + Image
- **Content**: Clinic story (AI-generated from business_intent)
- **Checkmarks**: Award Winning, Professional Staff, 24/7 Emergency, Fair Prices
- **CTA**: "Read More"
- **ID**: `#about`

### 7. Appointment Form Section
- **Layout**: Full-width with form
- **Headline**: "Book Your Appointment"
- **Form Fields**: Name, Email, Phone, Service select, Date picker, Time picker, Message
- **Submit**: Email to {{email}}
- **Background**: Primary color
- **ID**: `#appointment`

### 8. Services Section
- **Layout**: Before/After slider + 4 service cards
- **Before/After**: TwentyTwenty comparison slider (treatment results)
- **Service Cards**:
  - Cosmetic Dentistry (fa-tooth)
  - Dental Implants (fa-teeth)
  - Crowns & Bridges (fa-teeth-open)
  - Teeth Whitening (fa-star)
- **ID**: `#services`

### 9. Special Offer Banner (Optional - vSilver+)
- **Layout**: Full-width promotional banner
- **Content**: "30% Off First Visit" or similar promotion
- **CTA**: "Book Now"

### 10. Pricing Plans Section (Optional - vSilver+)
- **Type**: Owl Carousel with pricing cards
- **Cards**: Different treatment packages with pricing
- **Card Content**: Plan name + Features list + Price + CTA

### 11. Testimonials Section
- **Type**: Owl Carousel
- **Background**: Primary color
- **Content**: Patient testimonials with photos
- **Style**: White text on colored background

### 12. Team/Dentists Section
- **Layout**: 6-column or 4-column grid
- **Card Style**: Photo + Name + Specialty + Social links
- **ID**: `#team`

### 13. Newsletter Section
- **Layout**: Centered subscription form
- **Fields**: Email + Subscribe button

### 14. Footer
- **Layout**: 4-column dark footer
- **Columns**: Quick Links, Popular Links, Contact Info, Social Media
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Jost, Open Sans
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --dental-blue: #0EA5E9; }
  .btn-primary { background: var(--primary); }
  ```
- Modern, clean aesthetic with rounded elements
- Mobile-first responsive design

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Spinner/Loader animation
- TwentyTwenty.js for before/after sliders
- WOW.js for scroll animations
- Owl Carousel 2.3.4
- Tempus Dominus date/time picker
- Full-screen search modal
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - Dental clinic name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #0EA5E9)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)
- `{{operating_hours}}` - Clinic hours

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- dentist {{city}}
- dental clinic South Africa
- teeth whitening {{city}}
- orthodontist Gauteng
- dental care near me

### Long-tail Keywords
- affordable dentist {{city}}
- best dental clinic South Africa
- dental implants near me
- emergency dentist {{city}}
- family dentistry Gauteng

### Meta Tags
- **Title**: {{business_name}} | Professional Dental Care in {{city}}
- **Description**: Expert dental services in {{city}}, South Africa. Gentle care, modern techniques, beautiful smiles. Book your appointment today!
- **Keywords**: dentist, dental, teeth, orthodontist, {{city}}, South Africa, dental care

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Dentist",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "openingHours": "Mo-Fr 08:00-17:00"
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
