# Formalizing Evaluation Pipelines for Self-Supervised Vision Models under Resource Constraints

## Motivation
Modern self-supervised learning (SSL) methods (e.g., DINO) are often evaluated using ad-hoc or default probing pipelines, which can obscure the true quality of learned representations—especially in low-data, low-resolution, and limited-compute regimes.  
This project aims to **systematize and analyze the evaluation stage** of self-supervised vision models, treating evaluation methodology as a first-class optimization axis rather than a fixed afterthought.

---

## What This Project Studies
This repository focuses on **frozen-representation evaluation** for self-supervised vision models, with explicit modeling of:

- Feature extraction from ViT-based SSL backbones
- Post-processing steps (PCA, whitening, normalization)
- Test-time augmentation (TTA)
- Downstream probes (k-NN, logistic regression)

All components are designed to be **explicit, modular, and reproducible**, enabling controlled analysis of how evaluation choices affect downstream performance.

---

## Key Findings
- **Evaluation methodology is an independent optimization axis**: substantial performance gains can be recovered without modifying the learned representations.
- **Domain-aligned unlabeled data and tokenization density** strongly dominate performance in constrained regimes.
- Careful evaluation engineering (PCA whitening, TTA, probe selection) can nearly double downstream accuracy compared to default protocols.

---

## What This Project Does *Not* Do
- Propose a new self-supervised learning objective
- Analyze end-to-end SSL training dynamics theoretically
- Provide convergence guarantees or formal proofs for representation learning

The emphasis is on **evaluation rigor**, not training-time innovation.

---

## Status
🚧 **Work in Progress**

- Core evaluation pipeline implemented
- Results reproduced on CUB-200, miniImageNet, and SUN397
- Ongoing work:
  - Additional ablations and stress tests
  - Cleaner abstraction boundaries
  - Manuscript preparation for a workshop submission

---

## Why This Matters
Reported progress in self-supervised learning is often conflated with improvements in evaluation protocol.  
This work demonstrates that **evaluation choices alone can materially change conclusions**, particularly in low-resource settings, and argues for more principled, transparent evaluation standards in SSL research.

---

## Notes for Readers
- This is a research-oriented repository, not a production system
- Code prioritizes clarity and traceability over optimization
- All results are intended to be auditable and reproducible
