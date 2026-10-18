# I2DS 26/27

The repository holds the exercises of Introduction to Data Science for the
2026/27 academic year, together with the environment they run in. The
environment is defined by `pyproject.toml` and `uv.lock`, and every exercise has
been run on exactly the package versions that `uv.lock` pins.

## Setup

The setup takes a few minutes and is done once. It needs internet access, but
the exercises themselves run offline.

1. Clone the repository and enter it.

   ```sh
   git clone https://github.com/peshevskidimitar/I2DS-26-27.git
   cd I2DS-26-27
   ```

2. Install [uv](https://docs.astral.sh/uv/), which installs Python and the
   packages. On macOS and Linux, run this command in a terminal:

   ```sh
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

   On Windows, run this command in PowerShell:

   ```powershell
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

   Open a new terminal afterwards, so that the `uv` command is found.

3. Create the environment in the repository root. The command downloads Python
   3.12 if the machine does not have it, and it installs the packages into a
   `.venv` directory inside the repository.

   ```sh
   uv sync
   ```

4. Install the browser that the exercises drive.

   ```sh
   uv run playwright install chromium
   ```

   On Linux, Chromium also needs system libraries. If the browser check below
   reports a missing library, run `uv run playwright install-deps chromium`,
   which asks for an administrator password.

5. Check the setup by running `environment/verify.ipynb` from top to bottom, as
   described below. Every cell prints what it confirmed, and the machine is
   ready when all of them pass.

## Opening the Notebooks

An exercise notebook reads its data from the `data` directory beside it, so open
it in place rather than copying it elsewhere.

- **JupyterLab.** Run `uv run jupyter lab` in the repository root and open a
  notebook from the file browser.
- **Visual Studio Code.** Open the repository folder, open a notebook, choose
  Select Kernel, and pick the Python environment in `.venv`.

## Exercises

Each auditory exercise has a folder under `auditory` that holds its notebook,
its deck, and the data both of them use.

| Exercise | Notebook | Deck |
| --- | --- | --- |
| 1. Data Gathering and Exploratory Analysis | [notebook.ipynb](auditory/01-data-gathering-and-exploratory-analysis/notebook.ipynb) | [slides.pdf](auditory/01-data-gathering-and-exploratory-analysis/slides.pdf) |

## Updating

New exercises are added during the semester. Run `git pull` to receive them,
and then run `uv sync` again, because an exercise may add a package.
