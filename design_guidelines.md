# Design Guidelines: Personal Portfolio Website for KS

## Design Approach

**Selected Approach:** Reference-based, drawing inspiration from clean personal portfolio sites like those found on Behance and Dribbble, with emphasis on visual simplicity and flower-inspired aesthetics.

**Key Design Principles:**
- Minimalist elegance with breathing room
- Floral imagery as the visual anchor
- Soft, organic shapes balanced with clean typography
- Single-page scroll experience
- Mobile-first responsive design

## Typography

**Font Selection:**
- Primary: Playfair Display (serif) - for name and headings
- Secondary: Inter or Work Sans (sans-serif) - for body text and descriptions
- Use via Google Fonts CDN

**Hierarchy:**
- Name/Hero: 4xl to 6xl (responsive), font-weight 700
- Section Headings: 3xl to 4xl, font-weight 600
- Body Text: base to lg, font-weight 400
- Accents/Labels: sm, font-weight 500, uppercase letter-spacing

## Layout System

**Spacing Primitives:**
Consistent use of Tailwind units: 4, 8, 12, 16, 24 for margins and padding.

**Container Strategy:**
- Max-width: max-w-4xl for content sections
- Full-width hero section
- Centered content alignment throughout

**Vertical Rhythm:**
- Section padding: py-16 mobile, py-24 desktop
- Element spacing: space-y-8 for section content
- Component gaps: gap-6 to gap-8

## Component Library

### Hero Section
- Full-width background with floral imagery
- Centered name presentation
- Subtle tagline or welcome message
- Soft gradient overlay for text readability
- Height: 80vh to 100vh

### About/Introduction Section
- Clean single-column layout
- Personal introduction paragraph (max-w-2xl centered)
- Rounded profile accent (subtle decorative element)

### Hobbies Section - Flowers Focus
- Two-column grid on desktop (md:grid-cols-2)
- Flower imagery showcase with descriptions
- Card-based layout with soft shadows
- Each card: rounded-2xl, padding p-6
- Include 3-4 flower cards with images and short descriptions

### Contact/Footer Section
- Simple centered layout
- Social links with icons (use Heroicons via CDN)
- Email or contact method
- Minimal footer text

## Images

**Hero Image:**
Large, high-quality floral photography - soft focus bouquet or garden scene, positioned as full-width background with subtle parallax effect.

**Flower Cards (3-4 images):**
Individual flower close-ups or arrangements representing different favorites (roses, tulips, orchids, etc.). Images should be square or 4:3 ratio, placed within rounded cards.

**Image Treatment:**
- Border-radius: rounded-2xl for all images
- Subtle shadow: shadow-lg
- Hero overlay: gradient overlay for text legibility

## Interactive Elements

**Navigation:**
Smooth scroll to section anchors. Simple fixed header with minimal links (About, Hobbies, Contact) if content warrants, otherwise skip navigation.

**Cards:**
Subtle hover elevation - increase shadow on hover, gentle scale transform (scale-105).

**Links/Buttons:**
- Rounded-full for primary actions
- px-8 py-3 sizing
- Blur backdrop for buttons over images (backdrop-blur-md)
- Icon integration where appropriate

## Animations

**Minimal Motion:**
- Fade-in on scroll for sections (subtle)
- Smooth scroll behavior
- Gentle hover transitions (200-300ms)
- No distracting parallax or complex animations

## Accessibility

- Semantic HTML structure (header, main, section, footer)
- Proper heading hierarchy (h1 for name, h2 for sections)
- Alt text for all flower images
- Sufficient contrast ratios throughout
- Focus states for interactive elements

## Layout Structure

1. **Hero Section** (full viewport)
2. **Introduction Section** (personal greeting)
3. **Flowers/Hobbies Section** (grid showcase with 3-4 cards)
4. **Contact/Footer Section** (social links, minimal info)

**Overall Feel:** Clean, personal, and visually gentle - like a digital garden showcase. The design should feel welcoming and reflect a passion for flowers through thoughtful imagery placement and organic, soft design elements.