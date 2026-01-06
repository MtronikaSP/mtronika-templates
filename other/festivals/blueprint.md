# Blueprint: Event/Festival Industry

## Meta
- **Industry**: Events / Festivals / Concerts
- **Style**: Bold, Energetic, Exciting
- **Color Palette**: Yellow primary (#F8CB2E) + Orange secondary (#EE5007) + Dark backgrounds
- **Target Pages**: 4-7 (vBronze/vSilver, single-page scrolling)
- **Template Source**: Festava

---

## Sections

### 1. Navbar
- **Style**: Sticky transparent-to-dark on scroll
- **Logo**: Event/Festival name
- **Navigation**: Home, About, Artists, Schedule, Tickets, Contact
- **CTA**: "Get Tickets" button

### 2. Hero Section
- **Type**: Full-screen with video background (optional)
- **Content**: Event name/branding centered
- **Info**: Date + Location + Venue
- **CTAs**: "Get Tickets" + "Learn More"
- **Background**: HTML5 Video or Image with overlay
- **ID**: `#hero`

### 3. About Section
- **Layout**: Text content + Image with overlay info
- **Content**: Event description (AI-generated from business_intent)
- **Highlights**: Key features/attractions
- **CTA**: "Read More"
- **ID**: `#about`

### 4. Artists/Performers Section
- **Layout**: Grid of artist cards
- **Card Content**: Image + Name + Genre + Social links
- **Hover Effect**: Reveal additional details
- **Style**: Dark cards with accent colors
- **ID**: `#artists`

### 5. Schedule Section
- **Layout**: Table or timeline format
- **Content**: Color-coded or image-background cells for different events/times
- **Columns**: Time, Stage, Performer, Description
- **Style**: Easy to scan, mobile-responsive
- **ID**: `#schedule`

### 6. Pricing/Tickets Section
- **Layout**: 2-3 pricing cards
- **Ticket Types**: Early Bird, Standard, VIP
- **Card Content**: Price + Features list + Savings badge + "Buy Now" CTA
- **Style**: Highlighted popular option
- **ID**: `#tickets`

### 7. Contact Section
- **Layout**: Tabbed (Contact Form vs Google Map)
- **Form Fields**: Name, Email, Subject, Message
- **Submit**: Email to {{email}}
- **Map**: Venue location embed
- **ID**: `#contact`

### 8. Footer
- **Top Bar**: Social media links (prominent)
- **Columns**: Quick Links, Contact Info, Copyright
- **Social**: Facebook, Instagram, Twitter, YouTube
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x
- Google Fonts: Outfit, Poppins
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --yellow: #F8CB2E; --orange: #EE5007; }
  .btn-primary { background: var(--primary); }
  ```
- Bold, energetic aesthetic
- Dark theme with vibrant accents
- Mobile-first responsive design

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Video background support (HTML5)
- Smooth scroll navigation
- Click scroll with active section highlighting
- Tab switching for contact section
- WhatsApp float button (bottom-right, links to {{whatsapp}})

---

## Variable Placeholders
- `{{business_name}}` - Event/Festival name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City/Venue location
- `{{brand_colour}}` - Hex color code (default: #F8CB2E)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)
- `{{event_date}}` - Event date

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- events {{city}}
- concerts South Africa
- festival {{city}}
- live music Gauteng
- entertainment near me

### Long-tail Keywords
- music festival {{city}}
- best events South Africa
- live shows near me
- concert tickets {{city}}
- festival lineup Gauteng

### Meta Tags
- **Title**: {{business_name}} | Epic Events & Entertainment in {{city}}
- **Description**: Experience unforgettable events with {{business_name}} in {{city}}, South Africa. Live music, festivals, incredible performances. Get your tickets now!
- **Keywords**: events, concerts, festivals, entertainment, {{city}}, South Africa

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Event",
  "name": "{{business_name}}",
  "location": {
    "@type": "Place",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "{{city}}",
      "addressCountry": "ZA"
    }
  },
  "organizer": {
    "@type": "Organization",
    "telephone": "{{phone}}",
    "email": "{{email}}"
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
