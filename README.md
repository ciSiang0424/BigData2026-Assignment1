# BigData2026-Assignment1

NYCU Big Data Analytics, Fall 2026, Assignment 1.
Student ID: 314552039

Fine-tuning Llama-3.2-1B with PiSSA (SVD-based) on MetaMathQA, evaluated on GSM8K and MATH.

## Files

- `finetune_q1_q3.ipynb` — Questions 1, 2, and 3. Change `MANUAL_RUNS` in the second cell.
- `q4_svd_analysis.ipynb` — Question 4 only. No fine-tuning.

## How to run

Kaggle notebook. Internet On. Secret `HF_TOKEN` set.

Question 1 and 2: set `component` to `default`, and set `rank` to 16, 64, or 256. One rank per run.

Question 3: set `rank` to 16, and set `component` to `default`, `p25`, `p50`, or `bottom`.

Question 4: run `q4_svd_analysis.ipynb`. It does full SVD on `q_proj` of layers 0, 7, and 15. No rank setting.
