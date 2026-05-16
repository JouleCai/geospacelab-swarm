# Installation
## Python environment and IDEs
The Python distribution **Anaconda** is recommended. To install **Anaconda**, see [Installing Anaconda Distribution](https://www.anaconda.com/docs/getting-started/anaconda/install/overview). After installation, a **conda** virtual environment can be created by, e.g.,

```{code-block} shell
conda create --name YOUR_ENV_NAME python=3.12 cython spyder
```

After creating the virtual environment, one needs to activate it:

```{code-block} shell
conda activate YOUR_ENV_NAME
```

### Python IDEs
Popular Python IDEs include **Spyder**, **PyCharm**, and **VS Code**. 


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






