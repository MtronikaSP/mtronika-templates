# Blueprint: Retail E-Commerce Industry (Variant B - Fashion)

## Meta
- **Industry**: Retail / Fashion E-Commerce
- **Style**: Minimalist, Elegant, High-End Fashion
- **Color Palette**: Black/White minimalist + Accent colors
- **Target Pages**: 4-12 (vBronze to vGold)
- **Template Source**: Karl

---

## Sections

### 1. Side Category Menu (Optional)
- **Type**: Off-canvas collapsible menu
- **Trigger**: Hamburger icon
- **Categories**: Collapsible list (Women, Men, Kids, Accessories, Footwear)
- **Style**: Slide-in from left

### 2. Header
- **Top Header**: Logo (centered or left) + Cart dropdown (with item preview) + Menu trigger
- **Main Header**: Social links + Main navigation + Helpline phone number
- **Cart Dropdown**: Mini cart with product previews
- **Style**: Clean, minimal

### 3. Top Discount Banner
- **Layout**: 3-column flex bar
- **Content**: Free Shipping notice, Discount codes, Special offers
- **Style**: Light background, centered text

### 4. Hero Slider
- **Type**: Owl Carousel
- **Slides**: 3 fullscreen fashion images
- **Content**: Subtitle + Headline + "Shop Now" CTA
- **Animations**: Entrance animations on content
- **ID**: `#hero`

### 5. Category Banners
- **Layout**: 2-column full-width
- **Cards**: Category image with overlay
- **Content**: Category name + Sale percentage + CTA
- **Categories**: Men's Fashion, Women's Fashion (or custom)

### 6. Quick View Modal
- **Type**: Bootstrap Modal
- **Content**: Product image + Title + Rating + Price + Description + Quantity + Add to Cart + Wishlist
- **ID**: `#quickview`

### 7. New Arrivals/Products Section
- **Layout**: Isotope filterable grid
- **Filter Menu**: All, Women, Men, Accessories, Shoes, Kids
- **Product Cards**: Image + Quick view button + Price + Title + Add to Cart
- **Animation**: fadeInUp on scroll
- **ID**: `#products`

### 8. Promotional Banner
- **Layout**: Full-width image background
- **Content**: Product spotlight + Hot badge + Free shipping + Price + CTA
- **Style**: Overlay text on image

### 9. Testimonials Section
- **Type**: Owl Carousel
- **Layout**: Centered single testimonial
- **Content**: Quote + Customer photo + Name + Location

### 10. Footer
- **Layout**: 4-column
- **Columns**:
  - Logo + Copyright
  - About links (About, Blog, FAQ, Returns, Contact)
  - Account links (My Account, Shipping, Policies)
  - Newsletter subscription form
- **Footer Bottom**: Social icons (Pinterest, Facebook, Twitter, Instagram)
- **Copyright**: © 2026 {{business_name}}. Designed by Mtronika.

---

## CSS Requirements
- Bootstrap 4.x or 5.x (CDN)
- Themify Icons or FontAwesome 6.x
- Google Fonts: Poppins, Playfair Display
- Brand color override:
  ```css
  :root { --primary: {{brand_colour}}; --dark: #1A1A1A; }
  .btn-primary { background: var(--primary); }
  ```
- Minimalist black/white aesthetic
- Elegant typography
- Mobile-first responsive design
- Product hover effects

## JavaScript Requirements
- jQuery 3.6.x
- Bootstrap Bundle
- Owl Carousel 2.3.4 for hero/testimonials
- Isotope.js for product filtering
- WOW.js for scroll animations
- Quick view modal functionality
- Cart dropdown interactions
- Side menu toggle
- WhatsApp float button (bottom-right, links to {{whatsapp}})

---

## Variable Placeholders
- `{{business_name}}` - Store name
- `{{phone}}` - Phone number
- `{{email}}` - Email address
- `{{city}}` - City location
- `{{brand_colour}}` - Hex color code (default: #1A1A1A)
- `{{whatsapp}}` - WhatsApp number (27xxxxxxxxx format)

---

## SEO Keywords (South Africa Focus)
### Primary Keywords
- fashion store {{city}}
- clothing South Africa
- online fashion {{city}}
- designer clothes Gauteng
- boutique near me

### Long-tail Keywords
- affordable fashion {{city}}
- trendy clothing South Africa
- women's fashion near me
- men's fashion {{city}}
- latest styles Gauteng

### Meta Tags
- **Title**: {{business_name}} | Trendy Fashion & Clothing in {{city}}
- **Description**: Discover the latest fashion trends at {{business_name}} in {{city}}, South Africa. Quality clothing, great prices, stylish looks. Shop now!
- **Keywords**: fashion, clothing, boutique, style, {{city}}, South Africa, trendy

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
