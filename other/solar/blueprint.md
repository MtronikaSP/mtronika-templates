# Blueprint: Solar/Renewable Energy Industry

## Meta
- **Industry**: Solar / Renewable Energy / Green Technology
- **Style**: Modern, Eco-Friendly, Professional
- **Color Palette**: Green primary (#32C36C) + Dark (#1A2A36) + Light (#F6F7F8)
- **Target Pages**: 4-12 (vBronze to vGold)
- **Template Source**: Solar Template

---

## Sections

### 1. Navbar
- **Logo**: Solar/Leaf icon + Brand name
- **Navigation**: Home, About, Services, Projects, Team, Contact
- **CTA**: "Get Quote" button
- **Style**: Sticky, green accents

### 2. Hero Carousel
- **Type**: Owl Carousel or Bootstrap Carousel
- **Content**: Full-screen solar energy imagery
- **Headline**: "Clean Energy for {{city}}"
- **Subheadline**: AI generates from business_intent
- **CTAs**: "Learn More" + "Get Quote"
- **ID**: `#hero`

### 3. Features Section
- **Layout**: 3-4 column feature cards
- **Features**:
  - Pioneers in Solar (fa-sun)
  - Sustainable Solutions (fa-leaf)
  - Cost Savings (fa-money-bill-wave)
  - Expert Installation (fa-tools)
- **Style**: Icon + Title + Description

### 4. About Section
- **Layout**: Image + Content
- **Content**: Company story (AI-generated from business_intent)
- **Checkmarks**: Key benefits and values
- **CTA**: "Read More"
- **ID**: `#about`

### 5. Services Section
- **Layout**: Grid of service cards
- **Service Items**:
  - Solar Panels (fa-solar-panel)
  - Wind Turbines (fa-wind)
  - Battery Storage (fa-battery-full)
  - Energy Consulting (fa-chart-line)
  - Installation (fa-wrench)
  - Maintenance (fa-cogs)
- **Card Style**: Icon + Title + Description + Link
- **ID**: `#services`

### 6. Projects Portfolio
- **Type**: Isotope filterable gallery
- **Filters**: All, Solar, Wind, Hydropower, Commercial
- **Layout**: Grid with lightbox
- **Card Style**: Image + Project name + Category
- **ID**: `#projects`

### 7. Quote Request Form
- **Headline**: "Request a Free Quote"
- **Fields**: Name, Email, Phone, Energy Type select, Property Type, Message
- **Submit**: Email to {{email}}
- **Background**: Image background with overlay
- **ID**: `#quote`

### 8. Statistics Counter
- **Stats**: Years Experience, Projects Completed, Clients Served, kWh Generated
- **Style**: CounterUp animation

### 9. Team Section
- **Layout**: 4-column grid
- **Card Style**: Photo + Name + Position + Social links
- **ID**: `#team`

### 10. Testimonials Section
- **Type**: Owl Carousel
- **Content**: Client testimonials
- **Style**: Quote card with green accents

### 11. Footer
- **Layout**: 4-column dark footer
- **Columns**: Address ({{city}}), Quick Links, Project Gallery grid, Newsletter signup
- **Gallery**: Mini photo grid of projects
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Roboto
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --green: #32C36C; --dark: #1A2A36; }
  .btn-primary { background: var(--primary); }
  ```
- Eco-friendly, modern aesthetic
- Mobile-first responsive design
- Green/natural color scheme

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Owl Carousel 2.3.4 for hero/testimonials
- Isotope.js for project filtering
- Lightbox2 for gallery
- WOW.js for scroll animations
- CounterUp.js for statistics
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation

---

## Variable Placeholders
- `{{business_name}}` - Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #32C36C)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- solar panels {{city}}
- solar installation South Africa
- renewable energy {{city}}
- solar power Gauteng
- solar company near me

### Long-tail Keywords
- affordable solar {{city}}
- best solar installers South Africa
- solar battery near me
- loadshedding solution {{city}}
- off-grid solar Gauteng

### Meta Tags
- **Title**: {{business_name}} | Solar Energy Solutions in {{city}}
- **Description**: Power your future with {{business_name}} in {{city}}, South Africa. Expert solar installation, quality panels, reduce electricity costs. Go green today!
- **Keywords**: solar, renewable energy, solar panels, installation, {{city}}, South Africa

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
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
