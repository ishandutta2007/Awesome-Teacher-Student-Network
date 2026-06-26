# The Softmax Saturation Bottleneck

## Concept Diagram
```mermaid
graph LR
    Logits[Raw Logits] -->|Normal Softmax T=1| Crisp[Crisp Predictions (No dark knowledge)]
    Logits -->|Divided by T > 1| Smooth[Smooth Distribution (Exposes relationships)]
```

## Detailed Explanation
The Softmax Saturation Bottleneck occurs when a fully converged teacher model outputs extremely crisp probabilities, rendering knowledge distillation ineffective.

### Core Concept
If a teacher model is highly confident, the softmax function maps the correct class near 1.0 and others near 0.0. The "soft targets" become identical to hard labels, and the valuable "dark knowledge" about class similarities is lost.

### Mitigation: Temperature Scaling
Dividing the logits by a temperature parameter $T > 1$ before the softmax function softens the output distribution, preserving the class relationship information for the student.

### Seminal Paper
- **Distilling the Knowledge in a Neural Network (2015):** [arXiv:1503.02531](https://arxiv.org/abs/1503.02531)

---
[← Back to README](../README.md)
