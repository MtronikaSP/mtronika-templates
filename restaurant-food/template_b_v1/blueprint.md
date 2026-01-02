# Restaurant/Food Template B - Feane (Fast Food)

## Template Overview
- **Theme**: Fast Food Restaurant
- **Template Name**: Feane
- **Primary Color**: Orange/Red (#ffbe33)
- **Fonts**: System fonts with custom styling
- **Framework**: Bootstrap 4

## Page Sections

### 1. Hero Area
- **Class**: `hero_area`
- **Background**: Full-screen image (`hero-bg.jpg`)
- **Contains**: Header + Slider

### 2. Header/Navbar
- **Class**: `header_section`
- **Logo**: Text-based "Feane"
- **Navigation**:
  - Home, Menu, About, Book Table
- **User Options**:
  - User icon, Cart (SVG), Search
  - "Order Online" CTA button

### 3. Hero Slider
- **Class**: `slider_section`
- **ID**: `#customCarousel1`
- **Slides**: 3 slides with headline, description, CTA
- **Indicators**: Bottom carousel dots

### 4. Offers Section
- **Class**: `offer_section`
- **Layout**: 2-column promotional cards
- **Content**:
  - "Tasty Thursdays" - 20% Off
  - "Pizza Days" - 15% Off
- **CTA**: "Order Now" with cart SVG icon

### 5. Menu/Food Section
- **Class**: `food_section`
- **Filter Menu**: All, Burger, Pizza, Pasta, Fries
- **Layout**: Isotope/Masonry grid
- **Product Cards**:
  - Image, Title, Description
  - Price + Add to Cart icon
- **Classes**: `.filters_menu`, `.filters-content`

### 6. About Section
- **Class**: `about_section`
- **Layout**: 2-column (image + content)
- **Content**: Heading, description, "Read More" CTA

### 7. Book Table Section
- **Class**: `book_section`
- **Form Fields**: Name, Phone, Email, Persons, Date, Time
- **CTA**: "Book A Table" button

### 8. Client Testimonials
- **Class**: `client_section`
- **Type**: Owl Carousel
- **Cards**: Quote + client image + name

### 9. Footer
- **Class**: `footer_section`
- **Columns**:
  - About Us info
  - Quick Links (Menu, About, Book Table)
  - Contact (Address, Phone, Email)
  - App Download (Play Store, App Store)
- **Social**: Facebook, Twitter, LinkedIn, Instagram
- **Copyright**: Bottom section

## Key Features
- **Isotope Filtering**: Menu filter by food category
- **SVG Cart Icons**: Custom inline SVG for cart
- **Nice Select**: Styled dropdown selects
- **Full-screen Hero**: Background image with overlay

## Dependencies
- Bootstrap 4
- jQuery
- Owl Carousel 2.3.4
- Nice Select
- Isotope (for filtering)
- Font Awesome

## Styling Notes
- Orange/gold accent color (#ffbe33)
- Dark overlay on hero section
- Card-based menu items with hover effects
- Responsive design with mobile hamburger menu
