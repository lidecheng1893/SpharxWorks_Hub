# SpharxHub - 物理世界数据基础设施平台

<div align="center">

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/docker-ready-green.svg)](https://www.docker.com/)
[![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20Windows-lightgrey.svg)](#)

**构建 AI 时代的物理世界数据基础设施**

</div>

## 📋 项目简介

SpharxHub 是一个面向具身智能和物理世界理解的端到端数据基础设施平台。平台分为三个核心子系统：

- **🧠 Workshop**: 物理世界数据工厂 - 从传感器到标准化数据集的自动化流水线
- **🔬 Deepness**: 深度加工生产线 - 物理属性注入、交互轨迹记录和高级处理
- **📊 Benchmark**: 世界模型评测中心 - 数据集、指标和评测基准

我们的使命是成为人工智能时代的"数据台积电"，为具身智能、机器人视觉、物理仿真等领域提供高质量、可扩展的物理世界数据解决方案。

## 🏗️ 整体架构

```
SpharxHub/
├── workshop/           # L0-L2 数据生产流水线
│   ├── pipelines/      # 6个处理模块（采集→质检→增强→标定→打包→交付）
│   ├── hardware/       # 硬件控制（RealSense同步、标定工具）
│   ├── dashboard/      # Web监控面板
│   └── schemas/        # 数据模型定义
│
├── deepness/           # L2-L4 深度加工
│   ├── pipelines/      # 物理属性注入、交互记录、评测导出
│   ├── common/         # 共享组件和模型
│   └── base/           # 基础Docker镜像
│
└── benchmark/          # 评测基准套件
    ├── datasets/       # 标准评测数据集
    ├── metrics/        # 评测指标和工具
    └── results/        # 基准测试结果
```

## 🚀 核心子系统

### 1. Workshop - 物理世界数据工厂 ✅

**状态**: 生产就绪 (v3.1)

基于 Intel RealSense 相机的自动化数据采集与处理流水线，已完成功能包括：

- ✅ 硬件同步方案（3×D455相机同步采集）
- ✅ 真实数据解析（RGB视频、深度图、IMU数据提取）
- ✅ 自动化质检（模糊/曝光/丢帧检测）
- ✅ 语义标注（YOLOv8目标检测）
- ✅ 相机标定（棋盘格内参标定）
- ✅ 数据集打包（SHA256哈希验证）
- ✅ Web监控面板（Streamlit）

**技术栈**: Python 3.10+, Docker, OpenCV, PyTorch, YOLOv8, Intel RealSense SDK

### 2. Deepness - 深度加工生产线 ⚡

**状态**: 开发中

基于 Fast-SAM3D 的高级物理世界处理平台：

- 🔨 物理属性注入模块（Fast-SAM3D, PyTorch3D, Open3D）
- 📝 交互轨迹记录模块（预留）
- 📤 评测数据导出模块（Genie Sim 3.0, NVIDIA Cosmos 格式）

**技术栈**: Fast-SAM3D, PyTorch 2.5.1, CUDA 12.1, PyTorch3D 0.7.6

### 3. Benchmark - 评测中心 📊

**状态**: 规划中

面向世界模型的标准化评测平台：

- 📁 评测数据集管理
- 📏 性能指标定义
- 📊 结果分析工具
- 🔄 基准测试脚本

## 🛠️ 技术特色

### 🏭 工业化生产
- **模块化设计**: 每个处理阶段独立容器化，支持插拔式扩展
- **配置分离**: 所有参数集中管理，支持环境变量覆盖
- **异常处理**: 完善的日志系统和错误恢复机制
- **质量保证**: 自动化质检和数据完整性验证

### 🔧 开发者友好
- **Docker 化**: 一键构建和部署所有服务
- **多平台支持**: Linux/Windows 双平台兼容
- **文档完备**: 详细的开发文档和使用指南
- **测试覆盖**: 单元测试和集成测试框架

### 🚀 高性能计算
- **GPU 加速**: CUDA 优化的深度学习推理
- **批处理优化**: 支持大规模数据并行处理
- **资源管理**: 智能的内存和显存管理

## 📦 快速开始

### 环境要求

- **操作系统**: Ubuntu 22.04 / Windows 10+
- **Docker**: 20.10+
- **GPU**: NVIDIA GPU (可选，用于深度学习模块)
- **内存**: 16GB+ RAM
- **存储**: 100GB+ 可用空间

### 安装部署

```bash
# 克隆仓库
git clone https://gitee.com/spharx/spharxhub.git
cd spharxhub

# 构建 Workshop 系统
cd workshop
docker-compose build

# 启动数据处理流水线
./scripts/pipeline/run_full.sh /path/to/your/recording.bag
```

### 使用示例

```python
# Workshop 数据处理示例
from workshop.pipelines.ingest.parser import RealSenseParser
from workshop.pipelines.quality.detector import QualityDetector

# 解析 RealSense 数据
parser = RealSenseParser()
data = parser.parse('/path/to/recording.bag')

# 质量检测
quality_checker = QualityDetector()
report = quality_checker.analyze(data)
```

## 📊 项目状态

| 子系统 | 状态 | 版本 | 完成度 |
|--------|------|------|--------|
| Workshop | ✅ 生产就绪 | v3.1 | 100% |
| Deepness | ⚡ 开发中 | v0.1 | 60% |
| Benchmark | 📊 规划中 | v0.0 | 20% |

**总体进度**: 60%

## 🤝 贡献指南

我们欢迎各种形式的贡献：

1. **报告问题**: 提交 Bug 或功能需求
2. **代码贡献**: 提交 Pull Request
3. **文档改进**: 完善使用文档
4. **测试完善**: 增加测试覆盖率

请参考各子系统的 CONTRIBUTING.md 文件了解具体贡献流程。

## 📚 文档资源

- [📘 Workshop 完整文档](workshop/README.md)
- [🔬 Deepness 技术文档](deepness/README.md)
- [📊 Benchmark 设计文档](benchmark/README.md)
- [📈 项目进度报告](workshop/PROGRESS.md)

## 📄 许可证

本项目采用 MIT 许可证，详情请查看 [LICENSE](LICENSE) 文件。

## 🌟 致谢

感谢以下开源项目的贡献：

- [Intel RealSense SDK](https://github.com/IntelRealSense/librealsense)
- [YOLOv8](https://github.com/ultralytics/ultralytics)
- [Fast-SAM3D](https://github.com/wlfeng0509/Fast-SAM3D)
- [Open3D](http://www.open3d.org/)
- [PyTorch3D](https://pytorch3d.org/)

---

<div align="center">

**SpharxHub** —— 始于数据，终于智能

*构建 AI 时代的物理世界数据基础设施*

</div>