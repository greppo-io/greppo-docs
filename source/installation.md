# Installation

Greppo is a stand-alone library and can be installed using `pip` to install. Python 3.6 and newer is suported.

We recommend using a virtual environment to manage the dependencies for your project (<a href="#pyvenv">see below</a>).  

```shell
pip install greppo
```

## [Python Environment Management](#pyvenv)

Pip will install packages at a global level and it's good practice is to use an Environment manger to isolate individual
Python projects and their respective dependencies. The main reasons to do so are to avoid package conflicts as a project
grows in size and complexity, and to have a reproducible build system.

Here are a few managers commonly used,
- [virtualenv](https://virtualenv.pypa.io/en/latest/)
- [pyenv](https://github.com/pyenv/pyenv)
- [conda](https://docs.conda.io/en/latest/)

As a reference here's one such manager `virtualenv`, assuming you are working with `pip3`.

```shell
pip3 install virtualenv # install virtualenv

virtualenv ENV # Create a new environment

source ENV/bin/activate # activate it

pip install greppo # install greppo inside that environment

# .... build app ...

deactivate # close local environment
```
