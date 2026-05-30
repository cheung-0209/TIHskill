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
  <img alt="Formula Drill" src="https://img.shields.io/badge/Formula-Drill-16a34a">
  <img alt="Language" src="https://img.shields.io/badge/Output-Chinese-0ea5e9">
</p>

<p align="center">
  <a href="#overview">Overview</a> ·
  <a href="#skill">Skill</a> ·
  <a href="#repository-structure">Structure</a> ·
  <a href="#example-usage">Usage</a>
</p>

## Overview

This repository contains personal Codex skills for learning and research workflows.

The first skill, `algorithm-formula-drill`, turns algorithmic and mathematical formulas into practice problems with answers and explanations. It is designed for learners who prefer mastering formulas through drills rather than passive reading.

## Skill

### algorithm-formula-drill

`algorithm-formula-drill` focuses on formula learning in algorithm-heavy scenarios, especially formulas involving:

- matrix computation and vector operations
- machine learning losses and gradients
- large model formulas such as attention, softmax, embeddings, and normalization
- search, ads, and recommendation formulas such as CTR/CVR, ranking, retrieval, matrix factorization, and similarity scoring

By default, the skill generates Chinese practice problems in an algorithm-oriented style. Each problem includes the question, tested concept, answer, explanation, and common mistakes.

## Repository Structure

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

- `algorithm-formula-drill/SKILL.md`: Core instructions that define how the skill parses formulas and generates drills.
- `algorithm-formula-drill/references/problem-patterns.md`: Reusable problem templates, difficulty levels, and formula-to-question mappings.
- `algorithm-formula-drill/agents/openai.yaml`: UI metadata for displaying the skill in Codex.

## Example Usage

```text
Use $algorithm-formula-drill 根据下面的公式生成算法应用导向的刷题题目、答案和解析：

Attention(Q,K,V)=softmax(QK^T/sqrt(d_k))V
```

```text
Use $algorithm-formula-drill 给我围绕 softmax 公式出 8 道题，包含矩阵维度、手算、代码实现和常见错误。
```

## Notes

This skill is not a formula database. It is a practice-generation workflow: the user provides a formula, and Codex turns it into structured exercises for learning, review, and self-testing.
