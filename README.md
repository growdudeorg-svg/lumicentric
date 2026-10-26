# Anvaya Atelier — Premium Single-Page Interior Design Portfolio

A high-conversion, editorial, single-page portfolio landing page designed and built for an interior design and execution studio based in **Pune, Maharashtra, India**.

## 🌟 Key Architecture & Compliance Highlights

- **Strict Single-Page Architecture**: 100% of website content lives on a continuous, responsive scrollable landing page. Zero external routing or multi-page jumps.
- **Accessible Anchor Navigation**: Smooth scrolling with dynamic sticky header height compensation (`scroll-margin-top`). Active scroll spy highlights links as the user traverses sections.
- **Accessible Project Detail Modal / Drawer**: Deep project case studies open in a keyboard-accessible modal dialog (`role="dialog"`, `aria-modal="true"`) with focus management, ESC-to-close, before/after media, 4K walkthrough preview, verified material specifications, client testimonials, and contextual enquiry hooks.
- **Interactive Before-and-After Split Slider**: Accessible slider with touch/swipe, mouse drag, and keyboard navigation (Left/Right arrows, Home, End). Switchable between 3 Pune transformations (Amanora Penthouse, Wakad Modular Kitchen, Koregaon Park Epoxy Loft).
- **Specialised Flooring & Epoxy Division**: Complete 4-stage engineering walkthrough (Diamond grinding, moisture barrier, metallic pour, PU topcoat), 4 architectural finish systems, ASTM technical benchmarks, and Pune monsoon maintenance guidance.
- **Data-Driven Maintainability**: All projects, services, testimonials, process steps, differentiators, and FAQs are decoupled into structured ES6 modules in `js/data/`. Adding a project never requires restructuring HTML.
- **Conversion-Optimized Contact & WhatsApp**: Enquiry form with Indian phone validation, Pune micro-market locality selector, real-time dynamic WhatsApp message generator, and simulated asynchronous submission with verifiable ticket generation (`ANV-PUN-2026-XXXX`).
- **Mobile Sticky Conversion Dock**: Sticky bottom action bar on mobile devices (Call Now, WhatsApp, Get Quote).
- **Local SEO & Analytics**: LocalBusiness / HomeAndConstructionBusiness JSON-LD schema with Pune coordinates and area served, semantic markup, and custom event logging.

---

## 📁 Directory Structure

```
interior-design-portfolio/
├── index.html                   # Master single-page HTML5 semantic structure
├── package.json                 # Project configuration & npm scripts
├── server.js                    # Lightweight zero-dependency static server
├── test-integrity.js            # Automated verification test script
├── generate-assets.js           # Vector asset generator for high-res architectural media
├── css/
│   ├── main.css                 # Master stylesheet importing modular sheets
│   ├── variables.css            # Design tokens (charcoal, warm stone, burnished bronze)
│   ├── reset.css                # Modern reset & accessible focus styles
│   ├── typography.css           # Editorial Playfair serif & technical Plus Jakarta sans
│   ├── layout.css               # Header, container, grid, and sticky positioning
│   ├── components.css           # Buttons, badges, project cards, service cards, testimonials
│   ├── comparison.css          # Interactive before-and-after split slider
│   ├── modal.css                # Accessible project modal & drawer styles
│   ├── case-study.css           # Deep-dive on-page case studies
│   ├── flooring.css             # Epoxy stages, finishes, and ASTM spec grids
│   ├── form.css                 # Enquiry form, validation, chip selectors, success states
│   └── responsive.css           # Mobile conversion dock, media queries, reduced motion
├── js/
│   ├── app.js                   # Application bootstrap & DOM hydration orchestrator
│   ├── data/
│   │   ├── company.js           # Studio address, phone, WhatsApp, credentials, Pune localities
│   │   ├── services.js          # 6 verified services with deliverables, materials, timelines
│   │   ├── projects.js          # 8 rich Pune projects with verified specs & client quotes
│   │   ├── caseStudies.js       # 3 deep documented case studies
│   │   ├── flooring.js          # Epoxy stages, finishes, ASTM specs, maintenance guide
│   │   ├── process.js           # 6-step project delivery roadmap
│   │   ├── differentiators.js   # 6 evidence-led studio differentiators
│   │   ├── testimonials.js      # Authentic Pune homeowner reviews & society names
│   │   ├── faqs.js              # 8 practical FAQs covering commercials & execution
│   │   └── about.js             # Founding team, philosophy, Baner studio & Bhosari factory
│   └── components/
│       ├── navigation.js        # Sticky header, scroll spy, smooth scroll, mobile drawer
│       ├── comparisonSlider.js  # Draggable & keyboard-accessible split slider
│       ├── portfolio.js         # Category filtering and project card renderer
│       ├── projectModal.js      # Accessible dialog, focus trap, specs table, enquiry hook
│       ├── caseStudyViewer.js   # Deep-dive case study phase explorer
│       ├── flooringExplorer.js  # Epoxy stages, finish cards, ASTM testing
│       ├── faqAccordion.js      # Accessible FAQ accordion (aria-expanded, aria-controls)
│       ├── enquiryForm.js       # Form validation, ticket generation, WhatsApp live sync
│       └── analytics.js         # Custom event dispatcher for tracking interactions
└── assets/
    └── images/                  # 40+ high-definition architectural SVG project renders
```

---

## 🚀 How to Run & Preview

### Method 1: Using the Native Windows PowerShell Server (Zero Dependencies)

Run directly in PowerShell without installing any external runtimes:
```powershell
powershell -ExecutionPolicy Bypass -File .\serve.ps1
```
Or specify a custom port:
```powershell
powershell -ExecutionPolicy Bypass -File .\serve.ps1 -Port 8080
```

### Method 2: Using Node Server

If Node.js is installed:
```bash
node server.js
```
or
```bash
agy-node server.js
```

### Accessing the Web App

Open your browser to:
```
http://localhost:3000
```

### Method 2: Direct Browser Preview

You can also open `index.html` directly in any modern browser (Chrome, Edge, Safari, Firefox).
*(Note: For modern ES6 module imports `type="module"`, running via `server.js` or a local web server is recommended by browser CORS standards).*

---

## 🛠 Adding or Updating Projects

To add a new project, simply open `js/data/projects.js` and add an object to the `PROJECTS_DATA` array:

```javascript
{
  id: "your-project-id",
  title: "The Project Name",
  subtitle: "Brief subtitle",
  category: "residential", // "residential", "modular", "flooring", or "commercial"
  categoryLabel: "Turnkey Residential",
  location: "Kalyani Nagar, Pune",
  area: "2,400 sq.ft.",
  year: "2026",
  completionStatus: "Completed • Turnkey Handover",
  scopeTags: ["Full Turnkey", "Modular Kitchen", "Italian Marble"],
  coverImage: "assets/images/your-cover.svg",
  beforeImage: "assets/images/your-before.svg",
  afterImage: "assets/images/your-after.svg",
  gallery: [...],
  videoWalkthrough: { ... },
  brief: "...",
  challenges: [...],
  designDecisions: [...],
  executionApproach: [...],
  verifiedSpecs: { ... },
  testimonial: { ... }
}
```
The portfolio grid, category filters, and modal dialog will automatically render the new project!
