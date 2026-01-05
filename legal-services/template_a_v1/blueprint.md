# Template Blueprint: Legal Services Template A V1

## Template Style
- **Framework**: Bootstrap 4.x (inferred from class names like `ml-`, `badge-soft-primary`)
- **Typography**: Lato, Nunito Sans (Google Fonts)
- **Color Scheme**:
    - Primary: Blue/Dark Blue (implied by `text-primary`, `btn-raven-primary`)
    - Secondary: Success Green (`text-success`, `btn-raven-success`)
    - Backgrounds: White, Light Gray (`bg-light`, `section-gradient-bg`)

## Sections
1.  **Header**:
    -   Logo (`assets/img/raven-logo.svg`)
    -   Navigation Menu (Home, Pages, Team, Testimonial, Components, Documentation, Utilities, Plugins) with Dropdowns.
    -   Top Bar (hidden on mobile).
2.  **Hero Section**:
    -   Headline ("Ranked #1 World Class Law Firm")
    -   Video Popup Button (Fancybox)
    -   Image Banner
3.  **Recognition**:
    -   "Recognition" Badge
    -   Text describing awards.
4.  **Awards/Ratings Carousel**:
    -   Owl Carousel displaying awards (Lead Counsel, Avvo, NJSBA) with star ratings.
5.  **About Us**:
    -   "Who are we" text.
    -   Checklist/Values ("No Fees Unless We Win").
    -   Team/Office images collage.
6.  **Services (What we offer)**:
    -   List of services with icons (Proven Track Record, No Fees, Multilingual, 24/7, Experience, Trial Attorneys, Personal Injury).
7.  **Practice Areas**:
    -   "Practice areas" Badge
    -   Text description.
    -   Interactive Map/SVG (`#Layer_1`).
    -   List of areas: Personal Injury, Criminal Defense, Civil Litigation, Family Law, Environmental Law.
8.  **Recent Results**:
    -   Carousel of case studies/wins ("Car accident", "False criminal charge", "Divorce case").
    -   Hover effects with details.
9.  **CTA (Consultancy)**:
    -   Background image.
    -   "Need consultancy?" text and "Call Us Now" button.
10. **Team**:
    -   "Our team" Badge.
    -   Carousel of team members (Senior Attorney, Consultant, etc.) with bios and social links.
11. **Gallery**:
    -   "Life at raven is easy..." text.
    -   Isotope/Packery Filterable Gallery (All, Photography, Studio, etc.) with Fancybox integration.
12. **Career CTA**:
    -   "Want to join our team?" text.
13. **Footer**:
    -   4 Columns: About links, Account links, Resources links, Newsletter Subscription.
    -   Copyright and Credits (ThemeWagon).
    -   Google Map integration.
    -   Back to Top button.

## Additional Pages
-   `index-slider.html`
-   `index-video.html`
-   `contact.html`
-   `about.html`
-   `team.html`
-   `gallery.html`
-   `components/*.html` (Various component demos)
-   `documentation/*.html`

## Key Features
-   **Owl Carousel**: For Testimonials, Awards, Team, Recent Results.
-   **Fancybox**: For video popups and image gallery lightboxes.
-   **Isotope / Packery**: For the masonry gallery layout.
-   **Google Maps API**: Integrated in the footer.
-   **Sticky Navigation**: `sticky-top`, `sticky-kit`.
-   **Semantic UI**: Accordion and Transition libraries included.
-   **Animations**: Start-up animations, hover effects (`hover-scal`, `media-player-hover`).
