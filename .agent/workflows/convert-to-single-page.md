---
description: Convert any multi-file template into a single-page HTML with embedded CSS and JavaScript
---

# Template to Single-Page Converter

Use this workflow to convert any template folder into a self-contained, single-page HTML file with all CSS and JavaScript embedded inline.

---

## Prerequisites

Before running this workflow, identify:
1. **Template folder path** (e.g., `templates/construction/template_a_v1`)
2. **Main HTML file** (usually `index.html`)
3. **CSS folder/files** (usually `css/` directory)
4. **JavaScript folder/files** (usually `js/` directory)
5. **Library dependencies** (usually in `lib/` directory)

---

## Phase 1: Analysis

### Step 1.1: Explore Template Structure
```
List the template directory contents to identify:
- All HTML files
- CSS directory and files
- JS directory and files  
- Library dependencies (lib/ folder)
- Asset folders (img/, fonts/)
- Blueprint.md if present
```

### Step 1.2: Read Core Files
```
Read and analyze:
1. index.html - Identify all <link> and <script> tags
2. css/style.css - The custom template styles
3. js/main.js - The custom template JavaScript
4. blueprint.md - For template-specific documentation
```

### Step 1.3: Document Dependencies
Create a list of:
- **Local CSS files** to embed inline
- **Local JS files** to embed inline
- **External libraries** to convert to CDN links
- **Assets** that must remain as relative paths (images, fonts)

---

## Phase 2: CSS Integration

### Step 2.1: Replace Local Library CSS with CDN
Convert local library CSS to CDN equivalents:

| Library | CDN URL |
|---------|---------|
| Bootstrap 5 | `https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/css/bootstrap.min.css` |
| Bootstrap 4 | `https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css` |
| Owl Carousel | `https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.carousel.min.css` |
| Lightbox2 | `https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.4/css/lightbox.min.css` |
| Tempusdominus | `https://cdnjs.cloudflare.com/ajax/libs/tempusdominus-bootstrap-4/5.39.0/css/tempusdominus-bootstrap-4.min.css` |
| Font Awesome 5 | `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.0/css/all.min.css` |
| Bootstrap Icons | `https://cdn.jsdelivr.net/npm/bootstrap-icons@1.4.1/font/bootstrap-icons.css` |
| Animate.css | `https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css` |
| AOS | `https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.css` |

### Step 2.2: Embed Custom CSS
Copy the entire contents of `css/style.css` into a `<style>` tag in the `<head>` section:
```html
<style>
    /* Contents of style.css here */
</style>
```

### Step 2.3: Update CSS Path References
In the embedded CSS, update any relative paths:
- `url(../img/...)` → `url(img/...)` (adjust based on new file location)

---

## Phase 3: JavaScript Integration

### Step 3.1: Replace Local Library JS with CDN
Convert local library JS to CDN equivalents:

| Library | CDN URL |
|---------|---------|
| jQuery | `https://code.jquery.com/jquery-3.4.1.min.js` |
| Bootstrap 5 | `https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/js/bootstrap.bundle.min.js` |
| Bootstrap 4 | `https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/js/bootstrap.bundle.min.js` |
| jQuery Easing | `https://cdnjs.cloudflare.com/ajax/libs/jquery-easing/1.4.1/jquery.easing.min.js` |
| Waypoints | `https://cdnjs.cloudflare.com/ajax/libs/waypoints/4.0.1/jquery.waypoints.min.js` |
| Owl Carousel | `https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/owl.carousel.min.js` |
| Isotope | `https://cdnjs.cloudflare.com/ajax/libs/isotope-layout/3.0.6/isotope.pkgd.min.js` |
| Lightbox2 | `https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.4/js/lightbox.min.js` |
| Moment.js | `https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.29.4/moment.min.js` |
| Tempusdominus | `https://cdnjs.cloudflare.com/ajax/libs/tempusdominus-bootstrap-4/5.39.0/js/tempusdominus-bootstrap-4.min.js` |
| AOS | `https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.js` |
| CounterUp | `https://cdnjs.cloudflare.com/ajax/libs/Counter-Up/1.0.0/jquery.counterup.min.js` |

### Step 3.2: Embed Custom JS with Proper Initialization
Embed `js/main.js` with proper event handling:

```html
<script>
(function ($) {
    "use strict";

    // DOM-ready code (navigation, scroll events, basic interactions)
    $(document).ready(function () {
        // Back to top button
        // Smooth scrolling
        // Navbar toggle
    });

    // Window load code (plugins that need all resources loaded)
    $(window).on('load', function() {
        // Isotope initialization with existence check
        if (typeof Isotope !== 'undefined') {
            var iso = new Isotope('.portfolio-container', {
                itemSelector: '.portfolio-item',
                layoutMode: 'fitRows'
            });
            // Filter click handlers
        }

        // Owl Carousel with existence check
        if ($.fn.owlCarousel) {
            $(".carousel-class").owlCarousel({
                autoplay: true,
                items: 1,
                loop: true
            });
        }

        // AOS with existence check
        if (typeof AOS !== 'undefined') {
            AOS.init();
        }

        // CounterUp with existence check
        if ($.fn.counterUp) {
            $('[data-toggle="counter-up"]').counterUp();
        }
    });

})(jQuery);
</script>
```

