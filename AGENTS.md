# Repository Guide

## Scope

- `a1_first_network.ipynb` is both the assignment specification and the implementation; keep its narrative, code, plots, and reported values consistent.
- The network must remain NumPy-only. TensorFlow and Keras are dependencies for later coursework, not valid implementations for this assignment.
- Preserve the specified experiment unless the assignment text changes: seed `504`, architecture `2 -> 16 (ReLU) -> 1 (sigmoid)`, and 100 training epochs.

## Environment And Verification

- Install with `python -m pip install -r requirements.txt` inside a virtual environment.
- On Windows, activate the environment before running Jupyter: `.\.venv\Scripts\Activate.ps1`. The notebook's kernel specification launches bare `python`; using `.venv\Scripts\python.exe -m jupyter` without activation can still select global Python and fail on missing packages.
- There is no separate test or lint suite. Verify by executing every cell in order: `python -m jupyter nbconvert --to notebook --execute a1_first_network.ipynb --output a1_first_network.executed.ipynb --ExecutePreprocessor.timeout=120`.
- Treat `a1_first_network.executed.ipynb` as a disposable verification artifact unless explicitly requested for submission; the primary deliverable is `a1_first_network.ipynb`.

## Submission Constraints

- Keep the Moodle outputs easy to locate: `a1_repo`, `a1_loss_final`, `a1_params`, `a1_opencode_model`, and `a1_reflection`.
- Assignment evidence belongs under `opencode_setup/`; do not invent screenshots, logs, AI-disclosure details, verification claims, or the student's approximately 200-word reflection.
- After changing training code, rerun from a clean kernel so the loss plot and final loss come from the fixed seed rather than stale notebook state.
