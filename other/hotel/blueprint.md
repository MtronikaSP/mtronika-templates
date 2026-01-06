# Blueprint: Hotel/Hospitality Industry

## Meta
- **Industry**: Hotel / Hospitality / Lodging
- **Style**: Luxurious, Elegant, Welcoming
- **Color Palette**: Orange primary (#FEA116) + Dark (#0F172B) + Light (#F1F8FF)
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Hotel Template

---

## Sections

### 1. Navbar
- **Layout**: Dark sticky navbar
- **Logo**: Hotel name/icon
- **Navigation**: Home, About, Rooms, Services, Contact
- **CTA**: "Book Now" button
- **Style**: Transparent on hero, solid on scroll

### 2. Hero Carousel
- **Slides**: Luxurious hotel images
- **Caption**: "Discover A Luxurious Stay in {{city}}"
- **CTAs**: "Explore" + "Book Room"
- **Style**: Full-screen with overlay

### 3. Booking Form Bar
- **Layout**: Horizontal inline form
- **Fields**: Check-in date, Check-out date, Adults select, Children select
- **CTA**: "Check Availability"
- **Style**: Floating or positioned below hero

### 4. About Section
- **Layout**: Text content + 4-image grid
- **Statistics**: CounterUp (Rooms, Staff, Happy Clients)
- **Content**: Hotel story (AI-generated from business_intent)
- **ID**: `#about`

### 5. Rooms Section
- **Layout**: Grid of room cards
- **Card Content**: Room image + Name + Price per night + Star rating + Amenities icons (Bed, Bath, WiFi)
- **CTA**: "View Details" per room
- **ID**: `#rooms`

### 6. Video Section
- **Layout**: Full-width with text overlay
- **Content**: "Luxury Living" headline + Play button
- **Modal**: Opens YouTube/video modal on click

### 7. Services Section
- **Layout**: Grid of service cards
- **Service Items**: Spa, Gym, Pool, Restaurant, Events, Concierge
- **Card Style**: Icon + Title + Hover effect
- **ID**: `#services`

### 8. Testimonials Carousel
- **Type**: Owl Carousel
- **Content**: Guest reviews with avatar + name + rating
- **Style**: Card layout

### 9. Team Section
- **Layout**: Staff profile cards
- **Card Style**: Photo + Name + Position + Social overlay on hover

### 10. Newsletter Section
- **Layout**: Centered subscription form
- **Fields**: Email + Subscribe button
- **Background**: Light color

### 11. Footer
- **Layout**: Multi-column
- **Columns**: Company info + Contact details + Services links
- **Map**: Optional small map
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Heebo, Montserrat
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --dark: #0F172B; }
  .btn-primary { background: var(--primary); }
  ```
- Luxurious, elegant aesthetic
- Mobile-first responsive design
- Smooth transitions and hover effects

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Tempus Dominus Bootstrap 4 datepicker
- CounterUp.js for statistics
- Owl Carousel 2.3.4 for testimonials
- Video modal (YouTube integration)
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Booking form validation

---

## Variable Placeholders
- `{{business_name}}` - Hotel name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #FEA116)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- hotel {{city}}
- accommodation South Africa
- guest house {{city}}
- lodge Gauteng
- bed and breakfast near me

### Long-tail Keywords
- affordable hotel {{city}}
- best accommodation South Africa
- luxury lodge near me
- boutique hotel {{city}}
- weekend getaway Gauteng

### Meta Tags
- **Title**: {{business_name}} | Premium Accommodation in {{city}}
- **Description**: Experience exceptional hospitality at {{business_name}} in {{city}}, South Africa. Comfortable rooms, excellent service, unforgettable stays. Book now!
- **Keywords**: hotel, accommodation, guest house, lodge, {{city}}, South Africa

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Hotel",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  }
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
