# The 6-Step Algorithm (Shrier & Platt)

This algorithm determines if a proposed set of covariates (`S`) reduces bias for the effect of `X` on `Y`.

## The Algorithm

1.  **Check Descendants**: Ensure no variable in `S` is a descendant of `X` (caused by `X`). If yes, remove it or stop (it may be a mediator).
2.  **Delete Non-Ancestors**: Delete all variables that are NOT ancestors of `X`, `Y`, or variables in `S`. (Keep `S`, `X`, `Y`).
3.  **Delete Outgoing X**: Delete all lines originating from `X`. (We want to see if non-causal paths remain).
4.  **Connect Parents (Moralization)**: For every collider (child with two parents) that is in `S` (or has a descendant in `S`), connect the two parents with a dashed line.
    *   *Concept*: Conditioning on a collider induces an association between its parents.
5.  **Strip Arrowheads**: Remove all arrowheads (treat lines as undirected associations).
6.  **Delete S Connections**: Delete all lines touching any variable in `S`. (Conditioning blocks these paths).

## Interpretation

*   **If X and Y are disconnected**: The set `S` is sufficient to remove confounding bias (for the specific DAG structure assumed).
*   **If X and Y are still connected**: The set `S` is insufficient; bias remains.

## Source
Shrier & Platt (2008), adapting Pearl.
