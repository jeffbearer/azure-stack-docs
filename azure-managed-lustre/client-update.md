---
title: Update client software for Azure Managed Lustre
description: Tutorial that describes how to update client software for the Azure Managed Lustre File System.
ms.topic: tutorial
author: pauljewellmsft
ms.author: pauljewell
ms.lastreviewed: 06/30/2023
ms.reviewer: dsundarraj
ms.date: 06/30/2023
zone_pivot_groups: select-os

# Intent: As an IT Pro, I want to update the Azure Managed Lustre client software.
# Keyword: lustre

---

# Updating a Client running the Azure Managed Lustre software

This article describes how to update Linux clients that are already being used as Azure Managed Lustre clients. See [Connect clients to an Azure Managed Lustre file system](connect-clients) for information on installing the client software.

## Prerequisites

- Existing Azure Managed Lustre Clients that have available updates.

## Upgrade Considerations

The prebuilt Lustre Client software packages are compiled for specific kernel versions.  Before switching to a new Linux kernel update you should ensure that the corresponding Lustre client kernel module is available on packages.microsoft.com

Loaded Lustre kernel modules can obfuscate the upgrade process.  It's relatively easy for the wrong version of a kernel module loaded to be a source of problems when updating the client software.  To simplify this potential problem the following update process uses steps to completely remove the old client prior to installing the new client.

## Update procedure

### Unmount Lustre

Determine the mount path of the Lustre file system and issue a command to unmount the file system.

```bash
sudo umount /mnt/lustrefs
```

### Unload Lustre kernel modules

Lustre 

```bash
sudo lustre_rmmod
```

Review the loaded modules and if the lustre module is still listed issue another remove command.

```bash
sudo lsmod
```


### Uninstall Lustre client packages

::: zone pivot="rhel"

```bash
dnf remove 
```

::: zone pivot="ubuntu"

```bash
apt remove
```

### Install Linux updates

::: zone pivot="rhel"
sudo dnf update && sudo dnf -y upgrade

::: zone pivot="ubuntu"


### Reboot virtual machine

```bash 
sudo reboot
```

### Install Azure Managed Lustere client

::: zone pivot="rhel"

```bash
sudo dnf install
```

::: zone pivot="ubuntu"

```bash
sudo apt install
```

### Mount Lustre

```bash
sudo mount /mnt/lustrefs
```















# Install prebuilt client software

This tutorial shows how to install an appropriate client package, in order to set up client VMs and attach them to an Azure Managed Lustre cluster. Select an OS version to see the instructions.

::: zone pivot="alma-86"
## Tutorial: Install client software for AlmaLinux HPC 8.6

This tutorial shows how to install the client package to set up client VMs running AlmaLinux HPC 8.6, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* AlmaLinux HPC 8.6

In this tutorial you will:

> [!div class="checklist"]
> * Download a prebuilt client
> * Install the prebuilt client

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-hpc-alma-86](includes/client-install-hpc-alma-86.md)]
:::zone-end

::: zone pivot="rhel-7,centos-7"
## Tutorial: Install client software for Red Hat Enterprise Linux or CentOS 7

This tutorial shows how to install the client package to set up client VMs running RHEL 7 and CentOS 7, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* Red Hat Enterprise Linux 7 (RHEL 7)
* CentOS Linux 7

In this tutorial you will:

> [!div class="checklist"]
> * Download a prebuilt client
> * Install the prebuilt client

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-rhel-7](includes/client-install-rhel-7.md)]
::: zone-end

::: zone pivot="rhel-8,centos-8,alma-8"
## Tutorial: Install client software for Red Hat Enterprise Linux, CentOS Linux, or AlmaLinux 8

This tutorial shows how to install the client package to set up client VMs running RHEL 8, CentOS 8, and Alma 8, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* Red Hat Enterprise Linux 8 (RHEL 8)
* CentOS Linux 8
* Alma Linux 8

In this tutorial you will:

> [!div class="checklist"]
> * download a pre-built client
> * install the pre-built client

> [!NOTE]
> For AlmaLinux 8.6 HPC Marketplace images, see the separate [Alma 8.6 HPC install instructions](install-hpc-alma-86.md)

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-rhel-8](includes/client-install-rhel-8.md)]
::: zone-end

::: zone pivot="rhel-9"
## Tutorial: Install client software for Red Hat Enterprise Linux 9

This tutorial shows how to install the client package to set up client VMs running RHEL 9, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* Red Hat Enterprise Linux 9 (RHEL 9)

In this tutorial you will:

> [!div class="checklist"]
> * Download a prebuilt client
> * Install the prebuilt client

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-rhel-9](includes/client-install-rhel-9.md)]
::: zone-end


::: zone pivot="ubuntu-18"
## Tutorial: Install client software for Ubuntu 18.04

This tutorial shows how to install the client package to set up client VMs running Ubuntu 18.04, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* Ubuntu 18.04

In this tutorial you will:

> [!div class="checklist"]
> * download a pre-built client
> * install the pre-built client

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-rhel-8](includes/client-install-ubuntu-18.md)]
::: zone-end

::: zone pivot="ubuntu-20"
## Tutorial: Install client software for Ubuntu 20.04

This tutorial shows how to install the client package to set up client VMs running Ubuntu 20.04, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* Ubuntu 20.04

In this tutorial you will:

> [!div class="checklist"]
> * download a pre-built client
> * install the pre-built client

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-ubuntu-20](includes/client-install-ubuntu-20.md)]
::: zone-end

::: zone pivot="ubuntu-22"
## Tutorial: Install client software for Ubuntu 22.04

This tutorial shows how to install the client package to set up client VMs running Ubuntu 22.04, and attach them to an Azure Managed Lustre cluster.

For client VMs running:

* Ubuntu 22.04

In this tutorial you will:

> [!div class="checklist"]
> * download a pre-built client
> * install the pre-built client

For more information, see [Connect clients to an Azure Managed Lustre file system](connect-clients.md), including:

* [Client prerequisites and supported operating systems](connect-clients.md#client-prerequisites)
* [Installing on a client with existing Lustre client software](connect-clients.md#update-a-lustre-client-to-the-current-version)
* [Mount command](connect-clients.md#mount-command)

### Download and install prebuilt client software

[!INCLUDE [client-install-ubuntu-22](includes/client-install-ubuntu-22.md)]
::: zone-end

## Next steps

* [How to connect clients to the file system](connect-clients.md)
* [Azure Managed Lustre File System overview](amlfs-overview.md)
