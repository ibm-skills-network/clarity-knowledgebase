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
| 90% Libraries Compadible | 99% Libraries Compadible |
| Good Runtime Performance | Best Runtime Performance |

## When should you use JupyterLite?

In general, we recommend authors use jupyterlite:
 - __For the learner's best experience__
 - All libraries used are compadible
   - See [JupyterLite - Unsupported Libraries](./jupyterlite#unsupported-libraries) for additional info
 - Low-medium rumtime code cells

See [JupyterLite - Should you use JupyterLite?](./jupyterlite#should-you-use-jupyterlite) for additional info

## When should you use JupyterLab?

We recommend authors use jupyterlab:
 - Required libraries are incompadible with JupyterLite
 - CPU-intensive cells take too long in JupyterLite

See [JupyterLab](./jupyterlab) for additional info