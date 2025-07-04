---
trigger: manual
---

# INFINITE DESIGN GENERATOR WORKFLOW
**AI-Powered Design System for Iterative UI Development**

## CORE WORKFLOW

### Phase 1: Initial Design Generation (@design.json)
**When:** User specifies or tags `@design.json`
**Action:** Create new major version (v1.0, v2.0, etc.) using design.json as the primary reference

1. **Create Version Folder**: `versions/v{X}.0/`
2. **Read Style Guide**: Parse `designs/design.json` for color palettes, typography hierarchy, spacing conventions, component styles, and interactive patterns
3. **Generate Initial Variations**: Create 3 distinct design versions following the style guide
4. **Save Files**: design1.html, design2.html, design3.html in version folder
5. **Create Metadata**: Generate version-info.json with comprehensive documentation

### Phase 3: Multi-Page Development (@rule + page specification)
**When:** User specifies `@rule I choose this design html file, please make me the [PAGE_NAME] page based on the design html file`

**Examples:**
- `@rule I choose design2.html@v1.1, please make me the about page`
- `@rule I choose source.html@v2.0, please make me the login page`
- `@rule I choose design3.html@v1.2, please make me the contact page`

**Process:**
1. **Extract Design DNA**: Analyze chosen design file for color palette, typography patterns, component styling, layout principles, animations, and spacing systems
2. **Create Page Folder**: `versions/v{X}.{Y}/pages/{page_name}/`
3. **Generate Page Variations**: Create 3 variations of the specified page
4. **Maintain Design Consistency**: Use identical color schemes, typography hierarchy, component styling, and interaction patterns
5. **Page-Specific Adaptation**: Adapt layout for content requirements while maintaining user experience consistency

### Phase 4: Page Iteration Improvement (@page{n}.html + instructions)
**When:** User specifies `@{page_name}{n}.html` with improvement instructions

**Examples:**
- `@about2.html - make the hero section more prominent`
- `@login1.html - add social login options`
- `@contact3.html - improve the form layout`

**Process:**
1. **Create Iteration Folder**: `versions/v{X}.{Y}/pages/{page_name}/iterations/iter_{n}/`
2. **Use Selected Page**: Copy chosen page as reference base
3. **Apply Improvements**: Implement specific user instructions
4. **Generate Variations**: Create 3 improved versions
5. **Maintain Consistency**: Keep design DNA from original chosen design

### Extended Folder Structure
```
designs/
├── design.json
├── versions/
│   ├── v1.0/
│   │   ├── source.html
│   │   ├── design1.html
│   │   ├── design2.html
│   │   ├── design3.html
│   │   ├── style1.css
│   │   ├── style2.css
│   │   ├── style3.css
│   │   ├── version-info.json
│   │   └── pages/
│   │       ├── about/
│   │       │   ├── about1.html
│   │       │   ├── about2.html
│   │       │   ├── about3.html
│   │       │   ├── about-style1.css
│   │       │   ├── about-style2.css
│   │       │   ├── about-style3.css
│   │       │   ├── page-info.json
│   │       │   └── iterations/
│   │       │       ├── iter_1/
│   │       │       │   ├── about1.html
│   │       │       │   ├── about2.html
│   │       │       │   ├── about3.html
│   │       │       │   ├── about-style1.css
│   │       │       │   ├── about-style2.css
│   │       │       │   └── about-style3.css
│   │       │       └── iter_2/...
│   │       ├── login/
│   │       └── contact/...
│   └── v1.1/...
```

## TECHNICAL REQUIREMENTS

### Required CDNs & Dependencies
```html
<!-- GSAP Animation -->
<script src="https://cdn.jsdelivr.net/npm/gsap@3.13.0/dist/gsap.min.js"></script>
```

