---
trigger: manual
---

# DESIGN SYSTEM EXTRACTION PROMPT

## CORE OBJECTIVE
Extract a comprehensive, production-ready design system from the provided image by identifying visual patterns and creating structured design tokens.

## ANALYSIS FRAMEWORK

### VISUAL INSPECTION PRIORITIES
1. **Color Analysis** - Document all colors with hex values and usage context
2. **Typography Hierarchy** - Identify font families, sizes, weights, and relationships  
3. **Spacing Patterns** - Map consistent spacing units and component relationships
4. **Component Variations** - Catalog button styles, form elements, and interactive states
5. **Layout Structure** - Note grid systems, breakpoints, and container patterns

### EXTRACTION METHODOLOGY
**Step 1: Visual Inventory**
- Scan systematically from top-left to bottom-right
- Group similar elements (buttons, cards, text styles)
- Note recurring patterns and variations
- Identify semantic color usage (success, error, warning)

**Step 2: Token Classification**
- Primary colors (brand colors, most prominent)
- Neutral colors (grays, backgrounds, borders)
- Semantic colors (status indicators, alerts)
- Typography scale (logical size progression)
- Spacing scale (consistent mathematical relationships)

**Step 3: Component Mapping**
- Match visual elements to standard UI components
- Document state variations (hover, active, disabled)
- Note accessibility considerations (contrast ratios)

## OUTPUT REQUIREMENTS

### JSON STRUCTURE
Generate a `design-system.json` with this exact structure:

```json
{
  "metadata": {
    "name": "Extracted Design System",
    "version": "1.0.0",
    "source": "image-analysis",
    "timestamp": "current-date"
  },
  "tokens": {
    "colors": {
      "primary": {
        "50": "#hex-value",
        "500": "#hex-value",
        "900": "#hex-value"
      },
      "neutral": {
        "white": "#ffffff",
        "gray-100": "#hex-value",
        "gray-900": "#hex-value",
        "black": "#000000"
      },
      "semantic": {
        "success": "#hex-value",
        "warning": "#hex-value",
        "error": "#hex-value"
      }
    },
    "typography": {
      "fontFamily": {
        "primary": "font-stack-here"
      },
      "fontSize": {
        "sm": "14px",
        "base": "16px",
        "lg": "18px",
        "xl": "20px",
        "2xl": "24px"
      },
      "fontWeight": {
        "normal": "400",
        "medium": "500",
        "bold": "700"
      }
    },
    "spacing": {
      "xs": "4px",
      "sm": "8px",
      "md": "16px",
      "lg": "24px",
      "xl": "32px"
    },
    "borderRadius": {
      "sm": "4px",
      "md": "8px",
      "lg": "12px"
    }
  },
  "components": {
    "button": {
      "primary": {
        "backgroundColor": "colors.primary.500",
        "color": "colors.neutral.white",
        "padding": "spacing.sm spacing.md",
        "borderRadius": "borderRadius.sm"
      }
    }
  }
}
```

### QUALITY STANDARDS
- **Accurate Values**: All hex colors, font sizes, and spacing must reflect actual measurements
- **Consistent Naming**: Use semantic names (primary, secondary) over descriptive names (blue, red)
- **Token References**: Components must reference base tokens, not hardcoded values
- **Realistic Measurements**: Ensure extracted values are web-standard and implementable

### VALIDATION CHECKLIST
Before finalizing, verify:
- [ ] All visible colors are captured with correct hex values
- [ ] Typography scale follows logical progression (1.2x or 1.25x ratios)
- [ ] Spacing uses consistent increments (4px, 8px base units)
- [ ] Component tokens reference base design tokens
- [ ] JSON is valid and properly formatted

## EXECUTION GUIDELINES

**DO:**
- Be precise with color extraction using visual analysis
- Create logical token hierarchies with clear relationships
- Document only what's visually present in the image
- Use production-ready values and measurements

**DON'T:**
- Invent values not visible in the image
- Include specific text content or copy
- Create overly complex token structures
- Use non-standard naming conventions

**OUTPUT FORMAT:**
Save as `design-system.json` with clean, readable formatting. Include brief explanations for token choices when patterns aren't immediately obvious.

## SUCCESS CRITERIA
The extracted design system should enable a developer to recreate the visual design with high fidelity using only the provided tokens and component definitions.