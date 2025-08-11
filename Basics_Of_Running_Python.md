# Basics Of Running Python

Created Time: August 11, 2025 5:24 PM
Last Edited Time: August 11, 2025 6:43 PM

## Running Things In Python

- To find the python version on mac → **`python3 —version`**
- For Scripts [Files basically] → **`python3 main.py`**
- For running a python module → **`python3 -m pkg.module`**
- One line statements Ex. **`print(2 + 2)`** → **`python -c "print(2+2)”`**

---

## Main Guard

```python
**if __name__ == "__main__":
    # Code here only runs when the script is executed directly
    main()**
```

- The main guard in python is a statement that’s included in a file to control whether or not code executes when a file is run directly verus if it’s imported as a module

### How It Works

- When python runs a file, it changes the value of the variable **`__name__`**
- If the file is run directly [**`python3 script.py`**], this variable will be set to **`__main__`**
- If the file is imported as a part of a module, then the value of this variable will be set to the name of the module **`Script`**

### Benefits Of This

- Lets code run as both a part of a module and as a standalone file
- Makes testing easier without interfering with the implementation that might exist elsewhere
- Reduces the execution of unnecessary code

---

## Virtual Environments

### The purposes of virtual environments in python

- **Dependency Isolation** → Creates an isolated space where you can install your python modules and packages without messing with your system wide python installations
- **Version Management** → Different projects require different versions of some packages in order to work, so each environment can have its own installation of the package in question
- **Project Reproducibility** → if you add a **`requirements.txt`** file to your venv, anyone can reproduce your project by installing the packages listed in it, making collaboration easier
- **System Protections** → By installing your packages in virtual environments, you keep them separate from your system packages, avoiding any conflicts
- **Avoiding package installation conflicts** → avoids conflicts between different versions of a package installed for different projects

```bash
**python3 -m venv .venv
source .venv/bin/activate   # Win: .venv\Scripts\Activate.ps1
python -m pip install requests**
```

---
