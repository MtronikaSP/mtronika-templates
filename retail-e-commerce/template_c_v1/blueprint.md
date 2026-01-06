# Blueprint: Retail E-Commerce Industry (Variant C - Fashion/Believe)

## Meta
- **Industry**: Retail / Fashion E-Commerce
- **Style**: Modern, Trendy, Fashion-Forward
- **Color Palette**: Blue/Dark Blue primary + Magenta secondary + White backgrounds
- **Target Pages**: 4-12 (vBronze to vGold)
- **Template Source**: Believe

---

## Sections

### 1. Header
- **Top Bar**: Phone ({{phone}}) + Email ({{email}}) + Offers ("Free Shipping") + Login/Register links
- **Navbar**: Logo + Navigation (Home, Shop, Blog, Contact) + Search icon + Cart/Wishlist icons
- **Mega Menu**: Dropdown with subcategories and featured products carousel

### 2. Hero Slider
- **Type**: Owl Carousel
- **Slides**: Promotional fashion slides (Men's, Women's collections)
- **Content**: Seasonal promotions + "Shop Now" CTA
- **ID**: `#hero`

### 3. Category Banners
- **Layout**: 3-column grid
- **Categories**: Men, Women, Accessories
- **Card Style**: Image with overlay text + CTA

### 4. Products Section
- **Layout**: Tabbed interface with product grids
- **Tabs**: Featured, New Arrivals, Best Sellers
- **Product Grid**: Owl Carousel grids within tabs
- **Product Cards**: Image + Hover icons (Wishlist, Compare, Quick View) + Price + Add to Cart
- **Style**: Fade/hover effects on products
- **ID**: `#products`

### 5. Promotional Banner
- **Layout**: Full-width promotional banner
- **Content**: Featured brand/collection spotlight
- **CTA**: "Shop Collection"

### 6. Brands Carousel
- **Type**: Owl Carousel
- **Content**: Partner/Brand logos
- **Style**: Grayscale with color on hover

### 7. Blog Preview (Optional - vSilver+)
- **Layout**: 3-column blog cards
- **Card Style**: Image + Date + Title + Excerpt
- **CTA**: "Read More"

### 8. Footer
- **Layout**: 4-column
- **Columns**:
  - About Us + Store info
  - Quick Links (Shop, Blog, Contact, FAQ)
  - Customer Service (Returns, Shipping, Policies)
  - Newsletter subscription
- **Social**: Facebook, Twitter, Instagram, Pinterest
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.x or 5.x (CDN)
- FontAwesome 6.x
- Google Fonts: Raleway, Roboto Slab, Playfair Display
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --blue: #2563EB; --magenta: #D946EF; }
  .btn-primary { background: var(--primary); }
  ```
- Modern, trendy aesthetic
- Mobile-first responsive design
- Product hover effects

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap Bundle
- Owl Carousel 2.3.4 (heavily used)
- PrettyPhoto or GLightbox for image lightbox
- Mega menu functionality
- Bootstrap tabs for product filtering
- WhatsApp float button (bottom-right, links to {{whatsapp}})

---

## Variable Placeholders
- `{{business_name}}` - Store name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #2563EB)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- online shop {{city}}
- fashion store South Africa
- clothing {{city}}
- boutique Gauteng
- shop online near me

### Long-tail Keywords
- affordable clothes {{city}}
- best online fashion South Africa
- women's wear near me
- designer clothing {{city}}
- trending fashion Gauteng

### Meta Tags
- **Title**: {{business_name}} | Shop Fashion Online in {{city}}
- **Description**: Explore amazing fashion at {{business_name}} in {{city}}, South Africa. Stylish clothing, great prices, fast delivery. Shop your style today!
- **Keywords**: fashion, online shop, clothing, boutique, {{city}}, South Africa, style

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "ClothingStore",
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
