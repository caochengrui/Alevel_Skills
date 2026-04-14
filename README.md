# Alevel_Skills

## Overview

This project provides:

1. **Claude Code Skills** — installable skills that enable Claude to generate full-mark exam answers for specific CAIE A-Level Physics paper types.
2. **Structured Datasets** — past paper questions and mark schemes in machine-readable JSON format, used for skill development, testing, and evaluation.

## Repository Structure

```
Alevel_Skills/
├── README.md
├── LICENSE
├── CAIE-Physics-Paper_5-Q1-Answer-Generator/
│   └── SKILL.md                          # Claude Code skill
└── Dataset/
    └── CAIE-Physics-Paper_5-Q1-Past-Papers-2021_2024.json
```

## Skills

### CAIE-Physics-Paper\_5-Q1-Answer-Generator

Generates full-mark (15/15) exam-style answers for **CAIE A-Level Physics 9702 Paper 5 Question 1** — the experimental planning question.

**What it does:**
- Accepts a Paper 5 Q1 question (raw text or structured JSON)
- Identifies independent/dependent variables and control variables
- Describes a workable labelled diagram
- Specifies measurement methods with appropriate instruments
- Performs the algebraic rearrangement to determine what graph to plot
- Derives formulas for unknown constants from gradient and y-intercept
- Includes additional detail points (repeat/average, precision, safety)

**Supported question types:**
- Type A — 1 unknown constant, linear graph through origin
- Type B — 2 unknown constants, linear graph y = mx + c
- Type C — 2 unknown constants, log-log graph (power laws)
- Type D/F — unknowns in exponential relationships (ln graphs)

**How to install:**

```bash
# In Claude Code
/install-skill path/to/CAIE-Physics-Paper_5-Q1-Answer-Generator
```

## Dataset

### CAIE-Physics-Paper\_5-Q1-Past-Papers-2021\_2024

A structured JSON dataset containing **20 deduplicated** Paper 5 Question 1 samples from 2021–2024 (5 per year, covering Feb/March, May/June, and Oct/Nov series).

Each sample includes:
- Full question text and experiment context
- Given relationship and unknown constants
- Complete mark scheme (defining problem, data collection, analysis, detail pool)
- Target answer in exam-style structured format
- Training notes and extraction rules

**Schema overview:**

```json
{
  "dataset_name": "CAIE-Physics-Paper_5-Q1-Past-Papers-2021_2024",
  "samples": [
    {
      "sample_id": "9702_m21_qp_52",
      "question": {
        "raw_question_text": "...",
        "given_relationship": "T = 2π√(m / (σKr²))",
        "unknown_constants": ["K"]
      },
      "mark_scheme": {
        "defining_problem": [...],
        "methods_of_data_collection": [...],
        "method_of_analysis": [...],
        "additional_detail_pool": [...]
      },
      "target_answer": { "response": "..." }
    }
  ]
}
```

## Disclaimer

This project is an independent educational tool. It is not affiliated with, endorsed by, or officially connected to Cambridge Assessment International Education (CAIE) or Cambridge University Press & Assessment. All past paper content is used for educational and research purposes. Exam questions and mark schemes remain the intellectual property of Cambridge Assessment International Education.
