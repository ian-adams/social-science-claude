# Confounding Bias

**Definition**: Confounding bias occurs when there is a common cause of the exposure (X) and the outcome (Y) that is not blocked by conditioning.

## Traditional vs. Graphical Definitions

*   **Traditional**: A variable is a confounder if it is associated with X, associated with Y, and not a descendant of X.
*   **Graphical (DAG)**: Confounding is the presence of an open backdoor path from X to Y. A backdoor path is any path that starts with an arrow pointing *into* X (e.g., `X <- Z -> Y`).

## Addressing Confounding

To remove confounding, you must "block" all backdoor paths.
*   **Blocking**: Conditioning on a non-collider along the path.
*   **Caution**: Adjusting for a variable that is NOT a confounder (or is a collider) can *introduce* bias (see `colliders.md`).

## Source
Based on Shrier & Platt (2008) and Greenland, Pearl, & Robins (1999).
