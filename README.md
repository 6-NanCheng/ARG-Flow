# ARG-HGT 复现项目

## 项目简介
本仓库用于复现 Lund et al. (2025) 论文 “Genetic compatibility and ecological connectivity drive the dissemination of antibiotic resistance genes” 中的关键结果，包括主图（Fig2–Fig5）和补充图。

---

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


---

## 数据准备
在项目根目录运行以下命令解压数据：
```bash
tar -xzf data_for_figures.tar.gz
解压后会生成 data_for_figures/ 文件夹，包含运行脚本所需的所有数据。

使用方法
打开 R 或 RStudio，将工作目录切换到项目根目录。

运行主图脚本生成主图：

r
source("generate_main_figures.R")
运行补充图脚本生成补充图：

r
source("generate_supplementary_figures.R")
所有生成的 PNG/PDF 图像将保存在 figures/ 和 figures/supplementary/ 下，与论文图号对应。

依赖环境
R ≥ 4.2.0

以下 R 包（建议一次性安装）：

aplot (≥ 0.2.3)

caret (≥ 6.0-94)

corrplot (≥ 0.92)

data.table (≥ 1.15.4)

GGally (≥ 2.2.1)

igraph (≥ 2.0.3)

patchwork (≥ 1.2.0)

pdp (≥ 0.8.1)

pROC (≥ 1.18.5)

randomForest (≥ 4.7-11)

readxl (≥ 1.4.3)

rfPermute (≥ 2.5.2)

rfUtilities (≥ 2.1-5)

tidyverse (≥ 2.0.0)

vegan (≥ 2.6-6.1)

一键安装依赖
在 R 控制台中执行：

r
install.packages(c(
  "aplot","caret","corrplot","data.table","GGally","igraph",
  "patchwork","pdp","pROC","randomForest","readxl",
  "rfPermute","rfUtilities","tidyverse","vegan"
))
报告生成
若需生成 HTML/Markdown 报告，可使用 quarto 或 RMarkdown：

bash
# 安装 Quarto CLI
conda install -c conda-forge quarto
# 渲染报告
quarto render report/report.qmd --to html
quarto render report/report.qmd --to gfm
生成的报告文件将存放在 report/ 目录下。

联系与反馈
如有问题，请在本仓库 Issues 提问，或联系项目负责人 俊豪 (jh-reproduce@researchmail.edu.cn)。 祝复现顺利！
