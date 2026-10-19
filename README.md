# Detecting Prompt Injection in LLM Applications

> Comparative study of lightweight classifiers vs LLM-based guards for detecting prompt injection attacks.

[![Status](https://img.shields.io/badge/status-in%20progress-yellow)]()
[![License](https://img.shields.io/badge/license-MIT-blue)]()

---

## Overview

Prompt injection is currently ranked as the **#1 risk** for LLM applications by OWASP (LLM01 in the 2025 & 2026 Top 10).  
This project investigates whether simple, fast, and cheap classifiers can detect prompt injection attacks nearly as well as more expensive LLM-based guards — and how well they generalise to new attack formulations.

**Research Question**  
> Can a lightweight classifier detect prompt injection as effectively as an LLM-based guard, at a fraction of the cost and latency, and how well does it handle paraphrased or non-English attacks?

---

## Planned Approach

1. **Data**  
   Collect and combine public prompt-injection datasets (starting with [`deepset/prompt-injections`](https://huggingface.co/datasets/deepset/prompt-injections)) with benign prompts.

2. **Models**  
   - Classical baseline: TF-IDF + Logistic Regression  
   - Lightweight transformer: Fine-tuned DistilBERT  
   - Comparison: LLM used as a guard + existing open detectors (if available)

3. **Evaluation**  
   - Accuracy, Precision, Recall, F1  
   - False Positive Rate on normal prompts  
   - Inference speed and estimated cost  
   - Generalisation tests on paraphrased and non-English attacks

---

## Project Structure (planned)

```text
├── data/                  # Datasets and preprocessing scripts
├── notebooks/             # Exploratory analysis and experiments
├── src/
│   ├── classifiers/       # TF-IDF + Logistic Regression, DistilBERT
│   ├── llm_guard/         # LLM-as-a-guard implementation
│   └── evaluation/        # Metrics and generalisation tests
├── results/               # Experiment outputs, plots, tables
├── report/                # LaTeX report source
└── README.md
```

## Current Status

- [x] Project defined and research question formulated
- [x] Initial literature review (OWASP Top 10 for LLMs, Greshake et al. 2023)
- [x] Report chapters 1–3 drafted
- [ ] Dataset collection and cleaning
- [ ] Baseline classifier training
- [ ] DistilBERT fine-tuning
- [ ] LLM-as-a-guard experiments
- [ ] Generalisation evaluation
- [ ] Final report and results

---

## Key References

- OWASP GenAI Security Project (2026). *OWASP GenAI LLM Top 10 2026*.  
  https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/
- Greshake, K., et al. (2023). *Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection*.  
  https://arxiv.org/abs/2302.12173
- deepset (2023). *prompt-injections dataset*.  
  https://huggingface.co/datasets/deepset/prompt-injections

---

## Getting Started (coming soon)

```bash
# Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# (Instructions for environment setup and running experiments will be added here)
```

---

## License

This project is licensed under the MIT License — see the LICENSE file for details.

---

## Acknowledgements

This work builds on public datasets and open research in LLM security. Special thanks to the authors of the OWASP Top 10 for LLM Applications and Greshake et al. (2023) for laying the foundation for this area of research.
