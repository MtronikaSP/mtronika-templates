# Blueprint: Education Industry (Variant B - Kindergarten/Preschool)

## Meta
- **Industry**: Education / Kindergarten / Preschool / Daycare
- **Style**: Playful, Colorful, Kid-Friendly
- **Color Palette**: Colorful multi-color (Blue, Green, Yellow, Orange) with rounded elements
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Kider

---

## Sections

### 1. Navbar
- **Logo**: Playful icon + School name
- **Navigation**: Home, About, Classes, Facilities, Team, Contact
- **CTA**: "Join Us" pill button
- **Style**: Sticky, rounded edges, colorful

### 2. Hero Carousel
- **Type**: Owl Carousel
- **Content**: Fullscreen images of children/school activities
- **Headline**: "Quality Early Learning in {{city}}"
- **CTAs**: "Learn More" + "Our Classes"
- **Style**: Colorful, playful typography
- **ID**: `#hero`

### 3. Facilities Section
- **Layout**: 4-column colored icon cards
- **Facilities**:
  - School Transport (fa-bus, color: blue)
  - Safe Playground (fa-child, color: green)
  - Healthy Meals (fa-utensils, color: yellow)
  - Positive Learning (fa-book-reader, color: orange)
- **Card Style**: Rounded, colored backgrounds

### 4. About Section
- **Layout**: Left content + Right circular images layout
- **Content**: School story (AI-generated from business_intent)
- **Features**: Headline + Description + Founder info/quote
- **CTA**: "Read More"
- **ID**: `#about`

### 5. Call To Action Banner
- **Layout**: Full-width with image
- **Content**: "Become A Teacher" or "Join Our Team"
- **CTA**: "Get Started"
- **Background**: Illustrated/Pattern background

### 6. Classes/Courses Section
- **Layout**: 6-card grid
- **Card Content**: Circular image + Class name + Teacher info + Age range + Time + Capacity + Price pill
- **Style**: Rounded cards, colorful accents
- **ID**: `#classes`

### 7. Enrollment/Appointment Form
- **Layout**: Left form + Right image
- **Headline**: "Enroll Your Child"
- **Form Fields**: Guardian Name, Email, Child Name, Child Age, Message
- **Submit**: Email to {{email}}
- **ID**: `#enroll`

### 8. Team/Teachers Section
- **Layout**: 3-column grid
- **Card Style**: Circular photo + Name + Position + Social links
- **Style**: Rounded, friendly design
- **ID**: `#team`

### 9. Testimonials Carousel
- **Type**: Owl Carousel
- **Content**: Parent testimonials with photos
- **Style**: Rounded cards, colorful quotes

### 10. Footer
- **Layout**: Dark 4-column footer
- **Columns**: Get In Touch (Address, Phone, Email), Quick Links, Photo Gallery grid, Newsletter signup
- **Gallery**: Small photo grid (Instagram-style)
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Heebo, Inter, Lobster Two (for playful headings)
- Brand color override:
  ```css
  :root { 
    --primary: {{brand_colour}}; 
    --blue: #3498db; --green: #2ecc71; 
    --yellow: #f1c40f; --orange: #e67e22; 
  }
  ```
- Colorful, kid-friendly aesthetic
- Rounded/circular design elements
- Mobile-first responsive design

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Spinner/Loader animation
- WOW.js for scroll animations
- Owl Carousel 2.3.4
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - School/Kindergarten name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #3498db)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- kindergarten {{city}}
- preschool South Africa
- daycare {{city}}
- nursery school Gauteng
- early childhood education near me

### Long-tail Keywords
- affordable preschool {{city}}
- best kindergarten South Africa
- creche near me
- toddler education {{city}}
- playschool Gauteng

### Meta Tags
- **Title**: {{business_name}} | Quality Early Childhood Education in {{city}}
- **Description**: Nurturing kindergarten in {{city}}, South Africa. Safe, fun learning environment for your little ones. Enroll today for a bright start!
- **Keywords**: kindergarten, preschool, daycare, nursery, {{city}}, South Africa, early learning

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Preschool",
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
