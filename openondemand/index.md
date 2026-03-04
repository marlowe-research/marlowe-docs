---
layout: docs
doc_title: Open OnDemand
permalink: /documentation/openondemand/
---

Marlowe has an Open OnDemand instance available at [https://ood.marlowe.stanford.edu](https://ood.marlowe.stanford.edu)

There are currently two interactive apps available for use on the Marlowe Open OnDemand instance: Jupyter Lab, and Code Server.

## Jupyter Lab

From the official [Jupyter Lab website](https://jupyterlab.readthedocs.io/en/latest/): **JupyterLab is a highly extensible, feature-rich notebook authoring application and editing environment**

If you need to run a Jupyter Notebook, you can allocate resources and run them remotely through the Marlowe Open OnDemand instance.

## Code Server

Code Server is a tool to allow you to run VSCode on a remote server.

As Marlowe does not allow SSH port forwarding on compute nodes, accessing Code Server via Open OnDemand is the only way to run Code Server on Marlowe (see the [SLURM page]({{ '/documentation/slurm/' | relative_url }}) for more details).

**Note on GitHub Copilot**: As GitHub Copilot uses the `VSIXPackage` format instead of `VSIX`, code-server does not support directly installing it through the extension tab. However, you can still manually install the VSIXPackage file through the user interface. Any extension that doesn't use the `VSIXPackage` format will install correctly from the extension tab.

## Running Apps

To run an app on Open OnDemand, click the `Interactive Apps` button at the top and choose your specific application:

![interactive apps]({{ '/assets/images/docs/marlowe-ood-int-apps.png' | relative_url }})

After that, you will see a submit form similar to this:

![submit form]({{ '/assets/images/docs/marlowe-ood-submit-form.png' | relative_url }})

Once your job has been submitted and resources have been allocated, you will be presented with this screen:

![sessions screen]({{ '/assets/images/docs/marlowe-ood-sessions.png' | relative_url }})

Click "Connect" and your app instance will be launched automatically.
