# Phase 1: Critique & Identification

You are helping the user **validate** their DAG blueprint from Phase 0. This phase is about rigorous identification: ensuring the proposed structure identifies the causal effect and does not introduce bias.

## Goal
Transform a "Theory DAG" (Phase 0) into a "Validated DAG" by:
1.  Checking for structural biases (colliders, mediators).
2.  Determining the **sufficient adjustment set**.
3.  Identifying threats to validity (unobserved confounders).

## Core Concepts to Apply
Refer to the `concepts/` directory for definitions:
- `concepts/six_step_algorithm.md` (The Shrier & Platt audit)
- `concepts/d_separation.md` (Greenland’s sufficiency rules)
- `concepts/confounding.md`
- `concepts/colliders.md`

## The Identification Audit

Ask the user to run their DAG through this checklist (or do it for them if the DAG is simple):

### 1. The Mediator Check
*   "Are any of your control variables actually **downstream** of the treatment (X)?"
*   *Rule*: Do not adjust for mediators (descendants of X) unless you specifically want the Direct Effect (and know the risks).
*   *Action*: Remove descendants of X from the adjustment set (Step 1 of 6-Step Algorithm).

### 2. The Collider Check
*   "Does X and Y both influence any variable C (or C's ancestor) that we are conditioning on (e.g., by selecting only those people)?"
*   *Rule*: Conditioning on a collider opens a non-causal path.
*   *Action*: Check for **Selection Bias** (`concepts/selection_bias.md`).

### 3. The Confounder Check (Backdoor Criterion)
*   "Is there an open backdoor path from X to Y?" (Any path starting with an arrow into X).
*   *Rule*: You must block all backdoor paths.
*   *Action*: Identify the **Minimally Sufficient Adjustment Set**.

### 4. The Unobserved Variable Check
*   "Are there common causes of X and Y that are **unmeasured** (U)?"
*   *Sensitivity*: If U exists and is strong, the effect is not identifiable. Ask the user to note this limitation.

## Output: Validated DAG Strategy

Produce a short **Identification Memo**:
1.  **Valid Adjustment Set**: List the variables that *must* be controlled.
2.  **Variables to Ignore**: List variables that must *not* be controlled (colliders, mediators).
3.  **Threats**: Note any unblocked paths due to unobserved variables.

## Handoff to Phase 2
Once the identification strategy is set, move to **Phase 2: Inputs & Format** to prepare for rendering.
