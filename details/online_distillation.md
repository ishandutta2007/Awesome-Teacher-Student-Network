# Online Distillation (Co-Distillation)

## Concept Diagram
```mermaid
graph LR
    ModelA[Model A (Student 1)] <-->|Peer Mimicry Loss| ModelB[Model B (Student 2)]
    ModelA -->|Update| OptA[Optimizer A]
    ModelB -->|Update| OptB[Optimizer B]
```

## Detailed Explanation
Online Distillation (Co-Distillation) allows multiple peer models to learn collaboratively without needing a pre-trained teacher.

### Core Concept
All models in the cohort start from random initializations and train simultaneously. During each forward pass, the models share their logit distributions. Each model updates its weights using a standard classification loss and a peer-mimicry loss that encourages agreement between models.

### Seminal Paper
- **Deep Mutual Learning (2017/2018):** [arXiv:1706.00384](https://arxiv.org/abs/1706.00384)

---
[← Back to README](../README.md)
