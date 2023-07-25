# ECLab东西情报Beamer模板

## 生成pdf

确保安装了所有依赖：`python, pip, virtualenv, texlive-full, make`

其中`texlive-full`不是硬性要求，但至少需要`xelatex`和一些宏包：
`beamer, ctex, newtxtext, fontenc, graphicx, hyperref`

首先克隆仓库到本地：

```bash
git clone https://gitee.com/edenqwq/eclab-beamer
cd eclab-beamer
```

进入`eclab-beamer`后，首先运行`make setup`构建python虚拟环境

然后运行`make`即可生成`tex/eclab-beamer.pdf`

## toml文件格式

为方便收集和解析，本项目采用了toml格式存储文献信息

本项目规定的标准格式为：

```toml
[editor]
name = "你的名字" # 格式类似于Shuoan Li
degree = "你的学位" # 格式类似于Undergraduate, 2022

[article.1] # 罗马数字指定文献编号
title = "文献标题"
doi = "文献doi"
authors = "文献作者"
journal = "期刊名"
publish = "期刊发布信息" # 如发布日期，卷号、页码等
category = "分类" # Emotion, Face, Cross-culture等，注意首字母大写
summary = "你的概括" # 中文的概括
abstract = "文献摘要"
keywords = "关键词" # 用英文逗号分隔

[article.2] # 参照article.1
...

[article.3]
...
```

### *！！注意！！*

- 除了summary中的内容，其余所有标点（如双引号，作者和关键词中的逗号等）用英文标点
- 文献编号用罗马数字递增，格式为`[article.x]`
- 等号右边的内容一定要用英文双引号括起来