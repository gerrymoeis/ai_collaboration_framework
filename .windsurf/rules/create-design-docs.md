---
trigger: manual
description: "Path to the base design.json file for reference."
---

---
command: "create-docs"
description: "Generates a comprehensive documentation package from a final, implemented design version."
author: "Gerry & Cascade"
version: "2.0"
args:
  - name: "--from-version"
    type: "string"
    description: "The version directory to generate documentation for (e.g., 'versions/v1.2')."
    required: true
  - name: "--output-dir"
    type: "path"
    description: "The directory where the documentation package will be saved."
    required: false
    default: "documentation/"
  - name: "--design-tokens"
    type: "path"
    description: "Path to the base design.json file for reference."
    required: false
    default: "design.json"
---

# Rule: Documentation Generation (v2.0)

This rule governs the process of generating a complete documentation package from a finalized design version. It ensures that the documentation is a true reflection of the implemented code, creating a reliable source of truth for developers.

## Phase 1: Analysis & Asset Collection

1.  **Parse Source Files:** The AI reads the HTML and CSS files from the specified `--from-version` directory.
2.  **Extract Implemented Styles:** The AI analyzes the CSS to identify all unique colors, font styles, spacing values, and component structures that were actually used in the final design.
3.  **Cross-Reference with Tokens:** The AI compares the implemented styles against the base `design.json` file. This helps identify any one-off styles or deviations from the original token system, which can be flagged in the documentation.

## Phase 2: Style Guide Generation

The AI generates a `style-guide.html` file that visually documents the project's aesthetic.

-   **Color Palette:** Displays all used colors with their HEX/RGB values and corresponding token names.
-   **Typography Scale:** Shows examples of all heading levels and body text, detailing the font family, size, weight, and line height.
-   **Spacing System:** Visually represents the spacing scale (e.g., `sm`, `md`, `lg`) used for margins and padding.

## Phase 3: Interactive Component Library

The AI generates a `component-library.html` file that serves as a live, interactive showcase of the UI components.

1.  **Isolate Components:** The AI identifies and isolates each unique component (buttons, cards, forms, etc.) from the source code.
2.  **Create Live Previews:** For each component, the AI renders a live example in the HTML file.
3.  **Provide Code Snippets:** Alongside each live preview, the AI provides ready-to-copy HTML and CSS code snippets, making it easy for developers to reuse the components.

## Phase 4: Package & Save (Agency & Empowerment)

1.  **Create Output Directory:** The AI ensures the `--output-dir` exists.
2.  **Save Artifacts:** The generated `style-guide.html`, `component-library.html`, and any other assets (like a `final-tokens.json`) are saved into the output directory.
3.  **Update Project State:** The AI logs the documentation generation event in `project-state.json`, linking the documentation to its specific source version.
4.  **Confirmation:** The AI notifies the user of the successful creation of the documentation package and provides the path to the output directory.
