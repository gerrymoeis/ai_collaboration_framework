---
trigger: manual
---

# DESIGN DOCUMENTATION GENERATOR
**Professional Design System Export & Handoff**

## CORE PURPOSE

Transform your chosen design implementation into production-ready documentation that bridges design and development seamlessly.

## COMMAND SYSTEM

### Basic Usage
```bash
@create-docs @v{X}.{Y} @design{n}.html
```

### Advanced Options
```bash
@create-docs @v1.2 @design3.html --focus=mobile
@create-docs @v2.0 @design1.html --package=complete
@create-docs @v1.1 @design2.html --format=dev-handoff
```

## GENERATED DOCUMENTATION

### File Structure
```
design-docs/{project-name}-v{X}.{Y}-design{n}/
├── 📋 README.md                   # Quick start guide
├── 🎨 style-guide.html           # Interactive visual guide
├── 🧩 component-library.html     # Live component showcase
├── 💻 implementation-guide.md    # Developer reference
├── 🎭 design-tokens.json         # Extracted design system
├── 📦 production-ready/          # Ready-to-use files
└── 📸 screenshots/               # Visual documentation
```

## INTELLIGENT GENERATION PROCESS

### 1. **Design Analysis**
- Extract real implementation values (not theoretical tokens)
- Identify design patterns and component relationships
- Assess accessibility, performance, and responsive behavior
- Understand design philosophy and user experience goals

### 2. **Documentation Creation**
- **Interactive Style Guide** - Professional design system showcase
- **Living Component Library** - Copy-ready code with all states
- **Developer Handoff** - Clear implementation instructions
- **Production Package** - Complete assets and optimized files

### 3. **Quality Assurance**
- Validate all code examples work correctly
- Ensure accessibility compliance documentation
- Cross-reference consistency across all documents
- Performance optimization recommendations

## KEY FEATURES

### Interactive Style Guide
```html
<!-- Enhanced color system with accessibility info -->
<div class="color-swatch" data-color="primary">
  <div class="color-preview"></div>
  <div class="color-info">
    <h4>Primary</h4>
    <code>--color-primary: #3B82F6</code>
    <span class="contrast-ratio">AA ✓</span>
    <div class="usage-tags">
      <span>CTA Buttons</span>
      <span>Links</span>
      <span>Focus States</span>
    </div>
  </div>
</div>
```

### Living Component Library
```html
<!-- Component with interactive states and copy-ready code -->
<div class="component-showcase">
  <div class="component-preview">
    <button class="btn-primary">Primary Button</button>
  </div>
  <div class="component-code">
    <pre><code><!-- Copy-ready HTML --></code></pre>
    <button class="copy-code">Copy Code</button>
  </div>
</div>
```

### Developer Quick Start
```markdown
# 🚀 Implementation Guide

## Setup (2 minutes)
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<link rel="stylesheet" href="styles.css">
```

## Design Tokens
```css
:root {
  --color-primary: #3B82F6;
  --font-family-base: 'Inter', system-ui, sans-serif;
  /* Complete token system */
}
```

## Accessibility: WCAG 2.1 AA compliant
## Performance: ~45KB CSS, ~12KB JS (gzipped)
```

### Enhanced Design Token Export
```json
{
  "metadata": {
    "version": "v1.2",
    "extractedFrom": "design3.html",
    "approach": "modern-minimal"
  },
  "tokens": {
    "colors": {
      "primary": {
        "value": "#3B82F6",
        "usage": ["CTA buttons", "Links"],
        "accessibility": "AA compliant"
      }
    },
    "typography": {
      "h1": {
        "fontSize": "2.5rem",
        "fontWeight": "700",
        "usage": "Page titles"
      }
    },
    "components": {
      "button-primary": {
        "background": "var(--color-primary)",
        "padding": "16px 24px",
        "borderRadius": "8px",
        "states": {
          "hover": "transform: translateY(-2px)",
          "active": "transform: translateY(0)"
        }
      }
    }
  }
}
```

## DOCUMENTATION INTELLIGENCE

### Smart Analysis
- **Design Intent Recognition** - Understand design philosophy automatically
- **Pattern Detection** - Identify reusable component patterns
- **Context Adaptation** - Adjust documentation style for project type
- **Quality Assessment** - Built-in accessibility and performance audits

### Output Formats
- **Standard**: Complete documentation package
- **Dev-Handoff**: Developer-focused implementation guide
- **Design-Tokens**: Token-only export for design tools
- **Component-Library**: Isolated component documentation

## QUALITY STANDARDS

### Documentation Completeness
✅ All design elements documented with working examples  
✅ Copy-paste ready code that works immediately  
✅ WCAG 2.1 AA accessibility compliance verified  
✅ Mobile-first responsive implementation  
✅ Performance optimizations included  
✅ Cross-browser compatibility tested  
✅ Future-proof maintenance guidance  

### Developer Experience
- **Time to Implementation**: Minutes, not hours
- **Zero Configuration**: Works out of the box
- **Self-Explanatory**: Minimal context switching required
- **Production-Ready**: Optimized for performance and accessibility

---

## YOUR ROLE AS DOCUMENTATION ARCHITECT

**Create the definitive design-to-development handoff.**

**Your Documentation Should:**
- **Bridge the Gap** - Translate design vision into implementable code
- **Enable Success** - Make implementation straightforward and error-free
- **Preserve Quality** - Maintain design integrity and performance standards
- **Future-Proof** - Provide maintenance and evolution guidance

**Process:**
1. **Analyze** - Deep dive into the chosen design implementation
2. **Extract** - Pull real values, patterns, and design decisions
3. **Document** - Create comprehensive, interactive documentation
4. **Validate** - Ensure everything works and meets quality standards
5. **Package** - Deliver production-ready assets and guidance

**Remember:** Great documentation transforms inspiration into implementation. Make the developer's life easier while preserving the designer's vision.

---

*This generator creates professional design system exports that serve as the definitive handoff between design and development, ensuring pixel-perfect implementation and long-term maintainability.*