---
title: FinanceChatGLM
date: 2023-08-13T12:16:10+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1689164907758-b075c7bc76cd?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTE5MDAwMTl8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1689164907758-b075c7bc76cd?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTE5MDAwMTl8&ixlib=rb-4.0.3
---

# [RonaldJEN/FinanceChatGLM](https://github.com/RonaldJEN/FinanceChatGLM)

# SMP 2023 ChatGLM 金融大模型挑战赛 60 分 Baseline 思路

**队伍:** 小打小闹

## 数据提取整体过程
![数据提取整体过程](/img/001.png)

## PDF 表格识别结果对比
![识别结果1](/img/002.jpeg) ![识别结果2](/img/003.jpeg)

## 自研PDF表格识别逻辑
![逻辑1](/img/004.png) 
![逻辑2](/img/005.png)
![逻辑3](/img/006.png)

### 主要步骤:
1. 定位表格区域 
2. 识别单元格 
3. 跨页表格合并

## 识别单元格并生成表格算法伪代码
![伪代码1](/img/007.jpeg)
![伪代码2](/img/008.jpeg)

## 基于有限状态机的数据提取
![有限状态机](/img/009.png)

## 资产负债表示意图 (三大表之一) 数据入库
![数据入库](/img/010.jpeg)

### 主要内容:
- 公司基本信息 
- 资产负债表 
- 现金流量表 
- 利润表 
- 公司员工信息 

## 公司全称与简称及代码对照
![对照表](/img/011.jpeg)

## 信息从表格转为文本描述

### 公司员工信息
![员工信息](/img/012.png)

### 文本描述示例: 安靠智电
安靠智电（股票代码：300617）在2019年共有642名职工，其中74人是研发人员，研发人员占比11.53%。该公司有10名硕士学历以上学历的员工，但没有博士学历的员工。

## 整体推理流程
![推理流程](/img/013.jpeg)

## ⚠️ 不要相信大模型的数学能力

### 改进前
![改进前](/img/014.png)

### 改进后
直接帮他算好。

安记食品2019年营业利润为49072627.15元, 2019年营业收入为421296738.60元。根据公式: 

\[
\text{营业利润率} = \frac{\text{营业利润}}{\text{营业收入}} \times 100
\]

得出结果安记食品2019年营业利润率为11.65%。

## ⚠️ 不要相信大模型的推理能力

### 建议 剔除冗余信息，否则可能无法得到正确答案。
![推理示例](/img/015.jpeg)
"""