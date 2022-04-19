---
sidebar_position: 4
---

# JupyterLite

JupyterLite is a responsive python notebook environment we provide for your learners' best experience.

## Using JupyterLite

### Loading Data

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

raw_data = skillsnetwork.load_dataset(URL)
df = pd.read_csv(raw_data)
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

### Additional Caveats

Even if your lab uses libraries supported by JupyterLite, there are specific scenarios where you may want to consider using [JupyterLab](./jupyterlab):

 - Your lab has highly cpu-intensive code cells.
   - For example, `sklearn.manifold.TSNE.fit_transform` was found to be impractical in JupyterLite.
 - Large datasets (>100MB+) are being used.
   - Loading large datasets may be inconvenient for your learners on jupyterlite - they will load faster with JupyterLab.
