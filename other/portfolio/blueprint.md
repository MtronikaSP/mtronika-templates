# Blueprint: Personal Portfolio Industry

## Meta
- **Industry**: Personal Portfolio / Freelancer / Creative Professional
- **Style**: Clean, Modern, Personal Branding
- **Color Palette**: Multi-color theme defined in CSS variables + Dark accents
- **Target Pages**: Single-page scrolling (vBronze)
- **Template Source**: Portfolio Template

---

## Sections

### 1. Navbar
- **Style**: Custom sticky navbar
- **Logo**: Personal name/brand
- **Navigation**: Home, About, Services, Portfolio, Testimonials, Contact
- **Mobile**: Hamburger menu toggle
- **Scroll Spy**: Active section highlighting

### 2. Hero Section
- **Layout**: Full-height with overlay
- **Content**: Name + Title/Role + Tagline
- **CTA**: "Visit My Works" or "Contact Me"
- **Background**: Professional photo or pattern
- **ID**: `#home`

### 3. About Section
- **Headline**: "Who Am I?"
- **Layout**: Image + Text content
- **Content**: Personal bio (AI-generated from business_intent)
- **Highlights**: Skills, experience, personality
- **ID**: `#about`

### 4. Services Section
- **Headline**: "What I Do?"
- **Layout**: 4-column service cards
- **Service Items**:
  - Service 1 (e.g., Web Design)
  - Service 2 (e.g., Development)
  - Service 3 (e.g., Consulting)
  - Service 4 (e.g., Support)
- **Card Style**: Icon + Title + Description
- **ID**: `#services`

### 5. Portfolio Section
- **Headline**: "What I Did?"
- **Layout**: Grid of portfolio cards
- **Card Style**: Image + Overlay caption with project name
- **Lightbox**: Click to view full project
- **ID**: `#portfolio`

### 6. Pricing Section (Optional - vSilver+)
- **Headline**: "How Much I Charge?"
- **Layout**: 3-tier pricing cards
- **Tiers**: Basic, Standard, Premium
- **Card Content**: Price + Features list + CTA

### 7. Hire Me CTA
- **Layout**: Full-width banner
- **Content**: "Want to Work With Me?"
- **CTA**: "Let's Talk" button
- **Background**: Accent color or pattern

### 8. Testimonials Section
- **Layout**: Client feedback cards or carousel
- **Content**: Quote + Client name + Company
- **ID**: `#testimonials`

### 9. Blog Section (Optional - vSilver+)
- **Headline**: "Recent Posts"
- **Layout**: 3-column blog cards
- **Card Style**: Image + Date + Title + Excerpt

### 10. Contact Section
- **Headline**: "How Can You Reach Me?"
- **Layout**: Contact form
- **Form Fields**: Name, Email, Subject, Message
- **Submit**: Email to {{email}}
- **Info**: Phone ({{phone}}), Email ({{email}}), Location ({{city}})
- **ID**: `#contact`

### 11. Footer
- **Layout**: Centered, minimal
- **Content**: Copyright + Social links
- **Social**: LinkedIn, GitHub, Twitter, Dribbble (or custom)
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.x or 5.x (CDN)
- Themify Icons or FontAwesome 6.x
- Google Fonts: Open Sans, Baloo Paaji or Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; }
  .btn-primary { background: var(--primary); }
  ```
- Clean, personal branding aesthetic
- Multi-color theme support (sections can have different accents)
- Mobile-first responsive design

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap Bundle
- Scroll Spy for navigation
- Smooth scroll navigation
- Affix/Sticky navigation behavior
- Hamburger menu toggle
- Portfolio lightbox
- WhatsApp float button (bottom-right, links to {{whatsapp}})

---

## Variable Placeholders
- `{{business_name}}` - Personal name or brand
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #6366F1)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- portfolio {{city}}
- freelancer South Africa
- creative professional {{city}}
- designer Gauteng
- developer near me

### Long-tail Keywords
- web designer {{city}}
- graphic designer South Africa
- freelance developer near me
- creative portfolio {{city}}
- UX designer Gauteng

### Meta Tags
- **Title**: {{business_name}} | Creative Portfolio in {{city}}
- **Description**: Discover the work of {{business_name}} in {{city}}, South Africa. Creative professional delivering quality design and development. Let's create together!
- **Keywords**: portfolio, freelancer, designer, developer, {{city}}, South Africa, creative

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "{{business_name}}",
  "telephone": "{{phone}}",
  "email": "{{email}}",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "{{city}}",
    "addressCountry": "ZA"
  },
  "jobTitle": "Creative Professional"
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
