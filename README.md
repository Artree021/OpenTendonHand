<div align="right">

[![README-EN](https://img.shields.io/badge/README-English-blue)](README.en.md) [![README-ZH](https://img.shields.io/badge/README-%E4%B8%AD%E6%96%87-red)](README.md)

</div>

# OpenTendonHand

**开源高自由度线驱灵巧手**
An open-source high-DOF tendon-driven dexterous hand.

本仓库公开这款灵巧手的机械模型、电路板与设计文档，供学习、复现与二次开发使用。

![机械手实物](images/hand-photo.jpg)

<p align="center">
  <img src="images/hand-front.png" height="480" alt="正面模型图">
  &nbsp;&nbsp;&nbsp;
  <img src="images/hand-back.png" height="480" alt="背面模型图">
</p>

## 目录

| 目录 | 内容 |
| --- | --- |
| `solidworks/` | SolidWorks 2025 源模型：60 个零件 + 8 个装配体，特征完整可编辑 |
| `step/` | 整机 STEP 中性格式，任意 CAD 软件均可打开 |
| `pcb/` | 电路板 Gerber 文件，原理图与 PCB 见立创开源广场 |
| `images/` | 实物照片、PCB 渲染图与原理图 |
| `docs/` | 设计文档 `机械手.pdf` |

## 电路板

电路板（AD7606B）的原理图、PCB、BOM 与打板文件已发布在立创开源广场，可直接下单：

**https://oshwhub.com/shusheng60602/ad7606b**

Gerber 文件：[`pcb/AD7606b-gerber.zip`](pcb/AD7606b-gerber.zip)

**3D 渲染**

<img src="images/ad7606b-3d-render.png" width="600">

**PCB 正面**

<img src="images/ad7606b-pcb-front.png" width="600">

**原理图**

<img src="images/ad7606b-schematic.png" width="600">

## 设计文档

[`docs/机械手.pdf`](docs/机械手.pdf)（17 页）

> 本文档由作者 [@Artree021](https://github.com/Artree021) 在本科阶段参加竞赛时整理，内容仅供参考，不保证全部真实、准确或完整。

## 使用说明

- 单位：毫米（mm）。
- 只想看结构或换软件打开：用 `step/`。
- 要改设计：用 `solidworks/`，特征完整可编辑。
- 本仓库为设计归档，以发布文件为主，不承诺持续更新。

## 许可证

机械模型、电路板与文档均按 [CERN-OHL-S-2.0](LICENSE) 发布：可自由使用、修改、制造；修改后的设计文件需以同样许可公开。个人制作与校内使用不受限制。

## 反馈

使用中遇到问题，欢迎提 Issue 记录。

---

*Mechanical models (SolidWorks 2025 + STEP), PCB files and design documentation for an open-source, high degree-of-freedom tendon-driven dexterous hand. Licensed under CERN-OHL-S-2.0.*