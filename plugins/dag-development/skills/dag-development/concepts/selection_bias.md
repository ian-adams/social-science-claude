# Selection Bias

**Definition**: In the structural approach (DAGs), selection bias is often a form of **collider-stratification bias**. It occurs when participation, follow-up, or observation (`S`) is a common effect of the exposure (`X`) and the outcome (`Y`) (or their ancestors).

## Mechanism

Structure: `X -> S <- Y`
*   If we restrict analysis to the observed sample (`S=1`), we are conditioning on `S`.
*   Since `S` is a collider, conditioning on it opens the path between `X` and `Y`.
*   This creates a non-causal association between exposure and outcome.

## Examples
*   **Loss to follow-up**: If treatment (`X`) causes side effects that lead to dropout (`S`), and the disease severity (`Y`) also leads to dropout, analyzing only complete cases biases the result.
*   **Berkson's Bias**: Hospital admission (`S`) depends on two independent diseases (`X` and `Y`). In the hospital population, `X` and `Y` appear associated.

## Source
Based on Hernán, Hernández-Díaz, & Robins (2004) and Shrier & Platt (2008).
