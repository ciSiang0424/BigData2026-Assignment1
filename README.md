# BigData2026-Assignment1

NYCU Big Data Analytics, Fall 2026, Assignment 1.
Student ID: 314552039

Fine-tuning Llama-3.2-1B with PiSSA (SVD-based) on MetaMathQA, evaluated on GSM8K and MATH.

## Files

- `finetune_q1_q3.ipynb` — Questions 1, 2, and 3. Fine-tuning, evaluation, and timing.
- `q4_svd_analysis.ipynb` — Question 4 only. SVD of `q_proj` in layers 0, 7, 15. No fine-tuning.
- `results/` — per-run summary JSON files (accuracy, training time, unparsed counts, trainable parameters) and Q4 CSVs. All numbers in the report come from these files.

## How to run

Kaggle notebook, 2× T4 GPU, Internet On, Kaggle secret `HF_TOKEN` set (gated Llama-3.2-1B).

All runs use the fixed settings: lr 2e-5, 1 epoch, FP16, max 256 output tokens,
25,000 MetaMathQA training examples, 1,000 GSM8K + 1,000 MATH test questions, seed 42.

- **Question 1 baseline (original model):** set `RUN_FRESH_BASELINE = True` in the config cell.
- **Questions 1 & 2 (rank sweep):** set `MANUAL_RUNS = [{'rank': R, 'component': 'default'}]` with R = 16, 64, 256. One rank per run.
- **Question 3 (singular-value ranges):** set `rank` to 16 and `component` to `default`, `p25`, `p50`, or `bottom`. The `default` run is shared with Question 1.
- **Question 4:** run `q4_svd_analysis.ipynb` as is.

The notebook currently keeps the output of the Question 3 `p50` run; the other runs are summarized in `results/`.
