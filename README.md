# jupyterlite-emscripten-forge-sandbox
Repo to test the deployment of JupyterLite Xeus from emscripten-forge packages

## Overview

This repository demonstrates how to build and deploy JupyterLite with emscripten-forge packages to GitHub Pages.

## Installed Packages

The following packages are pre-installed in the JupyterLite environment:
- scikit-learn
- pyarrow
- pandas
- matplotlib-base

## Configuration Files

- `environment.yml`: Conda environment file specifying the packages to install
- `jupyter-lite.json`: JupyterLite configuration pointing to the environment file
- `content/`: Directory containing demo notebooks

## Building Locally

To build the JupyterLite site locally:

1. Install dependencies:
   ```bash
   pip install jupyterlite jupyterlite-xeus
   ```

2. Install micromamba (required for emscripten-forge packages):
   ```bash
   # Follow instructions at https://mamba.readthedocs.io/en/latest/installation/micromamba-installation.html
   ```

3. Build the site:
   ```bash
   jupyter lite build --contents content --output-dir dist
   ```

4. Serve the site:
   ```bash
   jupyter lite serve
   ```

## Deployment

The site is automatically built and deployed to GitHub Pages when changes are pushed to the `main` branch. The deployment is handled by the GitHub Actions workflow in `.github/workflows/deploy.yml`.

## Usage

Once deployed, you can access the JupyterLite site at: `https://<username>.github.io/<repository-name>/`

Try the demo notebook in `content/demo.ipynb` to see the installed packages in action.

