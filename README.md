[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/RS1U-rwk)
# HW1: Environment Setup & GitHub Basics

## Overview

This assignment ensures you have properly set up your development environment and can use GitHub for version control. By completing this assignment, you will:

1. Install Anaconda (if not already installed)
2. Create a conda environment with all required packages for the bootcamp
3. Verify your installation with a Python script
4. Commit and push your verification results to GitHub

## Prerequisites

### GitHub Account
If you don't have a GitHub account yet, create one at: https://github.com/signup

### Git Installation

**Mac Users:**
Install Xcode Command Line Tools, which includes git:
```bash
xcode-select --install
```
This will open a dialog to install the command line developer tools. Once installed, you'll have git available.

**Windows/Linux Users:**
Download and install git from: https://git-scm.com/downloads

Verify git is installed by running:
```bash
git --version
```

### GitHub CLI (Recommended)
We recommend installing the GitHub CLI for easier GitHub integration:
- Installation instructions: https://cli.github.com/
- After installing, authenticate with: `gh auth login`

### Basic Command Line Familiarity
You should be comfortable navigating directories and running commands in a terminal.

Here is a popular GitHub and command line tutorial video: https://www.youtube.com/watch?v=HVsySz-h9r4

## Instructions

### Step 1: Install Anaconda (or Alternative)

**Note:** If you already have Miniconda, Miniforge, Mambaforge, or Mamba installed, you can use those instead - they all work with this assignment!

**Option 1: Download Anaconda**
Download and install from: https://www.anaconda.com/download

**Option 2: Install via Homebrew (Mac users only)**
If you have Homebrew installed:
```bash
brew install --cask anaconda
```
Then add conda to your PATH (follow the instructions shown after installation).

Verify installation by running:
```bash
conda --version
```

### Step 2: Create the Conda Environment

In the directory containing this README, run:

```bash
conda env create -f environment.yml
```

This will create an environment named `bootcamp2025_HW1` with all required packages:
- Python 3.11
- PyRosetta (for protein structure manipulation - channels configured in environment.yml)
- NumPy (numerical computing)
- Pandas (data analysis)
- Matplotlib & Seaborn (visualization)
- Jupyter (interactive notebooks)
- SciPy (scientific computing)
- scikit-learn (machine learning)
- Biopython (bioinformatics tools)

**Note:** The environment.yml file includes the RosettaCommons conda channel, so you don't need to configure it manually.

### Step 3: Activate the Environment

```bash
conda activate bootcamp2025_HW1
```

You should see `(bootcamp2025_HW1)` in your terminal prompt.

### Step 4: Run the Verification Script

```bash
python verify_setup.py
```

This script will:
- Check that all required packages are installed
- Display version information for each package
- Generate a `verification_result.json` file

If all checks pass, you should see:
```
🎉 SUCCESS! All packages are installed correctly!
```

If some checks fail, the script will provide guidance on what went wrong.

### Step 5: Update the Verification File

Open `verification_result.json` in a text editor and replace `"REPLACE_WITH_YOUR_NAME"` with your actual name.

### Step 6: Commit and Push Your Verification

Now that you have your verification file, commit and push it to your GitHub Classroom repository:

```bash
# Add the verification file
git add verification_result.json

# Create your commit
git commit -m "Add environment verification"

# Push to GitHub
git push
```

### Step 7: Verify Your Submission

Go to your GitHub repository (the one created when you accepted the assignment) and verify that:
- The `verification_result.json` file is present
- It contains your name (not "REPLACE_WITH_YOUR_NAME")
- The `verification_passed` field is `true`

## Submission

Your work is automatically submitted when you push to your GitHub Classroom repository. The instructor will be able to see your verification file and check that all requirements are met.

## Troubleshooting

### PyRosetta Installation Issues

If PyRosetta fails to install:
1. Make sure you're using the environment.yml file which includes the RosettaCommons channel
2. Try creating the environment again with verbose output: `conda env create -f environment.yml --verbose`
3. If that fails, try installing PyRosetta separately: `conda install -c https://conda.rosettacommons.org pyrosetta`
4. Check that you're using a compatible Python version (3.11 is specified in environment.yml)

### Import Errors

If packages are installed but imports fail:
1. Make sure you've activated the environment: `conda activate bootcamp2025_HW1`
2. Try reinstalling the problematic package: `conda install --force-reinstall <package-name>`

### Git Issues

If you have trouble with git:
- Make sure git is installed: `git --version`
- Configure your git identity if needed:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

### Authentication with GitHub

If you have trouble pushing to GitHub, you may need to set up authentication:
- Use GitHub's personal access token: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token
- Or set up SSH keys: https://docs.github.com/en/authentication/connecting-to-github-with-ssh

## Questions?

If you run into any issues or have questions, contact Ian at: **icanderson@ucdavis.edu**
