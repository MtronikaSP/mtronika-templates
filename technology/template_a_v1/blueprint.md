# Blueprint: Technology Industry (Variant A)

## Meta
- **Industry**: Technology / Digital Agency / IT Services
- **Style**: Modern, Corporate, Tech-forward
- **Color Palette**: Dark header + Gradient accents (Purple/Blue or Orange)
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: SEO Digital Agency

---

## Sections

### 1. Pre-Header Bar
- **Layout**: Contact info bar
- **Content**: Phone ({{phone}}) | Email ({{email}}) | Address ({{city}}) | Social Icons
- **Background**: Dark or primary color

### 2. Header/Navbar
- **Logo**: Left-aligned with tech icon or text logo
- **Navigation**: Home, Services, Projects, About, Contact
- **Style**: Sticky on scroll
- **ID**: `#top`

### 3. Hero Section
- **Headline**: "Digital Solutions for {{city}} Businesses"
- **Subheadline**: AI generates from business_intent (e.g., "Transform your business with technology")
- **CTAs**: "Discover More" (primary) + "Check our FAQs" (secondary)
- **Background**: Gradient or tech-themed image
- **Style**: Full-width with overlay

### 4. Services Grid
- **Layout**: 4-column icon grid
- **Service Items** (examples):
  - Web Development (fa-code)
  - Mobile Apps (fa-mobile-alt)
  - Cloud Solutions (fa-cloud)
  - Cybersecurity (fa-shield-alt)
- **Card Style**: Icon + Title + Short description
- **ID**: `#services`

### 5. Projects/Portfolio Carousel
- **Type**: Owl Carousel
- **Content**: Project screenshots/previews
- **Layout**: 3 visible items, loop enabled
- **ID**: `#projects`

### 6. About/Infos Section
- **Layout**: Left image + Right content
- **Content**: Company story (AI-generated from business_intent)
- **Skill Bars**: Technology expertise percentages
- **CTA**: "Learn More About Us"
- **ID**: `#infos`

### 7. Contact Section
- **Layout**: Split (Google Maps embed left + Form right)
- **Form Fields**: Name, Surname, Email, Subject, Message
- **Submit**: Email to {{email}}
- **ID**: `#contact`

### 8. Footer
- **Layout**: Simple centered
- **Content**: Logo + Copyright + Social icons
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; }
  .btn-primary, .bg-primary { background: var(--primary); }
  ```
- Modern tech aesthetic (gradients, clean lines)
- Mobile-first responsive design
- Smooth scroll navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Preloader animation
- Scroll-to-section navigation
- Owl Carousel 2.3.4 for projects
- Skill bar animations (on scroll)
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation

---

## Variable Placeholders
- `{{business_name}}` - Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #6366F1)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- IT company {{city}}
- software development South Africa
- tech solutions {{city}}
- web development Gauteng
- app development near me

### Long-tail Keywords
- affordable IT services {{city}}
- best software developers South Africa
- custom software near me
- mobile app development {{city}}
- IT support Gauteng

### Meta Tags
- **Title**: {{business_name}} | Innovative Technology Solutions in {{city}}
- **Description**: Cutting-edge technology services in {{city}}, South Africa. Software development, web solutions, IT consulting. Transform your business with technology!
- **Keywords**: IT, software, technology, web development, {{city}}, South Africa, app

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "ProfessionalService",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "areaServed": "South Africa"
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
