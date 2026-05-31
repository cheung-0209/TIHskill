---
name: algorithm-formula-drill
description: "Generate algorithm-oriented practice problems, answers, and explanations from user-provided mathematical formulas. Use when the user wants刷题, 练习题, 题目生成, 答案解析, or formula drills for algorithms, machine learning, large models, matrix computation, search, ads, recommendation, CTR/CVR, loss functions, gradients, attention, softmax, embeddings, or related mathematical formulas."
---

# Algorithm Formula Drill

## Core Behavior

Turn each user-provided formula into Chinese practice problems that help the user understand and remember the formula through solving. Favor algorithm application over pure mathematical display. Unless the user requests otherwise, output all problems first, then provide the answer key and explanations at the end of the same response.

Use this default response shape:

1. **公式拆解**: Explain variables, dimensions, constraints, and likely algorithm context.
2. **刷题清单**: Generate about 6-8 problems by default. List all problems before any answer appears.
3. **答案与解析**: After the full problem list, provide answers, key steps, and common mistakes in the same numbering order.
4. **掌握建议**: End with 2-4 short tips on what to practice next.

## Formula Rendering

Render mathematical formulas directly with Markdown math whenever the platform can render them. Prefer ChatGPT/Codex-style delimiters because some clients display dollar-delimited math as plain text.

- Use display math for standalone formulas, for example `\[ ... \]`.
- Use inline math for short symbols or terms, for example `\(QK^T\)`, `\(d_k\)`, or `\(p_u^T q_i\)`.
- Avoid `$...$` and `$$...$$` unless the user specifically targets a renderer that requires dollar-delimited math.
- Do not put formulas in fenced code blocks or inline code merely to show the formula source.
- Use fenced code blocks only for real code, pseudo-code, command lines, or literal file content.
- When the user provides LaTeX, preserve the notation and place it inside renderable math delimiters instead of showing only the raw LaTeX string.
- If the current interface still displays delimiters instead of rendering math, recognize this as a client-side rendering limitation and keep formulas readable without switching to code blocks.

## Workflow

1. Parse the formula first.
   - Identify symbols, inputs, outputs, dimensions, domains, normalization terms, sums/products, transpose, inverse, gradients, and constraints.
   - Infer the likely context, such as attention, loss function, recommender scoring, matrix factorization, similarity, ranking, or feature interaction.
   - If the context is ambiguous but still workable, state a concise assumption and continue.

2. Ask only when missing information would materially change the exercises.
   - Ask about matrix dimensions when several incompatible interpretations are plausible.
   - Ask about the learning target when the same formula could support very different drills, such as proof, coding, numerical calculation, or model interpretation.
   - Do not ask for routine details that can be reasonably assumed.

3. Build problems with a difficulty gradient.
   - Start with symbol recognition and dimension checks.
   - Add numerical substitution or small matrix computation.
   - Include derivation, transformation, or gradient reasoning when appropriate.
   - Add algorithm application questions tied to large models, machine learning, search, ads, or recommendation systems.
   - Include at least one mistake-diagnosis or boundary-case question when it fits the formula.

4. Keep the style practical.
   - Use exam-like clarity, but avoid artificial trick questions unless they reveal a real misunderstanding.
   - Prefer small numbers and matrices that can be solved by hand.
   - Make the answer process explicit enough for a learner to check their own work.
   - Use stable terminology. Do not rename the same variable or concept just to avoid repetition.
   - Keep answers out of the problem list. Put all answers and explanations in a separate final section.

## Problem Design Defaults

- Default language: Chinese.
- Default quantity: 6-8 problems per formula.
- Default mode: all problems first, then a consolidated answer-and-explanation section.
- Default audience: a learner studying algorithmic formulas through practice.
- Default style: algorithm application with some exam-style structure.
- Default notation: preserve and render the user's formula notation unless it is unclear; define any added notation.

For larger formula sets, group questions by formula and keep each group short. Within each group, list questions first and answers afterward. If the user requests an interactive quiz, provide only the problems first and wait for their answers before grading.

## Domain Emphasis

For large-model formulas, prioritize:

- attention score shapes, `QK^T`, scaling by `sqrt(d_k)`, softmax axes, and output dimensions
- softmax probabilities, log-sum-exp intuition, temperature, and numerical stability
- cross-entropy, negative log-likelihood, gradients, and label distributions
- normalization, embeddings, residuals, positional encodings, and matrix shape consistency

For search, ads, and recommendation formulas, prioritize:

- recall, ranking, CTR/CVR estimation, calibration, and score combination
- matrix factorization, dot-product scoring, similarity, and embedding retrieval
- pairwise/listwise losses, negative sampling, feature crossing, and cold-start interpretations
- offline metric interpretation and how formula terms affect ranking behavior

## Reference

When a user asks for richer题型, more difficulty levels, or a large set of exercises, read `references/problem-patterns.md` and select templates that fit the formula. Do not load it for very simple one-off drills unless needed.
