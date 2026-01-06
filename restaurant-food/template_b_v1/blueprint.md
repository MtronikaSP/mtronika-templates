# Blueprint: Restaurant/Food Industry (Variant B - Fast Food)

## Meta
- **Industry**: Restaurant / Fast Food / Quick Service
- **Style**: Bold, Energetic, Appetizing
- **Color Palette**: Orange/Red primary (#FFBE33) + Dark overlays
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Feane

---

## Sections

### 1. Hero Area
- **Background**: Full-screen image with dark overlay
- **Contains**: Header + Hero Slider

### 2. Header/Navbar
- **Logo**: Text-based restaurant name
- **Navigation**: Home, Menu, About, Book Table
- **User Options**: User icon, Cart (with item count), Search
- **CTA**: "Order Online" button with orange background
- **Style**: Dark, integrated with hero

### 3. Hero Slider
- **Type**: Bootstrap Carousel
- **Slides**: 3 slides with food images
- **Content**: Headline + Description + "Order Now" CTA
- **Indicators**: Bottom carousel dots
- **ID**: `#customCarousel1`

### 4. Offers Section
- **Layout**: 2-column promotional cards
- **Cards**:
  - "Special Thursday" - 20% Off
  - "Weekend Special" - 15% Off
- **Card Content**: Title + Discount percentage + "Order Now" button with cart icon
- **Style**: Image backgrounds with overlay

### 5. Menu/Food Section
- **Layout**: Isotope/filterable grid
- **Filter Menu**: All, Burgers, Pizza, Pasta, Fries (or custom categories)
- **Product Cards**: Image + Title + Description + Price + Add to Cart icon
- **Style**: Hover effects on cards
- **ID**: `#menu`

### 6. About Section
- **Layout**: 2-column (Image + Content)
- **Content**: Restaurant story (AI-generated from business_intent)
- **CTA**: "Read More"
- **ID**: `#about`

### 7. Book Table Section
- **Headline**: "Reserve Your Table"
- **Form Fields**: Name, Phone, Email, Number of Persons, Date picker, Time picker
- **CTA**: "Book A Table" button
- **Background**: Dark or pattern
- **ID**: `#book-table`

### 8. Testimonials Carousel
- **Type**: Owl Carousel
- **Content**: Customer reviews with photos
- **Card Style**: Quote + Client image + Name
- **ID**: `#testimonials`

### 9. Footer
- **Layout**: 4-column layout
- **Columns**:
  - About Us brief info
  - Quick Links (Menu, About, Book Table)
  - Contact Info (Address {{city}}, Phone {{phone}}, Email {{email}})
  - App Download (optional: Play Store, App Store badges)
- **Social**: Facebook, Twitter, LinkedIn, Instagram icons
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.x or 5.x (CDN)
- FontAwesome 6.x
- Google Fonts: Poppins, Roboto
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --orange: #FFBE33; }
  .btn-primary { background: var(--primary); }
  ```
- Bold, appetizing aesthetic
- Dark overlays on images
- Mobile-first responsive design
- Card hover effects

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap Bundle
- Owl Carousel 2.3.4 for testimonials
- Isotope.js for menu filtering
- Nice Select for styled dropdowns (optional)
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Cart interaction animations

---

## Variable Placeholders
- `{{business_name}}` - Restaurant name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #FFBE33)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- fast food {{city}}
- restaurant South Africa
- takeaway {{city}}
- food delivery Gauteng
- burger near me

### Long-tail Keywords
- best fast food {{city}}
- pizza delivery South Africa
- quick meals near me
- food order {{city}}
- cheap eats Gauteng

### Meta Tags
- **Title**: {{business_name}} | Delicious Fast Food in {{city}}
- **Description**: Fresh, fast, and delicious food at {{business_name}} in {{city}}, South Africa. Order now for quick delivery or takeaway!
- **Keywords**: fast food, restaurant, takeaway, delivery, {{city}}, South Africa, burgers

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "FastFoodRestaurant",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "servesCuisine": "Fast Food"
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
