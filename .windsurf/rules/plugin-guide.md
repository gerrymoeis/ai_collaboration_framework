# Plugin Developer Guide

This document outlines the architecture and best practices for creating and maintaining plugins for the AI Collaboration Framework. Our framework operates on a modular, extensible model inspired by NeoVim, where each `.md` file in the `rules` directory acts as a self-contained plugin.

## Core Philosophy

Plugins are the heart of our framework. They are not just prompts; they are structured, machine-readable rule sets that define a specific capability. Each plugin should be focused on a single, well-defined task (e.g., 'extracting a design', 'generating variations').

## The YAML Frontmatter API

Every plugin file **must** begin with a YAML frontmatter block. This block is the API that the Core Engine (the AI Agent) uses to understand and execute the plugin. It must be valid YAML enclosed by `---`.

### Required Fields

-   `command` (string): The unique, single-word command that invokes the plugin. This should be concise and verb-based (e.g., `extract-design`, `generate-docs`).
-   `description` (string): A clear, one-sentence description of what the plugin does. This is used for help menus and logging.
-   `author` (string): The author(s) of the plugin.
-   `version` (string): The version of the plugin, following semantic versioning (e.g., `1.0`, `2.1.3`).

### The `args` Block

The `args` field is an array of objects, where each object defines a command-line argument that the plugin accepts.

-   `name` (string): The name of the argument, including the preceding dashes (e.g., `--from-file`, `--count`).
-   `type` (string): The expected data type for the argument's value. Supported types are: `string`, `integer`, `boolean`, `path`.
-   `description` (string): A brief explanation of what the argument is for.
-   `required` (boolean): Whether the argument must be provided when the command is run.
-   `default` (any): A default value to be used if a non-required argument is not provided.

### Example Frontmatter

```yaml
---
command: "generate-variations"
description: "Generates multiple, visually distinct UI variations."
author: "Gerry & Cascade"
version: "1.0"
args:
  - name: "--from-file"
    type: "path"
    description: "Path to a source HTML file to create variations of."
    required: true
  - name: "--count"
    type: "integer"
    description: "The number of variations to generate."
    required: false
    default: 3
---
```

## Writing Effective Rules

The markdown content that follows the frontmatter should be a clear, step-by-step guide for the AI.

-   **Use Phases:** Break down the plugin's logic into numbered `## Phase X:` sections. This creates logical checkpoints.
-   **Be Explicit:** Clearly state the inputs and expected outputs of each phase.
-   **Reference Principles:** Where applicable, explicitly mention how a step adheres to our core principles (e.g., *"User Confirmation (Agency & Empowerment)"*).
-   **Provide Examples:** Use code blocks to show examples of file structures, JSON schemas, or code snippets that the AI is expected to produce.
