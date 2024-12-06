---
date: 2024-11-07 08:03
sources: 
tags:
  - zettel
  - tools
status: literature
publish: true
---
# latex 
### **Basic Syntax**

1. **Inline Math:** `\( ... \)` or `$ ... $`
2. **Display Math:** `\[ ... \]` or `$$ ... $$`

---
### **Common Symbols**

1. **Greek Letters:**
    - Lowercase: `\alpha, \beta, \gamma, \theta, \lambda, \mu, \sigma, \pi`
    - Uppercase: `\Gamma, \Lambda, \Sigma, \Pi`
2. **Operators:**
    - Sum: `\sum_{i=1}^n`
    - Product: `\prod_{i=1}^n`
    - Integral: `\int_{a}^{b}`
    - Partial Derivative: `\frac{\partial y}{\partial x}`
3. **Comparison:**
    - Greater/Less: `>, <, \geq, \leq`
    - Approx: `\approx, \sim`
4. **Set Notation:**
    - Belongs to: `\in`
    - Subset: `\subset, \subseteq`
    - Empty Set: `\emptyset`

---
### **Data Science and ML-Specific Notation**

1. **Vectors and Matrices:**
    - Bold letters for vectors: `\mathbf{v}`
    - Matrix: `\mathbf{X}`
    - Transpose: `\mathbf{X}^\top`
2. **Probability:**    
    - Expectation: `\mathbb{E}[X]`
    - Probability: `P(A)`
    - Conditional Probability: `P(A \mid B)`
3. **Loss Functions:**
    - Mean Squared Error: `\frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2`
    - Cross-Entropy Loss: `- \sum_{i=1}^n y_i \log(\hat{y}_i)`
4. **Linear Algebra:**
    - Dot Product: `\mathbf{u} \cdot \mathbf{v}`
    - Norm: `\|\mathbf{x}\|`
    - Determinant: `\det(\mathbf{A})`
5. **Optimization:**
    - Gradient: `\nabla f(\mathbf{x})`
    - Argmin/Argmax: `\arg\min_x f(x), \arg\max_x f(x)`
6. **Bayes' Theorem:**
    - `P(A \mid B) = \frac{P(B \mid A) P(A)}{P(B)}`

---
### **Formatting**

1. **Subscripts and Superscripts:**
    - `x_i, x^2`
2. **Fractions:**
    - `\frac{a}{b}`
3. **Brackets:**
    - Normal: `(a + b)`
    - Square: `[a + b]`
    - Curly: `\{a, b\}`
4. **Math Functions:**
    - `\log, \ln, \exp, \sin, \cos`

---
### **Advanced Notation**

1. **Softmax:**
    - `\text{softmax}(\mathbf{z})_i = \frac{\exp(z_i)}{\sum_{j=1}^n \exp(z_j)}`
2. **Matrix Multiplication:**
    - `\mathbf{C} = \mathbf{A} \cdot \mathbf{B}`
3. **KL Divergence:**
    - `D_{\text{KL}}(P \parallel Q) = \sum_{i} P(i) \log\frac{P(i)}{Q(i)}`
4. **Activation Functions:**
    - Sigmoid: `\sigma(x) = \frac{1}{1 + \exp(-x)}`
    - ReLU: `\text{ReLU}(x) = \max(0, x)`

---
## Related Notes

## References(links)
