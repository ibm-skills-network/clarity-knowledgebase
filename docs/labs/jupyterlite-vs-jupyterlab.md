---
sidebar_position: 5
---

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
   - See [JupyterLite - Unsupported Libraries](./jupyterlite#unsupported-libraries).
 - Only low-medium rumtime code cells.
   - See [JupyterLite - Additional Caveats](./jupyterlite#additional-caveats).

## When should you use JupyterLab?

We recommend authors use JupyterLab:
 - Required libraries are incompatible with JupyterLite.
 - CPU-intensive cells take too long in JupyterLite.
