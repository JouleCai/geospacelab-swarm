
# Configuration

## Initial configuration in GeospaceLAB
When importing GeospaceLAB for the first time, a sequence of messages will be prompted in the Python console, allowing the user to set the root directory for data storage. All settings are defined in the configuration file, which can be found at:
```{code-block} shell
[YOUR_HOME_DIR]/.geospacelab/config.toml
```
The default directory for data storage is 
```{code-block} shell
[YOUR_HOME_DIR]/Geospacelab/Data
```
The Swarm data files downloaded from the Swarm Dissemination Sever will be stored in this root data directory. The sub-directories indicates the data providers and data products. Data downloaded from Swarm VirES or HAPI services will be stored in their own cache files.

## Configuration for Swarm
### Create and set ESA EO account
To access Swarm data from the [Swarm Dissemination Sever](https://swarm-diss.eo.esa.int/), an ESA EO account is required. When importing a Swarm dataset for the first time, a message will be prompted in the Python console, asking for the account name and password of [ESA Earth Online](https://earth.esa.int/eogateway). Please register an account following the instructions at [ESA EO Identity and Access Management System](https://eoiam-idp.eo.esa.int/) or [How do I access Swarm data?](https://earth.esa.int/eogateway/faq/how-do-i-access-swarm-data).

The account name and password will be stored using [Python keyring](https://github.com/jaraco/keyring).

:::{note}
The Python [keyring](https://github.com/jaraco/keyring) package securely stores and retrieves passwords, similar to the MacOS keychain. Using this module, Python code can access the system keyring service. 
:::

:::{tip}
If you input incorrect account name and/or password, you can reset the account name and password by removing the following lines in the configuration file:
```{code-block} toml
[datahub.esa_eo]
username = "xxx@xxx"
``` 
Then run the script again and follow the messages to reset the username and password. Alternatively, you can reset your password using Python keyring.
:::

### Optional: Configuration for Swarm VirES
By default, GeospaceLAB will download the Swarm data from ESA's [Swarm Dissemination Sever](https://swarm-diss.eo.esa.int/) and the data will be stored locally. An developing feature is that a VirES user can use GeospaceLAB to touch the Swarm data that supported in VirES and use the functions in GeospaceLAB to manage and visualize the data. Configuration for the VirES Python client can be found in [Swarm Notebooks](https://notebooks.vires.services/docs/welcome) (see [Swarm access through VirES](https://notebooks.vires.services/notebooks/02a__intro-swarm-viresclient)).

Another benefit to use the VirES service is that the data can be accessed without downloading and storing the data locally. This is particularly useful for users with limited local storage space. However, the data access speed may vary, depending on the internet connection and server load. In addition, if the version of the data product is updated, the data accessed through VirES will be updated accordingly. The updated results may be different from the previous results, which may cause issues for reproducibility. Therefore, it is recommended to download and store the data locally for long-term use.



