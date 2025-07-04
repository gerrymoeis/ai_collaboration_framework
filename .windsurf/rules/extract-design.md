---
trigger: manual
---

# EXTRACT DESIGN WITH DESIGN TOKEN MANAGEMENT

## OBJECTIVE
Extract a comprehensive and reusable design system from the image pasted, with enhanced design token management for better scalability and consistency in UI development.

## ANALYSIS INSTRUCTIONS

### Examine the image to identify:

**Color System**
• Primary, secondary, and accent color palettes
• Neutral colors (grays, whites, blacks)
• Semantic colors (success, warning, error, info)
• Color variations (light, medium, dark shades)
• Opacity levels and transparency usage

**Typography Hierarchy**
• Font families and font stacks
• Font weights (light, regular, medium, bold)
• Font sizes for headers (H1-H6)
• Body text and caption sizing
• Line heights and letter spacing
• Text color applications

**Spacing System**
• Consistent spacing units (4px, 8px, 16px grid systems)
• Padding and margin patterns
• Component spacing relationships
• Layout gaps and gutters

**Component Design Tokens**
• Button variations (primary, secondary, outline, text)
• Form input styles and states
• Card designs and elevation levels
• Navigation patterns
• Interactive element sizing

**Animation & Interaction Preferences**
• Transition timing and easing
• Hover state behaviors
• Animation duration patterns
• Interactive feedback styles

## ENHANCED JSON STRUCTURE

Generate a design-system.json file with this comprehensive structure:

```json
{
  "metadata": {
    "name": "Extracted Design System",
    "version": "1.0.0",
    "extractedFrom": "source-image",
    "createdAt": "timestamp",
    "framework": "framework-agnostic"
  },
  "tokens": {
    "colors": {
      "primary": {
        "50": "#color-value",
        "100": "#color-value", 
        "500": "#color-value",
        "900": "#color-value"
      },
      "semantic": {
        "success": "#color-value",
        "warning": "#color-value",
        "error": "#color-value",
        "info": "#color-value"
      },
      "neutral": {
        "white": "#ffffff",
        "gray-50": "#color-value",
        "gray-900": "#color-value",
        "black": "#000000"
      }
    },
    "typography": {
      "fontFamily": {
        "primary": "font-stack",
        "secondary": "font-stack"
      },
      "fontSize": {
        "xs": "size-value",
        "sm": "size-value",
        "base": "size-value",
        "lg": "size-value",
        "xl": "size-value",
        "2xl": "size-value"
      },
      "fontWeight": {
        "light": "300",
        "normal": "400",
        "medium": "500",
        "bold": "700"
      },
      "lineHeight": {
        "tight": "1.25",
        "normal": "1.5",
        "relaxed": "1.75"
      }
    },
    "spacing": {
      "xs": "4px",
      "sm": "8px",
      "md": "16px",
      "lg": "24px",
      "xl": "32px",
      "2xl": "48px"
    },
    "borderRadius": {
      "none": "0",
      "sm": "4px",
      "md": "8px",
      "lg": "12px",
      "full": "9999px"
    },
    "shadows": {
      "sm": "shadow-definition",
      "md": "shadow-definition",
      "lg": "shadow-definition"
    },
    "animations": {
      "duration": {
        "fast": "150ms",
        "normal": "300ms",
        "slow": "500ms"
      },
      "easing": {
        "linear": "linear",
        "easeIn": "ease-in",
        "easeOut": "ease-out",
        "easeInOut": "ease-in-out"
      }
    }
  },
  "components": {
    "button": {
      "primary": {
        "backgroundColor": "token-reference",
        "color": "token-reference",
        "padding": "token-reference",
        "borderRadius": "token-reference",
        "fontSize": "token-reference",
        "fontWeight": "token-reference",
        "transition": "token-reference"
      },
      "secondary": {},
      "outline": {}
    },
    "card": {
      "default": {
        "backgroundColor": "token-reference",
        "borderRadius": "token-reference",
        "padding": "token-reference",
        "boxShadow": "token-reference"
      }
    },
    "input": {
      "default": {
        "backgroundColor": "token-reference",
        "border": "token-reference",
        "borderRadius": "token-reference",
        "padding": "token-reference",
        "fontSize": "token-reference"
      }
    }
  },
  "layout": {
    "breakpoints": {
      "sm": "640px",
      "md": "768px",
      "lg": "1024px",
      "xl": "1280px"
    },
    "container": {
      "maxWidth": "1200px",
      "padding": "token-reference"
    },
    "grid": {
      "columns": "12",
      "gap": "token-reference"
    }
  }
}
```

## REQUIREMENTS

**Design Token Priorities**
• Create scalable token hierarchy with meaningful names
• Use consistent naming conventions (BEM-like approach)
• Reference tokens within components (avoid hardcoded values)
• Include semantic color mapping for accessibility
• Document responsive behavior patterns

**Quality Standards**
• Ensure all extracted values are realistic and usable
• Maintain design consistency across token definitions
• Create logical relationships between similar tokens
• Include fallback values for web-safe implementations

**Output Standards**
• Save to designs/design.json
• Use proper JSON formatting with comments via description fields
• Include token usage examples in component definitions
• Omit literal text, imagery, or specific data from screenshots
• Framework-independent structure for maximum reusability

## VALIDATION CHECKLIST

✅ Color palette is complete with proper contrast ratios  
✅ Typography scale follows logical progression  
✅ Spacing system uses consistent mathematical relationships  
✅ Component tokens reference base design tokens  
✅ Animation preferences are defined with realistic timing  
✅ JSON structure is valid and well-organized  
✅ Token names are semantic and developer-friendly  
✅ All values are production-ready and accessible