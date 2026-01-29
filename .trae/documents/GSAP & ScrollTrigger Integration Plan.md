I have analyzed your `index.html` and prepared a comprehensive plan to integrate GSAP and ScrollTrigger, transforming your website with professional, scroll-driven animations.

## 1. Setup & Dependencies
- **Add GSAP Core & ScrollTrigger Plugin**: Insert CDN links in the `<head>` section to ensure they load before your custom scripts.
- **Register Plugin**: Initialize `gsap.registerPlugin(ScrollTrigger)` at the start of the script.

## 2. Animation Implementation Strategy

### **Hero Section (Load Animation)**
- **Timeline**: Create a `gsap.timeline()` that plays immediately on load.
- **Elements**:
  - **Logo**: Fade in + scale up.
  - **Heading (`h1`)**: Split text or simple fade-up with a slight scale (0.95 → 1).
  - **Subtitle**: Fade up with delay.
  - **Buttons**: Staggered entry (pop in).
- **Background**: Smooth fade-in for the video/overlay.

### **Navigation (`.dynamic-nav`)**
- **Scroll Effect**: Use `ScrollTrigger` to detect scrolling past the hero section.
  - Animate background opacity/blur.
  - Shrink padding for a sleeker look on scroll.

### **Services Section (`.services-modern`)**
- **Section Header**: Fade up + slide in.
- **Cards (`.card`)**:
  - **Trigger**: When the grid enters the viewport (top 80%).
  - **Animation**: Staggered fade-in from bottom (`y: 60`, `opacity: 0`) with a subtle 3D rotation (`rotateX: 10deg`).
  - **Hover**: Keep existing CSS hover effects but ensure they play nicely with GSAP.

### **Portfolio Section (`.portfolio-showcase`)**
- **Grid Items (`.portfolio-item`)**:
  - **Batching**: Use `ScrollTrigger.batch()` for efficient handling of many items.
  - **Effect**: Staggered fade-up with a slight scale start (0.9 → 1) to create a "pop" effect as you scroll.

### **CTA Section (`.cta-block`)**
- **Container**: Scale up gently (0.95 → 1) with opacity fade when entering the viewport.
- **Content**: Stagger text and button reveal.

### **Footer (`.footer-modern`)**
- **Reveal**: Slide up from the bottom (`y: 50`) as the user reaches the end of the page.

## 3. Technical Enhancements
- **Smooth Scroll**: Implement `gsap.to(window, { scrollTo: target })` for all anchor links (Navigation, CTA buttons), replacing the native behavior for a consistent feel.
- **Performance**:
  - Use `will-change` properties where appropriate.
  - Enable `markers: false` (debug mode off).
- **Accessibility**:
  - Wrap animations in a `gsap.matchMedia()` check for `(prefers-reduced-motion: no-preference)`.
  - Ensure content remains visible if JS fails or for screen readers.

## 4. Code Organization
- **Clean Up**: Remove the old `revealOnScroll` function and event listeners.
- **Structure**:
  ```javascript
  // 1. Setup
  gsap.registerPlugin(ScrollTrigger);
  
  // 2. Load Animations (Hero)
  
  // 3. ScrollTrigger Animations (Sections)
  
  // 4. Utils (Smooth Scroll, etc.)
  ```

I will now apply these changes to your `index.html` file.
