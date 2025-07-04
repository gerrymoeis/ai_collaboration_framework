---
command: "adapt-for-geo"
description: "Adapts a design for different geographical regions, creating culturally and legally appropriate UI variations."
author: "Gerry & Cascade"
version: "1.0"
args:
  - name: "--from-version"
    type: "string"
    description: "The version directory of the source design to adapt (e.g., 'versions/v1.2')."
    required: true
  - name: "--target-regions"
    type: "string"
    description: "A comma-separated list of ISO 3166-1 alpha-2 region codes (e.g., 'jp,de,sa')."
    required: true
  - name: "--output-dir"
    type: "path"
    description: "The base directory where the regional variations will be saved."
    required: false
    default: "geo-variations/"
---

# Rule: Geographical Adaptation (v1.0)

This rule governs the process of creating localized versions of an app design. It takes a source design and generates multiple variations, each optimized for a specific geographical region.

## Phase 1: Analysis & Preparation

1.  **Load Source Design:** The AI loads the HTML and CSS from the specified `--from-version` directory.
2.  **Parse Target Regions:** The AI parses the `--target-regions` string into a list of regions to process.
3.  **Create Output Directory:** The AI ensures the base `--output-dir` exists.

## Phase 2: Regional Adaptation Loop

The AI iterates through each region in the target list and applies specific adaptations.

1.  **Create Region Subdirectory:** A new subdirectory is created for each region (e.g., `geo-variations/jp/`).
2.  **Apply Adaptations:** For each region, the AI will create a copy of the source design and modify it based on known localization best practices:
    -   **Text Direction (RTL/LTR):** For regions like 'sa' (Saudi Arabia) or 'il' (Israel), the AI will modify the CSS to support a right-to-left (RTL) layout. This includes changing properties like `direction: rtl`, and adjusting margins, padding, and positioning.
    -   **Cultural Color Palette:** The AI can suggest adjustments to the color scheme based on cultural associations. *This would be a suggestion for the user to implement, rather than an automatic change, to respect Agency & Empowerment.*
    -   **Typography:** The AI may suggest alternative fonts that better support the region's language and character sets.
    -   **Legal & Compliance:** The AI will inject placeholder elements for region-specific legal requirements, such as a GDPR-compliant cookie consent banner for EU countries (`de`, `fr`, etc.).
    -   **Imagery & Iconography:** The AI will flag images and icons that may need to be reviewed for cultural appropriateness, adding comments in the code for the user.

## Phase 3: Save & Report

1.  **Save Artifacts:** The adapted HTML and CSS files for each region are saved in their respective subdirectories.
2.  **Update Project State:** The AI logs the adaptation event in `project-state.json`, detailing the source version and the regions it was adapted for.
3.  **Confirmation:** The AI confirms the completion of the process and provides a list of the newly created regional directories for the user to review.
