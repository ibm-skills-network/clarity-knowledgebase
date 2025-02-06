# JupyterLite

JupyterLite is a responsive python notebook environment we provide for your learners' best experience.

## Using JupyterLite

### Installing Packages

Installing packages in JupyterLab is usually done with a package manager such as `pip`, `conda` or `mamba` like:

```
!pip install numpy pandas
!conda install -c conda-forge numpy pandas
!mamba install numpy pandas
```

In JupyterLite you simply use the `%pip` magic command:

```python
%pip install numpy pandas
```

For [pure python packages](#libraries-from-pypi) we ***strongly recommend*** pinning the python version you wish to install:
```python
%pip install optuna==4.2.0
```

For additional information about supported packages and caveats read the [Supported Libraries](#supported-libraries), [Unsupported or Partially Supported Libraries](#unsupported-or-partially-supported-libraries) and [Additional Caveats](#additional-caveats) sections.

### Downloading Data

You may be accustomed to loading data the following way:

```python
import pandas as pd

URL = 'https://www.url.to/my/dataset.csv'

df = pd.read_csv(URL)
```

In JupyterLite, you must use the following method instead:

```python
import pandas as pd
import skillsnetwork

URL = 'https://www.url.to/my/dataset.csv'

await skillsnetwork.download_dataset(URL)
df = pd.read_csv('dataset.csv')
```

### Best practices

Follow these best practices when creating JupyterLite labs:

 - Ask your learners to launch the lab in the Chrome browser
   - Chrome is recommended for JupyterLite, though Firefox has been shown to work in many cases
 - Do not ask your learners to restart the kernel after `%pip install`
   - Restarting the kernel is common after installing packages in JupyterLab. However, restarting the kernel after installing packages in JupyterLite will make those packages unavailable in JupyterLite
 - Pin [pure python package](#libraries-from-pypi) versions when installing from [PyPI](https://pypi.org/)


## Should you use JupyterLite?

For python-notebook labs, we ***strongly recommend*** you use JupyterLite for your learners' best experience.

However, sometimes JupyterLite may not be an option for you - we lay out these cases in the next sections.

For more information on why JupyterLite is preferred over JupyterLab see [JupyterLite vs JupyterLab](../jupyterlite-vs-jupyterlab).

<!-- ### Supported libraries

Many popular python science libraries are compadible with JupyterLite:
 - `numpy`
 - `sklearn`
 - `scipy`
 - `pandas`
 - `matplotlib`
 - `plotly`
 - `seaborn`
 - And many more -->


### Supported Libraries

#### Preinstalled libraries
JupyterLite comes preinstalled with a set of Python packages. You can find a list of these packages [here](https://pyodide.org/en/latest/usage/packages-in-pyodide.html). The preinstalled packages include some popular Python libraries such as `numpy`, `pandas` and `sklearn`. In order to use these packages, you simply have to import them after an optional `%pip install`:
```python
### OPTIONAL ###
%pip install numpy pandas scikit-learn
################

import numpy as np
import pandas as pd
import sklearn
```

Note that the aforementioned [list](https://pyodide.org/en/latest/usage/packages-in-pyodide.html) of preinstalled packages relates to the latest version of JupyterLite that ***can*** be deployed. However, the JupyterLite version that is ***actually*** deployed by Skills Network is not necessarily the latest version, so the actual list of preinstalled libraries as well as the preinstalled libraries' versions may differ somewhat from that [list](https://pyodide.org/en/latest/usage/packages-in-pyodide.html).

#### Libraries from PyPI
Pure python packages with wheels on [PyPI](https://pypi.org/) can be installed. Pure python packages are those that have files on [PyPI](https://pypi.org/) with the pattern `*py3-none-any.whl`. An example of such a package is `seaborn`: if you go to https://pypi.org/project/seaborn/#files you will notice a file with a pattern matching `*py3-none-any.whl`. In order to install pure python packages remember to pin the version you wish to install, otherwise your lab may break when the package is updated on [PyPI](https://pypi.org/):
```python
%pip install seaborn==0.13.2
```

### Unsupported or Partially Supported Libraries

Packages that are not [preinstalled](#preinstalled-libraries) and not [pure python packages](#libraries-from-pypi) cannot be installed. Moreover, because access to the internet is restricted in the JupyterLite environment, packages that rely on an established internet connection may not work even if they can be installed; for these packages the workaround at [Downloading Data](#downloading-data) might work for you and you may not need to use the non-working package at all. 

The following popular python libraries are not supported or only partially supported in JupyterLite:


 - `pytorch`: this package is not [preinstalled](#preinstalled-libraries) and is not a [pure python package](#libraries-from-pypi)
 - `tensorflow`: this package is not [preinstalled](#preinstalled-libraries) and is not a [pure python package](#libraries-from-pypi)
 - `pyspark`: this package is not [preinstalled](#preinstalled-libraries) and is not a [pure python package](#libraries-from-pypi)
 - `requests`: this package is [preinstalled](#preinstalled-libraries) but under typical usage requires unrestricted access to the internet
 - `sqlite3`: works only with in-memory databases; for example `con = sqlite3.connect(":memory:")`

If your lab requires an unsupported package and a suitable alternative or workaround does not exist, you should use [JupyterLab](./jupyterlab) instead.

### Additional Caveats

Even if your lab uses libraries supported by JupyterLite, there are specific scenarios where you may want to consider using [JupyterLab](./jupyterlab):

 - Your lab has highly cpu-intensive code.
   - For example, `sklearn.manifold.TSNE.fit_transform` was found to be impractical in JupyterLite.
 - Large datasets (>100MB+) are being used.
   - Loading large datasets may be inconvenient for your learners on JupyterLite - they will load faster with JupyterLab.
 - You need a specific version of a Python package that differs from the one that is [preinstalled](#preinstalled-libraries) **AND** the [preinstalled](#preinstalled-libraries) package is not a [pure python package](#libraries-from-pypi).
   - JupyterLite does not allow you to upgrade or downgrade [preinstalled](#preinstalled-libraries) packages ***unless*** they are [pure python packages](#libraries-from-pypi). For instance, `%pip install numpy==1.26.3` will fail, but `%pip install tqdm==4.67.1` will succeed even if another version of `tqdm` is [preinstalled](#preinstalled-libraries).
 - You need to use two or more versions of a Python package in one notebook
   - JupyterLite does not allow you to upgrade or downgrade packages once they have been `%pip install`ed or `import`ed. For instance, `%pip install seaborn==0.13.1` followed by `%pip install seaborn==0.13.2` will fail at the second install.

## Convert from JupyterLab to JupyterLite

You can easily convert from JupyterLab to JupyterLite by following [Convert Labs from JupyterLab to JupyterLite (and Vice Versa) - Convert JupyterLab to JupyterLite](../convert-between-jupyterlab-and-jupyterlite#convert-jupyterlab-to-jupyterlite).

## Convert from JupyterLite to JupyterLab

You can easily convert from JupyterLite to JupyterLab by following [Convert Labs from JupyterLab to JupyterLite (and Vice Versa) - Convert JupyterLite to JupyterLab](../convert-between-jupyterlab-and-jupyterlite#convert-jupyterlite-to-jupyterlab).
