# Paper Reproduction Log - Engineer 2: Martina Riascos

# Biologist 2's papers

### Paper 1 – Targeting Neurodegeneration: three machine learning methods for G9a inhibitors discovery Using PubChem and scikit-learn

- **Link to paper**: [https://doi.org/10.1007/s10822-025-00642-z](https://doi.org/10.1007/s10822-025-00642-z)
- **Code repo**: [https://github.com/articlesmli/G9a_Inhibitors_efficacy](https://github.com/articlesmli/G9a_Inhibitors_efficacy)

**What we tried**

- Cloned repo
- Opened the README to find how to run
- Attempted running from jupyter notebook

**What went wrong**

- No instruction in the README, only links to datasets
- After modifying first step of repo, realized that there was too much pre-processing to continue working on this project

**Conclusion**

- Could have been interesting, but required too much work for a short-term project

### Paper 2 - Dual inhibition of AChE and MAO-B in Alzheimer’s disease: machine learning approaches and model interpretations

- **Link to paper**: https://link.springer.com/article/10.1007/s11030-024-11061-x?fromPaywallRec=false#Abs1
- **Code repo**: https://github.com/houzhe122/AChE-MAOB-Models

**What we tried**

- Cloned repo to run on terminal, since we are working with .py files
- Creating environments to run code

**What went wrong**

- No readme, but maybe because it's all python code
- Datasets missing while running

**Conclusion**

- Cannot run normally as excel file is missing from repository

### Paper 3 – A machine-learning based objective measure for ALS disease severity

- **Link to paper**: https://www.nature.com/articles/s41746-022-00588-8
- **Code repo**: https://github.com/PMPhelp/paper-code

**What we tried**

- Cloned the GitHub repository and verified all code files were present
- Installed required dependencies (tensorflow, keras, numpy)
- Ran all provided Python scripts
- Reviewed .py files to identify model training, evaluation, and output steps

**What we observed**

- Scripts executed without runtime errors
- Code consists of model architecture definitions and preprocessing layers only
- No scripts initiate training or evaluation directly
- Running the files produced no terminal output and no saved result or figure files

**What went wrong**

- The repository doesn't include any end-to-end pipeline or post-processing code to reproduce the paper’s figures or metrics
- Additional custom scripts would be required to train models, export predictions, and generate figures

**Conclusion**

- The provided code does not reproduce any experimental results on its own
- Reproducing the paper’s figures is not possible using the repository as-is
- This represents a reproducibility limitation despite access to the model definitions