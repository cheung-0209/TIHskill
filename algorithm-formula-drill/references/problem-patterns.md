# Problem Patterns

Use this reference when generating more varied or larger exercise sets from algorithmic formulas. Select only the patterns that fit the formula and the user's learning goal.

## Difficulty Ladder

**Level 1: 符号与概念识别**

- Ask what each symbol means in an algorithm context.
- Ask which quantities are inputs, trainable parameters, intermediate variables, or outputs.
- Ask what assumptions make the formula valid.

**Level 2: 维度与合法性判断**

- Provide concrete matrix/vector shapes and ask whether the formula can be computed.
- Ask for the output shape.
- Ask which axis softmax, normalization, or summation should operate on.
- Ask the learner to repair an invalid shape configuration.

**Level 3: 手算与代入**

- Use small vectors, 2x2 matrices, or 2x3 matrices.
- Ask for a single scalar score, probability, prediction, or loss.
- Keep numbers simple enough to solve by hand.
- For softmax-like formulas, allow approximate values and emphasize relative magnitude.

**Level 4: 推导与变形**

- Ask the learner to derive an equivalent expression.
- Ask how a term changes when one variable is scaled, shifted, normalized, or removed.
- Ask for a simple gradient when it is central to the formula.
- Ask why a normalization or scaling term appears.

**Level 5: 代码与实现理解**

- Give a short pseudo-code fragment and ask whether it matches the formula.
- Ask about broadcasting, batch dimension, numerical stability, or vectorization.
- Ask how to implement the formula for a batch of samples.
- Ask what bug would appear if an axis, transpose, or reshape is wrong.

**Level 6: 算法场景应用**

- Put the formula into attention, retrieval, ranking, CTR/CVR, loss optimization, embedding similarity, or feature interaction.
- Ask how changing a formula term affects model behavior.
- Ask which part of the formula controls confidence, ranking order, normalization, or gradient signal.
- Ask for interpretation of a wrong prediction or ranking result.

## Formula-to-Question Mapping

**Softmax**

- Check probability normalization and invariance to adding the same constant.
- Compare logits and probability concentration.
- Ask which axis is normalized in batch or sequence settings.
- Include numerical stability questions using max-subtraction.

**Attention**

- Check shapes for `Q`, `K`, `V`, `QK^T`, attention weights, and final output.
- Ask why division by `sqrt(d_k)` is used.
- Ask how masking changes the softmax result.
- Ask what happens if softmax is applied on the wrong axis.

**Cross-entropy / NLL**

- Ask for loss calculation from predicted probabilities.
- Ask how loss changes when the probability of the true class increases.
- Ask for the relationship between softmax and cross-entropy.
- Include common mistakes such as applying `log` to logits instead of probabilities.

**Matrix factorization / dot-product scoring**

- Check user/item embedding dimensions.
- Ask for prediction from a dot product.
- Ask how embedding similarity affects ranking.
- Include cold-start or bias-term interpretation when present.

**Similarity formulas**

- Compare dot product, cosine similarity, and normalized embeddings.
- Ask how vector length affects score.
- Ask which metric is better for retrieval under a given assumption.

**Gradient formulas**

- Ask what each term contributes to the update.
- Ask how learning rate, regularization, or batch size affects parameter change.
- Use one-step update questions with small numbers.

## Output Templates

Use this compact template for each problem:

```text
题目 n｜考察点：...
题干：...
答案：...
解析：...
常见误区：...
```

For interactive mode, omit answers and use:

```text
题目 n｜考察点：...
题干：...
作答要求：写出关键步骤，不只给最终结果。
```

## Quantity Defaults

- One formula, ordinary request: 6-8 problems.
- One formula, "多出一些": 10-12 problems.
- Multiple formulas: 3-5 problems per formula unless the user asks for depth.
- Exam-style request: include more hand calculation and proof-like questions.
- Engineering-style request: include more dimensions, pseudo-code, and bug diagnosis.