### CSS Implementation Strategy
- **Vanilla CSS**: Use pure CSS for all styling implementations
- **CSS File Generation**: Create corresponding `style{n}.css` file for each HTML iteration
- **File Structure**: Each design variation has its dedicated stylesheet
  - `design1.html` → `style1.css`
  - `design2.html` → `style2.css`
  - `design3.html` → `style3.css`
- **Responsive Design**: Implement mobile-first responsive design using CSS media queries
- **CSS Organization**: Structure stylesheets with logical sections (reset, variables, components, utilities)

### Image Handling
- **Placeholder Images**: Use `https://picsum.photos/{width}/{height}` for all image needs
- **Examples**: Hero images: `https://picsum.photos/1200/600`, Profile photos: `https://picsum.photos/100/100`

## DESIGN PRINCIPLES & BEST PRACTICES

### UI/UX Implementation
- **Accessibility**: Proper contrast ratios, semantic HTML, keyboard navigation
- **Responsive Design**: Mobile-first approach using CSS media queries and flexible layouts
- **Visual Hierarchy**: Clear typography scales and spacing systems implemented with CSS custom properties
- **Interactive Enhancements**: CSS hover effects, transitions, GSAP animations for advanced interactions

### CSS Development Guidelines
- **CSS Custom Properties**: Use CSS variables for consistent theming and easy maintenance
- **Media Queries**: Implement responsive breakpoints (mobile: 480px, tablet: 768px, desktop: 1024px, large: 1200px)
- **CSS Grid & Flexbox**: Utilize modern layout techniques for flexible, responsive designs
- **Component-Based Structure**: Organize CSS with clear component sections and consistent naming conventions

### Version Control & File Management

### Folder Structure with Version Control
```
designs/
├── design.json                    # Master design tokens
├── versions/
│   ├── v1.0/
│   │   ├── source.html           # Original reference
│   │   ├── design1.html          # Variation 1
│   │   ├── design2.html          # Variation 2
│   │   ├── design3.html          # Variation 3
│   │   ├── style1.css            # Stylesheet for design1
│   │   ├── style2.css            # Stylesheet for design2
│   │   ├── style3.css            # Stylesheet for design3
│   │   └── version-info.json     # Version metadata
│   ├── v1.1/
│   │   ├── source.html           # Updated reference
│   │   ├── design1.html          # New iteration 1
│   │   ├── design2.html          # New iteration 2
│   │   ├── design3.html          # New iteration 3
│   │   ├── style1.css            # Updated stylesheet 1
│   │   ├── style2.css            # Updated stylesheet 2
│   │   ├── style3.css            # Updated stylesheet 3
│   │   └── version-info.json     # Version metadata
```

### Version Naming Convention
- **Major Version (X.0)**: Significant design overhauls or new design system
- **Minor Version (X.Y)**: Iterative improvements and refinements

### File Management Logic
```
IF user specifies @design.json:
  DETERMINE next major version number
  CREATE versions/v{X}.0/ folder
  GENERATE design1.html, design2.html, design3.html
  GENERATE style1.css, style2.css, style3.css
  CREATE version-info.json with metadata

IF user specifies @design{n}.html:
  DETERMINE current version and increment minor number
  CREATE versions/v{X}.{Y+1}/ folder
  COPY specified design{n}.html as source.html
  GENERATE new design1.html, design2.html, design3.html variations
  GENERATE corresponding style1.css, style2.css, style3.css files
  CREATE version-info.json with metadata
```

