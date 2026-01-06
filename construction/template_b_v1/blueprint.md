# Blueprint: Construction Industry (Variant B - Painting)

## Meta
- **Industry**: Construction / Painting / Home Services
- **Style**: Bold, Professional, Friendly
- **Color Palette**: Yellow/Gold primary + Dark secondary accents
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: PAINTER

---

## Sections

### 1. Topbar
- **Layout**: Full-width bar
- **Content**: Phone ({{phone}}) + Email ({{email}}) + Social icons
- **Background**: Primary yellow

### 2. Navbar
- **Layout**: Dark navigation bar
- **Logo**: Paint roller icon + Brand name
- **Navigation**: Home, About, Services, Team, Blog, Contact
- **CTA**: "Call Now" sidebar button
- **Style**: Sticky on scroll

### 3. Hero Section
- **Layout**: Primary background with hero image
- **Headline**: "Professional Painting in {{city}}"
- **Subheadline**: AI generates from business_intent
- **CTAs**: "Get A Quote" + "Contact Us"
- **Background**: Hero image with overlay
- **ID**: `#hero`

### 4. About Section
- **Layout**: Dual zigzag layout
- **Block 1**: Welcome content + Image
- **Block 2**: Image + Why Choose Us content
- **Content**: Company story (AI-generated from business_intent)
- **ID**: `#about`

### 5. Services Grid
- **Layout**: 6-card icon grid
- **Service Items**:
  - Regular Painting (fa-paint-roller)
  - Wall Painting (fa-brush)
  - Floor Coating (fa-fill)
  - Graffiti Removal (fa-spray-can)
  - Mildew Removal (fa-tint)
  - Window Washing (fa-square)
- **Card Style**: Icon + Title + Description + Link
- **ID**: `#services`

### 6. Quote Form Section
- **Layout**: Split (Background image left + White form right)
- **Headline**: "Request a Free Quote"
- **Form Fields**: Name, Email, Phone, Service Type, Message
- **Submit**: Email to {{email}}
- **ID**: `#quote`

### 7. Team Section
- **Layout**: 3-column grid
- **Card Style**: Photo + Name + Position
- **Hover Effect**: Social icons overlay on hover

### 8. Testimonials Section
- **Layout**: Split (Primary background + Owl Carousel on right)
- **Content**: Customer reviews with photos and quotes
- **Style**: White text on primary background

### 9. Blog Section (Optional - vSilver+)
- **Layout**: 3-column blog cards
- **Card Style**: Image + Date badge + Title + Excerpt
- **CTA**: "Read More"

### 10. Call To Action Section
- **Headline**: "Do You Have Any Project?"
- **Subheadline**: Encouraging text
- **CTA**: "Get Started" button
- **Background**: Secondary color or pattern

### 11. Footer
- **Layout**: Dark 4-column footer
- **Columns**: About/Address, Quick Links, Services, Newsletter
- **Social Links**: Icon links
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Roboto Condensed, Roboto
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --yellow: #FFD700; --dark: #333; }
  .btn-primary { background: var(--primary); }
  ```
- Bold, friendly aesthetic
- Mobile-first responsive design
- Rounded pill buttons
- Zigzag section layouts

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Owl Carousel 2.3.4 for testimonials
- WOW.js for scroll animations
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #FFD700)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- construction company {{city}}
- building contractors South Africa
- home builders {{city}}
- renovation services near me
- commercial construction Gauteng

### Long-tail Keywords
- affordable house building {{city}}
- trusted construction company South Africa
- residential builders Krugersdorp
- home renovation quotes {{city}}
- construction project management Gauteng

### Meta Tags
- **Title**: {{business_name}} | Professional Construction & Building in {{city}}
- **Description**: Trusted construction company in {{city}}, South Africa. Residential & commercial building, renovations, and project management. Get a free quote today!
- **Keywords**: construction, building, renovation, {{city}}, South Africa, contractors, home builders

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "GeneralContractor",
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
