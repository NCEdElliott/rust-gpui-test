# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
# Build the project
cargo build

# Run the application
cargo run

# Build with release optimizations
cargo build --release
```

## Project Overview

This is a Rust application using GPUI, the GPU-accelerated UI framework from the Zed editor. The project uses Rust 2024 edition.

### Architecture

- **src/main.rs**: Entry point containing a simple GPUI application with a `HelloWorld` component
- The app demonstrates basic GPUI patterns: creating a window, defining a renderable struct implementing `Render`, and using GPUI's flexbox-style layout system

### GPUI Patterns Used

- `Application::new().run()` - Application lifecycle
- `cx.open_window()` - Window creation with bounds
- `div()` builder pattern for UI elements with flexbox layout (`.flex()`, `.flex_col()`, `.gap_*()`, etc.)
- `Render` trait implementation for custom components
- `SharedString` for text that can be efficiently shared
