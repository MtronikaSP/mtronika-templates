# Blueprint: Retail E-Commerce Industry (Variant A - Fruitables/Grocery)

## Meta
- **Industry**: Retail / E-Commerce / Grocery
- **Style**: Fresh, Organic, Friendly
- **Color Palette**: Green primary (#81C408) + Orange/Yellow accents + White/Light backgrounds
- **Target Pages**: 4-7 (vBronze/vSilver)
- **Template Source**: Fruitables

---

## Sections

### 1. Header
- **Top Bar**: Contact info + Privacy/Terms links
- **Navbar**: Logo + Navigation (Home, Shop, Pages, Contact) + Search trigger + Cart/User icons
- **Style**: White background, sticky

### 2. Hero Carousel
- **Content**: Hero images of products (vegetables/fruits/products)
- **Overlay**: Search box
- **Headline**: "Fresh Products from {{city}}"
- **ID**: `#hero`

### 3. Features Bar
- **Layout**: 4-column icon row
- **Features**:
  - Free Shipping (fa-truck)
  - Secure Payment (fa-lock)
  - 30 Day Return (fa-undo)
  - 24/7 Support (fa-headset)

### 4. Products Shop Section
- **Layout**: Tabbed interface with product grid
- **Tabs**: All Products, Category 1, Category 2, Category 3
- **Product Cards**: Image + Title + Price + "Add to Cart" button
- **ID**: `#shop`

### 5. Promotional Banners
- **Layout**: 3-column promotional cards
- **Content**: Special offers/featured categories
- **Style**: Image background with overlay text

### 6. Featured Products Carousel
- **Type**: Owl Carousel
- **Content**: Featured/bestseller products
- **Card Style**: Image + Rating stars + Price

### 7. Banner/Promo Section
- **Layout**: Full-width promotional banner
- **Content**: Featured product with detailed pricing
- **CTA**: "Buy Now" button
- **Background**: Product image

### 8. Bestsellers Grid
- **Layout**: Product grid
- **Card Style**: Image + Star rating + Title + Price
- **ID**: `#bestsellers`

### 9. Statistics Counter
- **Stats**: Happy Customers, Quality Products, Certifications, Products Available
- **Style**: CounterUp animation

### 10. Testimonials Carousel
- **Type**: Owl Carousel
- **Content**: Customer reviews
- **Style**: Card with avatar + quote + name

### 11. Footer
- **Layout**: Multi-column
- **Columns**: Company info, Why People Like Us, Shop Info, Account, Contact
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 5.2.2 (CDN)
- FontAwesome 6.x + Bootstrap Icons
- Google Fonts: Open Sans, Raleway
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --green: #81C408; }
  .btn-primary { background: var(--primary); }
  ```
- Fresh, organic aesthetic
- Mobile-first responsive design
- Product hover effects

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap 5 Bundle
- Owl Carousel 2.3.4 for products/testimonials
- Lightbox for product images
- Search modal functionality
- CounterUp.js for statistics
- WhatsApp float button (bottom-right, links to {{whatsapp}})
- Add to Cart interactions (visual feedback)

---

## Variable Placeholders
- `{{business_name}}` - Store name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #81C408)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- online shop {{city}}
- buy online South Africa
- e-commerce {{city}}
- online store Gauteng
- shop near me

### Long-tail Keywords
- affordable shopping {{city}}
- best online store South Africa
- free delivery near me
- discount shopping {{city}}
- online deals Gauteng

### Meta Tags
- **Title**: {{business_name}} | Shop Online in {{city}} - Quality Products, Great Prices
- **Description**: Discover amazing products at {{business_name}} in {{city}}, South Africa. Wide selection, competitive prices, fast delivery. Start shopping today!
- **Keywords**: online shop, e-commerce, buy online, {{city}}, South Africa, shopping

### Schema.org Markup
```json
{
  "@context": "https://schema.org",
  "@type": "Store",
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
