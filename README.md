# WAT CLOCK | WAT时钟
[LIVE DEMO | 实时演示](https://kennyfully1988.github.io/wat_clock/)

A minimalistic, high-performance pixel clock powered by an embedded WebAssembly (Wasm) binary module rendering directly to an HTML5 Canvas.

## Features

* Low-Level Precision: Core clock rendering and logic are implemented inside a hand-crafted/optimized WebAssembly binary module.
* Embedded Architecture: The Wasm module is directly compiled inline as a Uint8Array inside the HTML file, meaning zero external .wasm file loading overhead.
* Retro Aesthetic: Renders a clean, pixelated 64x8 clock interface using pixel-perfect alignment.
* Lightweight & Portable: Fully contained in a single standalone index.html file with no dependencies or build tools required.

## Tech Stack

* WebAssembly (Wasm): Binary byte array managing pixel manipulation and state tracking.
* JavaScript: Houses the animation loop, handles timing via performance.now(), maps the Wasm memory buffer, and hooks DOM elements.
* HTML5 Canvas: Configured with image-rendering: pixelated for that crisp pixel-art appearance.

## Project Structure

index.html      # Single-file entry point containing HTML, CSS, JS, and embedded Wasm bytes

## How It Works Under the Hood

1. Wasm Memory Mapping: JavaScript instantiates the embedded binary block and extracts its exported memory buffer.
2. Buffer Sections:
* Image Data Buffer: A shared pixel space (first 2048 bytes) mapped directly into a browser ImageData array.
* State Vectors: Dedicated memory regions handling time variables and active parameters.


3. The Loop: The animation frame loop calls the compiled Wasm render export function every frame, letting low-level instructions handle pixel processing at native speeds.

## Getting Started

Because it is entirely self-contained, you don't need any complex development servers to run it locally.

### Prerequisites

Any modern web browser supporting WebAssembly (Chrome, Firefox, Edge, Safari).

## License

Distributed under the MIT License. See LICENSE for more information.

---

Crafted with passion and low-level engineering.
