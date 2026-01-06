# Blueprint: Healthcare/Medical Industry (Variant A)

## Meta
- **Industry**: Healthcare / Medical Clinic
- **Style**: Clean, Professional, Trustworthy
- **Color Palette**: Medical blue primary + White + Light gray accents
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Klinik

---

## Sections

### 1. Topbar
- **Layout**: Location + Operating Hours + Phone + Social Icons
- **Background**: Light gray
- **Phone**: Highlighted with icon

### 2. Header/Navbar
- **Logo**: Left-aligned with clinic icon
- **Navigation**: Home, About, Services, Pages dropdown, Contact
- **CTA**: "Book Appointment" button → #appointment
- **Style**: Sticky on scroll, white background

### 3. Hero Section
- **Layout**: Split (Stats counters left + Image carousel right)
- **Stats**: Number of Doctors, Staff, Patients Served
- **Carousel**: Medical specialty images (Cardiology, Neurology, Pulmonary)
- **Headline**: "Quality Healthcare in {{city}}"
- **ID**: `#hero`

### 4. About Section
- **Layout**: Dual image layout (overlapping) + Content
- **Content**: Trust-building text + Bullet checklist
- **Checklist Items**: Qualified Doctors, Emergency Care, Modern Facilities
- **CTA**: "Read More About Us"

### 5. Services Grid
- **Layout**: 6-card grid (3x2)
- **Service Items**:
  - Cardiology (fa-heartbeat)
  - Pulmonary (fa-lungs)
  - Neurology (fa-brain)
  - Orthopedics (fa-bone)
  - Dental Surgery (fa-tooth)
  - Laboratory (fa-flask)
- **Card Style**: Icon + Title + Description + "Learn More" link
- **ID**: `#services`

### 6. Features/Why Choose Us
- **Layout**: Full-width banner with 4 feature icons
- **Features**: Expert Doctors, Quality Services, Free Consultation, 24/7 Support
- **Background**: Primary blue color
- **Style**: Alternating icon + text blocks

### 7. Team/Doctors Section
- **Layout**: 4-column grid
- **Card Style**: Photo + Doctor Name + Specialty + Social links
- **Hover Effect**: Social icons overlay
- **ID**: `#doctors`

### 8. Appointment Form
- **Layout**: Split (Info block left + Form right)
- **Left Info**: Address, Phone, Email, Operating hours
- **Form Fields**: Name, Email, Phone, Department select, Date picker, Message
- **Submit**: Email to {{email}}
- **ID**: `#appointment`

### 9. Testimonials Carousel
- **Type**: Owl Carousel
- **Content**: Patient review quote + Name + Condition treated
- **Style**: Card with subtle shadow

### 10. Footer
- **Layout**: 4-column
- **Column 1**: Address ({{city}}, South Africa), Map link
- **Column 2**: Services quick links
- **Column 3**: Quick navigation links
- **Column 4**: Newsletter subscription
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Open Sans, Roboto
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --medical-blue: #0EA5E9; }
  .btn-primary { background: var(--primary); }
  ```
- Clean medical aesthetic (lots of white space)
- Mobile-first responsive design
- Smooth scroll navigation

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Spinner/Loader animation on page load
- WOW.js animations
- CounterUp.js for stats
- Owl Carousel 2.3.4
- Tempus Dominus date/time picker for appointments
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation (HTML5 required + custom)

---

## Variable Placeholders
- `{{business_name}}` - Clinic/Hospital name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #0EA5E9)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)
- `{{operating_hours}}` - Clinic hours (default: "Mon-Fri: 8:00 AM - 6:00 PM")

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- doctor {{city}}
- medical clinic near me
- healthcare South Africa
- GP {{city}}
- clinic Gauteng

### Long-tail Keywords
- affordable medical care {{city}}
- trusted doctor South Africa
- family clinic near me
- medical checkup {{city}}
- specialist consultation Gauteng

### Meta Tags
- **Title**: {{business_name}} | Quality Healthcare & Medical Services in {{city}}
- **Description**: Trusted medical clinic in {{city}}, South Africa. Professional doctors, quality care, convenient appointments. Your health is our priority!
- **Keywords**: doctor, clinic, healthcare, medical, {{city}}, South Africa, GP

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "MedicalClinic",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "openingHours": "Mo-Fr 08:00-18:00"
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
