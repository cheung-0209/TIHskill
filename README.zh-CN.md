# TIHskill

<p align="center">
  <a href="./README.md">
    <img alt="English" src="https://img.shields.io/badge/English-README-2563eb?style=for-the-badge">
  </a>
  <a href="./README.zh-CN.md">
    <img alt="简体中文" src="https://img.shields.io/badge/%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-README-dc2626?style=for-the-badge">
  </a>
</p>

<p align="center">
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-111827">
  <img alt="公式刷题" src="https://img.shields.io/badge/Formula-Drill-16a34a">
  <img alt="中文输出" src="https://img.shields.io/badge/Output-Chinese-0ea5e9">
</p>

<p align="center">
  <a href="#项目简介">项目简介</a> ·
  <a href="#skill-说明">Skill 说明</a> ·
  <a href="#目录结构">目录结构</a> ·
  <a href="#使用示例">使用示例</a>
</p>

## 项目简介

这个仓库用于存放个人 Codex skills，主要服务于学习、研究和知识整理流程。

当前包含的第一个 skill 是 `algorithm-formula-drill`。它可以把算法和数学公式转化为带答案与解析的刷题练习，适合希望通过做题来理解公式、熟悉矩阵计算和掌握算法细节的学习者。

## Skill 说明

### algorithm-formula-drill

`algorithm-formula-drill` 主要面向算法学习中的公式训练，尤其适合以下内容：

- 矩阵计算与向量运算
- 机器学习中的损失函数与梯度
- 大模型相关公式，如 attention、softmax、embedding、normalization
- 搜索、广告与推荐系统公式，如 CTR/CVR、排序、召回、矩阵分解、相似度计算

默认情况下，这个 skill 会用中文生成偏算法应用场景的练习题。每道题包含题干、考察点、答案、解析和常见误区，帮助学习者从计算、维度、推导和应用几个角度熟悉公式。

## 目录结构

```text
TIHskill/
  README.md
  README.zh-CN.md
  algorithm-formula-drill/
    SKILL.md
    agents/
      openai.yaml
    references/
      problem-patterns.md
```

- `algorithm-formula-drill/SKILL.md`：skill 的核心规则，定义如何解析公式、如何生成题目和解析。
- `algorithm-formula-drill/references/problem-patterns.md`：题型模板、难度分层和常见公式的出题方向。
- `algorithm-formula-drill/agents/openai.yaml`：Codex 界面展示所需的元数据。

## 使用示例

```text
Use $algorithm-formula-drill 根据下面的公式生成算法应用导向的刷题题目、答案和解析：

Attention(Q,K,V)=softmax(QK^T/sqrt(d_k))V
```

```text
Use $algorithm-formula-drill 给我围绕 softmax 公式出 8 道题，包含矩阵维度、手算、代码实现和常见错误。
```

## 说明

这个 skill 不是公式数据库，而是一套公式练习生成流程。用户提供公式后，Codex 会围绕该公式生成结构化练习，用于理解、复习和自测。
