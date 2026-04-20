# GEMINI Context: MyBook MyWords

This project is a personal technical knowledge base and documentation book built using [mdBook](https://github.com/rust-lang/mdBook). It serves as a centralized repository for notes, cheatsheets, and guides on various software engineering topics, tools, and personal projects.

## Project Overview

- **Title:** MyBook MyWords
- **Author:** Ravi Sankar Karuturi
- **Technology Stack:** mdBook (Rust-based), Markdown.
- **Purpose:** A structured collection of technical knowledge ranging from low-level algorithms to high-level cloud architecture and personal project documentation.

## Directory Structure

- `book.toml`: The main configuration file for `mdBook`. It defines metadata like title, author, and source directory.
- `src/`: The source directory containing all Markdown content.
    - `SUMMARY.md`: The table of contents. It defines the structure and navigation of the book.
    - `*.md`: Individual topic-specific files (e.g., `Rust-learning.md`, `kubernetes.md`, `Nvim_cheats.md`).
    - `images/`: Stores visual aids and diagrams used within the documentation.
    - `work/`, `ideas/`, `mocktailbird/`, `LLM/`: Subdirectories for categorized content.
- `book/`: (Generated) Contains the rendered HTML output of the book after running `mdbook build`.

## Usage & Development

### Prerequisites

- [Rust](https://www.rust-lang.org/) and Cargo.
- `mdbook` CLI: Install via `cargo install mdbook`.

### Key Commands

- **Serve Locally:** `mdbook serve`
  - Runs a local web server (usually at `http://localhost:3000`) and automatically reloads when files are changed.
- **Build:** `mdbook build`
  - Generates the static HTML site in the `book/` directory.
- **Watch:** `mdbook watch`
  - Watches for changes and rebuilds without serving.
- **Clean:** `mdbook clean`
  - Deletes the generated `book/` directory.

## Content Conventions

- **Cheatsheets:** Many files are structured as quick-reference guides with commands and brief explanations.
- **Setup Guides:** Documentation often includes step-by-step instructions for setting up environments or tools.
- **Visuals:** Diagrams are stored in `src/images/` and referenced in the markdown files.
- **Organization:** New topics should be added to `src/` (or a relevant subdirectory) and linked in `src/SUMMARY.md` to appear in the book's navigation.
