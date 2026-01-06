# Blueprint: Restaurant/Food Industry (Variant A)

## Meta
- **Industry**: Restaurant / Fine Dining / Food Service
- **Style**: Elegant, Dark, Upscale
- **Color Palette**: Dark/Black background + Gold/Amber accents (#CDA45E)
- **Target Pages**: 4-12 (vBronze to vGold, single-page scrolling)
- **Template Source**: Restaurantly

---

## Sections

### 1. Topbar
- **Layout**: Fixed top bar
- **Content**: Phone ({{phone}}) + Operating Hours + Language/Social icons
- **Background**: Dark, transparent overlay

### 2. Header/Navbar
- **Layout**: Fixed header below topbar
- **Logo**: Restaurant name with decorative styling
- **Navigation**: Home, About, Menu, Specials, Events, Gallery, Contact
- **CTA**: "Book a Table" button
- **Style**: Transparent on hero, solid on scroll

### 3. Hero Section
- **Type**: Full-height with video or image background
- **Headline**: "Welcome to {{business_name}}"
- **Subheadline**: AI-generated tagline (elegant, upscale)
- **CTAs**: "Our Menu" + "Book a Table"
- **Video Button**: Play button for promo video (optional)
- **ID**: `#hero`

### 4. About Section
- **Layout**: Left content + Right image
- **Content**: Restaurant story (AI-generated from business_intent)
- **Checklist**: Signature dishes or philosophy points
- **CTA**: "Learn More"
- **ID**: `#about`

### 5. Why Us Section
- **Layout**: 3 numbered feature boxes
- **Features**: Quality Ingredients, Master Chefs, Unique Experience
- **Style**: Numbered circles with descriptions

### 6. Menu Section
- **Layout**: Tabbed menu with filter categories
- **Tabs**: All, Starters, Main Course, Desserts, Drinks
- **Menu Items**: 2-column layout with image, name, price, ingredients
- **Style**: Elegant font, gold accents
- **ID**: `#menu`

### 7. Specials Section
- **Layout**: Vertical tab menu left + Large image/content right
- **Content**: Daily/Weekly specials with descriptions
- **ID**: `#specials`

### 8. Events Section
- **Type**: Swiper carousel
- **Event Cards**: Birthday Parties, Private Events, Custom Catering
- **Card Content**: Event type + Description + Pricing
- **ID**: `#events`

### 9. Reservation Form
- **Headline**: "Book a Table"
- **Fields**: Name, Email, Phone, Date picker, Time picker, Number of Guests, Special Requests
- **Submit**: Email to {{email}}
- **Background**: Dark with gold accents
- **ID**: `#book-a-table`

### 10. Testimonials Carousel
- **Type**: Swiper carousel
- **Content**: Customer reviews with photos and quotes
- **Style**: Elegant card with light text on dark
- **ID**: `#testimonials`

### 11. Gallery Section
- **Layout**: 8-image lightbox grid
- **Content**: Food/Restaurant photos
- **Lightbox**: GLightbox integration
- **ID**: `#gallery`

### 12. Chefs Section (Optional - vSilver+)
- **Layout**: 3-column cards
- **Card Style**: Photo + Name + Position + Social icons overlay
- **ID**: `#chefs`

### 13. Contact Section
- **Layout**: Info columns + Map + Form
- **Info**: Address ({{city}}), Operating Hours, Phone ({{phone}}), Email ({{email}})
- **Map**: Google Maps embed
- **Form**: Quick contact form
- **ID**: `#contact`

### 14. Footer
- **Layout**: Centered minimal
- **Content**: Social icons row + Copyright
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Playfair Display, Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --gold: #CDA45E; }
  .btn-primary { background: var(--primary); border-color: var(--gold); }
  ```
- Dark elegant theme
- Mobile-first responsive design
- Fixed topbar + header

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Swiper.js for events/testimonials
- GLightbox for gallery/video
- Isotope-like filtering for menu (Bootstrap tabs or custom)
- AOS scroll animations
- Tempus Dominus date/time picker for reservations
- WhatsApp float button (bottom-right, links to {{whatsapp}})

---

## Variable Placeholders
- `{{business_name}}` - Restaurant name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #CDA45E)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)
- `{{operating_hours}}` - Restaurant hours (default: "Tue-Sun: 12:00 PM - 10:00 PM")

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- restaurant {{city}}
- dining near me
- food South Africa
- cafe {{city}}
- fine dining Gauteng

### Long-tail Keywords
- best restaurants {{city}}
- family restaurant South Africa
- takeaway near me
- food delivery {{city}}
- romantic dinner Gauteng

### Meta Tags
- **Title**: {{business_name}} | Delicious Dining Experience in {{city}}
- **Description**: Experience exceptional cuisine at {{business_name}} in {{city}}, South Africa. Fresh ingredients, talented chefs, unforgettable flavors. Reserve your table today!
- **Keywords**: restaurant, dining, food, cafe, {{city}}, South Africa, cuisine

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Restaurant",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "openingHours": "Tu-Su 12:00-22:00",
  "servesCuisine": "South African"
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
