# Managing Python Virtual Environments with Anaconda
Working on multiple Python projects often requires different dependencies or specific versions of libraries. This can lead to conflicts if managed within the same Python environment. This issue can be solved with virtual environments. Virtual environments provide an isolated setting for each project, ensuring that dependencies for one project do not interfere with those of another.  
A virtual environment is an isolated copy of Python that maintains its own files, directories, and paths so that you can manage project-specific dependencies without conflict. It does not inherit packages from your system's Python installation or other environments, making each project clean and manageable.  
Anaconda simplifies this process further by integrating environment management directly, allowing you to create, manage, and switch between environments with ease. This isolation helps maintain project integrity and avoids version conflicts among packages.  
When using Anaconda, each environment can also specify its own Python version, separate from the system's default Python or the base Anaconda installation. This feature is especially useful when different projects require different Python versions.

## Checking python version
If in doubt, which Python version you have, open your terminal and type:
```bash
python --version  
```
or
```bash
python3 --version  
```
The output should tell you which version of Python your system has and uses.

## Creating a Virtual Environment

To create a new virtual environment with Anaconda, use the following command in the Anaconda PowerShell Prompt or Terminal:

```bash
conda create --name my_env python=3.x
```

Replace "my_env" with your desired environment name. If you wish to specify the Python version, replace the x in "3.x" with the Python version you wish to use; otherwise, drop the "python=3.x".

Aside from anaconda, one can create a virtual environment using Python's **venv** module, which is contained in Python version 3.3 and up. For that, enter the following, depending on your OS (Operating System), into your terminal:
```bash
# For Windows:
python -m venv my_env

# For Linux and MacOS:
python3 -m venv my_env
```

## Activating and Deactivating the Virtual Environment

Activate the virtual environment via the following command in the Anaconda PowerShell Prompt or Terminal:

```bash
# Using Anaconda:
conda activate my_env

# For Windows:
.\my_env\Scripts\activate

# For Linux and MacOS:
source my_env/bin/activate
```

Now you have activated **my_env** (or whichever name you chose for your virtual environment).  

To deactivate the environment, use the following command in the Anaconda PowerShell Prompt or Terminal:
```bash
conda deactivate
```

> **Note:** To deactivate the environment, you do not need to specify the environment name, as there is only one environment active per terminal session.

## Installing Packages
When working within an Anaconda environment, you can install packages using either Conda or pip. While Conda is preferred for managing packages and their dependencies to avoid conflicts, there are instances where a package might only be available via pip, or a specific version is required that's not in the Conda repositories.

To install packages with Conda, use:
```bash
conda install my_lib
```
Replace **my_lib** with the name of the package you wish to install. If you are not using Anaconda or the package is not available through Conda or you need a version only available via pip, you can use pip within the Conda environment:  
```bash
pip install my_lib
```

## requirements.txt
Requirements.txt is central for documenting and managing project dependencies more efficiently, especially when sharing your project or setting it up on a different machine. This file lists all packages and their versions, making it straightforward to replicate an environment.  
### Generating requirements.txt
For packages installed with pip, use:
```bash
pip freeze > requirements.txt
```
This command creates requirements.txt with a list of all pip-installed packages and their versions in the current environment, including those installed by Conda if pip was used subsequently.

To install the required packages on a different system or environment, ensure you have the **requirements.txt** file in your current directory and run:
```bash
pip install -r requirements.txt
```
This will install all the packages listed in **requirements.txt** into the current environment.
> **Note:** for the best compatibility and to avoid potential issues, it's recommended to use the same Python version across different environments when installing from **requirements.txt**.

### Using conda list --export
For a Conda-centric approach, especially when the environment is heavily reliant on Conda for package management, use:
```bash
conda list --export > environment.txt
```
This command generates a list of all Conda-installed packages, which can be used to recreate the environment using:
```bash
conda create --name new_env --file environment.txt
```
### Best Practices
Utilizing both **pip freeze** and **conda list --export** allows for comprehensive environment documentation. **requirements.txt** is ideal for pip-specific dependencies, while **environment.txt** caters to Conda's ecosystem.  
