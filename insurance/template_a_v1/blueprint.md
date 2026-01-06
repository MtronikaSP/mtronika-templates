# Blueprint: Insurance Industry (Variant A)

## Meta
- **Industry**: Insurance / Finance / Financial Services
- **Style**: Corporate, Trustworthy, Professional
- **Color Palette**: Cyan primary (#00B2CE) + Dark Blue (#304254) + Light backgrounds
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Insurance Template

---

## Sections

### 1. Top Bar
- **Layout**: Address left + Social icons right
- **Background**: Dark or primary color

### 2. Navbar
- **Layout**: Sticky header
- **Logo**: Left-aligned
- **Navigation**: Home, About, Products, Services, Contact
- **CTA**: "Call Us Now" button with phone number
- **Style**: White background, shadow on scroll

### 3. Hero Slider
- **Type**: FlexSlider or Bootstrap Carousel
- **Content**: Insurance-themed images with text overlays
- **Headline**: "Trusted Insurance in {{city}}"
- **CTAs**: "Get a Quote" + "Learn More"

### 4. Intro & Quote Form
- **Layout**: Split (Welcome text left + Floating form right)
- **Content**: Company intro (AI-generated from business_intent)
- **Form Card**: "Get a Free Quote"
- **Form Fields**: Name, Email, Phone, Insurance Type select, Message
- **ID**: `#quote`

### 5. Products/Services Tabs
- **Layout**: Vertical tabs with content panels
- **Tab Items**: 
  - Home Insurance
  - Auto Insurance
  - Life Insurance
  - Travel Insurance
- **Tab Content**: Icon + Description + Benefits list
- **ID**: `#products`

### 6. Services Grid
- **Layout**: 4-6 column icon grid
- **Features**:
  - Expert Advice (fa-user-tie)
  - Fast Claims (fa-file-invoice)
  - 24/7 Support (fa-headset)
  - Competitive Rates (fa-percentage)
- **Card Style**: Icon + Title + Short description

### 7. Testimonials Section
- **Layout**: Tabbed reviews with client photos
- **Content**: Customer testimonials
- **Style**: Professional card layout

### 8. Recent News/Blog
- **Layout**: 3-column blog post grid
- **Card Style**: Image + Date + Title + Excerpt
- **CTA**: "Read More"

### 9. Partners Carousel
- **Type**: Owl Carousel
- **Content**: Insurance partner/provider logos
- **Style**: Grayscale with color on hover

### 10. Contact & Map Section
- **Layout**: Google Maps embed + Contact details
- **Content**: Address ({{city}}), Phone ({{phone}}), Email ({{email}})
- **Form**: Quick contact form

### 11. Footer
- **Layout**: Multi-column dark footer
- **Columns**: Agent Details, Quick Links, Services, Contact Info
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Themify Icons (optional)
- Google Fonts: Open Sans, Lato
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --cyan: #00B2CE; --dark-blue: #304254; }
  .btn-primary { background: var(--primary); }
  ```
- Corporate, trustworthy aesthetic
- Mobile-first responsive design
- Sticky navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- FlexSlider or Bootstrap Carousel for hero
- Easy Responsive Tabs for products
- Owl Carousel 2.3.4 for partners
- Google Maps API integration
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation

---

## Variable Placeholders
- `{{business_name}}` - Insurance company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #00B2CE)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- insurance {{city}}
- insurance broker South Africa
- life insurance {{city}}
- car insurance Gauteng
- health insurance near me

### Long-tail Keywords
- affordable insurance {{city}}
- best insurance South Africa
- insurance quotes near me
- business insurance {{city}}
- home insurance Gauteng

### Meta Tags
- **Title**: {{business_name}} | Trusted Insurance Solutions in {{city}}
- **Description**: Comprehensive insurance coverage in {{city}}, South Africa. Life, car, health, and business insurance. Get your free quote today!
- **Keywords**: insurance, broker, life insurance, car insurance, {{city}}, South Africa

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "InsuranceAgency",
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
