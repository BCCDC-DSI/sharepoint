# Linters

Linters analyze code and come in 3 broad categories:
- Logical: analyze code for errors, unintended results, "dangerous code" patterns
- Stylistic: code not conforming to conventions that are predefined
- Analytical: analyze code based on metrics 
  - lines of code, complexity, etc.
  - 

## Python Linters

Linters analyze code and come in 3 broad categories:

| Linter |	Category	| Description | Runtime |
| :-- | :-- | :-- | :-- |
| Bandit| 	Logical	Analyzes code to find common security issues|  - |
| [pycodestyle](https://github.com/PyCQA/pycodestyle)	|  Stylistic	Checks against some of the style conventions in PEP 8 | 0.14s |
| [pydocstyle-(https://github.com/PyCQA/pydocstyle)	|  Stylistic	Checks compliance with Python docstring conventions | 0.21s |
| [Pylint](https://www.pylint.org/)	|  Logical & Stylistic	Checks for errors, tries to enforce a coding standard, looks for code smells | 1.16s |
| [PyFlakes](https://github.com/PyCQA/pyflakes)	|  Logical	Analyzes programs and detects various errors | 0.15s |
| MyPy	|  Logical	Checks for optionally-enforced static types|  - |


References
- https://realpython.com/python-code-quality/
