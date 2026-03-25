# CASINO LANDING PAGE — DESIGN SPECIFICATION

## SUMMARY
High-contrast, trust-forward design with geolocation-aware hero, clear bonus hierarchy, and compliance-first micro-interactions that guide users through signup while building confidence via certifications and responsible gaming signals.

---

## LAYOUT

### HEADER (Full width, sticky)
- **Top Bar** (0–56px): Logo left | Nav links center-right | Account/Login button right
  - Logo: 160×40px, left margin 24px
  - Nav: 4–5 items (Games, Promotions, About, Responsible Gaming, Help), 16px text, 32px h-spacing
  - CTA Button: 120×40px, right margin 24px
  
- **Subheader** (56–120px, conditional): Geo-alert banner (red/yellow background) if user in restricted region
  - Text: "Available in [Region]" + compliance badge, 14px, centered
  - Dismiss icon top-right (16×16px)

---

### HERO SECTION (Full viewport height, 0–600px)
**Background**: Dark gradient (top #0a1e2e → bottom #16213e), overlay video loop (muted, 60% opacity) of casino chips/cards/roulette wheel  
**Content overlay** (centered, max-width 800px):
- **Headline**: 52px bold, #ffffff, "Your Premier Gaming Destination"
- **Subheadline**: 20px light, #e8e8e8, "Play smart. Win big. Stay in control."
- **Primary CTA**: Button (180×56px, #ffd700 background, #0a1e2e text, 18px bold), "Create Free Account"
  - Hover: brightness +10%, shadow +2px drop
  - Click: Scroll-to form or modal open
  
- **Secondary CTA**: Text link (16px, #ffd700), "Explore Games First"
  - Hover: underline

**Trust Row** (below CTAs, 40px height):
- 3 badges in row: Lock icon + "SSL Secure" | eCOGRA icon + "Certified" | Shield + "Fair Play"
- Icons: 24×24px, text 12px, #90ee90, center-aligned, 48px h-spacing

---

### BONUS DISPLAY SECTION (600–800px)
**Background**: #1a2332 (light gray-blue), no image  
**Grid layout**: 3 cards in row (responsive: 1 col mobile, 2 tablet, 3 desktop)
**Card dimensions**: 280×200px, padding 20px, rounded corners 12px

**Card 1: Welcome Bonus**
- Header: "Welcome Bonus" (18px bold, #ffd700)
- Body: "150% Match + 50 Free Spins" (24px bold, #ffffff)
- Footer: "T&Cs Apply" (12px gray, #999999)
- Button: "Claim Now" (100×36px, #00cc88, rounded 6px)
- Border: 2px solid #2d3e50
- Hover: scale 1.05, shadow +4px

**Card 2: Weekly Reload**
- Header: "Every Wednesday" (18px bold, #ffd700)
- Body: "25% Reload up to $500" (24px bold, #ffffff)
- Footer: "Min. deposit $20" (12px gray)
- Button: "Deposit Today" (100×36px, #00cc88)

**Card 3: VIP Rewards**
- Header: "Loyalty Program" (18px bold, #ffd700)
- Body: "Earn Points. Unlock Tier." (24px bold, #ffffff)
- Footer: "See details" (12px gray, underline on hover)
- Button: "Join VIP" (100×36px, #00cc88)

---

### GAME SHOWCASE SECTION (800–1200px)
**Background**: #0a1e2e (dark), full width  
**Title**: "Popular Games" (36px bold, #ffffff, left-aligned, 40px top margin)

**Horizontal scrollable carousel** (or 3-col grid on desktop):
- **Game card** (220×280px each, rounded 8px, overflow hidden):
  - Image: Game screenshot (220×200px)
  - Title: 16px bold, #ffffff, 12px padding
  - Category badge: "Slots" / "Table" / "Live" (12px, #ffd700 text on #16213e bg, border-radius 4px)
  - Play button overlay: 60×60px circle, centered on image, opacity 0 → 1 on hover, #ffd700
  
- **Scroll indicators** (if carousel): Left/right chevron buttons (40×40px, #ffd700, positioned outside carousel)
- **View All Games link**: 16px, #ffd700, below carousel, hover underline

---

### SIGNUP FORM SECTION (1200–1400px)
**Background**: Light gradient (#1a2332 → #0a1e2e horizontal)  
**Container**: centered, max-width 600px, padding 40px, rounded 12px, border 1px #2d3e50

**Form title**: "Create Your Account" (32px bold, #ffffff, 20px bottom margin)

**Fields** (each 100% width, 8px spacing):
1. **Email** (input, 48px height, 14px text)
   - Placeholder: "Enter email"
   - Validation: Real-time, shows checkmark (#00cc88) or error (#ff6b6b)
   - Accessible label: visible, 14px, #e8e8e8, above field

2. **Password** (input, 48px height, masked by default)
   - Toggle show/hide icon (eye icon, 20×20px, right-aligned inside field)
   - Strength indicator: 4px bar below, color gradient (red → yellow → green)

3. **Country/Region** (dropdown, 48px height)
   - Pre-filled based on GeoIP (server-side)
   - Shows "Not available in your region" if restricted (error state, red border)
   - Accessible via arrow keys + Enter

4. **Age Verification** (checkbox + text, 18px)
   - "I confirm I am 18+" (required, WCAG AA compliant)
   - Checkbox 24×24px, focus ring 2px #ffd700

5. **Responsible Gaming Checkbox** (18px)
   - "I accept Responsible Gaming Terms"
   - Link to modal overlay on click (no page load)

6. **Terms & Conditions** (18px)
   - "I agree to Terms & Privacy" (required)
   - Two links: underlined, #ffd700, hover color #ffed4e

**Submit Button**: Full width, 56px height, 18px bold text, #ffd700 bg / #0a1e2e text
- Disabled state: opacity 0.5, cursor not-allowed (until all fields valid + checks ticked)
- Loading state: spinner (16px) inside button, text fade

**Footer text below form**: "Secure signup. No spam. See our Privacy Policy." (12px, #999999)

---

### TRUST SIGNALS SECTION (1400–1550px)
**Background**: #16213e (dark slate)  
**Layout**: Horizontal flex, 4 columns (responsive: 2 cols tablet, 1 col mobile)

**Each signal**:
- Icon (48×48px, centered)
- Label (16px bold, #ffffff)
- Description (13px, #cccccc, max-width 120px, centered)

**Signal 1**: Lock icon → "Bank-Level Security" → "256-bit SSL encryption"  
**Signal 2**: Certificate icon → "eCOGRA Certified" → "Independent audits"  
**Signal 3**: Helpline icon → "24/7 Support" → "Live chat, email, phone"  
**Signal 4**: Green leaf icon → "Responsible Gaming" → "Limits & self-exclusion tools"

Hover: icon color shift to #ffd700, scale 1.1

---

### RESPONSIBLE GAMING BANNER (1550–1620px)
**Background**: #2d3e50 (medium gray-blue)  
**Content**: Centered, max-width 800px
- **Headline**: "Play Responsibly" (24px bold, #ffd700)
- **Text**: "Set limits. Take breaks. Get help if needed." (16px, #e8e8e8)
- **Link**: "Gambling Addiction Resources" (16px, #ffd700, underline on hover, opens external resource in new tab)
- **Stats row** (small text, 12px): "Helpline: 1-800-GAMBLER | Self-Exclude in Seconds"

---

### FOOTER (1620–1750px)
**Background**: #0a1e2e (darkest)  
**4-column layout** (responsive: 1 col mobile):

**Col 1: About**
- Logo (120×32px)
- 2–3 sentences about casino (14px, #cccccc)

**Col 2: Quick Links**
- Header: "Company" (14px bold, #ffffff)
- Links: About | Careers | Blog | Press (13px, #ffd700, hover underline)

**Col 3: Games**
- Header: "Games" (14px bold, #ffffff)
- Links: Slots | Table Games | Live Casino | Sports (13px, #ffd700)

**Col 4: Legal**
- Header: "Compliance" (14px bold, #ffffff)
- Links: Terms & Conditions | Privacy Policy | Cookie Policy | Responsible Gaming (13px, #ffd700)

**Bottom bar** (40px):
- Centered copyright (12px, #666666)
- Social icons (24×24px, 16px spacing): LinkedIn, Twitter, Facebook (hover: fill #ffd700)

---

## COLORS

| Element | Color | Hex | Usage |
|---------|-------|-----|-------|
| **Primary Background** | Dark Navy | #0a1e2e | Page BG, hero, footer |
| **Secondary Background** | Dark Slate | #16213e | Sections, cards bg |
| **Tertiary Background** | Light Gray-Blue | #1a2332 | Bonus section, panels |
| **Accent / CTA** | Gold | #ffd700 | Buttons, links, highlights |
| **Accent Hover** | Bright Gold | #ffed4e | On hover/focus states |
| **Success** | Bright Green | #00cc88 | Validation, confirm states |
| **Error** | Red | #ff6b6b | Warnings, restrictions |
| **Primary Text** | White | #ffffff | Headings, high priority |
| **Secondary Text** | Light Gray | #e8e8e8 | Body text, subheads |
| **Tertiary Text** | Medium Gray | #cccccc | Descriptions, footer links |
| **Disabled Text** | Dark Gray | #999999 | Disabled states, fine print |
| **Border / Divider** | Slate | #2d3e50 | Cards, form inputs |
| **Focus Ring** | Gold | #ffd700 | WCAG AA focus indicator, 2px |

**Contrast checks**:
- White (#ffffff) on Navy (#0a1e2e): 21:1 ✓
- Gold (#ffd700) on Navy (#0a1e2e): 9.2:1 ✓
- Light Gray (#e8e8e8) on Navy (#0a1e2e): 16:1 ✓
- Dark text on Gold: 12:1 ✓

---

## COMPONENTS

### 1. PRIMARY BUTTON (CTA)
**States**:
- **Default**: Width 180px | Height 56px | Bg #ffd700 | Text #0a1e2e (18px bold, sans-serif) | Border-radius 6px | Box-shadow 0 4px 8px rgba(0,0,0,0.2)
- **Hover**: Brightness +10% | Box-shadow 0 6px 12px rgba(255,215,0,0.3) | Cursor pointer
- **Active/Pressed**: Scale 0.98 | Box-shadow inset 0 2px 4px rgba(0,0,0,0.1)
- **Disabled**: Opacity 0.5 | Cursor not-allowed | No shadow
- **Focus**: Outline 2px solid #ffd700 | Outline-offset 2px (keyboard nav)
- **Loading**: Icon spinner (16×16px, rotating, 1s duration) + text opacity 0.6

**Accessibility**: ARIA-label, semantic `<button>`, keyboard trigger (Enter/Space)

---

### 2. SECONDARY BUTTON (Text Link)
**States**:
- **Default**: Text 16px | Color #ffd700 | No underline | Cursor pointer
- **Hover**: Text-decoration underline | Color #ffed4e
- **Active**: Scale 0.98
- **Focus**: Outline 2px solid #ffd700 | Outline-offset 2px
- **Visited** (if `<a>`): Color stays #ffd700 (casino rule, not browser default)

---

### 3. CARD (Bonus/Game)
**Layout**:
- Width: 280px (bonus) / 220px (game) | Padding: 20px | Border-radius: 8–12px | Border: 2px solid #2d3e50
- **Default**: Bg #16213e | Box-shadow 0 2px 4px rgba(0,0,0,0.3)
- **Hover**: Transform scale(1.05) | Box-shadow 0 8px 16px rgba(255,215,0,0.15)
- **Transition**: All 0.3s ease-out

---

### 4. FORM INPUT (Text, Email, Password)
**Layout**: 100% width | Height 48px | Padding 12px 16px | Font 14px | Border-radius 4px
- **Default**: Bg #1a2332 | Border 2px solid #2d3e50 | Color #e8e8e8 | Placeholder #666666
- **Focus**: Border 2px solid #ffd700 | Box-shadow 0 0 0 2px rgba(255,215,0,0.1) | Outline none
- **Error**: Border 2px solid #ff6b6b | Bg tint #ff6b6b 10% opacity
- **Disabled**: Opacity 0.6 | Cursor not-allowed | Bg #0a1e2e
- **Valid**: Border-left 4px solid #00cc88 | Right-aligned checkmark icon (16×16px, #00cc88)

**Label** (above field): 14px bold | Color #e8e8e8 | Margin-bottom 8px | Visibly associated (required asterisk in red)

---

### 5. DROPDOWN / SELECT
**Layout**: 100% width | Height 48px | Padding 12px 16px | Font 14px | Border-radius 4px
- **Default**: Bg #1a2332 | Border 2px solid #2d3e50 | Color #e8e8e8 | Chevron icon right-aligned (16×16px, #999999)
- **Focus**: Border 2px solid #ffd700 | Outline none
- **Expanded**: Dropdown list appears below | Max-height 240px (scrollable) | Bg #16213e | Item hover bg #2d3e50
- **Selected**: Checkmark left of text (16×16px, #ffd700)
- **Disabled item**: Opacity 0.5 | Cursor not-allowed

---

### 6. CHECKBOX
**Layout**: 24×24px | Border-radius 4px | Margin-right 12px (inline with label)
- **Default**: Bg #1a2332 | Border 2px solid #2d3e50 | Cursor pointer
- **Hover**: Border-color #999999
- **Checked**: Bg #ffd700 | Checkmark icon (white, 16×16px, centered)
- **Focus**: Outline 2px solid #ffd700 | Outline-offset 2px
- **Disabled**: Opacity 0.5 | Cursor not-allowed

**Label text** (adjacent, right-aligned): 14px | Color #e8e8e8 | Clickable target (entire label area)

---

### 7. BANNER / ALERT
**Geo-restriction banner** (if applicable, top of hero):
- **Layout**: Full width | Height 56px | Padding 12px 24px | Display flex (center-aligned)
- **Default**: Bg #ff6b6b | Border-bottom 4px solid #c92a2a | Text white 16px bold | Icon (warning) 24×24px left | Dismiss button (×, 20×20px, right)
- **Hover**: Brightness +5%
- **Click dismiss**: Fade-out 0.3s, then remove from DOM

---

### 8. CAROUSEL / SCROLL INDICATOR
**Left/Right Chevron Buttons** (if carousel):
- **Layout**: 40×40px circles | Positioned outside carousel (left/right) | Bg #1a2332 | Border 2px solid #2d3e50
- **Icon**: Chevron (24×24px, #ffd700, center-aligned)
- **Hover**: Border-color #ffd700 | Bg #16213e
- **Disabled** (at edges): Opacity 0.3 | Cursor not-allowed | Border-color #666666

---

### 9. MODAL / OVERLAY (Responsible Gaming, T&Cs)
**Layout**: Fixed, full-screen | Bg rgba(0,0,0,0.7) | Fade-in 0.3s
- **Modal box**: Max-width 600px | Bg #16213e | Border 2px solid #2d3e50 | Border-radius 12px | Padding 40px | Centered (flexbox)
- **Close button**: (×, 24×24px, top-right corner, hover color #ffd700)
- **Content**: Scrollable if > viewport height
- **Focus trap**: Keyboard nav (Tab) cycles through buttons only
- **Escape key**: Closes modal

---

### 10. MICRO-INTERACTIONS

#### Password Strength Indicator
- 4px bar below password field | Width 100% | Transitions color 0.3s
- **Colors**: Red (#ff6b6b, 0–33%) → Yellow (#ffb700, 33–66%) → Green (#00cc88, 66%+)
- **Trigger**: On every keystroke

#### Real-time Email Validation
- Right-aligned icon (16×16px) appears as user types
- **States**: 
  - Invalid format: Red (#ff6b6b) × icon
  - Valid format: Green (#00cc88) ✓ icon
  - Transition: Fade + scale 0.8→1.0 (0.2s)

#### Form Error Animation
- Field shakes slightly on invalid submit (translate -4px, 0 then +4px, 0, repeat 2x in 0.3s)
- Error text appears below field (12px, red, fade-in 0.2s)

#### Button Loading State
- On form submit, button text opacity fades 0.6, spinner (16×16px) rotates continuously (1s linear loop)
- Button disabled: Cursor not-allowed

#### Card Hover Lift
- On hover (mouse or keyboard focus): `transform: scale(1.05) translateY(-4px)` (0.3s cubic-bezier)
- Shadow deepens: `0 8px 16px rgba(255,215,0,0.15)`

#### Icon Color Shift
- Trust signal icons: On hover, color #999999 → #ffd700 (0.2s ease)

#### Scroll-triggered Fade-in
- Game cards, bonus cards: Fade-in (opacity 0→1) + slight translateY (20px up) as section enters viewport (0.5s, staggered 50ms per card)

---

## INTERACTIONS

### Click Behaviors

| Element | Trigger | Result |
|---------|---------|--------|
| **Create Free Account (Hero)** | Click / Enter / Space | Scroll to form section OR open modal overlay with form (TBD per flow) |
| **Explore Games First** | Click | Smooth scroll to Game Showcase section |
| **Claim Now / Deposit Today / Join VIP** | Click | Open bonus detail page OR redirect to deposit form (in new context) |
| **Checkbox (Age Verify)** | Click / Space | Toggle check, enable/disable submit button logic |
| **Country Dropdown** | Click / Enter | Expand list; if restricted region detected, show error message inline & disable submit button |
| **Play Button (Game Card)** | Click / Enter | Redirect to game detail page or open game in lightbox (if preview available) |
| **View All Games Link** | Click | Navigate to full games library page |
| **Trust Signal Badge** | Click (if link) | Open modal with certification details (e.g., eCOGRA audit info) |
| **Responsible Gaming Link** | Click | Open external resource in new tab (e.g., gamblinghelponline.org) |
| **Form Submit Button** | Click / Enter (if focus) | Validate all fields; if any error, shake & highlight fields; if valid, disable button + show spinner + POST to backend |
| **Modal Close (×)** | Click / Escape key | Fade-out modal, return focus to trigger element |
| **Social Icon** | Click | Navigate to casino's social media (new tab) |
| **Cookie Policy / Privacy Link** | Click | Open legal document (new tab or modal) |

---

### Hover Behaviors

| Element | Trigger | Result |
|---------|---------|--------|
| **Primary Button** | Hover | Brightness +10%, shadow deepen, cursor pointer |
| **Secondary Link** | Hover | Underline appears, text color #ffed4e |
| **Bonus/Game Card** | Hover | Scale 1.05, shadow +4px, play icon fade-in (for games) |
| **Form Input** | Hover | Subtle border color shift to #999999 (pre-focus) |
| **Chevron Button** | Hover | Border-color #ffd700, bg #16213e |
| **Trust Signal Icon** | Hover | Color shift to #ffd700, scale 1.1 |
| **Dropdown Item** | Hover | Bg #2d3e50, cursor pointer |
| **Footer Link** | Hover | Text color #ffed4e, underline |

---

### Keyboard Navigation

| Key | Behavior |
|-----|----------|
| **Tab** | Cycle forward through all interactive elements (buttons, links, inputs, checkboxes); visible focus ring (#ffd700, 2px, 2px offset) |
| **Shift+Tab** | Cycle backward |
| **Enter / Space** | Activate button, toggle checkbox, select dropdown option, open modal |
| **Arrow Up/Down** | Navigate dropdown options (if expanded) |
| **Escape** | Close modal, collapse dropdown |
| **Letter Key (A–Z)** | Jump to first option in dropdown starting with that letter |

---

### Focus States
- **All interactive elements**: 2px solid #ffd700 outline | 2px offset | No default browser outline (outline: none, then add custom)
- **High contrast**: Gold (#ffd700) on all backgrounds passes WCAG AA (min 4.5:1 ratio)
- **Visible by default**: Never hidden; never low-contrast

---

## STYLE NOTES

### Typography

| Element | Font | Size | Weight | Line-height | Color |
|---------|------|------|--------|-------------|-------|
| **H1 (Hero)** | Inter, sans-serif | 52px | 700 | 1.2 | #ffffff |
| **H2 (Section)** | Inter, sans-serif | 36px | 700 | 1.3 | #ffffff |
| **H3 (Card/Label)** | Inter, sans-serif | 18px | 700 | 1.4 | #ffffff / #ffd700 |
| **Body** | Inter, sans-serif | 16px | 400 | 1.6 | #e8e8e8 |
| **Small/Caption** | Inter, sans-serif | 14px | 400 | 1.5 | #cccccc |
| **Tiny (Fine Print)** | Inter, sans-serif | 12px | 400 | 1.4 | #999999 |
| **Button Text** | Inter, sans-serif | 18px | 700 | 1.0 | #0a1e2e |
| **Input Placeholder** | Inter, sans-serif | 14px | 400 | 1.5 | #666666 |

**Font stack**: `Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`
**Fallback**: Clean, modern sans-serif system fonts

### Spacing & Grid

- **Base unit**: 8px (all spacing multiples of 8px)
- **Padding standard**: 16px (2 units) or 24px (3 units)
- **Margin standard**: 24px (section spacing) or 16px (component spacing)
- **Button padding**: 12px horizontal | 16px vertical (inside button text area)
- **Card padding**: 20px (internal)
- **Form field spacing**: 16px vertical gap between fields

### Border Radius

- **Buttons / Form inputs / Modals**: 6px (slight roundness, modern)
- **Cards**: 8–12px (softer, friendlier feel)
- **Icons / badges**: 4px (subtle)
- **Checkboxes**: 4px

### Shadows

- **Light shadow** (default cards, inputs): `0 2px 4px rgba(0,0,0,0.3)`
- **Medium shadow** (hover cards, buttons): `0 4px 8px rgba(0,0,0,0.3)`
- **Deep shadow** (on-hover lift): `0 8px 16px rgba(0,0,0,0.3)` or `rgba(255,215,0,0.15)` for gold tint
- **Focus ring** (no shadow, outline only)

### Transitions & Animations

- **Micro-interactions**: 0.2–0.3s (button hover, text change)
- **Modal/Overlay**: 0.3s fade-in/out
- **Card scale/lift**: 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94) (ease-out)
- **Form shake (error)**: 0.3s (2 oscillations, -4px to +4px on X-axis)
- **Spinner (loading)**: 1s linear, continuous rotation
- **Scroll-triggered fade**: 0.5s ease-out, staggered 50ms between cards

### Responsive Breakpoints

- **Mobile** (0–640px): Single-column layout | Hero 70vh | Cards stack vertically | Form 100% width | Nav collapses to hamburger menu
- **Tablet** (641–1024px): 2-column grids | Hero 80vh | Form max-width 500px | Nav visible but compact
- **Desktop** (1025px+): Full 3-column layout | Hero 100vh | Form max-width 600px | All sections 100% width

### Accessibility Details

- **Color alone**: Never conveys critical info (always pair with icon, text, or state)
- **Contrast**: All text ≥ 4.5:1 (WCAG AA); links ≥ 3:1 (WCAG AA for large text)
- **Focus visible**: On all interactive elements, never hidden
- **Semantic HTML**: Use `<button>`, `<a>`, `<input>`, `<label>`, `<form>` properly
- **ARIA labels**: On icon-only buttons, form fields, modals (role="dialog")
- **Skip links**: "Skip to main content" link (visually hidden but keyboard-accessible)
- **Form validation**: Real-time feedback + summary of errors on submit
- **Motion**: Reduce animations if `prefers-reduced-motion: reduce` CSS media query detected

### Overall Feeling

**Premium, trustworthy, dark, energetic.**
- Dark navy & slate palette conveys security & sophistication.
- Gold accents add luxury & draw focus to CTAs.
- Clean spacing & modern font create professional feel.
- Smooth animations & hover states feel responsive & polished—not sluggish.
- Responsible gaming messaging visible but non-intrusive (respects user autonomy).
- Micro-interactions reward exploration (hover effects, validation feedback).
- No clutter: hierarchy is clear, CTAs obvious, trust signals prominent.

---

## ADDITIONAL NOTES FOR DEVELOPER

1. **Geolocation logic**: Server-side MaxMind GeoIP2 check determines if country is restricted; pass result as data attribute on body (e.g., `data-geo-allowed="true"` or `false"`). Show/hide geo-alert banner based on this.

2. **Form submission**: On submit, validate all fields client-side first. Show inline errors (red border + text below field). Only enable submit button when all required fields valid + checkboxes ticked. Once clicked, disable button, show spinner, POST to backend. Backend returns success/error; if error, display banner at top of form. If success, redirect or show confirmation.

3. **Modal overlay**: Use semantic `<dialog>` element or `role="dialog"` on div. Trap focus inside modal. Close on Escape or close button click. Return focus to trigger element when closed.

4. **Carousel**: If implemented as scrollable div (not slick/swiper library), ensure left/right chevron buttons work via keyboard (Enter/Space) + mouse click. Scroll position tracked by JS; disable chevron at edges.

5. **Countdown timer** (if bonus has expiry): Show in bonus card header, update every second, turn red when < 1 hour remaining.

6. **Dark mode assumption**: Design assumes always-dark theme. If light-mode toggle added later, swap hex values (e.g., #ffffff ↔ #0a1e2e), but maintain contrast ratios.

7. **Email validation**: Real-time (debounce 300ms). Check format (`/^[^\s@]+@[^\s@]+\.[^\s@]+$/`); once valid, show green checkmark + fade. Invalid shows red ×. Server-side re-validation on submit.

8. **Password strength**: Calc on input; show bar color + label ("Weak" / "Medium" / "Strong"). Criteria: 8+ chars, mixed case, number, special char. Visual feedback, no hard requirement (user can submit weak password, but warning shown).

9. **Smooth scroll**: On "Explore Games First" click, use `scrollIntoView({ behavior: 'smooth' })` or Lenis library.

10. **Performance**: Lazy-load game card images (below fold). Preload hero video (or use still image + play on hover). Minify CSS. Use Cloudflare Pages/Vercel for fast delivery.