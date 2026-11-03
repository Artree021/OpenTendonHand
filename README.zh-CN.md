<div align="center">

<img src="assets/logo/logo.svg" alt="OpenTendonHand" width="112" height="112" />

# OpenTendonHand

**开源高自由度线驱灵巧手**

机械结构 · 电子电路 · 固件 · 控制算法 —— 全部开源。

[![硬件许可: CERN-OHL-S-2.0](https://img.shields.io/badge/%E7%A1%AC%E4%BB%B6-CERN--OHL--S--2.0-blue)](LICENSE-HARDWARE)
[![软件许可: MIT](https://img.shields.io/badge/%E8%BD%AF%E4%BB%B6-MIT-green)](LICENSE)
[![项目状态: 设计阶段](https://img.shields.io/badge/%E7%8A%B6%E6%80%81-%E8%AE%BE%E8%AE%A1%E9%98%B6%E6%AE%B5-orange)](#项目状态)
[![欢迎贡献](https://img.shields.io/badge/%E6%AC%A2%E8%BF%8E-%E8%B4%A1%E7%8C%AE-brightgreen)](CONTRIBUTING.md)

[English](README.md) · [简体中文](README.zh-CN.md)

</div>

---

## 项目简介

OpenTendonHand 是一款基于**线驱（腱驱动）**架构的灵巧手：驱动器集中布置在
前臂，通过鲍登线（Bowden cable）把动力传到手指，手部本体因此可以做得轻、薄，
而把重量留在更好承托的位置。

项目目标是把一套可复现的设计完整公开——机械 CAD、电路原理图与 PCB、固件、
控制软件和装配指南——让实验室、学生和爱好者可以直接在此基础上改，而不是从
零开始。

> **当前状态：早期设计阶段。** 仓库目前包含项目骨架、文档结构和许可证。
> 机械与电路部分暂时留空（占位文档），后续按路线图补充。

## 为什么选择线驱？

- **重量放对地方。** 驱动器在前臂，不在手指里。
- **小手也能高自由度。** 走线方式允许在接近人手的体积内实现 20+ 自由度。
- **天然柔顺。** 绳驱和串联弹性让接触更安全、更容易控制。
- **可维护。** 线会磨损，设计上应当能「重新穿线」，而不是整个手指报废。

## 项目状态

| 模块 | 状态 |
| --- | --- |
| 文档与仓库骨架 | 🟡 进行中 |
| 机械设计（CAD、BOM） | ⬜ 未开始 |
| 电子电路（原理图、PCB） | ⬜ 未开始 |
| 固件 | ⬜ 未开始 |
| SDK 与上层控制 | ⬜ 未开始 |
| 仿真 | ⬜ 未开始 |

里程碑见[路线图](docs/roadmap.md)，参数目标见 [设计需求](docs/design/requirements.md)。

## 设计目标

以下均为**目标值**，不是实测结果。标 `TBD` 的仍在讨论，会在需求阶段确定。

| 参数 | 目标 | 状态 |
| --- | --- | --- |
| 自由度 | 20–24（五指，仿人构型） | TBD |
| 驱动方式 | 线驱，驱动器远置（前臂） | TBD |
| 传动 | 鲍登线 + 差动滑轮耦合 | TBD |
| 手部质量（手指 + 手掌） | < 800 g | TBD |
| 指尖力 | ≥ 10 N | TBD |
| 感知 | 关节角、指尖力、电机电流 | TBD |
| 上位机接口 | USB-C（驱动模块另走现场总线） | TBD |
| 材料 | 3D 打印 PA12/PETG + 6061 铝合金骨架 | TBD |

完整表格见 [docs/design/requirements.md](docs/design/requirements.md)。

## 仓库结构

```text
OpenTendonHand/
├── docs/                 设计、装配与规格文档
│   ├── design/           总体架构、需求、术语表
│   ├── mechanical/       机械规格与 BOM
│   ├── electronics/      电路规格与 BOM
│   ├── software/         控制栈架构
│   └── build/            装配与标定指南
├── hardware/
│   ├── mechanical/       CAD、工程图、3D 打印文件、BOM
│   └── electronics/      原理图、PCB、Gerber、BOM
├── firmware/             电机驱动、传感、实时控制
├── software/             SDK、上层控制、仿真、工具
├── assets/               Logo、渲染图、照片
└── scripts/              辅助脚本（打包、检查）
```

CAD、PCB 与网格文件通过 [Git LFS](#git-lfs-使用说明) 管理。

## 路线图

| 里程碑 | 内容 |
| --- | --- |
| **M0** | 仓库骨架、许可证、文档结构 |
| **M1** | 需求与运动学冻结 |
| **M2** | 机械设计冻结，发布 CAD |
| **M3** | 电路与固件打通（单指验证） |
| **M4** | 整手集成、遥操作、性能测试报告 |
| **M5** | v1.0 发布：完整搭建指南与装配说明 |

## 快速开始

目前还没有可以组装的东西——首批设计文件会在 M2/M3 阶段出现。届时：

```bash
git clone https://github.com/Artree021/OpenTendonHand.git
cd OpenTendonHand
git lfs pull
```

## 文档索引

| 文档 | 内容 |
| --- | --- |
| [docs/index.md](docs/index.md) | 文档总入口 |
| [docs/design/overview.md](docs/design/overview.md) | 总体架构与自由度分配 |
| [docs/design/requirements.md](docs/design/requirements.md) | 设计目标与验收标准 |
| [docs/mechanical/](docs/mechanical/README.md) | 机械设计说明（占位） |
| [docs/electronics/](docs/electronics/README.md) | 电路设计说明（占位） |
| [docs/software/architecture.md](docs/software/architecture.md) | 控制栈与 SDK |
| [docs/build/assembly-guide.md](docs/build/assembly-guide.md) | 装配与标定 |
| [docs/roadmap.md](docs/roadmap.md) | 里程碑 |
| [docs/licensing.md](docs/licensing.md) | 各部分的许可证说明 |

## Git LFS 使用说明

二进制设计文件用 Git LFS 存储：

```bash
git lfs install
git lfs pull
```

新增二进制格式时，请在同一个提交里更新 `.gitattributes`。

## 参与贡献

欢迎任何形式的贡献：CAD、电路评审、固件、控制理论、文档，或者直接指出这个
设计行不通。

- 先读 [CONTRIBUTING.md](CONTRIBUTING.md)。
- 动手做较大的改动前先开 issue，避免重复劳动。
- 讨论区：[GitHub Discussions](https://github.com/Artree021/OpenTendonHand/discussions)。

本项目遵循[行为准则](CODE_OF_CONDUCT.md)。

## 许可证

| 部分 | 许可证 |
| --- | --- |
| 硬件（CAD、工程图、PCB、BOM） | [CERN-OHL-S-2.0](LICENSE-HARDWARE) |
| 固件与软件 | [MIT](LICENSE) |
| 文档与图片 | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |

详见 [docs/licensing.md](docs/licensing.md)。

## 引用

如果这个设计对你的研究工作有帮助，请引用本项目，见 [CITATION.cff](CITATION.cff)。

```bibtex
@misc{opentendonhand,
  title  = {OpenTendonHand: An Open-Source High-DOF Tendon-Driven Dexterous Hand},
  author = {{OpenTendonHand Contributors}},
  year   = {2026},
  url    = {https://github.com/Artree021/OpenTendonHand}
}
```

## 致谢

设计决策会在确定时记录在案，并注明参考的论文与开源硬件项目。
