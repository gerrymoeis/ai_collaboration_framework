---
trigger: manual
description: "The file path for the generated design tokens."
---

---
command: "extract-design"
description: "Extracts a scalable, token-based design system from a source image and creates a structured, framework-agnostic `design.json` file. This is a foundational step in the AI Collaboration Framework."
author: "Gerry & Cascade"
version: "2.0"
args:
  - name: "--from-image"
    type: "path"
    description: "The file path to the source image to be analyzed."
    required: true
  - name: "--output-file"
    type: "path"
    description: "The file path for the generated design tokens."
    required: false
    default: "design.json"
---

# Rule: Extract Design System (v2.0)

This rule governs the process of analyzing a source image and extracting a complete, structured design system into a `design.json` file. This process is interactive and adheres to the principles of our AI Collaboration Framework.

## Phase 1: Analysis & Discovery

The AI will analyze the provided image to identify all core design elements.

1.  **Identify Core Colors:** Detect all primary, secondary, accent, and semantic colors (e.g., for success, error, warning states).
2.  **Identify Typography:** Detect font families, sizes, weights, and line heights for different text elements (headings, body text, captions).
3.  **Identify Spacing & Layout:** Infer the base spacing unit and scale (e.g., 4px or 8px grid) and identify common layout patterns (e.g., margins, padding, container widths).
4.  **Identify Core Components:** Recognize basic UI components like buttons, input fields, cards, and navigation bars.
5.  **Present Findings:** The AI will present a summary of its findings before proceeding, ensuring transparency.

## Phase 2: Interactive Tokenization (The Handshake)

This phase turns the discovered elements into a structured system of design tokens. This is a collaborative process.

1.  **Propose Semantic Names:** For each discovered value (e.g., `#007bff`), the AI will propose a semantic token name (e.g., `colors.brand.primary.500`).
2.  **Request User Validation:** The AI will present the proposed token system to the user for confirmation and refinement.
    -   *Example AI Prompt:* "I've identified the main blue as `colors.brand.primary.500`. Is this correct, or should it be named something else?"
3.  **Define Component States:** For interactive components like buttons, the AI will explicitly ask the user to define tokens for different states (`hover`, `active`, `disabled`) that cannot be inferred from a static image.

## Phase 3: JSON Structure Generation (The Common Ground)

Once the token system is validated, the AI will generate the `design.json` file using a strict, predictable schema. This ensures the output is a reliable "Common Ground."

The structure will separate global tokens from component-specific tokens, allowing for maximum scalability and reusability.

```json
{
  "global": {
    "colors": {
      "brand": { "primary": { "500": "#007bff" } },
      "neutral": { "100": "#f8f9fa", "900": "#212529" },
      "semantic": { "success": "#28a745", "error": "#dc3545" }
    },
    "typography": {
      "fonts": { "body": "Inter, sans-serif", "heading": "Poppins, sans-serif" },
      "weights": { "regular": 400, "bold": 700 },
      "lineHeights": { "body": 1.5, "heading": 1.2 }
    },
    "spacing": {
      "base": "8px",
      "scale": { "xs": "4px", "sm": "8px", "md": "16px", "lg": "24px", "xl": "32px" }
    }
  },
  "components": {
    "button": {
      "primary": {
        "background-color": "{colors.brand.primary.500}",
        "color": "{colors.neutral.100}",
        "padding": "{spacing.scale.sm} {spacing.scale.md}",
        "hover": {
          "background-color": "..."
        }
      }
    }
  }
}
```

## Phase 4: Final Review & Save (Agency & Empowerment)

1.  **Present Final File:** The AI will present the complete, formatted `design.json` content to the user for a final review.
2.  **Confirm & Save:** Upon user approval, the AI will save the file to the specified output path. The user always has the final say before any file is written to disk.
