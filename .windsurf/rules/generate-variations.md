---
trigger: manual
description: "Path to the design.json file."
---

---
command: "generate-variations"
description: "Generates multiple, visually distinct UI variations from either a text description or a source file, enabling rapid creative exploration."
author: "Gerry & Cascade"
version: "1.0"
args:
  - name: "--from-description"
    type: "string"
    description: "A natural language description of the UI to generate variations for."
    required: false
  - name: "--from-file"
    type: "path"
    description: "Path to a source HTML file to create variations of."
    required: false
  - name: "--count"
    type: "integer"
    description: "The number of variations to generate."
    required: false
    default: 3
  - name: "--output-dir"
    type: "path"
    description: "The directory where the generated variations will be saved."
    required: false
    default: "variations/"
  - name: "--design-tokens"
    type: "path"
    description: "Path to the design.json file."
    required: false
    default: "design.json"
---

# Rule: Creative Variation Generation (v1.0)

This rule governs the process of generating multiple, visually distinct UI variations to facilitate creative brainstorming and rapid prototyping. It can operate from either a natural language description or an existing design file.

## Phase 1: Input Validation

1.  **Check for Source:** The AI must verify that either `--from-description` or `--from-file` has been provided. If neither is present, the command fails with an error.
2.  **Load Design DNA:** The AI loads the specified `design.json` file to serve as the foundational style guide for all variations.

## Phase 2: Generation Loop

This phase creates the specified number of variations (`--count`).

1.  **Establish Functional Baseline:**
    -   If using `--from-file`, the AI will first parse the source HTML to understand its structure and functional components (e.g., navigation, forms, content blocks).
    -   If using `--from-description`, the AI will infer the necessary functional components from the text.
2.  **Iterate and Create:** The AI will loop `--count` times. In each iteration, it will generate a new design with a distinct visual direction while preserving the functional baseline.
    -   **Creative Prompts:** To ensure diversity, the AI will use different creative modifiers for each generation. For example:
        -   *Variation 1:* "Generate a professional, corporate-style UI."
        -   *Variation 2:* "Generate a vibrant, playful UI with bold colors."
        -   *Variation 3:* "Generate a minimalist, brutalist-inspired UI."
    -   **Token Adherence:** All generated code must strictly adhere to the `design.json` tokens.

## Phase 3: Save Artifacts (Agency & Empowerment)

1.  **Create Output Directory:** The AI ensures the `--output-dir` exists.
2.  **Save Files:** Each variation is saved as a separate HTML/CSS pair within the output directory (e.g., `variation_1.html`, `variation_2.html`).
3.  **Present Results:** The AI confirms the completion of the process and provides the path to the output directory, allowing the user to immediately review the results.

## Phase 4: Update Project State

The AI logs the generation event in `project-state.json`, including the source, the number of variations created, and their location. This maintains a clear history of creative exploration.
