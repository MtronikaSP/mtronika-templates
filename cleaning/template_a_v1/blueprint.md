# Blueprint: Cleaning Services Industry (Variant A)

## Meta
- **Industry**: Cleaning Services / Janitorial
- **Style**: Clean, Fresh, Professional
- **Color Palette**: Blue primary (#89CBEB) + White + Dark accents (#1F1F1F)
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Cleaning Services

---

## Sections

### 1. Header
- **Layout**: Logo left + Login/Register links + Search icon + Mobile menu toggle
- **Mobile Menu**: Overlay full-screen sidebar navigation
- **Style**: White background, sticky on scroll

### 2. Hero/Banner Section
- **Headline**: "Professional Cleaning in {{city}}"
- **Subheadline**: AI generates from business_intent
- **CTAs**: "Contact Us" button + "Watch Video" play icon
- **Background**: High-quality cleaning service image
- **ID**: `#banner`

### 3. Services Carousel
- **Type**: Carousel slider
- **Service Items**:
  - Tile & Grout Cleaning
  - Carpet Cleaning
  - Window Cleaning
  - Deep House Cleaning
- **Card Style**: Image + Title + Description
- **ID**: `#services`

### 4. About Section
- **Layout**: Text content left/center + Side image
- **Content**: Company story (AI-generated from business_intent)
- **CTA**: "Read More" button
- **ID**: `#about`

### 5. Why Choose Us Section
- **Layout**: Stats counters + Feature highlights
- **Stats**: Happy Clients, Awards Won, Years Experience
- **CTA**: "Get A Quote" button
- **Background**: Light blue gradient

### 6. Team Section
- **Layout**: Alternating rows (Image left/right)
- **Card Style**: Large photo + Name + Position + Description + Social icons
- **Style**: Staggered layout for visual interest

### 7. Newsletter Section
- **Layout**: Full-width centered
- **Content**: Headline + Email subscription form
- **Background**: Blue (#89CBEB)

### 8. Footer
- **Layout**: Dark background with columns
- **Column 1**: Contact info (Address, Phone, Email)
- **Column 2**: Location description
- **Column 3**: Small Google Maps embed
- **Column 4**: Quick contact form
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.6.0 or 5.x (CDN)
- FontAwesome 6.x
- Google Fonts: Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --blue: #89CBEB; }
  .btn-primary { background: var(--primary); }
  ```
- Clean, fresh aesthetic
- Mobile-first responsive design
- Full-screen overlay navigation for mobile

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap Bundle
- Owl Carousel or Slick for services
- FancyBox for image lightbox
- mCustomScrollbar (optional)
- Video modal/popup for hero
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation

---

## Variable Placeholders
- `{{business_name}}` - Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #89CBEB)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- cleaning services {{city}}
- house cleaning near me
- office cleaning South Africa
- domestic cleaning {{city}}
- commercial cleaning Gauteng

### Long-tail Keywords
- affordable cleaning services {{city}}
- trusted cleaners South Africa
- deep cleaning near me
- carpet cleaning {{city}}
- window cleaning Gauteng

### Meta Tags
- **Title**: {{business_name}} | Professional Cleaning Services in {{city}}
- **Description**: Expert cleaning services in {{city}}, South Africa. Residential and commercial cleaning, deep cleaning, and more. Sparkling results guaranteed!
- **Keywords**: cleaning, house cleaning, office cleaning, {{city}}, South Africa, domestic

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "HomeAndConstructionBusiness",
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
