# WAT CLOCK | WAT时钟
[LIVE DEMO | 实时演示](https://kennyfully1988.github.io/wat_clock/)

A minimalistic, high-performance pixel clock powered by an embedded WebAssembly (Wasm) binary module rendering directly to an HTML5 Canvas.

一个极简、高性能的像素时钟，由嵌入式 WebAssembly (Wasm) 二进制模块驱动，直接渲染到 HTML5 Canvas 画布上。

## Features

* Low-Level Precision: Core clock rendering and logic are implemented inside a hand-crafted/optimized WebAssembly binary module.
* Embedded Architecture: The Wasm module is directly compiled inline as a Uint8Array inside the HTML file, meaning zero external .wasm file loading overhead.
* Retro Aesthetic: Renders a clean, pixelated 64x8 clock interface using pixel-perfect alignment.
* Lightweight & Portable: Fully contained in a single standalone index.html file with no dependencies or build tools required.

## 功能特点
* 底层高精度：核心时钟渲染与逻辑运行在精心优化、手工打造的 WebAssembly 二进制模块内部。
* 嵌入式架构：Wasm 模块作为 Uint8Array 数组直接内联编译在 HTML 文件中，这意味着无需加载外部 .wasm 文件，实现零开销加载。
* 复古美学：采用像素级对齐，呈现出干净、像素风的 64x8 时钟界面。
* 轻量便携：完全包含在单个独立的 index.html 文件中，无需任何依赖项或构建工具。

## Tech Stack

* WebAssembly (Wasm): Binary byte array managing pixel manipulation and state tracking.
* JavaScript: Houses the animation loop, handles timing via performance.now(), maps the Wasm memory buffer, and hooks DOM elements.
* HTML5 Canvas: Configured with image-rendering: pixelated for that crisp pixel-art appearance.

## 技术栈

* WebAssembly (Wasm)：二进制字节数组，负责管理像素处理与状态追踪。
* JavaScript：承载动画循环、通过 performance.now() 处理时间、映射 Wasm 内存缓冲区并挂载 DOM 元素。
* HTML5 Canvas：配置了 image-rendering: pixelated 属性，以确保获得清晰的像素艺术外观。

## Project Structure

index.html      # Single-file entry point containing HTML, CSS, JS, and embedded Wasm bytes

## 项目结构

index.html      # 单文件入口，包含 HTML、CSS、JS 以及嵌入的 Wasm 字节数据

## How It Works Under the Hood

1. Wasm Memory Mapping: JavaScript instantiates the embedded binary block and extracts its exported memory buffer.
2. Buffer Sections:
* Image Data Buffer: A shared pixel space (first 2048 bytes) mapped directly into a browser ImageData array.
* State Vectors: Dedicated memory regions handling time variables and active parameters.
3. The Loop: The animation frame loop calls the compiled Wasm render export function every frame, letting low-level instructions handle pixel processing at native speeds.
  
## 底层工作原理
1. Wasm 内存映射：JavaScript 实例化嵌入的二进制块，并提取其导出的 memory 缓冲区。
2. 缓冲区划分：
* 图像数据缓冲区：共享的像素空间（前 2048 字节）直接映射到浏览器的 ImageData 数组中。
* 状态向量：处理时间变量和激活参数的专属内存区域。
3. 循环机制：动画帧循环（animation frame loop）在每帧都会调用编译好的 Wasm render 导出函数，让底层指令以原生速度处理像素。

## Getting Started

Because it is entirely self-contained, you don't need any complex development servers to run it locally.

## 快速入门

由于本项目完全独立，您不需要任何复杂的开发服务器即可在本地运行。


### Prerequisites

Any modern web browser supporting WebAssembly (Chrome, Firefox, Edge, Safari).

### 前提条件

任何支持 WebAssembly 的现代浏览器（Chrome、Firefox、Edge、Safari）。


## License

Distributed under the MIT License. See LICENSE for more information.


## 开源协议

基于 MIT 协议分发。欲了解更多信息，请参阅 LICENSE 文件。

---

Crafted with passion and low-level engineering.
精雕细琢，始于底层工程。
