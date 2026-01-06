# Blueprint: Farming/Agriculture Industry (Variant A)

## Meta
- **Industry**: Farming / Agriculture / Organic Products
- **Style**: Natural, Fresh, Trustworthy
- **Color Palette**: Green primary + Orange secondary (organic/natural colors)
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: FarmFresh

---

## Sections

### 1. Topbar
- **Layout**: 3-column (Phone left + Logo center + Social right)
- **Social Icons**: Twitter, Facebook, LinkedIn, Instagram
- **Background**: White/Light

### 2. Navbar
- **Logo**: Text logo with leaf icon
- **Navigation**: Home, About, Services, Products, Contact
- **Style**: Green sticky navbar
- **Mobile**: Collapsible menu

### 3. Hero Carousel
- **Content**: Fullscreen farm/agriculture images
- **Headline**: "Fresh from {{city}} Farms"
- **Subheadline**: AI generates from business_intent
- **CTAs**: "Explore" + "Contact Us"
- **ID**: `#header-carousel`

### 4. Banner Cards
- **Layout**: 2-column feature cards
- **Content**: 
  - "Organic Vegetables" with pattern background
  - "Fresh Produce" with pattern background
- **Style**: Decorative borders/patterns

### 5. About Section
- **Layout**: Left bordered image + Right content
- **Content**: Farm story (AI-generated from business_intent)
- **Badges**: "100% Organic" + "Award Winning" icons
- **CTA**: "Learn More"
- **ID**: `#about`

### 6. Statistics Counter
- **Layout**: Full-width primary background
- **Stats**: Years Experience, Farm Specialists, Completed Projects, Happy Clients
- **Style**: CounterUp animation

### 7. Services Section
- **Layout**: 5-card grid
- **Service Items**:
  - Fresh Vegetables (fa-carrot)
  - Fresh Fruits (fa-apple-alt)
  - Healthy Produce (fa-leaf)
  - Delivery Service (fa-truck)
  - Farming Plans (fa-seedling)
- **CTA**: "Contact Us" button
- **ID**: `#services`

### 8. Features Section
- **Layout**: 4-column with central feature card
- **Features**: 100% Organic, Award Winning, Modern Farming, 24/7 Support
- **Background**: Primary green
- **Center Card**: Featured product image

### 9. Products Carousel
- **Type**: Owl Carousel
- **Card Content**: Product image + Name + Price + Cart/View buttons
- **Style**: E-commerce style product cards
- **ID**: `#products`

### 10. Testimonials Section
- **Type**: Owl Carousel
- **Background**: Farm image with overlay
- **Content**: Customer reviews with white text
- **Style**: Quote with customer name/role

### 11. Team Section
- **Layout**: 3-column grid
- **Card Style**: Photo + Name + Position
- **Social**: Vertical side social icons column

### 12. Blog Section (Optional - vSilver+)
- **Layout**: 3-column blog cards
- **Card Style**: Image with hover overlay + Title + Date
- **CTA**: "Read More" link

### 13. Footer
- **Layout**: Primary background with 3 columns + Newsletter sidebar
- **Columns**: Get In Touch, Quick Links, Popular Links
- **Newsletter**: Email subscription
- **Copyright Bar**: Dark footer with copyright text
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Roboto
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --green: #28A745; --orange: #FD7E14; }
  .btn-primary { background: var(--primary); }
  ```
- Natural, organic aesthetic
- Mobile-first responsive design
- Smooth scroll navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- CounterUp.js for statistics
- Owl Carousel 2.3.4 for products/testimonials
- WOW.js for scroll animations
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - Farm/Company name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City/Region location
- `{{brand_colour}}` - Hex color code (default: #28A745)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- farm {{city}}
- agriculture South Africa
- farming supplies {{city}}
- fresh produce Gauteng
- farming equipment near me

### Long-tail Keywords
- organic farm {{city}}
- buy fresh produce South Africa
- agricultural services near me
- farm equipment {{city}}
- livestock farming Gauteng

### Meta Tags
- **Title**: {{business_name}} | Quality Farming & Agriculture in {{city}}
- **Description**: Leading agricultural business in {{city}}, South Africa. Fresh produce, quality farming, sustainable practices. From our farm to your table!
- **Keywords**: farm, agriculture, produce, farming, {{city}}, South Africa, organic

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
