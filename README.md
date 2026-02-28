# SpharxWorks - 物理世界数据基础设施平台

<div align="center">

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/docker-ready-green.svg)](https://www.docker.com/)
[![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20Windows-lightgrey.svg)](#)

**构建 AI 时代的物理世界数据基础设施**

*"From data intelligence emerges"*
*"始于数据，终于智能"*

</div>

</div>

## 📋 项目简介

SpharxWorks 是一个面向具身智能和物理世界理解的端到端数据基础设施平台。平台采用工业化生产理念，通过三条核心生产线实现从原始传感器数据到高质量评测数据集的完整转换链路：

- **🧠 Workshop (L0-L2)**: 物理世界数据工厂 - 从传感器到标准化数据集的自动化流水线
- **🔬 Deepness (L2-L4)**: 深度加工生产线 - 物理属性注入、交互轨迹记录和高级处理
- **📊 Benchmark (L4+)**: 世界模型评测中心 - 数据集、指标和评测基准

我们的使命是成为人工智能时代的"数据台积电"，为具身智能、机器人视觉、物理仿真等领域提供高质量、可扩展的物理世界数据解决方案。

## 🏗️ 整体架构

```
SpharxWorks/
├── workshop/              # L0-L2 数据生产流水线 (✅ 生产就绪 v3.1)
│   ├── pipelines/         # 6个处理模块（采集→质检→增强→标定→打包→交付）
│   │   ├── 00_ingest/     # 数据导入与隐私脱敏
│   │   ├── 01_quality/    # 多层次质量检测
│   │   ├── 02_enhance/    # YOLOv8语义标注
│   │   ├── 03_calibrate/  # 相机内外参标定
│   │   ├── 04_pack/       # 标准格式打包
│   │   └── 05_delivery/   # 多协议数据交付
│   ├── hardware/          # 硬件控制层
│   │   ├── camera/        # RealSense相机管理
│   │   └── calibration/   # 标定工具集
│   ├── dashboard/         # Web监控面板 (Streamlit)
│   ├── common/            # 公共组件
│   └── base/              # 基础Docker镜像
│
├── deepness/              # L2-L4 深度加工 (⚡ 开发中 v0.1)
│   ├── pipelines/         # 3个核心模块
│   │   ├── 01_physics_injection/    # Fast-SAM3D物理属性注入
│   │   ├── 02_interaction_recording/ # 交互轨迹记录
│   │   └── 03_benchmark_export/     # 评测格式导出
│   ├── common/            # 共享组件和模型
│   ├── partdata/          # 本地化依赖管理
│   └── base/              # CUDA优化基础镜像
│
└── benchmark/             # 评测基准套件 (📊 规划中 v0.0)
    ├── datasets/          # 标准评测数据集
    ├── metrics/           # 评测指标和工具
    └── results/           # 基准测试结果
```

## 🚀 核心子系统状态

### 1. Workshop - 物理世界数据工厂 ✅ 生产就绪 (v3.1)

**核心能力**:
- ✅ 硬件同步方案（3×D455相机同步采集，毫秒级精度）
- ✅ 真实数据解析（RGB视频、深度图、IMU数据一体化提取）
- ✅ 自动化质检（模糊检测、曝光分析、丢帧统计、完整性验证）
- ✅ 语义标注（YOLOv8目标检测，COCO格式输出）
- ✅ 相机标定（棋盘格内参标定，重投影误差<0.5px）
- ✅ 数据集打包（SHA256哈希验证，ROS/COCO双格式支持）
- ✅ Web监控面板（实时状态监控、处理进度可视化）

**技术架构**:
- **容器化部署**: 基于Docker的模块化微服务架构
- **配置管理**: 统一YAML配置系统，支持环境变量覆盖
- **数据流**: 标准化输入输出接口，模块间松耦合
- **监控体系**: Streamlit仪表板 + 结构化日志系统


### 2. Deepness - 深度加工生产线 ⚡ 开发中 (v0.1)

**核心模块**:
- 🔨 **物理属性注入** (01_physics_injection)
  - Fast-SAM3D单视图3D重建
  - PyTorch3D/Open3D后处理优化
  - .obj/.glb网格格式输出
  
- 📝 **交互轨迹记录** (02_interaction_recording)  
  - YOLO动态物体检测
  - ORB-SLAM3相机轨迹估计（预留真实SLAM）
  - PyBullet反事实轨迹生成
  - ToucHD分层轨迹记录

- 📤 **评测数据导出** (03_benchmark_export)
  - Genie Sim 3.0格式适配
  - NVIDIA Cosmos格式支持
  - 标准化评测数据结构

**技术特色**:
- **离线优先构建**: 所有依赖本地化管理，构建过程零网络依赖
- **分层镜像架构**: 基础层→共享层→模块层→运行时层
- **版本锁定机制**: 通过commit hash确保构建可重现


### 3. Benchmark - 评测中心 📊 规划中 (v0.0)

**规划功能**:
- 📁 标准化评测数据集管理
- 📏 世界模型性能指标体系
- 📊 多维度结果分析工具
- 🔄 自动化基准测试框架

## 🛠️ 技术架构特色

### 🏭 工业化生产体系

**模块化设计**
- 每个处理阶段独立容器化，支持插拔式扩展
- 标准化输入输出接口，模块间松耦合
- 统一异常处理和错误恢复机制

**配置驱动**
- 集中式YAML配置管理
- 环境变量灵活覆盖
- 运行时参数动态调整

**质量保障**
- 自动化质检贯穿全流程
- 数据完整性SHA256校验
- 多层次日志记录和监控

### 🔧 工程化实践

**容器化部署**
- Docker Compose编排管理
- 基础镜像分层复用
- 多平台(Linux/Windows)兼容

**依赖管理**
- 离线优先的本地化策略
- 多源镜像容错重试机制
- 版本锁定确保可重现构建

**开发体验**
- 完善的文档体系
- 标准化的编码规范
- 自动化测试框架

### 📈 项目健康度指标

| 指标类别 | 当前状态 | 目标值 | 说明 |
|---------|---------|--------|------|
| **代码质量** | 95% | 98%+ | 语法正确性、逻辑合理性 |
| **测试覆盖率** | 75% | 90%+ | 单元测试、集成测试 |
| **文档完整度** | 80% | 95%+ | 技术文档、使用指南 |
| **构建成功率** | 99% | 100% | CI/CD流水线稳定性 |
| **安全合规** | 100% | 100% | 安全扫描、漏洞修复 |

### 🚀 高性能计算

**GPU加速**
- CUDA 12.1优化的深度学习推理
- PyTorch3D几何计算加速
- 批处理并行化处理

**资源优化**
- 智能内存和显存管理
- 多进程并发处理
- 资源使用监控和限制

## 📦 快速开始

### 环境要求

```bash
# 系统环境
- 操作系统: Ubuntu 22.04 LTS / Windows 10+
- Docker Engine: 20.10+
- 内存: 16GB+ RAM (推荐32GB)
- 存储: 100GB+ 可用空间
- GPU: NVIDIA GPU (可选，用于深度学习模块)

# 软件依赖
- Python 3.10+
- Docker Compose v2.0+
- NVIDIA Container Toolkit (GPU支持)
```

### 安装部署

```bash
# 1. 克隆项目仓库
git clone https://gitee.com/spharx/spharxhub.git
cd spharxhub

# 2. 初始化子模块
git submodule update --init --recursive

# 3. 构建 Workshop 系统
cd workshop
cp .env.template .env
# 编辑 .env 文件配置必要参数

# 构建基础镜像
docker-compose build base

# 构建所有服务
./scripts/build_all.sh

# 4. 启动服务
docker-compose up -d

# 5. 验证部署
docker-compose ps
```

### 数据处理示例

```bash
# 处理单个RealSense数据文件
./scripts/pipeline/run_full.sh /path/to/your/recording.bag

# 启动Web监控面板
streamlit run dashboard/app.py

# 查看处理日志
docker-compose logs -f
```

### Python API 使用

```python
# Workshop 数据处理示例
from workshop.common.scripts.config_loader import load_config
from workshop.pipelines.ingest.runner import IngestRunner
from workshop.pipelines.quality.runner import QualityRunner

# 加载配置
config = load_config('workshop/common/configs/pipeline_config.yaml')

# 数据导入
ingest_runner = IngestRunner(config)
raw_data = ingest_runner.process('/path/to/recording.bag')

# 质量检测
quality_runner = QualityRunner(config)
quality_report = quality_runner.analyze(raw_data)

print(f"数据质量评分: {quality_report.overall_score}")
```

## 📊 项目状态概览

| 子系统 | 状态 | 版本 | 完成度 | 核心功能 |
|--------|------|------|--------|----------|
| **Workshop** | ✅ 生产就绪 | v3.1 | 100% | 完整L0-L2数据处理流水线 |
| **Deepness** | ⚡ 开发中 | v0.1 | 65% | 物理属性注入、交互记录 |
| **Benchmark** | 📊 规划中 | v0.0 | 25% | 评测基准框架 |

**总体进度**: 63%

### 质量保障状态

- ✅ **代码质量**: 95% (语法检查通过，逻辑合理)
- ✅ **配置管理**: 100% (YAML/JSON配置完整正确)
- ⚠️ **文档完备性**: 80% (核心文档齐全，部分模块文档待补充)
- ✅ **工程化实践**: 90% (容器化部署、依赖管理机制健全)

### 近期里程碑

- ✅ **v3.1 (2026.2)**: Workshop生产就绪版本发布，完成全面代码质量检查
- ⏳ **v0.2 (Q2 2026)**: Deepness模块功能完善，增加更多3D处理算法
- 📅 **v1.0 (Q3 2026)**: 三条生产线协同工作版本，完善文档体系
- 🚀 **v2.0 (规划中)**: 云原生自动化生产平台，支持分布式处理

### 最近更新 (2026.2)

- ✅ 完成Workshop项目全面代码和文档质量检查
- ✅ 修复Python文件编码问题，确保跨平台兼容性
- ✅ 完善依赖管理机制，建立版本锁定体系
- ✅ 优化目录结构，提升项目可维护性
- ⏳ 补充Pipeline模块文档（进行中）
- ⏳ Deepness模块功能开发持续推进
- 🔲 Benchmark评测框架设计规划

## 🤝 贡献指南

我们欢迎社区的各种形式贡献：

### 当前重点关注领域

1. **文档完善** 📚
   - Pipeline模块使用文档补充
   - API接口文档生成
   - 最佳实践案例整理

2. **功能增强** ⚡
   - 新的3D重建算法集成
   - 更多相机型号支持
   - 云存储协议扩展

### 贡献方式

1. **报告问题**: 提交Bug报告或功能需求
2. **代码贡献**: 提交Pull Request改进功能
3. **文档完善**: 优化使用文档和技术说明
4. **测试增强**: 增加测试覆盖率和用例
5. **用户体验**: 改进安装部署流程和使用体验

### 开发流程

```bash
# 1. Fork项目到个人仓库
# 2. 创建功能分支
git checkout -b feature/your-feature-name

# 3. 开发并测试
# 遵循项目编码规范
# 编写相应测试用例

# 4. 提交更改
git commit -m "feat: add new feature description"

# 5. 推送到远程仓库
git push origin feature/your-feature-name

# 6. 创建Pull Request
```

### 代码规范

- 遵循PEP 8 Python编码规范
- 使用类型提示增强代码可读性
- 编写清晰的docstring文档
- 保持模块间接口一致性

## 📚 文档资源

### 核心文档

- [📘 Workshop完整文档](workshop/README.md) - 数据工厂详细说明
- [🔬 Deepness技术文档](deepness/README.md) - 深度加工技术细节
- [📊 Benchmark设计文档](benchmark/README.md) - 评测系统规划
- [📈 项目进度报告](workshop/docs/PROGRESS.md) - 开发里程碑跟踪
- [📋 质量检查报告](workshop/docs/COMPREHENSIVE_CODE_AND_DOCUMENTATION_CHECK_REPORT.md) - 全面代码质量评估

### 技术规范

- [⚙️ 编码标准](workshop/docs/CODING_STANDARDS.md) - 开发规范和最佳实践
- [🔒 安全政策](workshop/docs/SECURITY.md) - 安全实践和漏洞报告
- [🤝 贡献指南](workshop/docs/CONTRIBUTING.md) - 详细贡献流程

### 架构设计

- [🏗️ Workshop架构文档](workshop/docs/WORKSHOP_ARCH.md) - 系统架构详解
- [🔬 Deepness架构说明](deepness/docs/DEEPNESS_ARCH.md) - 深度处理架构

## 🌟 技术生态

### 核心依赖

**计算机视觉**
- [Intel RealSense SDK](https://github.com/IntelRealSense/librealsense) - 硬件驱动和数据采集
- [OpenCV](https://opencv.org/) - 图像处理基础库
- [YOLOv8](https://github.com/ultralytics/ultralytics) - 目标检测框架

**3D处理与重建**
- [Fast-SAM3D](https://github.com/wlfeng0509/Fast-SAM3D) - 单视图3D重建
- [Open3D](http://www.open3d.org/) - 3D数据处理
- [PyTorch3D](https://pytorch3d.org/) - 几何深度学习

**深度学习框架**
- [PyTorch](https://pytorch.org/) - 深度学习核心框架
- [CUDA](https://developer.nvidia.com/cuda-zone) - GPU加速计算

### 基础设施

- [Docker](https://www.docker.com/) - 容器化部署
- [Streamlit](https://streamlit.io/) - Web监控面板
- [Prometheus](https://prometheus.io/) - 监控指标收集（规划中）

## 📄 许可证

本项目采用 MIT 许可证，详情请查看 [LICENSE](LICENSE) 文件。

## 🙏 致谢

感谢以下开源项目和社区的支持：

### 核心技术组件
- [Intel RealSense SDK](https://github.com/IntelRealSense/librealsense) - 提供可靠的硬件接口
- [YOLOv8](https://github.com/ultralytics/ultralytics) - 业界领先的实时目标检测
- [Fast-SAM3D](https://github.com/wlfeng0509/Fast-SAM3D) - 高效的单视图3D重建
- [Open3D](http://www.open3d.org/) - 强大的3D数据处理能力
- [PyTorch3D](https://pytorch3d.org/) - 几何深度学习框架

### 基础设施支持
- [Docker](https://www.docker.com/) - 容器化技术基石
- [Streamlit](https://streamlit.io/) - 简洁高效的可视化界面
- [GitHub](https://github.com/) - 代码托管和协作平台

### 社区贡献
特别感谢所有为开源社区做出贡献的开发者们，正是你们的努力让这样的项目成为可能。

---

<div align="center">

<h1>SpharxWorks</h1>

<h3>From data intelligence emerges</h3>
<h3>始于数据，终于智能</h3>

<p><em>构建 AI 时代的物理世界数据基础设施</em></p>

[项目官网](https://spharx.com) · [技术博客](https://blog.spharx.com) · [社区讨论](https://gitee.com/spharx/spharxhub/issues)

### 📞 联系我们

- 📧 邮箱: lidecheng@spharx.com

### 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=spharx/spharxhub&type=Date)](https://star-history.com/#spharx/spharxhub&Date)

</div>