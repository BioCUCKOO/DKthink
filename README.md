# DKthink : CRE - TF - Gene Syntax Inference 

DKthink is used for reasoning **cis-regulatory element (CRE) - transcription factor (TF) - target gene** syntax.  Here, we introduce an API for using DKthink.

---

## Core Capability

Given a **CRE genomic coordinate**, **species**, **tissue**, and **DNA sequence**, DKthink:

1. Infers the CRE type;
2. Identifies candidate transcription factors (TFs) binding the CRE;
3. Reasons the most likely **target gene**;
4. Assigns confidence of target gene and importance scores of biological function;
5. Summarizes a s**tep-by-step rationale** suitable for reports.

---

