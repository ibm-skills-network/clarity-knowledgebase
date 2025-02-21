---
sidebar_position: 1
---

# Overview

Jupyterlab is a fully-featured python notebook environment.

We provide it to authors when [JupyterLite](/docs/labs/tools/jupyterlite/overview) has insufficient compatibility.

## Should you use JupyterLab?

If possible, we ***strongly recommend*** you use [JupyterLite](/docs/labs/tools/jupyterlite/overview) instead of JupyterLab.

For more information on why [JupyterLite](/docs/labs/tools/jupyterlite/overview) is preferred over JupyterLab see [JupyterLite vs JupyterLab](/docs/labs/misc/jupyterlite-vs-jupyterlab).

For information on [JupyterLite](/docs/labs/tools/jupyterlite/overview)'s limitations and suitability for your lab, visit [Should you use JupyterLite?](/docs/labs/tools/jupyterlite/overview#should-you-use-jupyterlite).

You should only use JupyterLab if you have confirmed, based on the above resources, that [JupyterLite](/docs/labs/tools/jupyterlite/overview) is unsuitable for your purposes.

## JupyterLab Types

We offer two distinct versions of JupyterLab: JupyterLab Current and JupyterLab Classic. If you cannot use [JupyterLite](/docs/labs/tools/jupyterlite/overview) for your Jupyter notebook lab, we ***strongly recommend*** using JupyterLab Current unless you need some of the unique features of JupyterLab Classic. JupyterLab Current offers:

- Python 3.12
- A recent kernel for R
- Faster loading than JupyterLab Classic
- Free access to watsonx.ai, OpenAI, and Anthropic APIs; see [Free APIs Available in Skills Network Labs](/docs/labs/features/free-apis) for details and limitations

In contrast, JupyterLab Classic offers:
- Python 3.7
- An older kernel for R
- Kernels for Julia and Swift
- Slower loading than JupyterLab Current
- Free access to the OpenAI API, but not the watsonx.ai and Anthropic APIs; see [Free APIs Available in Skills Network Labs](/docs/labs/features/free-apis) for details and limitations

Since JupyterLab Current is ***strongly recommended*** over JupyterLab Classic, we have provided a guide to help you convert JupyterLab Classic labs to JupyterLab Current labs. You can find the guide at [Upgrading to the Latest Version of JupyterLab](/docs/labs/misc/upgrade-lab-tool-version).

## Using JupyterLab

### Installing Packages

#### Install from PyPI

