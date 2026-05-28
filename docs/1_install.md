# Installation
## Python environment and IDEs
A **conda** environment is recommended. The easiest way to set up a **conda** environment is to install **Anaconda**. For instructions, see [Installing Anaconda Distribution](https://www.anaconda.com/docs/getting-started/anaconda/install/overview). After installation, a **conda** virtual environment can be created by, e.g.,

```{code-block} shell
conda create --name YOUR_ENV_NAME -c conda-forge python=3.12 cython spyder
```

After creating the virtual environment, one needs to activate it:

```{code-block} shell
conda activate YOUR_ENV_NAME
```

### Python IDEs
Popular Python IDEs include **Spyder**, **PyCharm**, and **VS Code**. Choose one of them based on your preference and install it. For example, 
- to install **Spyder**, see [Installing Spyder](https://docs.spyder-ide.org/current/installation.html).
- to install **PyCharm**, see [Installing PyCharm](https://www.jetbrains.com/pycharm/download/#section=windows).
- to install **VS Code**, see [Installing Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview).

### Operating Systems
GeospaceLAB is compatible with Windows, macOS, and Linux. The installation process may vary slightly depending on the operating system. Please refer to the respective documentation for any OS-specific instructions.
If Windows users encounter issues with the installation, it is recommended to use the Windows Subsystem for Linux (WSL) to create a Linux environment on their Windows machine. For more information on WSL, see [Windows Subsystem for Linux Installation Guide](https://docs.microsoft.com/en-us/windows/wsl/install) and [VS Code Remote - WSL](https://code.visualstudio.com/docs/remote/wsl).

## Install GeospaceLAB

Install GeospaceLAB via PyPI:
```{code-block} shell
pip install geospacelab
```
To upgrade GeospaceLAB:
```{code-block} shell
pip install -U geospacelab
```

### Dependencies
Most of the dependencies are installed when the package is installed. A few packages can be installed manually. 

For example, the **Cartopy** package is useful for processing and mapping geospatial data. To install **Cartopy**, see [Installing Cartopy](https://cartopy.readthedocs.io/stable/installing.html).

Another useful package is **ApexPy**, which provides a Python interface to the Apex coordinate system. To install **ApexPy**, see [Installing ApexPy](https://apexpy.readthedocs.io/en/latest/installation.html).

To use the VirES and HAPI services, install the `viresclient`:
```{code-block} shell
pip install viresclient
```
and the `hapiclient`:
```{code-block} shell
pip install hapiclient
```

:::{note}
Pre-requisites for **ApexPy** include C++ and Fortran compilers. If you encounter issues during installation, please refer to the [ApexPy installation guide](https://apexpy.readthedocs.io/en/latest/installation.html) for troubleshooting steps.

It's recommended to install **gcc** and **gfortran** compilers. For example, on Ubuntu, you can install them using:
```{code-block} shell
sudo apt-get install build-essential gfortran
```
or using the `conda` package manager:
```{code-block} shell
conda install -c conda-forge gcc gfortran
```
:::








