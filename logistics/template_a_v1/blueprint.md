# Blueprint: Logistics Industry (Variant A)

## Meta
- **Industry**: Logistics / Transport / Cargo
- **Style**: Corporate, Professional, Trust-building
- **Color Palette**: Primary Orange (#F15A24 implied/customizable) + Dark Blue/Black + White
- **Target Pages**: 5-8 (vBronze/vSilver)
- **Template Source**: FASTER

---

## Sections

### 1. Topbar
- **Layout**: split (Contact info left, Social icons right)
- **Content**: Phone ({{phone}}) | Email ({{email}})
- **Style**: Dark background, white text

### 2. Navbar
- **Logo**: Truck Icon + "Faster" (or Brand Name)
- **Navigation**: Home, About, Service, Price, Pages (Dropdown), Contact
- **CTA**: "Get A Quote" button (Primary color)
- **Style**: Light background, sticky capability

### 3. Hero Section (Header)
- **Type**: Jumbotron / Large Header
- **Headlines**: "Safe & Faster", "Logistics Services"
- **Feature**: Shipment Tracking Input Form (Track & Trace)
- **Background**: Image background
- **ID**: `#home`

### 4. About Section
- **Layout**: Image Left + Content Right
- **Image Feature**: "25+ Years Experience" overlay box
- **Content**: "Trusted & Faster Logistic Service Provider", Description (AI generated)
- **Video**: Modal popup trigger button
- **ID**: `#about`

### 5. Quote Request & Counters
- **Layout**: Split Section
- **Left Side**: "Request A Free Quote" text + 3 Counters (Experts, Clients, Projects)
- **Right Side**: Quote Form (Name, Email, Service Select)
- **Background**: Secondary/Gray background
- **ID**: `#quote`

### 6. Services Section
- **Layout**: 4-column Grid
- **Service Items**:
  - Air Freight (fa-plane)
  - Ocean Freight (fa-ship)
  - Land Transport (fa-truck)
  - Cargo Storage (fa-store)
- **Card Style**: Icon box header + Description + "Read More" link
- **ID**: `#services`

### 7. Features Section
- **Headline**: "Why Choose Us"
- **Layout**: Image Left + Content Right
- **List**: Icon list (Best In Industry, Emergency Services, 24/7 Support)
- **CTA**: "Learn More" button

### 8. Pricing Plan
- **Layout**: 3-column Grid
- **Packages**: Basic, Premium, Business
- **Card Design**: Price header (Circle/Box) + Feature List + "Order Now" button
- **ID**: `#pricing`

### 9. Team Section
- **Headline**: "Meet Our Delivery Team"
- **Layout**: 4-column Grid
- **Card**: Image + Name/Designation overlay + Social links
- **ID**: `#team`

### 10. Testimonials
- **Headline**: "Our Clients Say"
- **Type**: Owl Carousel
- **Card Style**: Quote icon + User Image + Name + Review text

### 11. Blog Section
- **Headline**: "Latest From Blog"
- **Layout**: 2-column Grid
- **Card**: Image with Date Badge + Author/Category meta + Title + Excerpt + Read More
- **ID**: `#blog`

### 12. Footer
- **Layout**: 2-Column Main + Copyright Bar
- **Col 1**: Get In Touch (Address, Phone, Email, Socials) & Quick Links
- **Col 2**: Newsletter Signup input
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.4.1 (CDN or local)
- FontAwesome 5.10.0
- Google Fonts: Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; }
  .text-primary { color: var(--primary) !important; }
  .bg-primary { background-color: var(--primary) !important; }
  .btn-primary { background-color: var(--primary); border-color: var(--primary); }
  ```
- **Responsive**: Mobile-first design

## JavaScript Requirements
- jQuery 3.4.1
- Bootstrap Bundle
- Owl Carousel (Testimonials)
- CounterUp (Statistics)
- Waypoints
- Contact Form Validation
- Video Modal logic
- WhatsApp float button (bottom-right, links to {{whatsapp}})

---

## Variable Placeholders
- `{{business_name}}` - Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City/Address location
- `{{brand_colour}}` - Hex color code (default: #FF4800 or template default)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- logistics {{city}}
- transport company South Africa
- courier services {{city}}
- freight Gauteng
- delivery near me

### Long-tail Keywords
- affordable courier {{city}}
- best logistics South Africa
- shipping near me
- trucking {{city}}
- warehouse services Gauteng

### Meta Tags
- **Title**: {{business_name}} | Reliable Logistics & Transport in {{city}}
- **Description**: Trusted logistics and transport solutions in {{city}}, South Africa. Fast, safe, and reliable delivery services. Your cargo, our priority!
- **Keywords**: logistics, transport, courier, freight, {{city}}, South Africa, delivery

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
