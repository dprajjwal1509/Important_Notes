#  Technical Paper: Python Virtual Environments (`venv`)

## 1. Introduction
Python projects often require different sets of packages or even different versions of Python itself. Installing packages globally can cause version conflicts between projects. To solve this, Python provides **virtual environments** using the built-in `venv` module.

A virtual environment is an **isolated workspace** containing its own Python interpreter and libraries. This ensures that dependencies for one project do not interfere with another.

---

## 2. Why Use `venv`?
-  **Isolation**: Each project has its own Python and dependencies.
-  **Reproducibility**: Different versions of packages can coexist across projects.
-  **Safety**: No need to install packages globally with `sudo`.
-  **Portability**: Easy to recreate environments using `requirements.txt`.

---

## 3. Creating a Virtual Environment
```bash
python3 -m venv venv
```
This creates a folder `venv/` in the current directory containing:

```
venv/
├── bin/          # executables (python, pip, activate)
├── lib/          # installed packages
└── pyvenv.cfg    # environment metadata
```

---

## 4. Activating the Environment
```bash
source venv/bin/activate
```
- Modifies your `PATH` so `python` and `pip` point to `venv/bin/`.
- Shell prompt changes to show `(venv)` prefix.

Check with:
```bash
which python
python --version
```

---

## 5. Installing Packages Inside venv
```bash
pip install requests
pip list
```
These packages are stored inside `venv/lib/...`, not system-wide.

Different projects can have different versions of the same package without conflict.

---

## 6. Deactivating
```bash
deactivate
```
This restores your environment to use the system Python (`/usr/bin/python3` or `/usr/local/bin/python3`).

---

## 7. Removing a Virtual Environment
```bash
rm -rf venv
```
Simply deleting the folder removes the environment.

---

## 8. Best Practices
- Keep `venv/` out of version control by adding it to `.gitignore`.
- Use a `requirements.txt` to freeze dependencies:
  ```bash
  pip freeze > requirements.txt
  pip install -r requirements.txt
  ```
- For multiple Python versions, consider using **pyenv** or **Conda**.

---

## 9. Summary
- `venv` is a built-in tool for creating isolated Python environments.
- Each venv has its own interpreter and libraries.
- Activation modifies `PATH`, ensuring correct Python and pip are used.
- Deactivation restores the global environment.

**In one line:** 
`venv` enables clean, conflict-free, and reproducible Python development.

---

## 10. References
- [Python Docs – venv](https://docs.python.org/3/library/venv.html)
- [PEP 405 – Virtual Environments](https://peps.python.org/pep-0405/)

