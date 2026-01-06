# Blueprint: Consulting Industry (Variant B)

## Meta
- **Industry**: Consulting / Corporate / Insurance Services
- **Style**: Corporate, Professional, Modern
- **Color Palette**: Cyan/Teal primary (#5EDCD4) + Blue secondary (#186BE8) + Clean white backgrounds
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Insurance/Corporate Template

---

## Sections

### 1. Navbar
- **Layout**: Sticky top navigation
- **Logo**: Left-aligned text/image logo
- **Navigation**: Home, About, Services, Testimonials, News, Contact
- **CTA**: "Call Us Now" button with phone number
- **Mobile**: Hamburger toggler

### 2. Hero Section
- **Layout**: Split (Background illustration + Floating form card)
- **Headline**: "Professional Consulting in {{city}}"
- **Subheadline**: AI generates from business_intent
- **Form Card**: "Get a Quote" lead generation form
- **Form Fields**: Name, Email, Phone, Service Type, Message
- **ID**: `#hero`

### 3. Services Tabs
- **Layout**: Interactive horizontal tabs
- **Tab Items**: Different service categories (e.g., Business, Finance, Strategy, Operations)
- **Tab Content**: Icon + Description + CTA link
- **Style**: Icons change on active tab

### 4. Best Features Grid
- **Layout**: 4-column feature grid
- **Features**:
  - Expert Support (fa-headset)
  - Fast Processing (fa-bolt)
  - Flexible Plans (fa-sliders)
  - Secure & Confidential (fa-shield-alt)
- **Style**: Icon + Title + Description

### 5. Testimonials Carousel
- **Type**: Bootstrap Carousel or Owl Carousel
- **Content**: Client testimonials with circular branding
- **Style**: Quote card with professional styling

### 6. Recent News/Blog
- **Layout**: 3-column blog cards
- **Card Content**: Image + Date badge + Category + Title + Excerpt
- **CTA**: "Read More" per post

### 7. Partners Section
- **Layout**: Horizontal logo carousel
- **Content**: Client/Partner logos
- **Style**: Grayscale with color on hover

### 8. Contact & Footer
- **Contact Info**: Address ({{city}}), Phone ({{phone}}), Email ({{email}})
- **Newsletter**: Email subscription form
- **Columns**: About, Quick Links, Services, Newsletter
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Raleway, Open Sans
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --teal: #5EDCD4; --blue: #186BE8; }
  .btn-primary { background: var(--primary); }
  ```
- Corporate, clean aesthetic
- Mobile-first responsive design
- Smooth scroll navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Dynamic navbar (background change on scroll)
- Tab switching for services
- Testimonial carousel (Bootstrap or Owl)
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation
- Scroll animations

---

## Variable Placeholders
- `{{business_name}}` - Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #5EDCD4)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- consultant {{city}}
- business consulting South Africa
- management consulting {{city}}
- advisory services Gauteng
- strategy consultant near me

### Long-tail Keywords
- affordable consulting {{city}}
- best business consultants South Africa
- financial consulting near me
- HR consulting {{city}}
- marketing consultant Gauteng

### Meta Tags
- **Title**: {{business_name}} | Expert Business Consulting in {{city}}
- **Description**: Professional consulting services in {{city}}, South Africa. Strategy, management, and growth solutions for your business. Let's achieve success together!
- **Keywords**: consulting, business, strategy, advisor, {{city}}, South Africa, management

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
