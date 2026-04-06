# Chapter 4 Companion — VaR, CVaR and Downside Risk Assessment

This folder contains the revised Python companion notebook for Chapter 4 of *Risk Analytics*.

## Files

- `chapter4_companion_revised.ipynb` — revised notebook
- `requirements_revised.txt` — Python dependencies

## What this notebook does

The notebook reproduces and extends the chapter's computational material:

1. VaR and CVaR for a normal loss variable
2. Newsvendor mismatch loss
3. Critical-ratio benchmark
4. Induced newsvendor VaR and CVaR
5. Mean--CVaR optimization
6. Sensitivity analysis in `lambda` and `alpha`
7. Monte Carlo validation

## Recommended setup

The easiest approach is to create a virtual environment **inside the notebook folder**.

### Mac / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_revised.txt
python -m pip install ipykernel
python -m ipykernel install --user --name ch4-venv --display-name "Python (ch4-venv)"
```

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_revised.txt
python -m pip install ipykernel
python -m ipykernel install --user --name ch4-venv --display-name "Python (ch4-venv)"
```

## Using the notebook in VS Code

1. Open the folder in VS Code.
2. Open a terminal in VS Code.
3. Activate the virtual environment.
4. Install the requirements.
5. Open `chapter4_companion_revised.ipynb`.
6. At the top right of the notebook, select the kernel **Python (ch4-venv)**.
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
- then, in the notebook, choose the kernel **Python (ch4-venv)**

## Run order

This notebook is designed to be run from top to bottom.

Because later sections use functions and variables defined earlier, the safest workflow is:

1. **Restart Kernel**
2. **Run All**

If you run cells out of order, you may see errors such as:

- `NameError: q_bounds is not defined`
- `NameError: mean_cvar_objective is not defined`

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
python -m pip install -r requirements_revised.txt
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

The figures in Sections 4, 5, and 6 are configured with ranges, labels, and line styles chosen to resemble the corresponding chapter figures more closely. If you change the plotting ranges or parameter values, your plots may look different from the ones shown in the chapter.
