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

- **src/main.rs**: Single-file application implementing a high-performance data table displaying 10,000 stock quote rows
- The app demonstrates advanced GPUI patterns including virtualized lists, custom scrollbar, column sorting, and resizable columns

### Key Components

- `Quote`: Stock quote data structure with random generation for demo purposes
- `TableRow`: Implements `RenderOnce` via `IntoElement` derive for efficient row rendering
- `DataTable`: Main component implementing `Render`, manages state for sorting, scrolling, column resizing
- `FIELDS`: Constant array defining column names and default widths

### GPUI Patterns Used

- `Application::new().run()` - Application lifecycle
- `cx.open_window()` - Window creation with bounds
- `uniform_list()` - Virtualized list for rendering large datasets efficiently
- `UniformListScrollHandle` - Scroll state management for virtualized lists
- `canvas()` - Low-level drawing and mouse event handling for scrollbar/resize
- `div()` builder pattern for UI elements with flexbox layout
- `Render` trait for stateful components, `RenderOnce`/`IntoElement` for stateless elements
- `cx.listener()` and `cx.processor()` for event handling and list item generation
- `SharedString` for text that can be efficiently shared
- `Rc<Quote>` pattern to share data across rendered items without cloning
