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

## API Endpoint
Using in Windows CMD
```
POST http://47.75.151.53:8080/analyze
Content-Type: application/json
```

---

## Input Format

```json
{
  "question": "What is the target gene regulated by CRE at chrX:XXX-XXX in the species tissue? The sequence is ATCG..."
}
```

---

## Example Request
CMD input(https://github.com/BioCUCKOO/DKthink/blob/main/images/DK-input.png)
```bash
curl -X POST http://47.75.151.53:8080/analyze \
  -H "Content-Type: application/json" \
  -d @D:/request.json
```
---

## Example Response

```json
{
  "success": true,
  "data": {
    "input": "What is the target gene regulated by CRE at chr1:108991812-108994364 in the sheep rumen?",
    "output": {
      "enhancer": "chr1:108991812-108994364",
      "TF": "ETS1",
      "target_gene": "IVL",
      "confidence": 0.85,
      "importance_score": 0.90,
      "rationale": "Stepwise explainable regulatory inference",
      "output": "The CRE likely functions as a rumen-specific enhancer regulating IVL."
    }
  },
  "error": null
}
```

---

## Output Fields

| Field | Description |
|------|------------|
| enhancer | CRE genomic coordinate |
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