Packages can be installed from [PyPI](https://pypi.org/) using `pip`:

```
!pip install optuna
```

To ensure that labs are not broken when [PyPI](https://pypi.org/) updates library versions we ***strongly recommend*** pinning the version you wish to install:

```python
!pip install optuna==4.2.0
```

When installing packages from [PyPI](https://pypi.org/), a substantial amount of output can be generated. To hide this output from learners, you can use the `%%capture` magic command. Be aware that using `%%capture` might cause a cell to run for an extended period without producing output. In such cases, it is advisable to inform learners that the cell will take several minutes to execute:

```python
%%capture
!pip install optuna==4.2.0
```

After installing packages in JupyterLab, we recommend restarting your kernel and informing your learners to do the same. Please see [JupyterLab Best Practices](#jupyterlab-best-practices) for details.

#### Install using `conda` or `mamba`

Packages can be installed using `!conda`, `%conda`, `!mamba`, or `%mamba`. Since `mamba` is significantly faster than `conda`, it is ***strongly recommended*** to use `!mamba` or `%mamba`. Remember to use the `-y` option to automatically confirm all prompts. For example, to install matplotlib from the conda-forge channel, you can use the following command:

```python
!mamba install -c conda-forge -y matplotlib
```

To ensure that labs are not broken when library versions are updated on conda channels we ***strongly recommend*** pinning the version you wish to install:

```python
!mamba install -c conda-forge -y matplotlib==3.10.0
```

When installing packages using `conda` or `mamba`, a substantial amount of output can be generated. To hide this output from learners, you can use the `%%capture` magic command. Be aware that using `%%capture` might cause a cell to run for an extended period without producing output. In such cases, it is advisable to inform learners that the cell will take several minutes to execute:

```python
%%capture
!mamba install -c conda-forge -y matplotlib==3.10.0
```

After installing packages in JupyterLab, we recommend restarting your kernel and informing your learners to do the same. Please see [JupyterLab Best Practices](#jupyterlab-best-practices) for details.

### Downloading Data

JupyterLab has access to the internet, meaning that you can source datasets from online sources. For instance, `.csv` files can be downloaded and loaded as `pandas` dataframes using:

```python
import pandas as pd
URL = 'https://www.url.to/my/dataset.csv'
df = pd.read_csv(URL)
```

Moreover, with JupyterLab you have access to wget with `!wget` and curl with `!curl`. For instance, the following downloads and loads a dataset from Kaggle:

```python
!curl -L -o netflix-shows.zip\
  https://www.kaggle.com/api/v1/datasets/download/shivamb/netflix-shows
import zipfile
import pandas as pd
archive = zipfile.ZipFile('netflix-shows.zip', 'r')
df = pd.read_csv(archive.open('netflix_titles.csv'))
df.sample(5)
```

Relying on online sources carries the risk of labs becoming non-functional if those sources are moved or become unavailable. Therefore, we **strongly recommend** transferring these data sources to the Skills Network File Library before using them in your labs. To upload files to the Skills Network File Library, follow the steps provided in [Skills Network File Library -  Access File Library within Jupyterlite or Jupyterlab](/docs/labs/features/file-library#access-file-library-within-jupyterlite-or-jupyterlab).

### JupyterLab Best Practices

Follow these best practices when creating JupyterLab labs:

- Pin python package versions when installing from [PyPI](https://pypi.org/). For instance, instead of using `!pip install numpy`, use `!pip install numpy==2.2.1`
- Pin python package versions when installing using `conda` or `mamba`. For instance, instead of using `!mamba install -c conda-forge -y matplotlib`, use `!mamba install -c conda-forge -y matplotlib==3.10.0`
- Ask learners to restart their kernel between installing Python libraries and importing them. There are several ways that this can be accomplished. You can include a code cell that, when run, restarts the kernel:
```python
import os
os._exit(00)
```
And, as a workaround in case the above code fails to restart the kernel for a learner, you can include the following image in a markdown cell that asks the learner to click the kernel restart button:
![An image that shows the location of the jupyterlab restart kernel button](/img/labs/restart-jupyterlab-kernel.png)

## JupyterLab Caveats and Workarounds

<!-- | Issue | Solution |
|---|---|
| `pyspark` fails with JVM error | Find apache spark installation using `findspark`: \
```
pip install pyspark
from pyspark import SparkContext, SparkConf
from pyspark.sql import SparkSession
sc = SparkContext()
``` |
| Responsive UI | Less Responsive UI | -->


<table>
<tr>
<td> Issue </td> <td> Solution </td>
</tr>
<tr>
<td> The <code>pyspark</code> library fails with JVM error </td>
<td>

In JupyterLab Classic, Use <code>findspark</code>:

```python
!pip install pyspark==3.4.4
!pip install findspark==2.0.1
```

```python
import findspark
findspark.init()
```

```python
from pyspark import SparkContext, SparkConf
from pyspark.sql import SparkSession
```

```python
# Creating a spark context class
sc = SparkContext()

# Creating a spark session
spark = SparkSession \
    .builder \
    .appName("Python Spark DataFrames basic example") \
    .config("spark.some.config.option", "some-value") \
    .getOrCreate()
```

Should run with no errors.

</td>
</tr>
</table>

## Convert from JupyterLab to JupyterLite

You can easily convert from JupyterLab to JupyterLite by following [Convert JupyterLab to JupyterLite](/docs/labs/tools/jupyterlab/convert-to-jupyterlite).

## Convert from JupyterLite to JupyterLab

You can easily convert from JupyterLite to JupyterLab by following [Convert JupyterLite to JupyterLab](/docs/labs/tools/jupyterlite/convert-to-jupyterlab).
