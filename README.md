# Digit-Recognition

This repository contains a simple Digit Recognition application built as a learning/demo project. It demonstrates loading the MNIST dataset, visualizing samples, training several baseline classifiers (scikit-learn) and a simple neural network (TensorFlow / Keras) inside a notebook (`App.ipynb`).

## Features

- Load and visualize the MNIST digit dataset
- Train and evaluate classical ML classifiers (LogisticRegression, SVC, RandomForest)
- Train a small CNN using TensorFlow / Keras
- Example evaluation: accuracy, confusion matrix, classification report

## Recommended environment

- OS: Windows 10/11 (tested)
- Python: 3.8 - 3.11 recommended (TensorFlow wheels support specific Python versions)
- Create and use a virtual environment for reproducibility

## Setup (PowerShell)

1. Create a virtual environment (recommended):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

2. Install required packages (the notebook contains an installer cell that installs into the kernel Python):

```powershell
python -m pip install numpy pandas matplotlib scikit-learn seaborn tensorflow
```

Note: Installing `tensorflow` on Windows can take some time and may fail if your Python version or platform isn't supported. If you use conda, installing TensorFlow via conda-forge is often more reliable:

```powershell
conda create -n tf python=3.10
conda activate tf
conda install -c conda-forge tensorflow
```

## How to run

1. Open the project in VS Code or Jupyter Lab and open `App.ipynb`.
2. Run the first notebook cell (it installs packages into the active kernel using the kernel's Python interpreter).
3. Restart the kernel if the installer completed and then run the remaining cells in order.

## Troubleshooting

- Error: ModuleNotFoundError: No module named 'tensorflow.python'

	This usually means one of the following:
	- TensorFlow install was interrupted / partially installed. Try reinstalling in the same Python environment.
	- You ran `pip` in a different interpreter than the notebook kernel. Use the installer cell in `App.ipynb` (it uses the kernel's interpreter), or run `python -m pip install ...` using the same `python` executable printed by the diagnostics cell.
	- A local file or folder named `tensorflow` is shadowing the package. Search the project root for `tensorflow`-named files and remove/rename them.

	Quick fixes:

	- Reinstall TensorFlow into the active environment: `python -m pip uninstall tensorflow -y` then `python -m pip install --no-cache-dir tensorflow`.
	- If permission or path-length errors occur on Windows, try creating the virtualenv at a shorter path (e.g., `C:\venv`) or use conda.

## Notes

- The notebook includes diagnostic cells that print the kernel's Python executable and search for local shadowing files. Run them if you encounter import errors.
- This repository is meant as an educational demo, not a production-ready pipeline.

## License
📄 [License](./LICENSE.md): Proprietary – Permission Required

