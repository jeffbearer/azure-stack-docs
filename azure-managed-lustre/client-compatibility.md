---
title: Client compatibility Azure Managed Lustre
description: Document that describes the latest Linux client compatibility with Lustre.
ms.topic: tutorial
author: pauljewellmsft
ms.author: pauljewell
ms.lastreviewed: 06/30/2023
ms.reviewer: dsundarraj
ms.date: 06/30/2023
zone_pivot_groups: select-os

# Intent: The document provides detailed information about the compatibility of Lustre client software with various Linux distributions and kernels.
# Keyword: lustre

---
# Client Compatibility

This document explores the compatibility of Lustre client software with various Linux kernel versions and popular Linux distributions. For more information on using Azure Managed Lustre with the clients provided by Microsoft, see [Azure Managed Lustre Overview](amlfs-overview.md) or [Lustre Client Install for Azure Managed Lustre](client-install.md).

The Lustre software integrates tightly into the Linux kernel. It's not unusual for the upstream Lustre code to require changes to support new Linux kernels or distributions.

Moreover, the upstream Lustre community supports the Lustre client on a limited set of Linux distributions. Refer to the [Lustre Compatibility Matrix](https://wiki.whamcloud.com/display/PUB/Lustre+Support+Matrix).

Support for new Linux distributions or kernels in the Lustre client will always lag the releases from Linux distribution vendors.

Another consideration is the compatibility of the Azure Managed Lustre Client with the Azure Managed Lustre service. Azure Managed Lustre may not support the latest Lustre client version due to compatibility concerns with the service.

If you are running the latest Ubuntu Long Term Support (LTS) client, you also need to consider the kernel stream that you are using. Ubuntu has the LTS kernel stream (different from the LTS of a distribution) and the Hardware Enablement (HWE) kernel. The Azure Ubuntu 20.04 image defaults to the HWE kernel, which changes every 6 months and may not get a Lustre release that supports it before its end of life. Our [installation directions](client-install) suggest users switch to the LTS kernel stream, which uses the same kernel version for years.

## Microsoft-Provided Client Software

Microsoft offers prebuilt client software on packages.microsoft.com for the following popular Linux distributions:

- Red Hat Enterprise Linux (RHEL) Versions: 7, 8, 9
- Ubuntu Linux: 18.04 LTS, 20.04 LTS, 22.04 LTS
- Alma Linux: 7, 8, 9

Although Lustre supports SUSE Linux Enterprise Server, Microsoft does not provide packages for it at this time.

The Microsoft provided clients are for the x64 platform.  There are not plans to support the arm64 platform at this time.

Microsoft has no plans to support Linux distributions beyond those already supported by the Lustre community.

See the [Azure Managed Lustre Client Install Guide](client-install.md) for more information.

### Recent Azure Managed Lustre Client Releases

> [!TIP]
> Azure Managed Lustre recommends all customers upgrade to the most recent 2.15.4 client packages.

#### Azure Managed Lustre Client 2.15.4_42_gd6d405d

Version 2.15.4 adds support for RHEL 8.9 and 9.3.  See the [Lustre 2.15.4 Changelog](https://wiki.lustre.org/Lustre_2.15.4_Changelog) for more details.  

This following Linux Distribution versions are supported:

- RHEL 8 up to 8.9
- RHEL 9 up to 9.3
- Ubuntu 22.04 (Linux 5.15 LTS Kernel)
- Ubuntu 20.04
- Ubuntu 18.04

#### Azure Managed Lustre Client 2.15.3-43-gd7e07df

Version 2.15.3 added support for RHEL 8.8, 9.2. See the [Lustre 2.15.3 Changelog](https://wiki.lustre.org/Lustre_2.15.3_Changelog) for more details.

This version supports the following Linux distributions:

- RHEL 8 up to 8.8
- RHEL 9 up to 9.2
- Ubuntu 22.04 (Linux 5.15 LTS Kernel)
- Ubuntu 20.04
- Ubuntu 18.04

#### Older Lustre Client Versions

> [!IMPORTANT]
> Versions prior to 2.15.3 are not recommended and should be updated to the latest Lustre client packages.

### Upcoming Linux Releases

#### Ubuntu 24.04 LTS

Ubuntu 24.04, expected in April, will come with the Linux 6.8 kernel. An Azure Managed Lustre client will be available once the Upstream Lustre Community releases a version that supports this distribution.

#### Red Hat Enterprise Linux 9.4 and 8.10

These releases are anticipated in mid-2024. They may or may not require upstream changes. An assessment of compatibility will be made once they become available.

#### Red Hat Enterprise Linux 10

RHEL 10 is expected towards the end of 2024 or early 2025. An Azure Managed Lustre client will be available once the Upstream Lustre Community releases a version that supports this distribution.

## Bring Your Own Lustre Client

Customers who wish to compile their own Lustre Clients for use with Azure Managed Lustre are welcome to do so. Follow the [Lustre support matrix](https://wiki.whamcloud.com/display/PUB/Lustre+Support+Matrix) to ensure that your client is compatible with the version of Lustre provided by Azure Managed Lustre.
