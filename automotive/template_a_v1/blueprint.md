# Blueprint: Automotive Industry (Variant A)

## Meta
- **Industry**: Automotive / Car Repair
- **Style**: Professional, Trust-building, Modern Auto Theme
- **Color Palette**: Red primary (#D81324) + Dark secondary + White accents
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: CarServ

---

## Sections

### 1. Hero Carousel
- **Headline**: "Quality Auto Care in {{city}}"
- **Subheadline**: AI generates from business_intent (e.g., "Expert repairs you can trust")
- **CTA**: "Get A Quote" → #booking
- **Background**: 2 slides with car service images (Picsum seed)
- **ID**: `#header-carousel`

### 2. Quick Features (3 items)
- Quality Servicing (fa-cog)
- Expert Workers (fa-users)
- Modern Equipment (fa-tools)
**Layout**: 3-column icon cards with brief descriptions

### 3. About Section
- **Left**: Overlapping images with "{{years_experience}}+ Years" badge
- **Right**: Company story (AI-generated from business_intent)
- **Features**: Numbered list (Professional Technicians, Fair Pricing, etc.)
- **CTA**: "Read More" → #services

### 4. Facts/Stats Counter
- Years Experience
- Expert Technicians
- Satisfied Clients
- Complete Projects
**Background**: Dark with CounterUp animation

### 5. Services Section
- **Layout**: Vertical pill tabs (left) + Content panel (right)
- **Service Items**:
  - Diagnostic Test
  - Engine Servicing
  - Tires Replacement
  - Oil Changing
- Each tab shows image + description
- **ID**: `#services`

### 6. Booking Form
- **Layout**: Split (Left testimonial quote + Right form)
- **Fields**: Name, Email, Service Select dropdown, Date picker, Special Request
- **Submit**: Email to {{email}}
- **Background**: Primary/Secondary gradient

### 7. Team Section
- **Layout**: 4-column grid
- **Card Style**: Image + Name + Role + Social icons overlay
- **Hoverable**: Social icons appear on hover

### 8. Testimonials Carousel
- **Type**: Owl Carousel
- **Items**: Customer reviews with circular profile images
- **Content**: Quote text + Name + Role

### 9. Footer
- **Column 1**: Address ({{city}}, South Africa), Contact info
- **Column 2**: Opening Hours grid
- **Column 3**: Services quick links
- **Column 4**: Newsletter subscription form
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Barlow, Ubuntu
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; }
  .btn-primary { background: var(--primary); }
  ```
- Mobile-first responsive design
- Smooth scroll navigation
- Dark theme elements with red accents

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- WOW.js animations
- CounterUp.js for statistics
- Owl Carousel 2.3.4 for testimonials
- Tempus Dominus date picker for booking
- WhatsApp float button (bottom-right sticky, links to {{whatsapp}})
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - Client business name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)
- `{{years_experience}}` - Years in business (default: 10)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- car repair {{city}}
- auto mechanic near me
- car service center South Africa
- vehicle maintenance {{city}}
- automotive repair Gauteng

### Long-tail Keywords
- affordable car repairs {{city}}
- trusted auto mechanic South Africa
- car diagnostic services near me
- brake repair {{city}}
- engine service Gauteng

### Meta Tags
- **Title**: {{business_name}} | Expert Car Repairs & Auto Services in {{city}}
- **Description**: Professional automotive repair and maintenance in {{city}}, South Africa. Trusted mechanics, fair prices, quality service. Book your appointment today!
- **Keywords**: car repair, auto mechanic, vehicle service, {{city}}, South Africa, automotive

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "AutoRepair",
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
