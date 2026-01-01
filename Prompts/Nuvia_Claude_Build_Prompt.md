# CLAUDE OPUS 4: BUILD NUVIA FOUR-PAGE WEBSITE
## Production-Ready Prompt for AI Development

---

## MASTER PROMPT FOR CLAUDE OPUS 4

YOU ARE A WORLD-CLASS WEB DEVELOPER SPECIALIZING IN LUXURY BRAND WEBSITES AND SCROLL ANIMATIONS.

### PROJECT OVERVIEW
Build a production-ready single-file HTML website for **Nuvia Properties & Developments** - a Zimbabwean real estate company founded by a young female CEO from the diaspora.

**Key Principle:** Text-heavy website with minimal imagery. Design itself is the visual element. Beautiful typography, scroll animations, glassmorphism effects, and intentional layout create the "wow factor."

**One Optional Image:** CEO hero image (if provided) - otherwise use text/color blocks

---

## CRITICAL REQUIREMENTS

✓ Single-file HTML with embedded CSS and JavaScript  
✓ Responsive mobile-first design  
✓ GSAP (GreenSock) scroll animations with ScrollTrigger  
✓ **Minimal imagery** (0-1 CEO image maximum, no property photos)  
✓ **Typography-driven** (text is the design)  
✓ Glassmorphism UI effects  
✓ Premium, artistic scroll interactions  
✓ <2 second load time  
✓ 60fps smooth animations  
✓ Full accessibility compliance  
✓ No external images except optional CEO photo  

---

## DESIGN SYSTEM (EXACT SPECIFICATIONS)

### COLOR PALETTE (NON-NEGOTIABLE)

```css
/* Primary Colors */
--color-white: #ffffff;          /* Backgrounds, breathing room */
--color-navy: #1a3a52;           /* Headings, authority, trust */
--color-gold: #d4af37;           /* CTAs, hovers, emphasis */
--color-charcoal: #2a2a2a;       /* Body text, readability */
--color-cream: #f5f5f0;          /* Subtle section variation */
--color-gray: #e8e8e8;           /* Borders, dividers */
```

### TYPOGRAPHY

**Fonts to use:**
- **Headings:** Playfair Display (serif, elegant, premium) - 32-60px
- **Subheadings:** Inter (sans-serif, clean) - 18-24px, medium weight
- **Body Text:** Inter (sans-serif) - 16px, regular weight
- **Fallbacks:** Georgia for serif, Arial for sans-serif

**Font Weights:**
- Headings: 600-700 (bold)
- Subheadings: 500 (medium)
- Body: 400 (regular)

### LAYOUT & SPACING

- **Whitespace:** 40%+ of page is empty (luxury signal)
- **Max-width container:** 1200px
- **Padding:** 40px sides desktop, 20px mobile
- **Section vertical spacing:** 80-120px
- **Element gaps:** 16-32px
- **Line height:** 1.4-1.6 (readable, elegant)
- **Letter spacing:** 0.5-1px (breathing room)

---

## PAGE STRUCTURE (4 PAGES)

### PAGE 1: "OUR STORY" (Hero + Founder Narrative)

#### SECTION 1.1 - HERO BANNER

