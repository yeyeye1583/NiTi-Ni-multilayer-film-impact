# NiTi-Ni-multilayer-film-impact
Ni-NiTi Multilayer Thin Film Shock Simulation - LAMMPS MD. Investigates shock-induced behavior and phase transformations at atomic scale. Includes complete simulation scripts and analysis tools for impact dynamics research.

## 概述

核心模拟使用LAMMPS（一个广泛使用的开源分子动力学软件包）进行。主输入脚本配置了模型、原子间势函数、积分参数和分析例程。

## 文件与目录

- **`in.NiTitongjv`**: 主要的LAMMPS输入脚本。此文件定义了完整的模拟工作流程，包括：
  - 模型初始化和能量最小化。
  - 热力学平衡（NPT系综）。
  - 通过活塞方法进行冲击加载（NVE系综）。
  - 应力和温度等物性的在线计算与空间分布输出。

- **`Partial computational data`**: 此目录包含运行主脚本后获得的部分计算结果。它旨在用于验证和初步分析。内容可能包括：
  - `run.out`: 热力学输出。
  - `temp.profile`, `pressure.profile`: 温度和压力的空间分布文件。
  - `dumpschock_*.xyz`: 用于可视化的原子轨迹文件。

- **`Models and Parameters`**: 此目录存放定义模拟系统的基本输入文件。
  - `NiTi_Ni5cengNiTi.lmp`: 初始原子坐标数据文件。
  - `library.meam` 与 `NiTi.meam`: 定义Ni-Ti相互作用的修正嵌入原子法势函数文件。

## 开始使用

### 前提条件
*   您的系统必须安装LAMMPS。可以在 [LAMMPS官网](https://www.lammps.org/) 找到预编译的二进制文件或源代码。

### 自定义模拟
您可以通过编辑 `in.NiTitongjv` 文件轻松修改模拟参数。关键变量在脚本顶部定义：
- `stemperature`: 系统初始温度 (K)。
- `vpiston`: 活塞速度 (km/s)，控制冲击强度。
- `time_eq` 与 `time_shock`: 平衡阶段与冲击阶段的模拟时长。

## 许可证
MIT License

