
# Configuration

## Initial configuration in GeospaceLAB
When to import GeospaceLAB for the first time, a sequence of messages will be prompted in the Python console and a user can set the root directory of the data to be stored. All of the settings are defined in the configuration file, which can be found here
```{code-block} shell
[YOUR_HOME_DIR]/.geospacelab/config.toml
```
The default directory for data storage is 
```{code-block} shell
[YOUR_HOME_DIR]/Geospacelab/Data
```
If it is not modified, the Swarm data downloaded from the Swarm Dissemination Sever will be stored in that data folder. Data downloaded from Swarm VirES or HAPI services will be stored in their own cache files.

## Configuration for Swarm
### Create and set ESA EO account

The ESA EO account is required to access Swarm data from the [Swarm Dissemination Sever](https://swarm-diss.eo.esa.int/). A message will be prompted in the Python console, when a Swarm dataset is imported at the first time. It asks for the account name and password of [ESA Earth Online](https://earth.esa.int/eogateway). Please register the account following the instruction at [ESA EO Identity and Access Management System](https://eoiam-idp.eo.esa.int/) or [How do I access Swarm data?](https://earth.esa.int/eogateway/faq/how-do-i-access-swarm-data).

The account name and password will be stored using [Python keyring](https://github.com/jaraco/keyring).

:::{note}
The Python [keyring](https://github.com/jaraco/keyring) package securely stores and retrieves passwords, similar to the MacOS keychain. Using this module, Python code can access the system keyring service. 
:::

:::{tip}
In case that incorrect account name and/or passward are input, new account name and/or password can be reset by removing the following lines in the configuration file:
```{code-block} toml
[datahub.esa_eo]
username = "xxx@xxx"
``` 
Then run the script again and follow the messages to reset the username and password. Alternatively, you can reset your password using Python keyring.
:::

### Optional: Configuration for Swarm VirES
Defaultly GeospaceLAB will download the Swarm data from ESA's [Swarm Dissemination Sever](https://swarm-diss.eo.esa.int/) and the data will be stored locally. An developing feature is that a VirES user can use GeospaceLAB to touch the Swarm data that supported in VirES and use the functions in GeospaceLAB to manage and visualize the data. Configuration for the VirES Python client can be found in [Swarm Notebooks](https://notebooks.vires.services/docs/welcome) (see [Swarm access through VirES](https://notebooks.vires.services/notebooks/02a__intro-swarm-viresclient)).


