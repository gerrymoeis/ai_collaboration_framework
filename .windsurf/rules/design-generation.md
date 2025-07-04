---
command: "generate-design"
description: "Generates and iterates on UI designs using a version-controlled, multi-phase workflow. It uses an existing design.json as its foundation."
author: "Gerry & Cascade"
version: "2.0"
args:
  - name: "--from-description"
    type: "string"
    description: "A natural language description of the initial UI to generate."
    required: true
  - name: "--version"
    type: "string"
    description: "The initial version number to assign (e.g., 'v1.0')."
    required: true
  - name: "--design-tokens"
    type: "path"
    description: "Path to the design.json file."
    required: false
    default: "design.json"
---

# Rule: Iterative Design Generation (v2.0)

This rule governs the AI-powered workflow for generating, iterating, and expanding UI designs. It is version-controlled and relies on a foundational `design.json` file to ensure consistency.

## Phase 1: Initial Design Generation (`v1.0`)

This phase creates the first version of a UI component or page based on a user's description.

1.  **Parse Input:** The AI processes the user's natural language description (`--from-description`).
2.  **Load Design DNA:** The AI loads the `design.json` file to understand the project's visual identity (colors, fonts, spacing).
3.  **Generate Code:** The AI generates the initial HTML and CSS, strictly adhering to the design tokens. The code must be clean, semantic, and well-commented.
4.  **Create Version Directory:** The AI creates a new directory for the version (e.g., `versions/v1.0/`).
5.  **Save Artifacts:** The generated `index.html` and `style.css` files are saved within the version directory.
6.  **Update Project State:** The `project-state.json` file is updated to log the creation of this new version.

## Phase 2: Design Iteration (`v1.1`, `v1.2`, etc.)

This phase allows for non-destructive refinement of an existing design version.

1.  **Identify Source Version:** The user specifies which version they want to iterate on.
2.  **Gather Feedback:** The user provides feedback in natural language (e.g., "make the header smaller," "change the primary button color to the secondary brand color").
3.  **Propose Changes:** The AI analyzes the feedback and proposes specific code changes required to implement it. It explains *what* it will change and *why*.
4.  **User Confirmation (Agency & Empowerment):** The user must approve the proposed changes before the AI proceeds.
5.  **Create New Version:** The AI copies the source version's directory to a new minor version (e.g., `versions/v1.1/`) and applies the approved changes. This ensures the original version remains untouched.

## Phase 3: Multi-Page Expansion

This phase expands a single-page design into a multi-page website, ensuring consistency.

1.  **Define New Pages:** The user provides a list of new pages to create (e.g., "About Us", "Contact", "Pricing").
2.  **Extract Shared Layout:** The AI analyzes the source design to identify shared layout elements (header, footer, navigation) and extracts them into reusable components or templates.
3.  **Generate New Pages:** The AI generates the HTML for the new pages, reusing the shared layout and populating the content areas with placeholder text. All new pages will reference the same `design.json` and CSS.
4.  **Save in Version:** The new pages are saved within the appropriate version directory.

## Phase 4: Quality Assurance

For every generation or iteration, the AI must perform automated checks.

1.  **Accessibility Check:** Ensure generated code meets basic accessibility standards (e.g., alt tags for images, proper heading structure, sufficient color contrast based on tokens).
2.  **Token Validation:** Verify that all styles in the generated CSS correctly reference tokens from `design.json` and do not use hardcoded values.
