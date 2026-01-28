# d-Separation

**Definition**: d-separation (directional separation) is a criterion to determine if two variables, `X` and `Y`, are independent given a set of conditioning variables `Z`.

## Rules for Paths

A path between `X` and `Y` is **blocked** (d-separated) by a set `Z` if:
1.  **Chain**: The path contains `A -> M -> B` and `M` is in `Z` (conditioned on).
2.  **Fork**: The path contains `A <- C -> B` (common cause) and `C` is in `Z`.
3.  **Collider**: The path contains `A -> C <- B` and **neither** `C` **nor** any of its descendants are in `Z`.

## Implication
If all paths between `X` and `Y` are blocked by `Z`, then `X` and `Y` are conditionally independent given `Z`.
*   If `X` and `Y` are d-separated in the graph (after removing arrows out of `X`), then `Z` is a sufficient adjustment set to identify the causal effect.

## Source
Greenland, Pearl, & Robins (1999).