**Layout:**
- Full-width viewport hero section
- Background: Navy (#1a3a52) gradient to white OR white with subtle pattern
- NO LARGE IMAGE (optional: small 200x200px CEO photo centered, round corners)
- Main content: Typography ONLY

**Content - Main Heading:**
```
"The Diaspora
Deserves Better."

Subheading:
"Professional property solutions
built on transparency, integrity, and results."
```

**Styling:**
- H1: Playfair Display, 60px, Navy (#1a3a52), bold
- Line spacing: 1.2 (tight, elegant)
- Subheading: 18px, Charcoal, Inter
- Padding: Top 120px, Bottom 80px
- Text alignment: Center

**Animation (GSAP + ScrollTrigger):**
- Headline letters appear one-by-one on page load
- Each letter: 0.1s animation, 0.05s stagger between letters
- Easing: ease-out
- Total duration: ~1.2 seconds
- Subheading: Fade in after headline (600ms, 200ms delay)
- Scroll indicator: Subtle bouncing arrow below

**CSS Code Pattern:**
```css
@keyframes revealLetter {
  0% { opacity: 0; transform: translateY(10px); }
  100% { opacity: 1; transform: translateY(0); }
}

.hero-letter {
  animation: revealLetter 0.1s ease-out forwards;
  display: inline-block;
}

.hero-h1 {
  font-family: 'Playfair Display', serif;
  font-size: 60px;
  color: #1a3a52;
  font-weight: 700;
  line-height: 1.2;
  margin: 0;
  letter-spacing: 1px;
}
```

#### SECTION 1.2 - FOUNDER STORY (Scroll-Triggered Parallax)

**Layout:**
- Two columns on desktop, single column on mobile
- Background: White (#ffffff) or subtle cream gradient
- No images - pure text

**Content:**
Founder's personal narrative (2-3 paragraphs). Text should be emotional, personal, and establish:
- Her background (diaspora connection)
- Why she created Nuvia
- Her values (transparency, integrity, excellence)

**Example Content:**
```
"As a first-born daughter raised between two worlds—home in Zimbabwe 
and opportunity abroad—I've lived the pressure of wanting better for 
my family while navigating life in the diaspora.

I know what it feels like to dream of building back home but not knowing 
who to trust, who will be honest, or who will deliver the way you would 
if you were physically there.

That's why Nuvia exists.

I created this company to become the dependable bridge between the diaspora 
and home—a company that handles property development, construction, and 
student accommodation with heart, integrity, and excellence. Not because 
of money, but because I understand the emotional weight behind every decision."
```

**Styling:**
- Layout: Two equal columns (desktop), stacked (mobile)
- Column gap: 40px
- Body text: 16px, Charcoal, Inter, line-height 1.6
- Paragraph spacing: 24px between paragraphs
- Text alignment: Left
- Max-width per column: 500px

**Animation (GSAP + ScrollTrigger):**
- Left text enters from LEFT (-100px to 0)
- Right text enters from RIGHT (+100px to 0)
- Simultaneous animation (both at same time)
- Duration: 0.8s
- Easing: power2.out
- ScrollTrigger: scrub: 1 (linked to scroll speed)
- Start: "top 70%"
- End: "top 30%"

**GSAP Code Pattern:**
```javascript
gsap.registerPlugin(ScrollTrigger);

gsap.fromTo('.story-left', 
  { opacity: 0, x: -100 },
  {
    opacity: 1,
    x: 0,
    duration: 0.8,
    scrollTrigger: {
      trigger: '.story-section',
      start: 'top 70%',
      end: 'top 30%',
      scrub: 1
    }
  }
);

gsap.fromTo('.story-right',
  { opacity: 0, x: 100 },
  {
    opacity: 1,
    x: 0,
    duration: 0.8,
    scrollTrigger: {
      trigger: '.story-section',
      start: 'top 70%',
      end: 'top 30%',
      scrub: 1
    }
  }
);
```

**Section Spacing:**
- Top padding: 80px
- Bottom padding: 80px
- Background: White

#### SECTION 1.3 - CALL-TO-ACTION (Sticky)

**Layout:**
- Fixed position button (bottom-right desktop, full-width bottom mobile)
- Gold background, white text
- No image

**Content:**
```
"Learn More About Our Services →"
```

**Styling:**
- Position: fixed, bottom: 30px, right: 30px (desktop)
- Position: fixed, bottom: 20px, left: 20px, right: 20px (mobile)
- Background: #d4af37 (gold)
- Color: white
- Font: 14px, Inter, bold
- Padding: 12px 24px
- Border-radius: 8px
- Z-index: 100
- Box-shadow: 0 4px 12px rgba(212, 175, 55, 0.3)

**Hover Animation (0.3s ease):**
- Scale: 1.05
- Shadow: 0 10px 30px rgba(212, 175, 55, 0.4)

**Action:**
- Click: Smooth scroll to Page 2 (section with id="page-2")

---

### PAGE 2: "WHAT WE DO" (Services with Glassmorphism)

#### SECTION 2.1 - HEADER

**Content:**
```
"Our Services"
(Heading)

"Three core pillars built on trust and transparency."
(Subheading)
```

**Styling:**
- H2: Playfair Display, 48px, Navy, bold
- Subheading: 18px, Charcoal, Inter
- Text-align: center
- Padding: 60px 40px
- Background: White

**Animation:**
- Heading: Fade in + scale (0.95 to 1.0) on scroll, 0.7s
- Subheading: Fade in after heading, 0.6s, 200ms delay

#### SECTION 2.2 - SERVICE CARDS (3 Cards - CORE FEATURE)

**Layout:**
- 3 equal columns (desktop)
- Single column (mobile)
- Card gap: 24px
- Max-width per card: 400px
- Centered on page

**Background:** White or subtle cream (#f5f5f0)

**Card Content Structure (3 cards total):**

**CARD 1: DIASPORA DEVELOPMENT**
```
Icon: (SVG or emoji: 🏠 or 🌍)

Service Name:
"Diaspora Development"

Description:
"Build your dream property from anywhere with professional 
support, transparent costing, and weekly photo updates. We 
handle the details so you can focus on your vision."

What's Included:
• Land advisory and acquisition
• Design planning and consultation
• Transparent cost breakdown
• Weekly photo and progress updates
• Professional contract management
• Completion guarantee

[Learn More →] (Gold button)
```

**CARD 2: STUDENT HOUSING**
```
Icon: (SVG or emoji: 🎓 or 🏢)

Service Name:
"Student Housing"

Description:
"Safe, stylish, modern accommodations designed with dignity 
and comfort. We create spaces where young people can thrive 
academically and socially."

What's Included:
• Modern, well-maintained facilities
• Safety and security systems
• Community spaces and support
• Fair, transparent pricing
• Professional management
• Student-focused amenities

[Learn More →] (Gold button)
```

**CARD 3: PROPERTY MANAGEMENT**
```
Icon: (SVG or emoji: 🔑 or 📋)

Service Name:
"Property Management"

Description:
"Professional lettings, tenant vetting, rent collection, and 
maintenance coordination. Full portfolio management so property 
owners have peace of mind."

What's Included:
• Tenant sourcing and vetting
• Lease management and contracts
• Monthly rent collection
• Maintenance coordination
• Property inspections
• Transparent monthly reporting

[Learn More →] (Gold button)
```

**Card Styling (GLASSMORPHISM):**

```css
.service-card {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  
  border: 1px solid rgba(212, 175, 55, 0.4);
  border-radius: 12px;
  
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
  
  padding: 32px;
  transition: all 0.3s ease;
  
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.service-card:hover {
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(15px);
  
  border-color: rgba(212, 175, 55, 0.8);
  box-shadow: 0 15px 40px rgba(212, 175, 55, 0.2);
  transform: translateY(-8px);
}

.service-icon {
  font-size: 40px;
  height: 40px;
  margin: 0 auto;
  transition: color 0.3s ease;
}

.service-card:hover .service-icon {
  color: #d4af37;
  transform: rotate(10deg) scale(1.1);
}

.service-name {
  font-family: 'Playfair Display', serif;
  font-size: 24px;
  color: #1a3a52;
  font-weight: 700;
  margin: 0;
  text-align: center;
}

.service-description {
  font-size: 16px;
  color: #2a2a2a;
  line-height: 1.6;
  margin: 0;
  text-align: center;
}

.service-list {
  font-size: 14px;
  color: #2a2a2a;
  line-height: 1.8;
  padding-left: 20px;
  margin: 0;
}

.service-list li {
  margin-bottom: 8px;
}

.service-btn {
  background: #d4af37;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 8px;
  font-weight: 600;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.3s ease;
  align-self: center;
}

.service-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 20px rgba(212, 175, 55, 0.4);
}
```

**Card Animations (GSAP):**

```javascript
// Card reveal with stagger
gsap.fromTo('.service-card',
  { opacity: 0, scale: 0.85, y: 40 },
  {
    opacity: 1,
    scale: 1,
    y: 0,
    duration: 0.7,
    stagger: 0.15,
    ease: 'back.out(1.5)',
    scrollTrigger: {
      trigger: '.services-section',
      start: 'top 80%'
    }
  }
);

// Icon rotation (simultaneous)
gsap.fromTo('.service-icon',
  { rotation: -360, opacity: 0 },
  {
    rotation: 0,
    opacity: 1,
    duration: 0.8,
    ease: 'back.out(1.7)',
    scrollTrigger: {
      trigger: '.services-section',
      start: 'top 80%'
    }
  }
);
```

**Section Spacing:**
- Top padding: 80px
- Bottom padding: 80px
- Background: White (#ffffff)

---

### PAGE 3: "WHY NUVIA?" (Differentiation)

#### SECTION 3.1 - TEXT TRANSFORMATION (Key Section)

**Layout:**
- Center text, full-width
- Background: White
- No images

**Content Structure:**
Emotional statements that transform as user scrolls. Three statements:

```
"We don't just build houses...
...we build TRUST"

"We don't manage projects...
...we manage FUTURES"

"We don't house students...
...we empower THEM"
```

**Styling:**
- Statement text: 36px, Playfair Display, Navy, line-height 1.3
- Text-align: center
- Max-width: 800px
- Margin: auto
- Padding: 40px sides

**Key Words (TRUST, FUTURES, THEM):**
- Font-size: 1.2em (relative to statement)
- Color: Gold (#d4af37)
- Text-shadow: 0 0 20px rgba(212, 175, 55, 0.5)
- Font-weight: 700

**Animation (GSAP):**

```javascript
// Statement text appears first
gsap.fromTo('.why-statement',
  { opacity: 0, y: 20 },
  {
    opacity: 1,
    y: 0,
    duration: 0.6,
    scrollTrigger: {
      trigger: '.why-section',
      start: 'top 70%'
    }
  }
);

// Key words transform: Navy → Gold + scale + glow
gsap.to('.key-word', {
  color: '#d4af37',
  fontSize: '1.2em',
  textShadow: '0 0 20px rgba(212, 175, 55, 0.5)',
  duration: 0.6,
  ease: 'back.out(2)',
  stagger: 0.5
});
```

**Section Spacing:**
- Top padding: 80px
- Bottom padding: 80px
- Background: White

#### SECTION 3.2 - SIX REASONS (Icon Rotation Sequence)

**Layout:**
- Left-aligned list
- Full-width container
- Icons on left, text on right per item
- 6 items total

**Content:**
```
Reason 1:
Icon + "Transparent Communication"
Description: "Real-time updates, honest reporting, documented processes."

Reason 2:
Icon + "Female-Led Innovation"
Description: "Young CEO bringing fresh perspective to traditional industry."

Reason 3:
Icon + "Time-Bound Projects"
Description: "Structured timelines, professional contracts, on-schedule delivery."

Reason 4:
Icon + "One-Stop Solution"
Description: "Diaspora development + student housing + property management together."

Reason 5:
Icon + "Genuine Accountability"
Description: "We treat every project like we own it ourselves."

Reason 6:
Icon + "Family-First Approach"
Description: "Your vision is your legacy; we protect it with excellence."
```

**Styling:**

```css
.reason-item {
  display: flex;
  gap: 20px;
  align-items: flex-start;
  padding: 24px;
  margin-bottom: 24px;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.reason-item:hover {
  background: rgba(212, 175, 55, 0.05);
  border-left: 3px solid #d4af37;
  padding-left: 21px;
}

.reason-icon {
  font-size: 40px;
  min-width: 40px;
  text-align: center;
  transition: color 0.3s ease;
}

.reason-item:hover .reason-icon {
  color: #d4af37;
}

.reason-text h4 {
  font-family: 'Playfair Display', serif;
  font-size: 18px;
  color: #1a3a52;
  font-weight: 700;
  margin: 0 0 8px 0;
}

.reason-text p {
  font-size: 14px;
  color: #2a2a2a;
  line-height: 1.6;
  margin: 0;
}
```

**Animation (GSAP):**

```javascript
gsap.utils.toArray('.reason-item').forEach((item, index) => {
  // Icon rotation
  gsap.fromTo(item.querySelector('.reason-icon'),
    { rotation: -360, opacity: 0 },
    {
      rotation: 0,
      opacity: 1,
      duration: 0.8,
      delay: index * 0.15,
      ease: 'back.out(1.7)',
      scrollTrigger: {
        trigger: item,
        start: 'top 80%'
      }
    }
  );
  
  // Text fade in
  gsap.fromTo(item.querySelector('.reason-text'),
    { opacity: 0, x: -20 },
    {
      opacity: 1,
      x: 0,
      duration: 0.6,
      delay: index * 0.15 + 0.1,
      scrollTrigger: {
        trigger: item,
        start: 'top 80%'
      }
    }
  );
});
```

**Section Spacing:**
- Top padding: 60px
- Bottom padding: 60px
- Background: White

#### SECTION 3.3 - MISSION BLOCK (Full-Width Navy)

**Layout:**
- Full-width section
- Navy background
- Centered text
- No images

**Content:**
```
"At Nuvia, we don't just build properties.
We build trust. We build futures.
We build stories that last.

This is why families choose us. This is why we exist."
```

**Styling:**
- Background: Navy (#1a3a52)
- Text color: White (#ffffff)
- Text-align: center
- Font: Playfair Display, 32px, bold
- Line-height: 1.4
- Padding: 60px vertical, 40px horizontal
- Max-width: 900px
- Margin: auto

**Animation:**
- Fade in on scroll, 0.8s, ease-out

**Section Spacing:**
- Top padding: 60px
- Bottom padding: 60px
- Background: Navy (#1a3a52)

---

### PAGE 4: "LET'S BUILD TOGETHER" (Contact & Conversion)

#### SECTION 4.1 - CTA HERO

**Content:**
```
"Ready to Build Your Story?"
(H1)

"Let's talk about your vision. We'll handle the rest."
(Subheading)
```

**Styling:**
- H1: Playfair Display, 56px, Navy, bold
- Line-height: 1.2
- Subheading: 18px, Charcoal, Inter
- Text-align: center
- Padding: 80px 40px
- Background: White

**Animation:**
- Heading: Scale (0.9 to 1.0) + fade in, 0.8s, ease-out
- Subheading: Fade in + translate up, 0.6s, 200ms delay

#### SECTION 4.2 - CONTACT OPTIONS (3 Cards)

**Layout:**
- 3 columns (desktop)
- Single column (mobile)
- Cards equally spaced
- Card gap: 24px
- Background: White

**Content:**

**CARD 1: CALL US**
```
Icon: 📞
Title: "CALL US"
Contact: "+263 [Phone Number]"
Action: "TAP TO CALL"
```

**CARD 2: EMAIL US**
```
Icon: ✉️
Title: "EMAIL US"
Contact: "[Email Address]"
Action: "SEND EMAIL"
```

**CARD 3: MESSAGE US**
```
Icon: 💬
Title: "MESSAGE US"
Contact: "WhatsApp"
Action: "OPEN CHAT"
```

**Card Styling:**

```css
.contact-card {
  background: white;
  border: 2px solid #e8e8e8;
  border-radius: 12px;
  padding: 32px 24px;
  text-align: center;
  transition: all 0.3s ease;
}

.contact-card:hover {
  border-color: #d4af37;
  box-shadow: 0 15px 40px rgba(212, 175, 55, 0.2);
  transform: translateY(-8px);
}

.contact-icon {
  font-size: 40px;
  margin-bottom: 16px;
  transition: color 0.3s ease;
}

.contact-card:hover .contact-icon {
  color: #d4af37;
}

.contact-card h3 {
  font-size: 18px;
  color: #1a3a52;
  font-weight: 700;
  margin: 0 0 8px 0;
}

.contact-card p {
  font-size: 14px;
  color: #2a2a2a;
  margin: 0 0 16px 0;
}

.contact-btn {
  background: #d4af37;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 8px;
  font-weight: 600;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.3s ease;
  width: 100%;
}

.contact-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 20px rgba(212, 175, 55, 0.4);
}
```

**Card Animations (GSAP):**

```javascript
gsap.fromTo('.contact-card',
  { opacity: 0, y: 30 },
  {
    opacity: 1,
    y: 0,
    duration: 0.6,
    stagger: 0.1,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: '.contact-section',
      start: 'top 80%'
    }
  }
);
```

**Button Actions:**
- Call: `href="tel:+263..."`
- Email: `href="mailto:hello@..."`
- WhatsApp: `href="https://wa.me/263..."`

**Section Spacing:**
- Top padding: 80px
- Bottom padding: 80px
- Background: White

#### SECTION 4.3 - FOOTER

**Content:**
```
© 2025 Nuvia Properties & Developments
Harare, Zimbabwe

[Privacy] [Terms] [Contact]

Follow us: LinkedIn • Instagram • Twitter
```

**Styling:**
- Background: Cream (#f5f5f0)
- Text color: Charcoal
- Font-size: 14px
- Text-align: center
- Padding: 40px
- Link color: Navy, hover → Gold

---

## GLOBAL NAVIGATION

### STICKY HEADER

**Layout:**
- Fixed position at top
- Z-index: 1000
- Height: 70px
- Always visible while scrolling

**Content (Left to Right):**
- Logo/Company name (left, Navy, Playfair, 24px)
- Nav links (center): Home | Services | Why Nuvia | Contact
- CTA button (right): Gold button "Get Started"

**Styling:**
- Background: White (#ffffff)
- Border-bottom: 1px solid #e8e8e8
- Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05)

**Navigation Link Styling:**
- Color: Navy (#1a3a52)
- Hover: Gold (#d4af37)
- Active: Gold with underline
- Transition: 0.3s ease

**Mobile Navigation (< 768px):**
- Hamburger menu (3 lines) appears
- Click toggles slide-out panel
- Panel: Full-width, white background, navy text
- Animation: Slide from left (0.3s ease)

### SMOOTH SCROLL NAVIGATION

All anchor links smooth scroll:
```javascript
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    
    gsap.to(window, {
      duration: 1,
      scrollTo: { y: target, autoKill: false },
      ease: 'power2.inOut'
    });
  });
});
```

---

## TECHNICAL REQUIREMENTS

### PERFORMANCE

- **Page Load Time:** Target <2 seconds
- **Animation FPS:** 60fps smooth (no jank)
- **GPU Acceleration:** Only animate transform and opacity (no layout shifts)
- **File Size:** ~700-900 lines HTML (single file)
- **Network:** Optimize for slow connections

### ACCESSIBILITY

- **Color Contrast:** 4.5:1 minimum (WCAG AA)
- **Keyboard Navigation:** Tab through all interactive elements
- **Focus Visible:** Outline/highlight on all focusable elements
- **Reduced Motion:** Respect `prefers-reduced-motion` media query
- **Semantic HTML:** Proper heading hierarchy (h1 > h2 > h3)
- **ARIA Labels:** Where needed for screen readers

```javascript
// Detect reduced motion preference
const prefersReducedMotion = window.matchMedia(
  '(prefers-reduced-motion: reduce)'
).matches;

if (prefersReducedMotion) {
  // Disable animations or use instant versions
  gsap.globalTimeline.pause();
}
```

### MOBILE OPTIMIZATION

**Responsive Breakpoints:**
- Mobile: < 768px (single column)
- Tablet: 768px - 1024px (2 columns if applicable)
- Desktop: > 1024px (full multi-column layout)

**Touch-Friendly:**
- Button size: 48px minimum
- Tap target spacing: 16px minimum
- Text size: 16px minimum (prevents auto-zoom)
- No hover-only content

**Mobile Animation Adjustments:**
- Reduce stagger: 0.05s instead of 0.15s
- Shorter duration: 0.5s instead of 0.8s
- Simpler parallax (or remove)

### BROWSER SUPPORT

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile Safari (iOS 14+)
- Chrome Mobile

---

## EXTERNAL DEPENDENCIES

**GSAP Library (from CDN):**
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
```

**Fonts (from Google Fonts or system fonts):**
- Playfair Display: `<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">`
- Inter: `<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap" rel="stylesheet">`

**No other external libraries needed.**

---

## FILE STRUCTURE

**Single HTML File (index.html)**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Meta Tags -->
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Nuvia Properties & Developments - Property solutions built on trust and transparency">
  <meta name="keywords" content="diaspora development, student housing, property management, Zimbabwe">
  
  <!-- Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
  
  <!-- Inline Critical CSS -->
  <style>
    /* CSS Variables */
    :root {
      --color-white: #ffffff;
      --color-navy: #1a3a52;
      --color-gold: #d4af37;
      --color-charcoal: #2a2a2a;
      --color-cream: #f5f5f0;
      --color-gray: #e8e8e8;
    }
    
    /* All CSS here (embedded) */
    /* ... */
  </style>
</head>
<body>
  <!-- Navigation Header -->
  
  <!-- Page 1: Our Story -->
  
  <!-- Page 2: What We Do -->
  
  <!-- Page 3: Why Nuvia -->
  
  <!-- Page 4: Let's Build Together -->
  
  <!-- Footer -->
  
  <!-- GSAP Scripts -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
  
  <!-- Inline JavaScript -->
  <script>
    // Initialize GSAP
    // Define all animations
    // Event listeners
  </script>
</body>
</html>
```

---

## CRITICAL ANIMATION CODE (COPY-PASTE READY)

### ANIMATION 1: LETTER-BY-LETTER REVEAL

```javascript
gsap.registerPlugin(ScrollTrigger);

// Split headline into letters
const heroHeadline = document.querySelector('.hero-h1');
const letters = heroHeadline.textContent.split('');
heroHeadline.innerHTML = letters.map(letter => 
  `<span class="hero-letter">${letter}</span>`
).join('');

// Animate letters
gsap.fromTo(
  '.hero-letter',
  { opacity: 0, y: 10, rotation: -5 },
  {
    opacity: 1,
    y: 0,
    rotation: 0,
    duration: 0.1,
    stagger: 0.05,
    ease: 'back.out(1.7)',
    delay: 0.2
  }
);
```

### ANIMATION 2: SCROLL-LINKED PARALLAX TEXT

```javascript
gsap.fromTo('.story-left', 
  { opacity: 0, x: -100 },
  {
    opacity: 1,
    x: 0,
    duration: 0.8,
    scrollTrigger: {
      trigger: '.story-section',
      start: 'top 70%',
      end: 'top 30%',
      scrub: 1
    }
  }
);

gsap.fromTo('.story-right',
  { opacity: 0, x: 100 },
  {
    opacity: 1,
    x: 0,
    duration: 0.8,
    scrollTrigger: {
      trigger: '.story-section',
      start: 'top 70%',
      end: 'top 30%',
      scrub: 1
    }
  }
);
```

### ANIMATION 3: STAGGERED CARD REVEAL

```javascript
gsap.fromTo('.service-card',
  { opacity: 0, scale: 0.85, y: 40 },
  {
    opacity: 1,
    scale: 1,
    y: 0,
    duration: 0.7,
    stagger: 0.15,
    ease: 'back.out(1.5)',
    scrollTrigger: {
      trigger: '.services-section',
      start: 'top 80%'
    }
  }
);

gsap.fromTo('.service-icon',
  { rotation: -360, opacity: 0 },
  {
    rotation: 0,
    opacity: 1,
    duration: 0.8,
    ease: 'back.out(1.7)',
    scrollTrigger: {
      trigger: '.services-section',
      start: 'top 80%'
    }
  }
);
```

### ANIMATION 4: TEXT COLOR TRANSFORM

```javascript
gsap.to('.key-word', {
  color: '#d4af37',
  fontSize: '1.2em',
  textShadow: '0 0 20px rgba(212, 175, 55, 0.5)',
  duration: 0.6,
  ease: 'back.out(2)',
  stagger: 0.5
});
```

### ANIMATION 5: ICON ROTATION SEQUENCE

```javascript
gsap.utils.toArray('.reason-item').forEach((item, index) => {
  gsap.fromTo(item.querySelector('.reason-icon'),
    { rotation: -360, opacity: 0 },
    {
      rotation: 0,
      opacity: 1,
      duration: 0.8,
      delay: index * 0.15,
      ease: 'back.out(1.7)',
      scrollTrigger: {
        trigger: item,
        start: 'top 80%'
      }
    }
  );
  
  gsap.fromTo(item.querySelector('.reason-text'),
    { opacity: 0, x: -20 },
    {
      opacity: 1,
      x: 0,
      duration: 0.6,
      delay: index * 0.15 + 0.1,
      scrollTrigger: {
        trigger: item,
        start: 'top 80%'
      }
    }
  );
});
```

---

## CONTENT TO INSERT

**Before building, provide:**

### COMPANY INFORMATION
- Company name: Nuvia Properties & Developments
- Location: Harare, Zimbabwe
- Contact email: [TO BE PROVIDED]
- Contact phone: [TO BE PROVIDED]
- WhatsApp link: [TO BE PROVIDED]

### PAGE 1 CONTENT
**Founder Story (2-3 paragraphs):**
[Provide founder's personal narrative about:
- Background (diaspora connection)
- Why she created Nuvia
- Her values]

### PAGE 2 CONTENT
**Service Descriptions (already provided above in template)**
- Diaspora Development description
- Student Housing description
- Property Management description
- Features for each service

### PAGE 3 CONTENT
**Six Differentiation Points (already provided above in template)**
1-6 reasons why choose Nuvia

### PAGE 4 CONTENT
**Contact Information:**
- Email address
- Phone number
- WhatsApp link

---

## DELIVERABLES

**Provide:**
1. Single HTML file (index.html)
2. All CSS embedded in `<style>` tags
3. All JavaScript embedded in `<script>` tags
4. GSAP library loaded from CDN
5. Responsive mobile-first design
6. All animations smooth (60fps)
7. Accessibility compliant
8. SEO optimized
9. Well-commented code
10. Production-ready (no build process needed)

**File Characteristics:**
- Size: ~700-900 lines
- Load time: <2 seconds
- Animations: 60fps smooth
- Mobile: Fully responsive
- Accessibility: WCAG AA compliant
- Dependencies: Only GSAP from CDN (fonts optional)

---

## VALIDATION CHECKLIST

Before delivery, verify:

✅ All 4 pages render correctly
✅ All animations work smoothly (no jank)
✅ Mobile responsive (tested 375px, 414px, 768px, 1200px)
✅ Load time <2 seconds
✅ All interactive elements keyboard-accessible
✅ Text meets WCAG AA color contrast (4.5:1)
✅ Prefers-reduced-motion respected
✅ All links functional (including smooth scroll)
✅ No console errors
✅ CSS minified/optimized
✅ Only GPU-accelerated animations (transform + opacity)
✅ All images (if any) optimized
✅ Fonts loading properly
✅ Form actions properly configured

---

## DESIGN PHILOSOPHY

This website embodies:
- **Text-Heavy:** Content is king, design supports the message
- **Minimal Imagery:** 0-1 CEO photo max, no property photos
- **Whitespace:** 40%+ empty space = luxury perception
- **Typography:** Large, bold headings guide attention
- **Color:** Strategic gold accents, navy authority, white space
- **Animation:** Every motion serves a purpose
- **Accessibility:** Beautiful for everyone
- **Performance:** Fast, smooth, responsive

**Result:** A website that tells Nuvia's story beautifully without relying on imagery. Design and text work together to create premium brand perception.

---

## SPECIAL NOTES

1. **No Image Dependency:** This site works with ZERO images (except optional CEO photo). The design itself is the visual element.

2. **Typography is Hero:** Large, bold text with excellent spacing creates visual interest without images.

3. **Animation Enhances:** GSAP animations guide the eye and maintain engagement without being distracting.

4. **Text Quality:** Every word should be intentional. Proofread all copy before build.

5. **Color Restraint:** Only use white, navy, gold, charcoal, cream. No other colors.

6. **Whitespace:** Don't fill every space. Emptiness is intentional and premium.

---

## BUILD THIS WEBSITE TO PERFECTION

Your website will:
- ✅ Look beautiful (premium aesthetic)
- ✅ Load fast (<2 seconds)
- ✅ Feel smooth (60fps animations)
- ✅ Work everywhere (mobile-responsive)
- ✅ Captivate visitors (design-first, text-heavy)
- ✅ Build trust (founder story + professional design)
- ✅ Differentiate Nuvia (award-winning aesthetic)

**No images needed. Design is the visual element. Text tells the story. Animation captivates. Result: Beautiful, memorable website.**

---

**BUILD NOW. MAKE IT BEAUTIFUL. MAKE IT COUNT.**