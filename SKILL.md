---
name: latex-format-writing
description: Use when writing, editing, translating, explaining, or formatting content that contains mathematical formulas, equations, variables, mathematical symbols, scientific notation, Greek letters, operators, subscripts, superscripts, functions, inequalities, sums, integrals, matrices, vectors, or other math expressions that should be typeset as LaTeX. Only math-related content should be wrapped or converted; ordinary prose, wording, punctuation, and non-math content should remain unchanged.
---

# LaTeX Format Writing

## Core Rule

Only format mathematical expressions with LaTeX. Do not rewrite, wrap, or otherwise alter ordinary prose or non-mathematical content.

- Use inline math delimiters for short mathematical expressions inside a sentence: `$...$`.
- Use display math delimiters for standalone equations or multi-line derivations:

```latex
\[
...
\]
```

## Scope

Treat these as math content:

- Variables and symbols, such as `$x$`, `$a_n$`, `$\\alpha$`, `$\\Delta$`.
- Equations and inequalities, such as `$E=mc^2$`, `$x>0$`.
- Functions, fractions, powers, roots, sums, integrals, limits, matrices, and vectors.
- Scientific notation or units when they are part of a formula.

Leave these unchanged unless the user explicitly asks otherwise:

- Normal prose and explanations.
- Non-mathematical punctuation.
- Code blocks that are not meant to be rendered as math.
- Existing valid LaTeX unless it needs delimiter correction.

## Delimiter Choice

- Use `$...$` when the expression belongs inside a sentence.
- Use `\[...\]` when the expression is displayed on its own line, is visually important, or contains a larger structure such as a sum, integral, fraction, matrix, or derivation.
- Keep sentence punctuation outside the math delimiters unless the punctuation is part of the mathematical expression.

## Examples

Inline:

```markdown
When $x>0$, the function $f(x)=\ln x$ is defined.
```

Display:

```markdown
\[
S_n=\sum_{k=1}^{n} k=\frac{n(n+1)}{2}
\]
```

Mixed prose:

```markdown
Let the radius be $r$. The area of the circle is
\[
A=\pi r^2
\]
so when $r=3$, the area is $9\pi$.
```
