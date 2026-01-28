# Colliders and Collider-Stratification Bias

**Definition**: A node is a **collider** on a specific path if two arrowheads meet at that node (e.g., `A -> C <- B`). Here, `C` is a collider between `A` and `B`.

## Key Properties

1.  **Blocking**: A collider *naturally blocks* the path. Information does not flow from `A` to `B` through `C` unless you condition on `C`.
2.  **Opening (Bias)**: If you condition on a collider (or a descendant of a collider), you **open** the path. This creates a spurious association between `A` and `B`.

## Collider-Stratification Bias

This bias occurs when you control for a common effect of the exposure and the outcome (or their causes).
*   **Example**: `Exposure -> Hospitalization <- Outcome`.
*   If you study only hospitalized patients (conditioning on `Hospitalization`), you induce a correlation between Exposure and Outcome even if none exists in the general population (Berkson's Bias).

## In the 6-Step Algorithm
*   **Step 4**: Connect any two parents sharing a common child (collider). This visualizes the association created by conditioning on the collider.

## Source
Based on Shrier & Platt (2008) and Greenland, Pearl, & Robins (1999).
