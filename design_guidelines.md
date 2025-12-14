# Creative Writing Platform Design Guidelines

## Design Approach

**Hybrid Strategy**: Reference-based aesthetics for public pages + design system efficiency for admin/user dashboards

**Primary References**: 
- Medium (reading experience, article layouts)
- Substack (writer-focused interface)
- Notion (content creation UX)
- Linear (clean dashboard design)

**Design Principles**:
- Celebrate written content with generous whitespace and elegant typography
- Clear distinction between creator workspace and public showcase
- Trust-building design for copyright/payment features
- Community-first visual language

## Typography

**Font Families** (Google Fonts):
- Headlines/Display: "Playfair Display" (serif, literary elegance)
- Body/Interface: "Inter" (sans-serif, readable)
- Code/Monospace: "JetBrains Mono" (for any technical elements)

**Type Scale**:
- Hero/Landing: text-6xl to text-8xl (Playfair Display, font-bold)
- Page Titles: text-4xl to text-5xl (Playfair Display, font-semibold)
- Section Headers: text-2xl to text-3xl (Inter, font-semibold)
- Content Headings: text-xl to text-2xl (Inter, font-medium)
- Body Text: text-base to text-lg (Inter, leading-relaxed)
- Small Text/Meta: text-sm (Inter, font-normal)

## Layout System

**Spacing Primitives**: Use Tailwind units of 2, 4, 8, 12, 16, 24
- Component padding: p-4, p-8
- Section spacing: py-12, py-16, py-24
- Card margins: m-4, m-8
- Grid gaps: gap-4, gap-8

**Container Strategy**:
- Public pages: max-w-7xl (hero), max-w-4xl (reading content)
- Dashboards: max-w-screen-2xl with px-8
- Reading content: max-w-prose for optimal readability

**Grid Patterns**:
- Content cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Creator profiles: grid-cols-2 md:grid-cols-3 lg:grid-cols-4
- Dashboard stats: grid-cols-1 md:grid-cols-2 lg:grid-cols-4
- Article previews: Single column with max-w-4xl

## Component Library

### Navigation
**Public Header**: Full-width, sticky, with logo left, nav center (Browse, Community, Submit), auth buttons right. Height h-16, backdrop-blur effect when scrolling.

**Dashboard Sidebar**: Fixed left sidebar w-64, full-height, with logo top, nav items stacked, user profile bottom. Categories with icons from Heroicons.

### Content Cards
**Submission Card**: Rounded-lg, p-6, shadow-sm border. Title (text-xl font-semibold), excerpt (text-base line-clamp-3), author info with avatar (h-10 w-10 rounded-full), category badge, status indicator.

**Creator Profile Card**: Rounded-xl, p-6, center-aligned. Large avatar (h-24 w-24), name (text-xl), bio (text-sm), published count, "View Works" button.

### Forms & Inputs
**Rich Text Editor**: Full-width container with toolbar (sticky at top), formatting buttons (bold, italic, headings, lists), word count footer. Min-height h-96 for writing area.

**Standard Inputs**: Rounded-lg, px-4 py-3, border-2, focus:ring-2 effect. Labels text-sm font-medium above inputs with mb-2.

**Select Dropdowns**: Rounded-lg with Heroicons chevron-down, custom styling matching inputs.

### Dashboard Components
**Admin Review Queue**: Table layout with columns: thumbnail/preview, title, author, category, submission date, status, actions. Row hover effects, pagination at bottom.

**Statistics Cards**: Rounded-xl, p-6, with icon (h-12 w-12), large number (text-4xl font-bold), label (text-sm), trend indicator.

**Payment Modal**: Centered overlay (max-w-md), rounded-2xl, p-8. Certificate preview, pricing breakdown, Stripe payment element, confirmation button.

### Community Features
**Creator Directory**: Masonry-style grid on desktop, stacked on mobile. Filter bar at top with search, category tags, sort options.

**Published Work Display**: Hero section with full-width title treatment, author byline, publication date. Content in max-w-prose with generous line-height (leading-loose). Category tags inline.

### Buttons
**Primary CTA**: Rounded-lg, px-6 py-3, font-semibold, shadow-md
**Secondary**: Rounded-lg, px-6 py-3, border-2, font-medium
**Text/Ghost**: px-4 py-2, underline-offset-4

### Badges & Tags
**Status Badges**: Rounded-full, px-3 py-1, text-xs font-medium (Draft, Pending, Approved, Published, Rejected)
**Category Tags**: Rounded-md, px-3 py-1.5, text-sm, clickable with hover effect

## Images

**Hero Image**: Full-width, h-96 to h-[32rem], subtle overlay for text readability. Place on homepage showing diverse creators writing/reading. Buttons on hero should have backdrop-blur-md backgrounds.

**Creator Avatars**: Circular (rounded-full), sizes h-10 w-10 (cards), h-24 w-24 (profiles), h-32 w-32 (full profile page). Fallback to initials with generated background.

**Content Thumbnails**: 16:9 aspect ratio, rounded-lg, object-cover. Used in cards and lists. Placeholder for text-only submissions using category-based illustrations.

**Community Banner**: Wide format (3:1), subtle literary-themed illustration or photography (libraries, typewriters, notebooks). Height h-48 to h-64.

**Certificate Preview**: Display mockup certificate design in payment modal showing user's name, work title, unique ID. Dimensions maintaining readable preview in modal context.

**Empty States**: Illustrations for "No submissions yet", "No published works", etc. Centered, max-w-md, with encouraging copy below.

## Accessibility
- All interactive elements meet 44x44px minimum touch targets
- Form inputs have associated labels and error states
- Focus indicators visible on all interactive elements
- ARIA labels for icon-only buttons
- Skip-to-content link for keyboard users
- Consistent heading hierarchy throughout application