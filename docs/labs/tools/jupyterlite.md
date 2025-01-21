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

## Should you use JupyterLite?

For python-notebook labs, we recommend you use JupyterLite for your learners' best experience.

However, sometimes JupyterLite may not be an option for you - we lay out these cases in the next sections.

For more information on why JupyterLite is preferred over JupyterLab see [JupyterLite vs JupyterLab](./jupyterlite-vs-jupyterlab).

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

### Unsupported Libraries

The following libraries are currently unsupported in JupyterLite
If your lab requires them, you should use [JupyterLab](./jupyterlab) instead:

 - `pytorch`
 - `tensorflow`
 - `requests`
 - `wordcloud`
 - `pyspark`
 - `sqlite3`

### Additional Caveats

Even if your lab uses libraries supported by JupyterLite, there are specific scenarios where you may want to consider using [JupyterLab](./jupyterlab):

 - Your lab has highly cpu-intensive code cells.
   - For example, `sklearn.manifold.TSNE.fit_transform` was found to be impractical in JupyterLite.
 - Large datasets (>100MB+) are being used.
   - Loading large datasets may be inconvenient for your learners on jupyterlite - they will load faster with JupyterLab.
