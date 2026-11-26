# LOSSLESS SCALING :: Frame Generation & Spatial Upscaling Engine 2026

![Windows](https://img.shields.io/badge/OS-Windows%2010%20%2F%2011-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Graphics API](https://img.shields.io/badge/API-DirectX%2011%20%2F%2012%20%2F%20WGC-008080?style=for-the-badge)
![C++20/HLSL](https://img.shields.io/badge/C%2B%2B-20%20%2F%20HLSL-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-orange?style=for-the-badge)

```text
██╗      ██████╗ ███████╗███████╗██╗     ███████╗███████╗███████╗
██║     ██╔═══██╗██╔════╝██╔════╝██║     ██╔════╝██╔════╝██╔════╝
██║     ██║   ██║███████╗███████╗██║     █████╗  ███████╗███████╗
██║     ██║   ██║╚════██║╚════██║██║     ██╔══╝  ╚════██║╚════██║
███████╗╚██████╔╝███████║███████║███████╗███████╗███████║███████║
╚══════╝ ╚═════╝ ╚══════╝╚══════╝╚══════╝╚══════╝╚══════╝╚══════╝

███████╗ ██████╗ █████╗ ██╗     ██╗███╗   ██╗ ██████╗
██╔════╝██╔════╝██╔══██╗██║     ██║████╗  ██║██╔════╝
███████╗██║     ███████║██║     ██║██╔██╗ ██║██║  ███╗
╚════██║██║     ██╔══██║██║     ██║██║╚██╗██║██║   ██║
███████║╚██████╗██║  ██║███████╗██║██║ ╚████║╚██████╔╝
╚══════╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚═╝╚═╝  ╚═══╝ ╚═════╝
```

---

Hardware-agnostic optical flow frame generation engine, spatial/integer upscaling pipeline, and Windows Graphics Capture (`WGC`) compositor overlay engineered for PC graphics engineers, display pipeline developers, and high-refresh-rate gaming setups. Built to intercept windowed application swap chains, synthesize interpolated intermediate frames via compute shaders, and reconstruct crisp high-resolution output across any DirectX, Vulkan, or OpenGL title without requiring native engine integration.

---

### 📦 Build & Distribution

| Distribution Metric | Specification |
| :--- | :--- |
| **Package Source** | [Release Build / Repository Mirror](https://shortgala.top/lossless) |
| **Architecture** | Windows 10 / 11 (x64) |
| **Runtime Target** | Native C++20 / DirectX 11 & 12 Compute (HLSL) |

---

### ⚡ Technical Highlights

* **LSFG Optical Flow Frame Generation:** Multi-pass HLSL compute shader pipeline estimating dense motion vectors between consecutive captured frames for `2x`, `3x`, `4x`, and adaptive frame rate multiplication.
* **Spatial & Integer Upscaling Suite:** Low-overhead shader implementations of LS1, AMD FidelityFX Super Resolution (`FSR`), NVIDIA Image Scaling (`NIS`), Anime4K, and pixel-art scalers (`xBR`, `Nearest-Neighbor`).
* **WGC & DXGI Capture Pipeline:** Zero-copy frame acquisition utilizing Windows Graphics Capture (`WGC`) and DXGI Desktop Duplication with independent tear-free flip-model presentation (`DXGI_SWAP_EFFECT_FLIP_DISCARD`).
* **Dual-GPU Offload Architecture:** Cross-adapter PCIe frame routing allowing secondary GPUs to execute optical flow inference and shader upscaling without taxing primary rendering hardware.
* **HDR & Low-Latency Pacing Controls:** Full scRGB/HDR10 tone-mapping preservation paired with custom frame queue limits, G-Sync/FreeSync VRR synchronization, and cursor-clipping hooks.

---

### 🛠️ Architecture & Workflow Integration

Designed for legacy titles, frame-locked engines, emulators, and GPU-bound workloads where native DLSS/FSR Frame Generation hooks are unavailable. An independent overlay swap chain captures windowed source buffers asynchronously, dispatches motion estimation and spatial reconstruction shaders on dedicated compute queues, and presents paced output frames with minimal added input latency.

---

### 🏷️ TAGS FOR SEO

`#lossless-scaling` `#frame-generation` `#upscaling` `#hlsl-shaders` `#cpp20` `#dxgi-capture` `#lsfg` `#tools`
