# Potential Outcomes and DAGs

**Definition**: The Potential Outcomes framework (Neyman-Rubin Causal Model) defines a causal effect as the difference between two potential states:
*   $Y(1)$: The outcome if treated ($X=1$).
*   $Y(0)$: The outcome if untreated ($X=0$).

## Mapping to DAGs

*   **Consistency**: The observed outcome $Y$ is determined by the treatment $X$ and potential outcomes: $Y = X \cdot Y(1) + (1-X) \cdot Y(0)$.
*   **Ignorability (Exchangeability)**: The treatment assignment $X$ is independent of potential outcomes $(Y(0), Y(1))$ given covariates $Z$.
    *   In DAG terms: $X$ is d-separated from the unobserved error terms affecting $Y$, conditional on $Z$.

## Key Translations

1.  **Confounding**: In Potential Outcomes, confounding means $X$ depends on factors that also predict $Y(0)$ or $Y(1)$. In DAGs, this is a common parent of $X$ and $Y$.
2.  **Selection Bias**: Conditioning on a variable associated with both $Y(0)/Y(1)$ and $X$.
3.  **SUTVA (Stable Unit Treatment Value Assumption)**: Assumes no interference between units. In DAGs, this means the outcome of unit $i$ is not caused by the treatment of unit $j$.

## Source
Imbens & Rubin (2015); Hernán & Robins (2020).
