# Implementation Plan: Gurukul's Sports Single-Page Static Website

## Project Overview
Create a highly attractive, performance-optimized, single-page static website for **Gurukul's Sports** (Bengaluru) using HTML5, Tailwind CSS, and Alpine.js (or vanilla JS) for lightweight, high-performance interactions. The site must feature a premium dark/sporty aesthetic, rich typography, fluid hover states, number-counting indicators, scroll-driven entrance reveals, and custom testimonial layouts.

---

## Technical Specifications
- **Framework/Styling:** Tailwind CSS (via CDN) for modern utility-first layouts.
- **Interactions/Animations:** Alpine.js for interactive counters, tabs, and lightboxes; ScrollReveal.js or standard Intersection Observer API for smooth scrolling triggers.
- **Typography:** Inter or Montserrat for strong, sporty heading treatments.
- **Imagery:** High-definition, free-to-use sports photography sourced from Unsplash/Pexels via public CDN links.

---

## Section-by-Section Architecture

### 1. Navigation Bar (Sticky & Glassmorphism)
- **Layout:** Flexbox container holding the brand title ("Gurukul's Sports ®"), dynamic anchor links, and a prominent Action button.
- **Visuals:** Semi-transparent dark background (`backdrop-blur-md bg-zinc-950/80`) that morphs upon scroll.
- **Interactions:** Underline expand animations on text links during hover; scale transitions on the booking CTA button.

### 2. Hero Segment (The Hook)
- **Layout:** Full-viewport (`min-h-screen`) flex layout with a split view or dark text overlay over a massive background grid.
- **Visual Asset:** Full-bleed background depicting professional BWF-grade indoor badminton courts or multi-sport complexes.
- **Typography & Copy:** 
  - Massive bold title: *"Train at Bengaluru’s Record-Breaking Sports Hub"*
  - Subtext emphasizing the unique selling proposition: *"Home to 32+ World-Class Courts, Olympic-Grade Shooting Ranges, and Premium Amenities."*
- **Call-to-Action:** Secondary dual-button arrangement (`[Book Court Now]` and `[Explore Memberships]`).
- **Scroll Driver:** Smooth entrance animation where headers slide up and expand.

### 3. World Record Status & Animated Performance Counters
- **Layout:** Full-width accent container styled with striking warning-yellow or gold borders (`bg-zinc-900 border-y border-amber-500/30`).
- **Core Focus:** Highlight the official world record certification for holding the most badminton courts in a single academy.
- **Animated Counters:** Four statistical cards displaying numbers that smoothly count upward from 0 when scrolled into view:
  - **32+** World-Class Badminton Courts
  - **10k+** Registered Athletes Trained
  - **15+** Pro Coaching Staff
  - **100%** Premium BWF Synthetic & Wooden Flooring
- **Animation Implementation:** Use a robust scroll-triggered script utilizing `requestAnimationFrame` to animate numerical text fields smoothly.

### 4. Interactive Sports & Amenities Grid
- **Layout:** Responsive structural layout changing dynamically from 1 column up to 3 columns (`grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8`).
- **Content Cards:** Dedicated interactive components for each amenity:
  - *Badminton Arenas* (11+ Premium BWF Synthetic Courts)
  - *Air Rifle & Pistol Shooting Range* (Modern Electronic Targets)
  - *Swimming Pool & Aquatic Facility*
  - *Multi-Sport Turfs* (Football/Cricket)
  - *Table Tennis Lounge*
- **Animations:** 
  - Subtitle or description elements that slide up only when hovering over a card.
  - Image scaling effects (`scale-105 duration-500`) confined safely within card boundaries (`overflow-hidden`).

### 5. Membership Packages Section
- **Layout:** Vertical column structure breaking into parallel pricing structural cards.
- **Tier Structure:**
  - *Casual Player Pass:* Hourly bookings, basic equipment rental options.
  - *Academy Pro Training:* Monthly regular coaching regimens, tournament prep.
  - *Elite Multi-Sport Access:* Unlimited access to courts, pool, and shooting ranges.
- **Visual Polish:** The central "Pro" card must feature a distinct illuminated outer shadow glow or unique banner wrapper indicating it is the most popular choice.

### 6. Special Offers & Limited Discounts
- **Layout:** Full-width eye-catching element using deep gradients (`bg-gradient-to-r from-red-600 to-amber-600`).
- **Core Message:** Dynamic current deals (e.g., *"Festive Sports Surge: Get 20% off on bulk badminton court block-bookings this month"*).
- **Interactions:** Subtle background movement effects or glowing edge borders.

### 7. Verified Customer Testimonials (Using Review Commands)
- **Layout:** A smooth multi-card grid displaying local feedback.
- **Component Breakdown:** Star rating blocks, descriptive feedback blocks, and author avatars.
- **Review Assets:**
  - *"Incredible facilities. The sheer scale of 32 badminton courts is mind-blowing. Booking via Playo is seamless, and court lighting is top-tier."* – Rajesh K.
  - *"The newly added air rifle range is a game-changer for Bengaluru sports enthusiasts. Clean, professional coaching."* – Priya M.

### 8. Location Mapping & Contact Footer
- **Layout:** Two-column split interface.
  - *Left Column:* Operational hours info, telephone lines, complete regional address: *Gurukul's Sports, Varthur Main Road, Thubarahalli, Siddapura, Bengaluru, Karnataka 560066*.
  - *Right Column:* Full responsive Google Maps embed wrapper pointing safely to their operational location.

---

## Detailed Developer Step-by-Step Task List

### Phase 1: Core Setup & Boilerplate Generation
1. Initialize an `index.html` structure sourcing Tailwind CSS, FontAwesome icons, and Alpine.js through reliable content distribution networks.
2. Build global styling guidelines in the document `<head>` to maintain smooth scroll configurations (`scroll-behavior: smooth;`) and clean default dark theme layouts.

### Phase 2: Structural Markup & Visual Placement
1. Implement the responsive navigation layout and hero components using placeholders for structural images.
2. Organize the target container components for the numerical counts, sport grids, and membership tiers.
3. Inject the Google Maps iframe container pointing accurately to the destination coordinates on Varthur Main Road.

### Phase 3: Fine-Tuning Advanced Scroll & Hover Interactions
1. Implement an Intersection Observer within a script tag to identify when elements enter the viewport, immediately applying a CSS transition mask (`opacity: 1; transform: translateY(0);`) to create a fluid, premium scroll-reveal experience.
2. Wire up custom numeric counting mechanics into the observer to track performance stats. Ensure numbers tick up cleanly when seen, executing exactly once.
3. Apply standard styling rules (`transition-all duration-300 transform hover:-translate-y-2`) over interactive cards to produce elegant floating transitions.

### Phase 4: Verification & Asset Verification
1. Confirm all navigation menu selections jump cleanly to targeted section identifiers on the page.
2. Verify visual appearance across multiple simulated viewport dimensions to protect layouts from shifting or clipping incorrectly.
3. Test animation execution to prevent multiple counting loops from running concurrently or failing to start.

---
## Direct Setup Prompt
Run the following instructions to populate a clean execution setup:
```bash
cat << 'EOF' > index.html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gurukul's Sports | Bengaluru's Elite Sports Academy</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Alpine.js -->
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .reveal-element {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }
        .reveal-element.active {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body class="bg-zinc-950 text-zinc-100 font-sans overflow-x-hidden">
    <!-- Website structural shell. Build complete production sections here following the plan details. -->
</body>
</html>
EOF
```