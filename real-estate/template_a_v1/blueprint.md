# Blueprint: Real Estate Industry (Variant A)

## Meta
- **Industry**: Real Estate / Property
- **Style**: Modern, Clean, Professional
- **Color Palette**: Teal/Green primary (#00B98E) + White backgrounds
- **Target Pages**: 4-12 (vBronze to vGold)
- **Template Source**: Makaan

---

## Sections

### 1. Navbar
- **Layout**: Transparent on hero, solid on scroll
- **Logo**: Property icon + Brand name
- **Navigation**: Home, About, Properties, Agents, Contact
- **CTA**: "Add Property" button
- **Style**: Sticky, shadow on scroll

### 2. Hero Section
- **Layout**: Split (Left content + Right carousel)
- **Headline**: "Find Your Dream Property in {{city}}"
- **Subheadline**: AI generates from business_intent
- **CTA**: "Get Started" button
- **Carousel**: Property images (Owl Carousel)
- **ID**: `#hero`

### 3. Property Search Bar
- **Layout**: Horizontal inline form
- **Fields**: Keyword input, Property Type select, Location select
- **CTA**: "Search" button
- **Background**: Primary color
- **Position**: Below hero or floating

### 4. Property Types Grid
- **Layout**: 8-category icon cards
- **Categories**: Apartment, Villa, House, Office, Building, Townhouse, Shop, Commercial
- **Card Style**: Icon + Category name + Property count
- **Style**: Hover effect with lift

### 5. About Section
- **Layout**: Left bordered image + Right content
- **Content**: Agency story (AI-generated from business_intent)
- **Checklist**: Key advantages
- **CTA**: "Read More"
- **ID**: `#about`

### 6. Property Listings
- **Layout**: Tabbed interface with property grid
- **Tabs**: Featured, For Sale, For Rent
- **Card Content**: Image + Price badge + Location + Sqft/Bed/Bath icons
- **Cards Per Tab**: 6 properties
- **CTA**: "Browse More Properties"
- **ID**: `#properties`

### 7. Call To Action Banner
- **Layout**: Bordered card with agent image
- **Content**: "Contact With Certified Agent"
- **CTAs**: "Make A Call" ({{phone}}) + "Get Appointment"
- **Style**: Card with border effect

### 8. Agents/Team Section
- **Layout**: 4-column grid
- **Card Style**: Photo + Name + Title + Social icons overlay on hover
- **Content**: Real estate agent profiles
- **ID**: `#agents`

### 9. Testimonials Carousel
- **Type**: Owl Carousel
- **Content**: Client testimonials with quotes and photos
- **Style**: Card layout with subtle shadow

### 10. Footer
- **Layout**: Dark footer with columns
- **Column 1**: Address ({{city}}, South Africa), Contact info
- **Column 2**: Quick Links
- **Column 3**: Services
- **Column 4**: Newsletter subscription
- **Copyright Bar**: Separate dark bar with copyright
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Heebo, Inter
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --teal: #00B98E; }
  .btn-primary { background: var(--primary); }
  ```
- Clean, modern aesthetic
- Mobile-first responsive design
- Transparent navbar effect on hero

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Spinner/Loader animation
- WOW.js for scroll animations
- Owl Carousel 2.3.4 for hero/testimonials
- Bootstrap tabs for property filtering
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Back-to-top button

---

## Variable Placeholders
- `{{business_name}}` - Agency name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #00B98E)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- property {{city}}
- real estate South Africa
- houses for sale {{city}}
- property agents Gauteng
- rental property near me

### Long-tail Keywords
- affordable homes {{city}}
- best real estate agents South Africa
- property listings near me
- investment property {{city}}
- apartments for rent Gauteng

### Meta Tags
- **Title**: {{business_name}} | Find Your Dream Property in {{city}}
- **Description**: Discover the perfect property with {{business_name}} in {{city}}, South Africa. Buy, sell, or rent with trusted agents. Start your property journey today!
- **Keywords**: property, real estate, houses, apartments, {{city}}, South Africa, agents

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "RealEstateAgent",
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
