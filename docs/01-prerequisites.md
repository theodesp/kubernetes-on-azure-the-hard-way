# Prerequisites

## Azure Cloud Platform

This tutorial leverages the [Azure Cloud Platform](https://azure.microsoft.com/en-us/) to streamline provisioning of the compute infrastructure required to bootstrap a Kubernetes cluster from the ground up. [Sign up](https://azure.microsoft.com/en-in/account/) for $170 in free credits.

<!-- [Estimated cost](https://cloud.google.com/products/calculator/#id=78df6ced-9c50-48f8-a670-bc5003f2ddaa) to run this tutorial: $0.22 per hour ($5.39 per day). -->

> The compute resources required for this tutorial exceed the Azure Cloud Platform free tier.

## Azure Cloud Platform CLI

### Install the Azure Cloud CLI

Follow the Azure CLI [documentation](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) to install and configure the `az` command line utility.

Verify the Azure Cloud CLI version is 2.0.67 or higher:

```
az --version
```

### Authenticate

Before you do anything with the Azure service you need to authenticate first.

```
az login
```

Follow the login instructions in the browser that opens after you run the above command.

### Set a Default Location and Resource Group

This tutorial assumes a default compute Location and Resource Group have been configured.

If you are using the `az` command-line tool for the first time `configure --defaults` is the easiest way to do this:

```
az configure --defaults
```

For example set a default location:

```
az configure --defaults location=northeurope
```

Set a default resource group:

```
az configure --defaults group=K8sTheHardWay
```

> Use the `az group list` command to view all resource groups.

If you don't have a resource group ready you can create one using the following command:

```
az group create --name=K8sTheHardWay
```

## Running Commands in Parallel with tmux

[tmux](https://github.com/tmux/tmux/wiki) can be used to run commands on multiple compute instances at the same time. Labs in this tutorial may require running the same commands across multiple compute instances, in those cases consider using tmux and splitting a window into multiple panes with `synchronize-panes` enabled to speed up the provisioning process.

> The use of tmux is optional and not required to complete this tutorial.

![tmux screenshot](images/tmux-screenshot.png)

> Enable `synchronize-panes`: `ctrl+b` then `shift :`. Then type `set synchronize-panes on` at the prompt. To disable synchronization: `set synchronize-panes off`.

Next: [Installing the Client Tools](02-client-tools.md)