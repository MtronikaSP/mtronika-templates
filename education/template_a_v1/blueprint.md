# Blueprint: Education Industry (Variant A)

## Meta
- **Industry**: Education / School / Training
- **Style**: Modern, Friendly, Professional
- **Color Palette**: Purple/Pink gradient accent + White + Light backgrounds
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: EduWell

---

## Sections

### 1. Header/Navbar
- **Layout**: Logo image left + Navigation right
- **Navigation**: Home, Services, Courses, Testimonials, Contact
- **Style**: Sticky on scroll, white background
- **ID**: `#top`

### 2. Hero/Banner Section
- **Layout**: Split (Left content + Right illustration)
- **Left Content**: Welcome text + Headline + Gradient CTA button
- **Right**: Educational illustration/image
- **Headline**: "Quality Education in {{city}}"
- **CTA**: "Get Started" → #courses

### 3. Services Carousel
- **Type**: Owl Carousel slider
- **Service Items** (icon cards):
  - Useful Learning Tricks (fa-lightbulb)
  - Creative Teaching Ideas (fa-palette)
  - Goal-Oriented Training (fa-bullseye)
  - Modern Technology (fa-laptop)
- **ID**: `#services`

### 4. Courses Section
- **Layout**: Left sidebar tab menu + Right content area
- **Tab Items**: Different course categories
- **Content**: Course details, price, duration, certificates info
- **CTA**: "Subscribe Now" button
- **ID**: `#courses`

### 5. Promotional CTA
- **Layout**: Full-width banner
- **Content**: Special offer (e.g., "50% OFF First Month")
- **Style**: Gradient background with illustration
- **CTA**: White button

### 6. Testimonials Section
- **Type**: Owl Carousel
- **Content**: Student/Parent quotes with names + titles
- **Style**: Quote icon, card layout
- **ID**: `#testimonials`

### 7. Contact Section
- **Layout**: Google Maps embed + Contact info cards + Contact form
- **Info Cards**: Phone, Mobile, Address
- **Form Fields**: Name, Email, Message
- **CTA**: Gradient submit button
- **ID**: `#contact-section`

### 8. Footer
- **Layout**: Centered, minimal
- **Content**: Social icons row + Copyright
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.x or 5.x (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; }
  .btn-gradient { background: linear-gradient(135deg, var(--primary), #FF6B9D); }
  ```
- Purple/pink gradient theme
- Mobile-first responsive design
- Smooth scroll navigation
- Gradient buttons and borders

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap Bundle
- Scroll-to-section navigation
- Owl Carousel 2.3.4 for services/testimonials
- Lightbox integration
- Tab system for courses
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation

---

## Variable Placeholders
- `{{business_name}}` - School/Institution name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #8B5CF6)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- school {{city}}
- learning center near me
- education South Africa
- tuition {{city}}
- training courses Gauteng

### Long-tail Keywords
- affordable education {{city}}
- best schools South Africa
- online courses near me
- tutoring {{city}}
- skills development Gauteng

### Meta Tags
- **Title**: {{business_name}} | Quality Education & Learning in {{city}}
- **Description**: Premier educational institution in {{city}}, South Africa. Quality teaching, modern facilities, proven results. Enroll today for a brighter future!
- **Keywords**: education, school, learning, courses, {{city}}, South Africa, training

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "EducationalOrganization",
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
