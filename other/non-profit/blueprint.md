# Blueprint: Non-Profit/Charity Industry

## Meta
- **Industry**: Non-Profit / Charity / NGO
- **Style**: Warm, Compassionate, Trustworthy
- **Color Palette**: Green primary (#5BC1AC) + Blue-Grey secondary (#5A6F80) + Dark footer (#44525D)
- **Target Pages**: 4-12 (vBronze to vGold)
- **Template Source**: Kind Heart Charity

---

## Sections

### 1. Navbar
- **Logo**: Charity name + Heart/Hand icon
- **Navigation**: Home, About, Causes, Volunteer, Donate, News, Contact
- **CTA**: "Donate Now" button (prominent)
- **Style**: Sticky on scroll

### 2. Hero Slider
- **Type**: Full-screen Bootstrap Carousel
- **Content**: Impactful images with captions
- **Headline**: "Making a Difference in {{city}}"
- **CTAs**: "Discover More" + "Donate Now"
- **ID**: `#hero`

### 3. Features Section
- **Layout**: 3-column feature blocks
- **Features**:
  - Become a Volunteer (fa-hand-holding-heart)
  - Make a Donation (fa-donate)
  - Our Impact (fa-globe-africa)
- **Style**: Image background with hover effects

### 4. About Section
- **Headline**: "Our Story"
- **Layout**: Image + Text content
- **Content**: Organization story (AI-generated from business_intent)
- **Statistics**: Counter stats (People Helped, Volunteers, Projects, Countries)
- **ID**: `#about`

### 5. Make an Impact CTA
- **Layout**: Full-width banner
- **Content**: Inspiring message
- **CTAs**: "Volunteer" + "Donate"
- **Background**: Impactful image

### 6. Volunteer Form Section
- **Headline**: "Become a Volunteer"
- **Form Fields**: Name, Email, Phone, Skills, Availability, Message
- **Submit**: Email to {{email}}
- **ID**: `#volunteer`

### 7. Causes/Projects Section
- **Headline**: "Featured Causes"
- **Layout**: Grid of cause cards
- **Card Content**: Image + Title + Description + Donation progress bar + Goal amount + Raised amount
- **CTA**: "Donate" per cause
- **ID**: `#causes`

### 8. Donation Form
- **Headline**: "Make a Donation"
- **Form Fields**: Amount options (preset + custom), Name, Email, Phone, Frequency (One-time/Monthly)
- **Submit**: Payment integration or email
- **Style**: Prominent, easy to complete
- **ID**: `#donate`

### 9. News/Blog Section
- **Headline**: "Latest News"
- **Layout**: 3-column blog cards
- **Card Style**: Image + Date + Title + Excerpt
- **CTA**: "Read More"
- **ID**: `#news`

### 10. Testimonials Carousel
- **Headline**: "What People Say"
- **Type**: Owl Carousel
- **Content**: Supporter/Beneficiary testimonials
- **ID**: `#testimonials`

### 11. Contact Section
- **Layout**: Contact form + Info
- **Form Fields**: Name, Email, Subject, Message
- **Submit**: Email to {{email}}
- **Info**: Address ({{city}}), Phone ({{phone}}), Email ({{email}})
- **ID**: `#contact`

### 12. Footer
- **Layout**: Multi-column dark footer
- **Columns**: Quick Links, Contact Info, Recent Causes, Newsletter signup
- **Social**: Facebook, Twitter, Instagram, LinkedIn
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- Bootstrap Icons + FontAwesome 6.x
- Google Fonts: Metropolis (custom) or Open Sans
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --green: #5BC1AC; --grey: #5A6F80; }
  .btn-primary { background: var(--primary); }
  .progress-bar { background: var(--primary); }
  ```
- Warm, compassionate aesthetic
- Mobile-first responsive design
- Progress bars for donation goals

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- jQuery Sticky for navbar
- Smooth scroll navigation
- CounterUp.js for statistics
- Owl Carousel 2.3.4 for testimonials
- Donation form with frequency toggles
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Form validation

---

## Variable Placeholders
- `{{business_name}}` - Organization name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City/Region location
- `{{brand_colour}}` - Hex color code (default: #5BC1AC)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- charity {{city}}
- non-profit South Africa
- NGO {{city}}
- donate Gauteng
- volunteer near me

### Long-tail Keywords
- community support {{city}}
- charitable organization South Africa
- volunteer opportunities near me
- donate to charity {{city}}
- social impact Gauteng

### Meta Tags
- **Title**: {{business_name}} | Making a Difference in {{city}}
- **Description**: Join {{business_name}} in making a positive impact in {{city}}, South Africa. Support our cause, donate, volunteer. Together we can change lives!
- **Keywords**: charity, non-profit, NGO, donate, {{city}}, South Africa, volunteer

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "NGO",
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
