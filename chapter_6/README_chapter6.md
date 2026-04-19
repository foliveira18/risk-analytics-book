# Chapter 6 Companion — Tail Risk under Unknown Loss Distributions

This folder contains the Python companion notebook for Chapter 6 of *Risk Analytics*.

## Files

- `chapter6_companion.ipynb` — companion notebook
- `requirements_chapter6.txt` — Python dependencies

## What this notebook does

The notebook reproduces and extends the chapter's computational material:

1. Empirical VaR, TCE, and exact empirical CVaR from finite samples
2. A toy empirical example showing why empirical TCE and exact empirical CVaR can differ
3. Linear-programming formulation of empirical mean--CVaR optimization
4. Chapter 6 newsvendor example with a 1000-scenario asymmetric bimodal demand sample
5. LP solution of the empirical mean--CVaR newsvendor problem
6. Sensitivity analysis in `lambda`, `alpha`, sample size, and scenario representation
7. Reproduction of the Chapter 6 figures

## Recommended setup

The easiest approach is to create a virtual environment **inside the notebook folder**.

### Mac / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_chapter6.txt
python -m pip install ipykernel
python -m ipykernel install --user --name ch6-venv --display-name "Python (ch6-venv)"
```

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_chapter6.txt
python -m pip install ipykernel
python -m ipykernel install --user --name ch6-venv --display-name "Python (ch6-venv)"
```

## Using the notebook in VS Code

1. Open the folder in VS Code.
2. Open a terminal in VS Code.
3. Activate the virtual environment.
4. Install the requirements.
5. Open `chapter6_companion.ipynb`.
6. At the top right of the notebook, select the kernel **Python (ch6-venv)**.
7. Click **Restart Kernel and Run All**.

### If VS Code uses the wrong Python

If the notebook cannot import packages that are already installed in the terminal, the notebook is usually attached to the wrong interpreter or kernel.

Check the terminal interpreter:

```bash
which python
```

It should point to the `.venv` inside the project folder.

Then, in VS Code:

- press `Cmd+Shift+P` on Mac or `Ctrl+Shift+P` on Windows
- run **Python: Select Interpreter**
- choose the `.venv` interpreter in the project folder
- then, in the notebook, choose the kernel **Python (ch6-venv)**

## Run order

This notebook is designed to be run from top to bottom.

Because later sections use functions and variables defined earlier, the safest workflow is:

1. **Restart Kernel**
2. **Run All**

## Dependencies

The notebook uses:

- `numpy`
- `pandas`
- `matplotlib`
- `scipy`
- `jupyter`
- `ipykernel`

Install them with:

```bash
python -m pip install -r requirements_chapter6.txt
```

## Notes on figures

The notebook generates the Chapter 6 figures using the revised empirical demand sample with:

- 1000 scenarios
- a regular-demand regime
- a surge-demand regime
- a small stress tail

This construction is intentionally asymmetric and bimodal so that the scenario set does not correspond to a single standard theoretical distribution.