### Step 3.3: Critical JavaScript Patterns

**Always use library existence checks:**
```javascript
if ($.fn.pluginName) { /* use plugin */ }
if (typeof LibraryName !== 'undefined') { /* use library */ }
```

**Use vanilla Isotope API (not jQuery wrapper):**
```javascript
// Correct
var iso = new Isotope('.container', options);
iso.arrange({ filter: filterValue });

// Avoid jQuery wrapper which may not be registered
$('.container').isotope(options);  // May fail
```

---

## Phase 4: HTML Structure Updates

### Step 4.1: Convert to Single-Page Navigation
Replace multi-page links with anchor navigation:
```html
<!-- Before -->
<a href="about.html">About</a>
<a href="services.html">Services</a>

<!-- After -->
<a href="#about">About</a>
<a href="#services">Services</a>
```

### Step 4.2: Add Section IDs
Add `id` attributes to major sections:
```html
<section id="about">...</section>
<section id="services">...</section>
<section id="projects">...</section>
<section id="team">...</section>
<section id="testimonials">...</section>
<section id="contact">...</section>
```

### Step 4.3: Add Smooth Scrolling
Include smooth scroll handler with navbar offset:
```javascript
$('a[href^="#"]').on('click', function (e) {
    if (this.hash !== '') {
        e.preventDefault();
        const hash = this.hash;
        $('html, body').animate({
            scrollTop: $(hash).offset().top - 70  // Adjust for sticky navbar
        }, 800, 'easeInOutExpo');
    }
});
```

---

## Phase 5: Accessibility & SEO

### Step 5.1: Required Meta Tags
Ensure these exist in `<head>`:
```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Descriptive page summary">
<meta name="keywords" content="relevant, keywords">
<title>Page Title</title>
```

### Step 5.2: Accessibility Attributes
Add to all interactive elements:
```html
<!-- Icon-only buttons -->
<a href="#" aria-label="Facebook"><i class="fab fa-facebook"></i></a>

<!-- Navbar toggle -->
<button aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">

<!-- Images -->
<img src="..." alt="Descriptive text for image">
```

---

## Phase 6: Output File Structure

### Final HTML Template:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Page Title</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="...">
    
    <!-- Favicon -->
    <link href="img/favicon.ico" rel="icon">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=..." rel="stylesheet">
    
    <!-- Icon Libraries (CDN) -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/..." rel="stylesheet">
    
    <!-- Plugin CSS (CDN) -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/..." rel="stylesheet">
    
    <!-- Framework CSS (CDN) -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@..." rel="stylesheet">
    
    <!-- Embedded Custom CSS -->
    <style>
        /* All custom styles from css/style.css */
    </style>
</head>
<body>
    <!-- All HTML content with section IDs -->
    
    <!-- JavaScript Libraries (CDN) - Order matters! -->
    <script src="https://code.jquery.com/jquery-..."></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@..."></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/..."></script>
    
    <!-- Embedded Custom JavaScript -->
    <script>
        (function ($) {
            "use strict";
            $(document).ready(function () { /* DOM ready code */ });
            $(window).on('load', function() { /* Plugin initialization */ });
        })(jQuery);
    </script>
</body>
</html>
```

---

## Phase 7: Verification Checklist

// turbo
Run browser verification to check:
- [ ] Page loads without console errors
- [ ] Navbar is visible and sticky
- [ ] Carousel/hero section displays and animates
- [ ] All sections render correctly
- [ ] Portfolio/Isotope filtering works
- [ ] Carousels (testimonials, etc.) auto-play
- [ ] Forms are functional
- [ ] All images load
- [ ] Mobile responsive layout works
- [ ] Smooth scrolling works
- [ ] Back-to-top button appears on scroll

---

## Output

Save the merged file as `index-single-page.html` in the same template folder.

---

## Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| Isotope filter doesn't work | Use `new Isotope()` instead of jQuery wrapper, wrap in `$(window).on('load')` |
| Carousel doesn't auto-play | Check if `$.fn.owlCarousel` exists, wrap in `$(window).on('load')` |
| Images don't load | Verify `img/` folder is in same directory as HTML file |
| Styles missing | Check CSS path references, update `url(../img/)` to `url(img/)` |
| Date picker broken | Tempusdominus requires Bootstrap 4; consider using HTML5 `<input type="date">` |
| Console errors about undefined | Add existence checks before calling library functions |
