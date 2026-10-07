# Brainnet-Studio

**脑网络智能分析工具包 · Brain Network Intelligent Analysis Toolkit**

**v0.1.0 | Windows x64 | CUDA 12.1**

**中文版已发布 · 英文版已发布 / Chinese edition released · English edition released**

[中文说明](#中文说明) · [English documentation](#english-documentation)

**Citation:** Xiwei Zeng, Shengrong Li, Yiheng Liu, Chunwei Tian, Daoqiang Zhang, Qi Zhu. *BrainNet Studio: A Unified Toolkit for Brain Network Construction, Intelligent Analysis, and Visualization*. [arXiv:2609.37956](https://arxiv.org/abs/2609.37956).

## 中文说明

### 项目简介

Brainnet-Studio 是一款面向脑网络智能分析的可视化研究工具包，集成 27 种机器学习与深度学习方法，支持根据所选方法使用 fMRI、DTI 或多模态数据。Brainnet-Studio 将数据导入、网络构建、分类任务配置、模型训练和结果可视化整合到图形界面中，方便研究者开展实验与方法比较。

当前已发布中文版 **Windows 64 位 CUDA 可执行版本**，无需单独安装 Python 或配置 Python 依赖。英文界面版本也已发布。本文提供中英双语使用说明，并列出两个语言版本的文件命名规则。

### 语言版本与发布状态

| 软件版本 | 当前状态 | 主程序 | 压缩包文件名 |
| -------- | -------- | ------ | ------------ |
| 中文版 | 已发布 | 解压后的主程序 `.exe` | `Brainnet-Studio-chinese-v0.1.0.7z` |
| 英文版 | 已发布 | 解压后的主程序 `.exe` | `Brainnet-Studio-english-v0.1.0.7z` |

中文版压缩包使用 `Brainnet-Studio-chinese` 前缀，英文版使用 `Brainnet-Studio-english` 前缀；两个版本的 v0.1.0 均以单个 `.7z` 压缩包提供。请选择所需语言版本，只需下载对应的一个文件。

项目和下载压缩包统一使用 Brainnet-Studio 名称；现有 `.exe` 文件及程序内置数据目录保留原名，启动时请使用发行包内的主程序。

### 主要功能

| 功能           | 说明                                                         |
| -------------- | ------------------------------------------------------------ |
| 多方法集成     | 集成 27 种机器学习与深度学习方法，包括传统分类器、图神经网络及时间序列建模方法。 |
| 多模态数据分析 | 按方法支持 fMRI 时间序列、DTI 结构连接矩阵或多模态输入。     |
| 可视化实验配置 | 在界面中设置脑网络构建参数、分类分组、模型参数及训练参数。   |
| 训练前网络预览 | 查看实际输入网络及其构建规则，辅助检查数据与实验配置。       |
| 训练监控       | 查看模型训练进度及性能指标。                                 |
| 结果可视化     | 查看脑区与连接的重要性分析、连接矩阵及二维／三维交互式视图，并导出结果。 |
| AI 辅助分析    | 可选接入大语言模型服务，基于分析结果生成结构化辅助研究报告。 |

### 系统要求

| 项目        | 要求                                                         |
| ----------- | ------------------------------------------------------------ |
| 操作系统    | Windows 10 / 11，64 位                                       |
| 显卡与驱动  | 本发行包为 CUDA 12.1 版本，需要 NVIDIA GPU 及兼容驱动             |
| 内存        | 至少 4 GB；较大模型建议 8 GB 或以上，实际需求取决于数据规模和所选方法 |
| Python 环境 | 无需单独安装                                                 |
| 本地端口    | 默认使用 `5000`，可通过启动参数修改                          |
| 网络连接    | 部分页面图表、图标和报告渲染依赖公共 CDN；AI 辅助报告还需要访问所选模型服务 |

### 下载与启动

中英文版分别在对应的 Release 中提供一个完整的 `.7z` 压缩包，每个文件约 1.65 GB：

| 语言版本 | 下载压缩包 | 发布说明与 SHA-256 校验值 |
| -------- | ---------- | ----------------------- |
| 中文版 | [Brainnet-Studio-chinese-v0.1.0.7z](https://github.com/xbrainnet/Brainnet-Studio/releases/download/Brainnet-Studio-v0.1.0-chinese/Brainnet-Studio-chinese-v0.1.0.7z) | [中文版 Release](https://github.com/xbrainnet/Brainnet-Studio/releases/tag/Brainnet-Studio-v0.1.0-chinese) |
| 英文版 | [Brainnet-Studio-english-v0.1.0.7z](https://github.com/xbrainnet/Brainnet-Studio/releases/download/v0.1.0-english/Brainnet-Studio-english-v0.1.0.7z) | [英文版 Release](https://github.com/xbrainnet/Brainnet-Studio/releases/tag/v0.1.0-english) |

以下步骤适用于所下载的语言版本：

1. 下载所需语言版本的单个 `.7z` 文件，等待下载完成。
2. 使用 7-Zip 打开该 `.7z` 文件并解压。若同时使用两个版本，请分别解压到不同目录。
3. 完整保留解压后的文件夹。主程序需要同目录下的依赖文件，请勿只移动 `.exe` 文件。
4. 在所需语言版本的解压目录中双击 `start.bat`，或运行该目录中的主程序 `.exe`。
5. 浏览器将自动打开本地界面：[http://127.0.0.1:5000](http://127.0.0.1:5000)。

运行期间请保留程序的命令行窗口；关闭该窗口会停止本地服务。上述 `.7z` 文件是可运行的发行包，GitHub 自动生成的 `Source code` 压缩包不等同于该安装包。

### 数据准备

请准备已经完成预处理与脑区划分的 MATLAB `.mat` 数据。常用字段与维度如下，具体要求以所选方法为准：

| 数据             | 字段                   | 维度                 |
| ---------------- | ---------------------- | -------------------- |
| fMRI 时间序列    | `fdata`，也支持 `fmri` | `[N, R, T]`          |
| DTI 结构连接矩阵 | `DTI`，也支持 `dti`    | `[N, R, R]`          |
| 分类标签         | `label`，整数标签      | `[N, 1]` 或 `[1, N]` |

- `N`：受试者数量；`R`：脑区数量；`T`：时间点数量。
- 多模态数据中的受试者顺序和脑区顺序必须保持一致，标签顺序应与受试者顺序对应。
- 使用多模态合并上传时，在同一个 `.mat` 文件中提供 `fmri`、`DTI` 和 `label` 字段。
- 所需模态、脑区数及其他输入约束取决于具体方法，请以页面提示为准。

### 使用流程

1. **选择方法**：在首页选择适合研究任务的分析方法。
2. **导入数据**：上传 `.mat` 文件，或填写运行程序的计算机可访问的数据路径。
3. **配置任务与网络**：设置脑网络构建参数和分类分组，并预览输入网络。
4. **配置模型与训练**：调整模型及训练参数，确认配置后启动训练。
5. **查看结果**：查看训练指标及可视化结果；如页面提示，先运行特征重要性预计算，再查看脑区、连接及二维／三维视图。
6. **生成辅助报告（可选）**：进入“诊断”页面，配置模型服务并根据页面流程生成 AI 辅助分析报告。

### AI 辅助分析

Brainnet-Studio 支持配置 Anthropic、OpenAI 或 DeepSeek 等服务商的 API Key，默认不附带密钥。普通模型训练无需 API Key。

生成 AI 报告需要连接所选服务商；分析特征摘要及填写的补充说明会用于构建模型请求。具体可用模型以页面识别结果为准。

### 启动参数

在 PowerShell 中输入所需语言版本解压目录内主程序 `.exe` 的完整路径（输入时无需添加引号），再按需执行以下命令：

```powershell
# 选择已解压的主程序（中文或英文版）
$brainnetExecutable = Read-Host '请输入解压后的主程序 .exe 完整路径'
Set-Location -LiteralPath (Split-Path -Parent $brainnetExecutable)

# 使用其他端口
& $brainnetExecutable --port 8080

# 启动后不自动打开浏览器
& $brainnetExecutable --no-browser

# 指定数据保存目录
& $brainnetExecutable --data-dir "D:\Brainnet-StudioData"
```

中英文版使用相同参数；切换语言版本时，请重新选择对应解压目录中的主程序。

使用 `--port 8080` 后，通过 [http://127.0.0.1:8080](http://127.0.0.1:8080) 访问。

### 数据保存与随包资源

上传文件、训练日志、配置和模型检查点默认保存在：

```text
%APPDATA%\BrainToolbox\
```

该内置目录名为兼容现有程序而保留。可通过 `--data-dir` 修改保存位置。该目录独立于程序解压目录，删除程序文件夹不会自动清除其中的实验数据。

发行包包含 `examples/` 示例配置，以及 `nilearn_data/` 中的 AAL/SPM12 图谱与标签资源。图谱资源随包提供，但部分前端功能仍需联网加载资源。

### 常见问题

**解压失败或提示压缩包损坏**

确认所选语言版本的 `.7z` 文件已完整下载，并使用 7-Zip 解压。可按对应 Release 中的方法计算 SHA-256，与该页面公布的校验值比较；若不一致，请重新下载对应文件。

**程序无法启动或窗口立即关闭**

在 PowerShell 中按“启动参数”一节选择实际主程序，再运行 `& $brainnetExecutable` 查看错误信息。检查依赖文件是否完整，以及 NVIDIA 驱动是否满足该 CUDA 发行包的运行要求。

**浏览器没有自动打开**

确认程序仍在运行，再手动访问 `http://127.0.0.1:5000`；如修改了端口，请使用对应地址。

**端口被占用**

使用 `--port 8080` 等参数指定其他可用端口。

**部分图表或 AI 报告无法加载**

检查网络是否可以访问页面使用的公共 CDN 或所选模型服务。使用 AI 报告时，还需确认 API Key 和所选模型可用。

### 联系方式

邮箱：[xwzeng@nuaa.edu.cn](mailto:xwzeng@nuaa.edu.cn)

### 问题反馈

欢迎通过仓库 Issues 提交问题或建议。建议附上 Brainnet-Studio 版本及界面语言、Windows 版本、GPU 与驱动信息、所选方法、数据维度、复现步骤及错误日志。提交前请移除日志中的 API Key 和个人信息。

---

## English documentation

### Overview

Brainnet-Studio is graphical research toolkit for brain network intelligent analysis. It integrates 27 machine learning and deep learning methods and supports fMRI, DTI, or multimodal data, depending on the selected method. Its graphical interface brings together data import, network construction, classification task setup, model training, and result visualization to support experiments and method comparison.

The Chinese edition is available as a **Windows 64-bit CUDA executable package**. No separate Python installation or Python dependency setup is required. The English-interface edition has also been released. This bilingual README documents usage and the filenames for both language editions.

### Language editions and release status

| Edition | Current status | Executable | Archive filename |
| ------- | -------------- | ---------- | ---------------- |
| Chinese | Released | Main `.exe` in the extracted folder | `Brainnet-Studio-chinese-v0.1.0.7z` |
| English | Released | Main `.exe` in the extracted folder | `Brainnet-Studio-english-v0.1.0.7z` |

The Chinese package uses the `Brainnet-Studio-chinese` prefix, while the English package uses `Brainnet-Studio-english`. Each v0.1.0 edition is provided as a single `.7z` archive. Download the one file for your preferred language.

The project and downloadable archives use the Brainnet-Studio name; existing `.exe` files and the program's built-in data directory retain their original names. Launch the main executable included in the distribution.

### Features

| Feature                    | Description                                                  |
| -------------------------- | ------------------------------------------------------------ |
| Integrated methods         | 27 machine learning and deep learning methods, including conventional classifiers, graph neural networks, and temporal modeling methods. |
| Multimodal analysis        | Method-dependent support for fMRI time series, DTI structural connectivity matrices, or multimodal inputs. |
| Graphical experiment setup | Configure network construction, classification groups, model settings, and training parameters through the interface. |
| Input network preview      | Inspect the actual input networks and construction rules before training. |
| Training monitoring        | View training progress and performance metrics.              |
| Result visualization       | Explore brain region and connection importance, connectivity matrices, and interactive 2D/3D views, and export results. |
| AI-assisted analysis       | Optionally connect a large language model service to generate structured reports for research assistance. |

### System requirements

| Item                | Requirement                                                  |
| ------------------- | ------------------------------------------------------------ |
| Operating system    | Windows 10 / 11, 64-bit                                      |
| GPU and driver      | This CUDA 12.1 package requires an NVIDIA GPU and a compatible driver |
| Memory              | At least 4 GB; 8 GB or more is recommended for larger models. Actual requirements depend on the data and method |
| Python environment  | No separate installation required                            |
| Local port          | `5000` by default; configurable through a startup argument   |
| Internet connection | Some charts, icons, and report rendering depend on public CDNs; AI-assisted reports also require access to the selected model service |

### Download and launch

Each language edition provides one complete `.7z` archive in its corresponding Release. Each file is approximately 1.65 GB:

| Edition | Download archive | Release notes and SHA-256 checksum |
| ------- | ---------------- | --------------------------------- |
| Chinese | [Brainnet-Studio-chinese-v0.1.0.7z](https://github.com/xbrainnet/Brainnet-Studio/releases/download/Brainnet-Studio-v0.1.0-chinese/Brainnet-Studio-chinese-v0.1.0.7z) | [Chinese Release](https://github.com/xbrainnet/Brainnet-Studio/releases/tag/Brainnet-Studio-v0.1.0-chinese) |
| English | [Brainnet-Studio-english-v0.1.0.7z](https://github.com/xbrainnet/Brainnet-Studio/releases/download/v0.1.0-english/Brainnet-Studio-english-v0.1.0.7z) | [English Release](https://github.com/xbrainnet/Brainnet-Studio/releases/tag/v0.1.0-english) |

The following steps apply to the edition you download:

1. Download the single `.7z` file for your preferred language and wait for the download to finish.
2. Open the `.7z` file with 7-Zip and extract it. If using both editions, extract them into separate directories.
3. Keep the extracted folder intact. The executable depends on the accompanying files; do not move the `.exe` on its own.
4. Open `start.bat` in the extracted folder for your chosen language edition, or run the main `.exe` in that folder.
5. Your browser will automatically open the local interface at [http://127.0.0.1:5000](http://127.0.0.1:5000).

Keep the application's command window open while using Brainnet-Studio. Closing it stops the local service. The `.7z` archives above contain the runnable distribution; GitHub's automatically generated `Source code` archives are not equivalent to this package.

### Prepare your data

Prepare MATLAB `.mat` files containing data that have already undergone preprocessing and brain parcellation. Common fields and dimensions are listed below; the selected method determines the exact requirements.

| Data                                 | Field                             | Shape                |
| ------------------------------------ | --------------------------------- | -------------------- |
| fMRI time series                     | `fdata`; `fmri` is also supported | `[N, R, T]`          |
| DTI structural connectivity matrices | `DTI`; `dti` is also supported    | `[N, R, R]`          |
| Classification labels                | `label`, with integer labels      | `[N, 1]` or `[1, N]` |

- `N`: number of subjects; `R`: number of brain regions; `T`: number of time points.
- Subject and brain region ordering must match across modalities. Labels must follow the same subject order.
- For a combined multimodal upload, include `fmri`, `DTI`, and `label` in the same `.mat` file.
- Required modalities, region counts, and other input constraints depend on the method. Follow the instructions shown in the interface.

### Workflow

1. **Select a method:** choose a method suited to your research task on the home page.
2. **Import data:** upload a `.mat` file or provide a data path accessible to the computer running the application.
3. **Configure the task and networks:** set network construction parameters and classification groups, then preview the input networks.
4. **Configure and train the model:** adjust model and training settings, review the configuration, and start training.
5. **Inspect results:** explore training metrics and visualizations. If prompted, run feature importance precomputation before opening brain region, connection, and 2D/3D views.
6. **Generate an optional report:** open the AI-assisted analysis page (“诊断” in the Chinese edition), configure a model service, and follow the interface to generate an AI-assisted analysis report.

### AI-assisted analysis

Brainnet-Studio supports API Key configuration for providers such as Anthropic, OpenAI, and DeepSeek. No API Key is included. Standard model training does not require an API Key.

AI report generation requires access to the selected provider. Summarized analysis features and any supplementary notes you enter are used to construct the model request. Available models depend on the service detected by the interface.

### Startup arguments

In PowerShell, enter the full path to the main `.exe` in the extracted folder for your chosen language edition, without surrounding quotes. Then use the following commands as needed:

```powershell
# Choose the extracted main executable (Chinese or English edition)
$brainnetExecutable = Read-Host 'Enter the full path to the extracted main .exe'
Set-Location -LiteralPath (Split-Path -Parent $brainnetExecutable)

# Use a different port
& $brainnetExecutable --port 8080

# Start without automatically opening the browser
& $brainnetExecutable --no-browser

# Set a custom data directory
& $brainnetExecutable --data-dir "D:\Brainnet-StudioData"
```

Both language editions use the same arguments. To switch editions, select the main executable in the corresponding extracted folder again.

With `--port 8080`, open [http://127.0.0.1:8080](http://127.0.0.1:8080).

### Data storage and bundled resources

Uploaded files, training logs, configurations, and model checkpoints are saved by default under:

```text
%APPDATA%\BrainToolbox\
```

This built-in directory name is retained for compatibility with the existing application. Use `--data-dir` to change this location. This directory is separate from the extracted application folder, so deleting the application folder does not automatically remove your experiment data.

The distribution includes example configurations in `examples/` and AAL/SPM12 atlas and label resources in `nilearn_data/`. Although atlas resources are bundled, some frontend features still load resources from the internet.

### Troubleshooting

**Extraction fails or the archive is reported as damaged**

Check that the `.7z` file for your selected edition has finished downloading, then extract it with 7-Zip. Follow the checksum instructions in the corresponding Release to calculate SHA-256 and compare it with the published value. If the values differ, download the file again.

**The application does not start or its window closes immediately**

In PowerShell, select the actual executable as described in Startup arguments, then run `& $brainnetExecutable` to inspect the error. Check that all accompanying files are present and that the NVIDIA driver supports this CUDA distribution.

**The browser does not open automatically**

Confirm that the application is still running, then open `http://127.0.0.1:5000` manually. If you changed the port, use the corresponding address.

**The default port is already in use**

Select an available port using an argument such as `--port 8080`.

**Some charts or AI reports do not load**

Check connectivity to the public CDNs used by the interface or to the selected model service. For AI reports, also verify that your API Key and selected model are available.

### Contact

Email: [xwzeng@nuaa.edu.cn](mailto:xwzeng@nuaa.edu.cn)

### Feedback

Please use the repository's Issues page to report problems or suggest improvements. Include the Brainnet-Studio version and interface language, Windows version, GPU and driver information, selected method, data dimensions, reproduction steps, and error logs where relevant. Remove API Keys and personal information before sharing logs.
