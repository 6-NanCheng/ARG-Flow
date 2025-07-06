# ARG-HGT 复现项目

## 项目简介

本仓库用于复现 Lund et al. (2025) 论文 “Genetic compatibility and ecological connectivity drive the dissemination of antibiotic resistance genes” 中的关键结果，包括主图（Fig2–Fig5）和补充图。

[全文链接](https://www.nature.com/articles/s41467-025-57825-3)



## 项目结构

```bash
- data_for_figures/     # 存放用于生成图表的原始数据文件
- report/               # HTML 格式的分析报告目录
  - Main Results.html   # 主要结果报告，包含关键指标和可视化
  - Supp Results.html   # 补充结果报告，包含附加分析和细节
- results/              # 最终导出的图像文件目录
- supp_results/         # 生成补充的结果
- Main Results.ipynb    # 生成主结果的 Jupyter 笔记本
- Supp Results.ipynb    # 生成补充结果的 Jupyter 笔记本
- README.md             # 说明文档
```




## 数据与代码准备

在以下地址下载并解压所需数据与代码

[下载地址](https://zenodo.org/records/14901409)

## 复现简要过程

1、在 RStudio中下载复现所需包（所需包在每一段代码前都有标注，直接下载即可）比如：

```bash
# Load packages
library(caret)
library(dplyr)
library(tidyr)
library(forcats)
library(data.table)
library(randomForest)
library(pROC)
library(utils)
library(patchwork)
```

则需要下载标注的所需包

2、在vscode中运行各部分代码：

在Jupyter Notebook 文件（*.ipynb 格式）中运行R代码，在右上角选择内核“Jupyter Kernel”，找到自己的R内核就能加载运行所需包，接着一步一步运行即可。

运行“Main Results.ipynb”的主结果在results文件夹下、运行“Supp Results.ipynb”的补充结果在supp_results文件夹下

3、html文件的生成

打开命令行工具（终端 / Anaconda Prompt / PowerShell）

```bash
# 输入命令（将路径替换为你自己的）

cd 路径/到/你的/项目文件夹

# 使用命令转换为 HTML 文件：

jupyter nbconvert --to html "Main Results.ipynb"
jupyter nbconvert --to html "Supp Results.ipynb"

# 执行成功后，目录下会生成：

Main Results.html
Supp Results.html

```


联系与反馈
如有问题，请在本仓库 Issues 提问，或联系项目负责人 Jun-Hao。 祝复现顺利！
