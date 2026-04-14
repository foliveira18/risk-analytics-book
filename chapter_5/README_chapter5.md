# Chapter 5 Companion — Tail Risk in Discrete Newsvendor Models: VaR, TCE, and CVaR

This folder contains the Python companion notebook for Chapter 5 of *Risk Analytics*.

## Files

- `chapter5_companion.ipynb` — companion notebook
- `requirements_chapter5.txt` — Python dependencies

## What this notebook does

The notebook reproduces and extends the chapter's computational material:

1. Generic discrete VaR, TCE, and exact discrete CVaR
2. A toy discrete example showing why TCE and exact CVaR can differ
3. Binomial-demand newsvendor example: emergency medical drone kits
4. Poisson-demand newsvendor example: backup portable generators
5. Mean--CVaR optimization
6. Sensitivity analysis in `lambda` and `alpha`
7. Reproduction of the Chapter 5 figures

## Recommended setup

The easiest approach is to create a virtual environment **inside the notebook folder**.

### Mac / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_chapter5.txt
python -m pip install ipykernel
python -m ipykernel install --user --name ch5-venv --display-name "Python (ch5-venv)"
```

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_chapter5.txt
python -m pip install ipykernel
python -m ipykernel install --user --name ch5-venv --display-name "Python (ch5-venv)"
```

## Using the notebook in VS Code

1. Open the folder in VS Code.
2. Open a terminal in VS Code.
3. Activate the virtual environment.
4. Install the requirements.
5. Open `chapter5_companion.ipynb`.
6. At the top right of the notebook, select the kernel **Python (ch5-venv)**.
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
- then, in the notebook, choose the kernel **Python (ch5-venv)**

## Run order

This notebook is designed to be run from top to bottom.

Because later sections use functions and variables defined earlier, the safest workflow is:

1. **Restart Kernel**
2. **Run All**

If you run cells out of order, you may see errors such as:

- `NameError` for helper functions
- missing figure variables
- missing distribution summaries

These usually mean that an earlier setup cell has not yet been executed.

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
python -m pip install -r requirements_chapter5.txt
```

## Suggested troubleshooting checks

### Check that SciPy is installed

```bash
python -m pip show scipy
```

### Check the active interpreter

```bash
python -c "import sys; print(sys.executable)"
```

### Check the notebook kernel inside a cell

```python
import sys
import scipy

print(sys.executable)
print(scipy.__version__)
```

## Notes on figure replication

The notebook generates the Chapter 5 figures for the binomial and Poisson examples using the parameter values described in the chapter.

In particular, the Poisson example uses the revised generator setting:

- demand \(D \sim \mathrm{Pois}(5.2)\)
- overage cost \(C_o = 90\)
- underage cost \(C_u = 520\)

If you change the plotting ranges, support truncation, or parameter values, your plots may differ from the figures shown in the chapter.