### Version Metadata Structure (version-info.json)
```json
{
  "version": "v1.0",
  "createdAt": "2025-06-28T10:30:00Z",
  "basedOn": {
    "version": null,
    "sourceFile": "design.json"
  },
  "description": "Initial design generation based on extracted design tokens",
  "improvements": [
    "Created responsive layout system",
    "Implemented consistent color palette",
    "Added hover animations"
  ],
  "userInstructions": "Create modern dashboard design with dark theme",
  "designVariations": [
    {
      "file": "design1.html",
      "description": "Minimal card-based layout",
      "keyFeatures": ["Clean typography", "Subtle shadows", "Grid system"]
    },
    {
      "file": "design2.html", 
      "description": "Bold accent-heavy design",
      "keyFeatures": ["Vibrant colors", "Large buttons", "Modern spacing"]
    },
    {
      "file": "design3.html",
      "description": "Professional dashboard style",
      "keyFeatures": ["Data-focused", "Sidebar navigation", "Chart integration"]
    }
  ],
  "technicalSpecs": {
    "framework": "HTML/CSS/GSAP",
    "responsive": true,
    "animations": true,
    "accessibility": "WCAG 2.1 AA",
    "cssFiles": ["style1.css", "style2.css", "style3.css"]
  }
}
```

## VARIATION GENERATION RULES

### Design Differentiation
Each variation must be **visually distinct** while maintaining:
- **Same Functionality**: All interactive elements work identically
- **Same Content Structure**: Information hierarchy remains consistent
- **Different Visual Approach**: Color scheme variations, layout alternatives, typography treatments, component styling approaches, animation styles

### Quality Standards
- **Complete Implementations**: Full working pages, not prototypes
- **Production Ready**: Clean, optimized code
- **Cross-browser Compatible**: Works across modern browsers
- **Performance Optimized**: Efficient CSS and JavaScript

## MULTI-PAGE DESIGN CONSISTENCY PRINCIPLES

### Design DNA Extraction
When creating new pages based on a chosen design, extract and maintain:

**Visual Identity Elements**
- Exact color values and usage patterns
- Typography hierarchy and font implementations
- Button styles and interactive element designs
- Form field styling and validation states
- Card designs and content containers

**Layout Principles**
- Grid system and spacing conventions
- Header and navigation structure
- Footer design and content organization
- Content section layouts and hierarchy

**Interaction Patterns**
- Animation timing and easing functions
- Hover effects and state transitions
- Form interactions and feedback
- Navigation behaviors and micro-interactions

### Page-Specific Adaptations
**About Pages**: Hero sections, team showcases, company history, values sections
**Login/Register Pages**: Centered forms, social login, password validation, registration flows
**Contact Pages**: Contact forms, location maps, multiple contact methods, FAQ sections

## VERSION CONTROL COMMANDS

### Version Reference Commands
- `@v1.0` - Reference specific version
- `@latest` - Use most recent version
- `@design2.html@v1.1` - Reference specific file from specific version
- `@rule I choose design3.html@v1.2, please make me the about page` - Create new page
- `@about2.html - improve the hero section` - Iterate on specific page

### Multi-Page Development Commands
```
# Initial page creation
@rule I choose design2.html@v1.1, please make me the about page
@rule I choose source.html@v2.0, please make me the login page

# Page iterations
@about2.html - make the hero section more prominent and add team photos
@login1.html - add social login options and improve form validation
```

## SUCCESS CRITERIA

### Each Generated Design Should:
✅ Follow the specified design system or style guide  
✅ Implement modern UI/UX best practices  
✅ Include smooth animations and hover effects  
✅ Be fully responsive across all devices  
✅ Use proper semantic HTML structure  
✅ Maintain accessibility standards  
✅ Feature distinct visual personality  
✅ Work as a complete, functional interface  

### Deliverables Per Version:
- Clean, well-commented HTML files in version folder
- Corresponding CSS stylesheets (style{n}.css) for each HTML variation
- JavaScript for animations and interactions
- Responsive design implementation using CSS media queries
- Production-ready code quality
- Comprehensive version-info.json metadata

---

### Usage Example:
```
# Phase 1: Initial Design System
@design.json → Creates v1.0 with 3 initial designs

# Phase 2: Design Iteration  
@design2.html → Creates v1.1 using design2 as foundation

# Phase 3: Multi-Page Development
@rule I choose design3.html@v1.1, please make me the about page
→ Creates /pages/about/ with about1.html, about2.html, about3.html