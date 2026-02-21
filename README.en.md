# SpharxHub - Physical World Data Infrastructure Platform

<div align="center">

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/docker-ready-green.svg)](https://www.docker.com/)
[![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20Windows-lightgrey.svg)](#)

**Building Physical World Data Infrastructure for the AI Era**

</div>

## 📋 Project Overview

SpharxHub is an end-to-end data infrastructure platform for embodied intelligence and physical world understanding. The platform consists of three core subsystems:

- **🧠 Workshop**: Physical World Data Factory - Automated pipeline from sensors to standardized datasets
- **🔬 Deepness**: Deep Processing Production Line - Physics property injection, interaction trajectory recording, and advanced processing
- **📊 Benchmark**: World Model Evaluation Center - Datasets, metrics, and evaluation benchmarks

Our mission is to become the "TSMC of data" for the AI era, providing high-quality, scalable physical world data solutions for embodied intelligence, robot vision, and physical simulation domains.

## 🏗️ Overall Architecture

```
SpharxHub/
├── workshop/           # L0-L2 Data Production Pipeline
│   ├── pipelines/      # 6 processing modules (ingest→quality→enhance→calibrate→pack→deliver)
│   ├── hardware/       # Hardware control (RealSense sync, calibration tools)
│   ├── dashboard/      # Web monitoring panel
│   └── schemas/        # Data model definitions
│
├── deepness/           # L2-L4 Deep Processing
│   ├── pipelines/      # Physics injection, interaction recording, evaluation export
│   ├── common/         # Shared components and models
│   └── base/           # Base Docker images
│
└── benchmark/          # Evaluation Benchmark Suite
    ├── datasets/       # Standard evaluation datasets
    ├── metrics/        # Evaluation metrics and tools
    └── results/        # Benchmark test results
```

## 🚀 Core Subsystems

### 1. Workshop - Physical World Data Factory ✅

**Status**: Production Ready (v3.1)

Automated data collection and processing pipeline based on Intel RealSense cameras, completed features include:

- ✅ Hardware synchronization solution (3×D455 camera synchronized capture)
- ✅ Real data parsing (RGB video, depth maps, IMU data extraction)
- ✅ Automated quality inspection (blur/exposure/frame drop detection)
- ✅ Semantic annotation (YOLOv8 object detection)
- ✅ Camera calibration (checkerboard intrinsic calibration)
- ✅ Dataset packaging (SHA256 hash verification)
- ✅ Web monitoring panel (Streamlit)

**Tech Stack**: Python 3.10+, Docker, OpenCV, PyTorch, YOLOv8, Intel RealSense SDK

### 2. Deepness - Deep Processing Production Line ⚡

**Status**: In Development

Advanced physical world processing platform based on Fast-SAM3D:

- 🔨 Physics property injection module (Fast-SAM3D, PyTorch3D, Open3D)
- 📝 Interaction trajectory recording module (reserved)
- 📤 Evaluation data export module (Genie Sim 3.0, NVIDIA Cosmos format)

**Tech Stack**: Fast-SAM3D, PyTorch 2.5.1, CUDA 12.1, PyTorch3D 0.7.6

### 3. Benchmark - Evaluation Center 📊

**Status**: In Planning

Standardized evaluation platform for world models:

- 📁 Evaluation dataset management
- 📏 Performance metric definition
- 📊 Result analysis tools
- 🔄 Benchmark testing scripts

## 🛠️ Technical Features

### 🏭 Industrial Production
- **Modular Design**: Each processing stage is containerized independently, supporting plug-and-play expansion
- **Configuration Separation**: All parameters centrally managed, supporting environment variable override
- **Exception Handling**: Comprehensive logging system and error recovery mechanisms
- **Quality Assurance**: Automated quality inspection and data integrity verification

### 🔧 Developer Friendly
- **Dockerized**: One-click build and deployment of all services
- **Multi-platform Support**: Linux/Windows dual-platform compatibility
- **Complete Documentation**: Detailed development documentation and usage guides
- **Test Coverage**: Unit testing and integration testing framework

### 🚀 High-Performance Computing
- **GPU Acceleration**: CUDA-optimized deep learning inference
- **Batch Processing Optimization**: Supports large-scale data parallel processing
- **Resource Management**: Intelligent memory and GPU memory management

## 📦 Quick Start

### System Requirements

- **Operating System**: Ubuntu 22.04 / Windows 10+
- **Docker**: 20.10+
- **GPU**: NVIDIA GPU (optional, for deep learning modules)
- **Memory**: 16GB+ RAM
- **Storage**: 100GB+ available space

### Installation and Deployment

```bash
# Clone repository
git clone https://gitee.com/spharx/spharxhub.git
cd spharxhub

# Build Workshop system
cd workshop
docker-compose build

# Start data processing pipeline
./scripts/pipeline/run_full.sh /path/to/your/recording.bag
```

### Usage Example

```python
# Workshop data processing example
from workshop.pipelines.ingest.parser import RealSenseParser
from workshop.pipelines.quality.detector import QualityDetector

# Parse RealSense data
parser = RealSenseParser()
data = parser.parse('/path/to/recording.bag')

# Quality detection
quality_checker = QualityDetector()
report = quality_checker.analyze(data)
```

## 📊 Project Status

| Subsystem | Status | Version | Completion |
|-----------|--------|---------|------------|
| Workshop | ✅ Production Ready | v3.1 | 100% |
| Deepness | ⚡ In Development | v0.1 | 60% |
| Benchmark | 📊 In Planning | v0.0 | 20% |

**Overall Progress**: 60%

## 🤝 Contribution Guidelines

We welcome contributions in various forms:

1. **Report Issues**: Submit bugs or feature requests
2. **Code Contributions**: Submit Pull Requests
3. **Documentation Improvement**: Enhance usage documentation
4. **Testing Enhancement**: Increase test coverage

Please refer to each subsystem's CONTRIBUTING.md file for specific contribution processes.

## 📚 Documentation Resources

- [📘 Complete Workshop Documentation](workshop/README.md)
- [🔬 Deepness Technical Documentation](deepness/README.md)
- [📊 Benchmark Design Documentation](benchmark/README.md)
- [📈 Project Progress Report](workshop/PROGRESS.md)

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🌟 Acknowledgements

Thanks to the following open-source projects for their contributions:

- [Intel RealSense SDK](https://github.com/IntelRealSense/librealsense)
- [YOLOv8](https://github.com/ultralytics/ultralytics)
- [Fast-SAM3D](https://github.com/wlfeng0509/Fast-SAM3D)
- [Open3D](http://www.open3d.org/)
- [PyTorch3D](https://pytorch3d.org/)

---

<div align="center">

**SpharxHub** —— Starting with Data, Ending with Intelligence

*Building Physical World Data Infrastructure for the AI Era*

</div>