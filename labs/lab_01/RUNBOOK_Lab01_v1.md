# Lab 1 · Runbook

1. Extract the complete package into your course repository; preserve labs/lab_01 and data/samples/lab01_v1.
2. Use your Week 2 Python environment. If needed: `python -m pip install -r requirements_lab01_v1.txt` from the package root.
3. Open labs/lab_01/Lab01_EDA_Baselines_Student_v1.ipynb with that environment's Python kernel. Default MODE is snapshot; no network is used by the notebook.
4. Work through train, then calibration. Complete the written evidence and freeze record before enabling RUN_TEST.
5. Restart and Run All after completing the notebook. Save its outputs. Confirm that you can reproduce the frozen evaluation without modifying decisions.
6. Record your actual Python/package versions, operating system, any changes to this procedure, the submitted commit and the date/result of your check below. Keep the source CSVs unchanged.

Actual environment and execution evidence:

- OS: Linux-7.0.0-31-generic-x86_64-with-glibc2.43.
- Python 3.12.14 (installed via `mise`, since the machine's default Python 3.14.6 has no compatible wheel for `numpy==1.26.4`), running inside a project-local virtual environment at `.venv/`.
- Installed with `python -m venv .venv && .venv/bin/pip install -r requirements_lab01_v1.txt`, matching the pinned versions exactly: numpy 1.26.4, pandas 2.3.1, matplotlib 3.10.3, ipykernel 6.30.0, notebook 7.4.5. Jupyter kernel registered as `lab01-udd`.
- Executed headlessly with `jupyter nbconvert --to notebook --execute --inplace --ExecutePreprocessor.kernel_name=lab01-udd labs/lab_01/Lab01_EDA_Baselines_Student_v1.ipynb`, equivalent to Kernel > Restart and Run All in the notebook UI.
- Procedure change: `Series.corr(method='spearman')` requires `scipy`, which is not in `requirements_lab01_v1.txt`. Rank-based Pearson correlation (`.rank().corr(..., method='pearson')`) was used instead to report the Spearman coefficient without adding an unpinned dependency.
- Run in two passes per the freeze procedure: (1) `RUN_TEST=False` through calibration, committed and tagged `lab1-pre-test-freeze`; (2) `RUN_TEST=True`, Restart and Run All again to produce the final executed notebook with test (2023-2024) results.
- Date of final executed run: 2026-09-24. Submitted commit: see repository log (final commit on top of tag `lab1-pre-test-freeze`).

Submission uses GitHub + Canvas as stated in the brief. Include support code and the six CSVs plus lab01_manifest_v1.json. No API credentials are needed. If your environment is blocked, record the exact error and contact the teaching team; do not label synthetic practice as real data.
