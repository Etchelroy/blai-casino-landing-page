# Casino Landing Page Research

**SUMMARY:**
A high-conversion casino landing page requires compliance-first design, responsive layout, geolocation targeting, and secure bonus presentation with clear terms visibility.

---

## APPROACH

**Recommended Tech Stack:**
- **Frontend:** HTML5 + CSS3 (Grid/Flexbox) + vanilla JavaScript (no framework overhead for landing pages)
- **CMS/Backend:** Headless CMS (Contentful or Strapi) for dynamic bonus/promotion updates + Node.js/Python API for geolocation & legal compliance checks
- **Hosting:** Cloudflare Pages or Vercel (built-in DDoS protection, edge caching for fast TTFB)
- **Analytics:** Segment or Mixpanel (event tracking for conversion funnel) + server-side tracking to avoid ad blockers
- **Payment/Verification:** Third-party KYC provider (e.g., Onfido) — never store compliance data on-page
- **Compliance:** Dedicated legal/compliance API endpoint (not client-side) to handle jurisdiction rules

**Why this stack:**
- Landing pages don't need React/Vue complexity; vanilla JS keeps bundle <60KB
- Geolocation & legal rules belong server-side (cannot be bypassed)
- Headless CMS allows marketing teams to update promos without deployment
- Edge caching ensures sub-1s load times globally (critical for paid traffic)

---

## REQUIREMENTS

### Core Page Structure
- **Hero Section**
  - Full-bleed background image (video fallback for older browsers)
  - Headline + subheadline (max 8 words each for clarity)
  - Primary CTA button ("Claim Welcome Bonus") with hover/active states
  - Trust badges (licenses, certifications) in hero footer
  - Background must support 16:9 and mobile 9:16 aspect ratios

- **Navigation**
  - Sticky header with logo, nav links, Login/Sign Up buttons
  - Mobile hamburger menu (slide-in from left, z-index managed)
  - Contrast ratio ≥ 4.5:1 for all text on background

### Bonus/Offer Section
- **Welcome Package Display**
  - Bonus amount clearly stated (e.g., "€500 Bonus + 100 Free Spins")
  - Wagering requirements visible on first interaction (not hidden)
  - Countdown timer for limited-time offers (if applicable)
  - Expandable "Terms & Conditions" accordion (legally required, pre-expanded on first visit)
  - No micro-fonts; minimum 14px body text

- **Multi-Bonus Carousel** (if applicable)
  - Swipeable cards (touch-friendly, 44px tap targets)
  - Autoplay paused on hover/focus
  - Dots/progress indicators
  - Keyboard navigation (arrow keys)

### Game/Content Showcase
- **Game Grid**
  - 3-column grid (responsive: 1 col mobile, 2 col tablet, 3 col desktop)
  - Game cards: image + title + brief description + "Play Now" link
  - Lazy-load images (IntersectionObserver API)
  - No autoplay videos; user-triggered only
  
- **Category Filters** (if >12 games)
  - Tabs or dropdown: "All, Slots, Table Games, Live Casino, Sports"
  - Filter state persisted in URL (e.g., `?category=slots`)

### Trust & Compliance Section
- **License Display**
  - License number + jurisdiction (e.g., "Licensed by Malta Gaming Authority - License #MGA/CL2/500/2021")
  - Link to regulator verification (opens in new tab)
  - Conspicuous placement (footer minimum, hero optional)

- **Responsible Gaming**
  - Betting limits explainer
  - Link to GAMCARE/GambleAware/national equivalent
  - Self-exclusion link
  - Minimum 12pt font for all compliance copy

- **Security/Fairness**
  - SSL/TLS badge (real link to certificate info)
  - RTP (Return-to-Player) percentages for major games
  - Certification logos (e.g., eCOGRA, iTech Labs)

