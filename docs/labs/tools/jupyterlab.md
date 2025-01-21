# JupyterLab

Jupyterlab is a fully-featured python notebook environment.

We provide it to authors when [JupyterLite](./jupyterlite) has insufficient compatibility.

## Should you use JupyterLab?

We recommend you only use JupyterLab for your labs when necessary. If possible, we recommend you use JupyterLite instead.

For more information on why JupyterLite is preferred over JupyterLab see [JupyterLite vs JupyterLab](./jupyterlite-vs-jupyterlab).

### JupyterLab Caveats

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

Use <code>findspark</code>:

```python
!pip install pyspark
!pip install findspark
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
