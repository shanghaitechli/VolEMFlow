# VolEMFlow

**A lightweight, local-first visual workflow for volumetric electron microscopy image processing.**

**面向生物学研究者的轻量级、本地化体积电子显微镜图像处理可视化工作流。**

[English](#english) | [中文](#中文)

---

## English

### Overview

**VolEMFlow** is a Windows-based image processing tool for volumetric electron microscopy (Volume EM) datasets. Designed for biologists with no coding experience, it brings preprocessing, registration, and cell segmentation into a unified, browser-based graphical workflow.

All image processing runs on your local computer. The browser serves only as the graphical user interface—no cloud processing or data upload is required. Once the required environment and models are prepared locally, the workflow can run offline.

VolEMFlow emphasizes lightweight packaging, efficient processing, and practical handling of large 3D image stacks.

### Core Workflow

| Node | Function |
|------|----------|
| **1 · Preprocessing** | Speed-adaptive downsampling and intensity equalization |
| **2 · Rigid Registration** | Feature-based rigid registration with multiple border-handling options |
| **3 · Non-rigid Registration** | B-spline-based elastic registration |
| **4 · Cell Segmentation** | Cellpose-based 2D/3D segmentation with interactive preview and export tools |

### Key Features

- **No-code visual workflow**: Configure and run processing steps through a browser-based GUI.
- **Local and offline-capable**: Keep image data on your own computer; run offline after environment setup and model caching.
- **Lightweight and efficient**: Compact application packaging and processing workflows designed for large volume stacks.
- **Interactive ROI selection**: Draw rectangular regions with the mouse to preview slice segmentation.
- **Dual-view preview**: Compare the source ROI with a color-mask overlay at 50% opacity.
- **Four visualization modes**: Source / Mask Overlay / Outline / Combined Gradients.
- **Flexible registration borders**: Fill Black / Fill White / Crop to Max Overlap.
- **Scientific export formats**: Label TIFF stacks and ImageJ ROI archives.
- **Consistent controls**: Preview before running, with orange-highlighted Run buttons.

### Compatibility

- **Operating system**: Windows 10 / Windows 11, 64-bit
- **Cellpose**: Versions 2.x / 3.x
  - Cellpose 4.x is not supported by the current integration due to architectural differences.
- **Memory**: 8 GB minimum; 16 GB or more recommended for large image stacks
  - Actual memory requirements depend on dataset size and processing settings.

### Quick Start

#### End Users — Precompiled Release

1. Download the latest portable package from [GitHub Releases](https://github.com/YourUsername/VolEMFlow/releases).
2. Extract the ZIP archive and launch `VolEMFlow.exe`.
3. Keep the console window open while using the application.
4. Your browser will automatically open `http://127.0.0.1:5000`.
5. To use segmentation, configure the path to the Python executable in your local Cellpose Conda environment in **Node 4**.

> **Before running offline:** Prepare a compatible Cellpose environment and cache the required models. The portable application still requires the configured Cellpose environment for Node 4.

#### Developers — Run from Source

```bash
git clone https://github.com/YourUsername/VolEMFlow.git
cd VolEMFlow
pip install -r requirements.txt
python server.py
```

A dedicated Python environment is recommended. For Node 4, configure a compatible Cellpose environment as described above.

### License

No license has been selected yet. Public availability of this repository does not, by itself, grant permission to use, modify, or redistribute the code.

---

## 中文

### 项目简介

**VolEMFlow** 是一款运行于 Windows 的体积电子显微镜（Volume EM）三维图像堆栈处理工具，专为**无编程基础的生物学研究者**设计，将预处理、图像配准和细胞分割整合到统一的浏览器可视化工作流中。

所有图像处理均在本地计算机上完成。浏览器仅作为图形用户界面，**无需云端计算，也无需上传图像数据**。完成本地环境配置并缓存所需模型后，即可离线运行。

VolEMFlow 注重轻量化打包、高效运算和大规模三维图像堆栈的实用处理体验。

### 核心工作流

| 节点 | 功能 |
|------|------|
| **1 · 图像预处理** | 速度自适应降采样与强度均衡 |
| **2 · 刚性配准** | 基于特征的刚性配准，支持多种边界处理策略 |
| **3 · 非刚性配准** | 基于 B 样条的弹性形变配准 |
| **4 · 细胞分割** | 基于 Cellpose 的二维/三维分割，支持交互式预览与结果导出 |

### 主要特点

- **无需编程**：通过浏览器 GUI 配置并运行各处理步骤。
- **本地运行，支持离线**：数据保留在本机；完成环境配置和模型缓存后，无需联网。
- **轻量高效**：紧凑的软件打包，面向大体积图像堆栈的处理工作流。
- **交互式 ROI 选择**：使用鼠标框选矩形区域，预览切片分割效果。
- **双视图预览**：对照查看原始 ROI 与 50% 不透明度的彩色掩膜叠加结果。
- **四种可视化模式**：原图 / 掩膜叠加 / 轮廓 / 组合梯度。
- **灵活的配准边界处理**：填充黑色 / 填充白色 / 裁剪至最大重叠区域。
- **科研常用格式导出**：标签 TIFF 堆栈与 ImageJ ROI 归档。
- **统一的操作逻辑**：先预览、后运行，运行按钮以橙色突出显示。

### 兼容性

- **操作系统**：Windows 10 / Windows 11，64 位
- **Cellpose**：2.x / 3.x
  - 由于架构差异，当前集成不支持 Cellpose 4.x。
- **内存**：最低 8 GB；处理大体积图像堆栈建议使用 16 GB 或以上
  - 实际内存需求取决于数据规模和处理参数。

### 快速开始

#### 普通用户：使用预编译发行包

1. 从 [GitHub Releases](https://github.com/YourUsername/VolEMFlow/releases) 下载最新便携包。
2. 解压 ZIP 文件，运行 `VolEMFlow.exe`。
3. 使用期间请保持控制台窗口开启。
4. 浏览器将自动打开 `http://127.0.0.1:5000`。
5. 如需使用分割功能，请在 **节点 4** 中配置本地 Cellpose Conda 环境的 Python 可执行文件路径。

> **离线使用前：** 请先准备兼容的 Cellpose 环境，并缓存所需模型。便携版应用的节点 4 仍需调用已配置的 Cellpose 环境。

#### 开发者：从源码运行

```bash
git clone https://github.com/YourUsername/VolEMFlow.git
cd VolEMFlow
pip install -r requirements.txt
python server.py
```

建议使用独立的 Python 环境。节点 4 需要按上述说明配置兼容的 Cellpose 环境。

### 许可证

本项目暂未选择许可证。仓库公开本身并不代表授予他人使用、修改或再分发代码的许可。
