---
title: "Pyfinny - Company Analysis with Python"
date: 2022-08-22
draft: false
---
## 简介
这是一个命令行界面（CLI）工具，用于分析财务报表和进行现金流折现（DCF）和可比性分析。该工具使用Financial Modelling Prep API，这需要一个API密钥。可以在Github资源库中找到源代码和发布的二进制文件[这里](https://github.com/larry-lime/pyfinny)

## 要求
1. 安装Python 3.10
2. 拥有[金融建模准备]的账户(https://site.financialmodelingprep.com/)
3. Bash或Zsh终端。强烈建议Windows用户使用WSL

## 可选要求
1. [Sqlite Browser](https://sqlitebrowser.org/)以查看和操作数据库中的数据
2. 2. [Homebrew](https://brew.sh/)和Git来开发应用程序。

## 安装
注意：在MacOS上使用`python3`,`pip3`，在Windows上使用`python`, `pip`。
1. 克隆版本库或下载[release binary](https://github.com/larry-lime/pyfinny/releases/download/v1.0.0/pyfinny-1.0.0.zip)
    ``shell
    git clone https://github.com/larry-lime/pyfinny.git
    cd pyfinny
    ```
2. 创建并启动Python虚拟环境
    ```shell
    python -m venv venv
    ```
3. 激活Python虚拟环境
    ``shell
    source venv/bin/activate
    ```
4. 安装需求
    ```shell
    pip3安装。
    ```
## 使用方法
在你的终端运行`pyfin`，开始使用该应用程序
###设置

在开始分析之前，你必须运行设置命令，以提供你的金融建模准备API密钥，并创建必要的数据库。
```shell
pyfin setup
```

### 打开Excel文件

要打开一个Excel文件，请使用open命令，并提供不含文件扩展名的文件名。`-d`或`-resource_dir`选项可以用来指定Excel文件所在的目录。如果没有提供，默认的目录是`resources`。
``shell
pyfin open filename [-d|--resource_dir] 。
```
#### 示例
要打开DCF模板，运行以下命令。
``shell
pyfin open dcf
```
要打开可比性分析模板，运行下面的命令。
``shell
pyfin打开比较
```

###加载公司财务报表

要加载公司的财务报表，请使用load命令。`-f`或`--filename`选项可以用来指定包含要加载的公司股票的文件。如果没有提供，默认文件是`load.txt`。
```shell
pyfin load [-f|--filename]
```
#### 示例
要加载`load.txt`中公司的财务报表，请运行以下命令。
``shell
pyfin load
```
要加载`dcf.txt`中的公司财务报表，运行下面的命令。
``shell
pyfin load -f dcf.txt
```

### 从数据库中打印数据

要打印数据库中的数据，请使用data命令。`-t`或`-table`选项可以用来指定要打印的表。如果没有提供这个选项，系统会提示用户选择要打印的表。

```
pyfin data [-t|--table]。
```
#### 示例
要启动交互式提示，请运行以下命令。
``shell
pyfin data
```

要打印 "income_statement "表中的数据，运行下面的命令。
``shell
pyfin data -t income_statement
```

### 打印图表

使用tickers命令来打印一个文件中的tickers。`-f`或`--filename`选项可以用来指定包含tickers的文件。如果没有提供，默认文件是`load.txt`。`-d`或`--ticker_dir`选项可以用来指定ticker文件所在的目录。如果没有提供，默认的目录是`tickers`。
``shell
pyfin tickers [-f|--文件名] [-d|--ticker_dir)
```
#### 示例
要打印`load.txt`中的tickers，请运行以下命令。
``shell
pyfin tickers
```
要打印 "dcf.txt "中的代码，请运行下面的命令。
``shell
pyfin tickers -f dcf.txt
```


### 贴现现金流分析

要进行折现现金流分析，请使用dcf命令。`-f`或`--filename`选项可以用来指定包含用于分析的tickers的文件。如果没有提供，默认文件是`load.txt`。`-t`或`--template_name`选项可以用来指定包含DCF模板的Excel表格的名称。如果没有提供，默认的工作表名称是`Template`。`-n`或`--dcf_analysis_name`选项可以用来指定写入DCF分析的Excel文件的名称。如果没有提供，默认文件名是`dcf.xlsx`。
``shell
pyfin dcf [-f|--文件名] [-t|--模板名称] [-n|--dcf_analysis_name]。
```
#### 示例
要使用`dcf.txt`中的公司进行DCF分析，请运行下面的命令。
``shell
pyfin dcf
```

### 可比性分析

要进行可比性分析，请使用comparables命令。`-n`或`--comparables_analysis_name`选项可以用来指定要写入比较分析的Excel文件的名称。如果没有提供，默认的文件名是`comparables_analysis.xlsx`。`-f`或`--filename`选项可以用来指定包含用于分析的tickers的文件。如果没有提供，默认文件是`load.txt`。

``shell
pyfin compare [-n|--comparables_analysis_name] [-f|--filename]。
```
#### 示例
要使用`compare.txt`中的公司进行可比性分析，请运行下面的命令。
``shell
pyfin比较
```
