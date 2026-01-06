# Blueprint: Construction Industry (Variant A)

## Meta
- **Industry**: Construction / Building
- **Style**: Corporate, Professional, Trust-building
- **Color Palette**: Dark radial gradient + Yellow/Gold primary accent
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: WEBUILD

---

## Sections

### 1. Topbar
- **Layout**: 3-column info bar
- **Content**: Office Address | Email ({{email}}) | Phone ({{phone}})
- **Background**: Primary color

### 2. Hero Carousel
- **Headline**: "Building {{city}}'s Future"
- **Subheadline**: AI generates from business_intent
- **CTA**: "Get A Quote" → #appointment
- **Background**: Fullscreen construction site images (Picsum seed)
- **ID**: `#header`

### 3. About Section
- **Left**: Text content with checkmark bullet points (2-column layout)
- **Right**: Offset construction photo + Signature image
- **Content Focus**: Company expertise, years of experience
- **CTA**: "Learn More" → #services

### 4. Services Grid
- **Layout**: 6-card responsive grid (3x2)
- **Service Items**:
  - Building Construction (fa-building)
  - House Renovation (fa-home)
  - Architecture Design (fa-drafting-compass)
  - Interior Design (fa-couch)
  - Fixing & Support (fa-wrench)
  - Painting (fa-paint-roller)
- **Card Style**: Image top + Title + Description + Link
- **ID**: `#services`

### 5. Appointment/Callback Form
- **Headline**: "Request a Callback"
- **Fields**: Name, Phone, Email, Project Type, Message
- **Submit**: Email to {{email}}
- **Background**: Secondary color with pattern overlay

### 6. Portfolio/Projects Gallery
- **Type**: Isotope filterable gallery
- **Filters**: All, Construction, Renovation, Interior
- **Lightbox**: Click to enlarge images
- **Layout**: 3-column masonry grid
- **ID**: `#portfolio`

### 7. Team Section
- **Layout**: 4-column grid
- **Card Style**: Photo + Name + Position
- **Social Icons**: Positioned on side (vertical)

### 8. Testimonials Carousel
- **Type**: Owl Carousel
- **Layout**: Quote card + Large side image of project
- **Content**: Client quote + Name + Company

### 9. Blog Preview (Optional - vSilver+)
- **Layout**: 3-column blog posts grid
- **Card Style**: Thumbnail + Date + Title + Excerpt
- **CTA**: "Read More" per post

### 10. Footer
- **Layout**: Dark radial gradient background
- **Column 1**: Company info + Logo
- **Column 2**: Quick Links
- **Column 3**: Newsletter subscription
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Roboto
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; }
  .bg-primary { background: var(--primary) !important; }
  ```
- Dark radial gradient theme
- Mobile-first responsive design
- Smooth scroll navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Isotope.js for portfolio filtering
- Lightbox2 for gallery
- Owl Carousel 2.3.4
- Tempus Dominus date/time picker
- WOW.js animations
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - Client business name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #FFA500)
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