### Forms & Conversions
- **Registration Form** (above fold or modal)
  - Fields: Email, Password (strength indicator), Country (geolocation pre-filled via API, user-editable), Age verification (radio: 18+)
  - Real-time validation (debounced, 300ms delay)
  - Submit button disabled until all required fields pass validation
  - Success state: redirect to verification email or onboarding flow
  - Error messages: specific, constructive, red text (#DC2626 or better contrast)

- **Geolocation Check** (server-side, pre-form)
  - Detect user country via IP (use MaxMind GeoIP2 API)
  - Block restricted jurisdictions (e.g., USA, UK depending on license) with modal explaining restrictions
  - Allow user override if applicable (require VPN detection before allowing)
  - Log rejections for compliance audit

### Social & FAQ
- **FAQ Accordion**
  - Expandable Q&A pairs (minimum 5 pairs)
  - Smooth height transitions (max-height animation, not transform)
  - Pre-indexed for search (data-faq-id attribute)
  - Keyboard-accessible (Tab, Enter/Space to toggle)

- **Social Proof**
  - Trustpilot or similar widget (real reviews, not fake testimonials)
  - Player count badge ("10,000+ active players")
  - Recent win notifications (real data from backend, no fabrication)

### Footer
- **Legal Links**
  - Terms of Service, Privacy Policy, Cookie Policy (clickable, not just text)
  - Responsible Gaming, Bonus Terms
  - Contact/Support link

- **Payment Methods**
  - Display logos of accepted methods (Visa, Mastercard, PayPal, e-wallets)
  - No actual payment processing on landing page (send to secure checkout)

- **Multi-Language Support**
  - Language selector (top-right or bottom)
  - URL routing: `/en/`, `/de/`, `/fr/` (not URL parameters)
  - Translations via CMS (content only, not hardcoded)

---

## CONSTRAINTS

### Performance
- **LCP (Largest Contentful Paint):** <2.5s (mobile on 4G)
- **CLS (Cumulative Layout Shift):** <0.1 (no jumping banners/ads)
- **Bundle Size:** CSS <50KB (minified), JS <60KB (minified)
- **Image Optimization:** WebP with JPG fallback; max 100KB per image; use CDN with srcset

### Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge) — last 2 versions
- IE11 no longer supported (but no errors if accessed — graceful degradation)
- Mobile: iOS 12+, Android 8+

### Security & Compliance
- **HTTPS only** (A+ SSL rating via Qualys)
- **No third-party embeds** (scripts, iframes) without security audit
- **API keys:** Environment variables only (never in JS)
- **Form submissions:** POST to backend, no direct API calls from client
- **Cookie consent:** Explicit opt-in before analytics/marketing pixels (GDPR/CCPA)
- **Content Security Policy (CSP):** Strict headers to prevent XSS
- **Geolocation enforcement:** Server-side validation (client-side checks are bypassable)

### Accessibility (WCAG AA minimum)
- **Contrast:** All text ≥4.5:1 on background
- **Focus indicators:** Visible outlines (not removed)
- **Keyboard nav:** All interactive elements reachable via Tab
- **Alt text:** All images (including logos) have descriptive alt
- **Video:** Captions required (if promotional video in hero)
- **Screen reader:** Semantic HTML (no div-only layouts)

### Legal Jurisdiction Handling
- **Geo-blocking list:** Hardcoded list of restricted regions in backend
- **AML/KYC checks:** Trigger for amounts >€1,000 deposit
- **Marketing opt-in:** Separate checkbox for email/SMS (not pre-checked)
- **Bonus eligibility:** Age 18+ only (validated against ID verification API)

---

## NOTES

### Edge Cases & Best Practices

**VPN/Proxy Detection:**
- If IP-based geolocation detects VPN, flag account for manual review before payment
- Do NOT reject VPN users outright (legitimate privacy use); require additional verification instead

**Bonus Abuse Prevention:**
- Never display bonus code in URL or meta tags (scraping/bots)
- Bonus claim tracked server-side with device fingerprinting (FingerprintJS or similar)
- Prevent multiple claims from same device within 30 days

**Mobile Considerations:**
- Hero button must be ≥44px tall (touch-friendly)
- Forms should trigger mobile keyboard without scrolling page up
- Avoid auto-play videos/audio (will fail user interaction tests)
- Test on actual devices (not just Chrome DevTools emulation)

**Analytics Without Bloat:**
- Use first-party cookies (not third-party Google Analytics if possible)
- Implement server-side event tracking for sensitive conversions (registration, deposit)
- Track but do NOT expose user PII in analytics (anonymize email addresses)

**Promotion Fatigue:**
- Limit "pop-up" offers to 1-2 per session
- Implement frequency cap: show bonus offer only if user scrolls 40% down
- Exit-intent popup only on desktop (mobile exit-intent is bad UX)

**A/B Testing:**
- Use feature flags (not URL parameters) to split test CTA colors, button text
- Server-side bucketing (not client-side) to prevent bots from gaming tests
- Minimum 2,000 conversions per variant before calling winner

**Email Verification:**
- Require email verification before allowing deposits (AML requirement in most jurisdictions)
- Verification link valid for 24 hours only
- Allow users to resend verification email (with rate limiting: max 5 resends per hour)

**Payment Page Redirect:**
- Never host payment form on landing page; redirect to separate PCI-DSS compliant domain
- Use POST with hidden form (not GET with exposed data)
- Implement redirect validation (no open redirects)

**Responsible Gaming Messaging:**
- "Gambling can be addictive" must appear in footer of EVERY page
- Self-exclusion link must work in real-time (not require support ticket)
- Betting limit setter must be functional on signup (not buried in account settings)

**License/Compliance Verification:**
- Store license number + expiry date in CMS with automated reminder to update
- Weekly check against official regulator DB (Malta Gaming Authority API, UK Gambling Commission, etc.)
- If license expires, hide landing page + show compliance hold message

**Browser Back Button:**
- Prevent users from returning to confirmation page after signup (redirect to account dashboard)
- Use history.replaceState() to replace signup form with success state in history

---

**Ready for implementation.** Developer should clarify: 
1. Which jurisdictions/licenses are in scope?
2. What bonus structures (deposit match, free spins, both)?
3. Is live-chat support required on page?
4. Target CPA/conversion target for paid traffic budgeting?