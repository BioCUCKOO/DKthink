# DKthink : CRE → TF → Gene Regulatory Inference API

DKthink is a lightweight, inference-focused REST API for hypothesizing **cis-regulatory element (CRE) → transcription factor (TF) → target gene** relationships in a **species- and tissue-specific context**.

It is designed for regulatory genomics workflows where experimental validation is unavailable or incomplete, and a **structured, explainable regulatory hypothesis** is required.

---

## Core Capability

Given a **CRE genomic coordinate**, **species**, **tissue**, and **DNA sequence**, DKthink:

1. Infers the CRE functions  
2. Identifies candidate transcription factors (TFs) binding the CRE  
3. Predicts the most likely **target gene**  
4. Assigns **confidence** and **biological importance scores**  
5. Produces a **step-by-step rationale** suitable for manuscripts or reports  

---

## Output Fields

| Field | Description |
|------|------------|
| CRE | CRE genomic coordinate |
| TF | Predicted regulatory transcription factor |
| target_gene | Predicted target gene |
| confidence | Confidence score (0–1) |
| importance_score | Biological relevance to tissue development |
| rationale | Explainable multi-step reasoning |
| output | Human-readable summary |

---

## Notes

- All outputs are **regulatory hypotheses**
- Scores are **interpretable, not absolute probabilities**
- Designed to complement experimental validation

---
