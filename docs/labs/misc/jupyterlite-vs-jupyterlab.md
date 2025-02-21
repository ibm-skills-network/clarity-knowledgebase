# JupyterLite vs JupyterLab

This page explains the differences between JupyterLite and JupyterLab - and which environment would be right for you.

## High Level

| JupyterLite | JupyterLab |
|---|---|
| Fast Startup Time | Slow Startup Time |
| Responsive UI | Less Responsive UI |
| 90% Libraries Compatible | 99% Libraries Compatible |
| Good Runtime Performance | Best Runtime Performance |

## When should you use JupyterLite?

In general, we recommend authors use JupyterLite:
 - __For the learner's best experience__
 - If all required libraries are compatible.
   - Check [JupyterLite - Supported Libraries](/docs/labs/tools/jupyterlite/overview#supported-libraries) and [JupyterLite - Unsupported or Partially Supported Libraries](/docs/labs/tools/jupyterlite/overview#unsupported-or-partially-supported-libraries) for details.
 - If you do not have highly cpu-intensive code.
   - Check [JupyterLite - Additional Caveats](/docs/labs/tools/jupyterlite/overview#additional-caveats) for details.
 - If you are not using large (>100MB+) datasets.
   - Check [JupyterLite - Additional Caveats](/docs/labs/tools/jupyterlite/overview#additional-caveats) for details.
 - If you are not using libraries that must connect to the internet to work.
   - Check [JupyterLite - Unsupported or Partially Supported Libraries](/docs/labs/tools/jupyterlite/overview#unsupported-or-partially-supported-libraries) for details and [JupyterLite - Downloading Data](/docs/labs/tools/jupyterlite/overview#downloading-data) for workarounds that might work for you.

## When should you use JupyterLab?

We recommend authors use JupyterLab:
 - Required libraries are incompatible with JupyterLite.
 - CPU-intensive cells take too long in JupyterLite.
