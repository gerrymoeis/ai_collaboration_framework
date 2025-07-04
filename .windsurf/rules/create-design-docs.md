---
trigger: manual
---

---
trigger: manual
---

# CREATE DESIGN DOCUMENTATION GENERATOR

## OBJECTIVE
Generate comprehensive design documentation for a specific version/iteration that you choose or like, creating a professional style guide and implementation reference.

## TRIGGER USAGE
**Command Format**: `@create-docs @v{X}.{Y} @design{n}.html`
**Examples**: 
- `@create-docs @v1.2 @design3.html`
- `@create-docs @v2.0 @design1.html`

## DOCUMENTATION GENERATION

### Input Analysis
1. **Load Specified Version**: Read from `versions/v{X}.{Y}/`
2. **Extract Target Design**: Analyze specified design{n}.html file
3. **Reference Design Tokens**: Use `designs/design.json` as foundation
4. **Parse Version Metadata**: Include version-info.json context

### Generated Documentation Structure

```
docs/
├── v{X}.{Y}-design{n}/
│   ├── style-guide.html          # Visual style guide
│   ├── component-library.html    # Component showcase
│   ├── implementation-guide.md   # Developer reference
│   ├── design-tokens.json        # Extracted tokens from chosen design
│   └── assets/
│       ├── screenshots/          # Component screenshots
│       └── examples/             # Code examples
```

## STYLE GUIDE CONTENT

### 1. Design Overview
- **Project Information**: Name, version, creation date
- **Design Philosophy**: Key principles and approach
- **Visual Identity**: Brand colors, typography, imagery style
- **User Experience Goals**: Target audience and design objectives

### 2. Color System Documentation
```html
<!-- Color palette showcase with hex values, usage notes, accessibility ratings -->
<div class="color-palette">
  <div class="color-swatch">
    <div class="color-preview" style="background: #3B82F6"></div>
    <div class="color-info">
      <h4>Primary Blue</h4>
      <p>Hex: #3B82F6</p>
      <p>Usage: Primary actions, links, highlights</p>
      <p>Accessibility: AA compliant</p>
    </div>
  </div>
</div>
```

### 3. Typography Scale
- **Font families and fallbacks**
- **Heading hierarchy (H1-H6) with examples**
- **Body text variations**
- **Special text treatments**
- **Line height and spacing specifications**

### 4. Component Library
- **Interactive component showcase**
- **Multiple component states** (default, hover, active, disabled)
- **Responsive behavior examples**
- **Usage guidelines and best practices**

### 5. Layout System
- **Grid system documentation**
- **Spacing scale and usage**
- **Responsive breakpoints**
- **Container and wrapper specifications**

## COMPONENT SHOWCASE STRUCTURE

### Interactive Component Library
```html
<!-- Example component documentation -->
<section class="component-showcase">
  <h3>Primary Button</h3>
  <div class="component-preview">
    <!-- Live component example -->
    <button class="btn-primary">Primary Action</button>
  </div>
  <div class="component-variations">
    <!-- Different states -->
    <button class="btn-primary">Default</button>
    <button class="btn-primary hover">Hover</button>
    <button class="btn-primary active">Active</button>
    <button class="btn-primary disabled">Disabled</button>
  </div>
  <div class="component-code">
    <pre><code><!-- HTML implementation --></code></pre>
  </div>
  <div class="component-notes">
    <p>Usage: Primary calls-to-action, form submissions</p>
    <p>Accessibility: Focus visible, keyboard accessible</p>
  </div>
</section>
```

## IMPLEMENTATION GUIDE CONTENT

### Developer Reference (Markdown)
```markdown
# Implementation Guide v{X}.{Y} - Design {n}

## Quick Start
- Design Tokens: Reference design-tokens.json
- Framework: HTML + Tailwind CSS + GSAP
- CDN Requirements: [list of required CDNs]

## Component Implementation

### Button Components
[Detailed implementation instructions with code examples]

### Form Elements
[Input fields, selects, checkboxes implementation]

### Layout Components
[Cards, grids, navigation implementation]

## Animation Guidelines
- Transition timing: 300ms ease-in-out
- Hover effects: Scale, color, shadow changes
- GSAP animations: [specific animation patterns used]

## Responsive Design
- Mobile-first approach
- Breakpoint usage: [specific breakpoint implementations]
- Component adaptations: [how components change across screens]

## Accessibility Compliance
- WCAG 2.1 AA compliance
- Keyboard navigation support
- Screen reader compatibility
- Color contrast requirements
```

## EXTRACTED DESIGN TOKENS

### Enhanced Token Extraction
Generate a design-tokens.json file specifically from the chosen design:

```json
{
  "metadata": {
    "extractedFrom": "v{X}.{Y}/design{n}.html",
    "extractionDate": "timestamp",
    "designVersion": "v{X}.{Y}",
    "sourceDesign": "design{n}"
  },
  "actualImplementation": {
    "colors": {
      "primary": "#actual-color-used",
      "secondary": "#actual-color-used"
    },
    "typography": {
      "headings": "actual-font-stack",
      "body": "actual-font-stack"
    },
    "spacing": {
      "implemented-values": "actual-spacing-used"
    },
    "animations": {
      "transitions": "actual-transition-values",
      "durations": "actual-timing-used"
    }
  },
  "componentTokens": {
    "button": {
      "primary": {
        "background": "token-reference",
        "color": "token-reference",
        "padding": "actual-padding",
        "borderRadius": "actual-radius"
      }
    }
  }
}
```

## GENERATION WORKFLOW

### Step 1: Analysis Phase
1. Load specified version and design file
2. Parse HTML/CSS to extract actual implemented values
3. Cross-reference with original design.json tokens
4. Identify design patterns and component usage

### Step 2: Documentation Creation
1. Generate visual style guide (HTML)
2. Create interactive component library (HTML)
3. Write implementation guide (Markdown)
4. Extract and document actual design tokens (JSON)

### Step 3: Asset Generation
1. Capture component screenshots
2. Create code examples for each component
3. Generate responsive behavior examples
4. Document animation specifications

### Step 4: Quality Assurance
1. Validate all generated documentation
2. Ensure code examples work correctly
3. Check accessibility compliance documentation
4. Verify design token accuracy

## OUTPUT SPECIFICATIONS

### Style Guide Features
- **Interactive Elements**: Hover to see component states
- **Copy-Paste Ready**: Code snippets with copy buttons
- **Responsive Preview**: Toggle between device sizes
- **Accessibility Info**: Color contrast ratios, keyboard support

### Implementation Guide Features
- **Step-by-step Setup**: From CDN inclusion to component usage
- **Best Practices**: Performance, accessibility, maintenance
- **Troubleshooting**: Common issues and solutions
- **Customization**: How to adapt components for different use cases

### Design Token Features
- **Actual Values**: Real implementations, not theoretical
- **Usage Context**: Where and how each token is applied
- **Relationship Mapping**: How tokens relate to each other
- **Implementation Notes**: Framework-specific usage guidance

## QUALITY CHECKLIST

✅ Documentation matches actual implemented design  
✅ All components are properly showcased with states  
✅ Code examples are copy-paste ready and functional  
✅ Design tokens reflect real implementation values  
✅ Accessibility guidelines are clearly documented  
✅ Responsive behavior is thoroughly explained  
✅ Implementation guide provides clear setup instructions  
✅ Visual style guide is comprehensive and professional  

---

**Usage Flow**:
1. Complete design iterations using infinite-design.md
2. Choose your favorite design from any version
3. Run: `@create-docs @v1.2 @design3.html`
4. Get: Complete documentation package for that specific design