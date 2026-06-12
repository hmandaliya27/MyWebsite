---
title: "Building a NAS Server from a Dell SFF PC"
description: "Repurposing an old Dell Small Form Factor PC into a cost-effective home NAS server"
draft: false
dateString: Jun 2026
showToc: true
weight: 299
cover:
   image: "projects/nasserver/nas server.jpg"
---

# Overview

This project demonstrates how an old **Dell Small Form Factor (SFF)** desktop was transformed into a fully functional **Network Attached Storage (NAS)** server. Rather than purchasing an expensive NAS enclosure, existing hardware was repurposed to provide dedicated storage for files, media, and backups.

The objective was to create a low-cost storage solution using readily available hardware while extending the life of a system that would otherwise remain unused.


# Hardware Configuration

The NAS consists of three storage devices, each serving a dedicated purpose.

The storage configuration includes:

> **256GB NVMe SSD** – Debian Linux operating system

> **2TB HDD** – General data storage

> **2TB SATA SSD** – Media storage

Using separate drives for the operating system, media, and data helps keep storage organised while improving overall responsiveness.


# Installing Debian Linux

Debian Linux was selected as the operating system due to its stability, lightweight resource requirements, and extensive software support.

The operating system was installed on the NVMe SSD, providing fast boot times and responsive system performance. Once installed, the system was configured for storage services. Future remote support will be implemented using tailscale.

![](/projects/nasserver/satassdcaddy.png)
![](/projects/nasserver/dvd.png)


# Expanding Storage Capacity

One challenge encountered during the build was finding space for the additional 2TB SATA SSD.

The Dell SFF chassis did not provide a dedicated mounting location for another drive. To overcome this limitation, the DVD drive was removed and replaced with a SATA SSD caddy adapter (no additional cables were needed as the DVD SATA cables were reused). As optical drives are rarely used today, the DVD bay provided an ideal solution for adding additional storage without modifying the chassis.

![](/projects/nasserver/removingdvd.png)
![](/projects/nasserver/caddyinstall.png)


# Storage Configuration

Once all drives were installed, storage was organised according to its intended purpose.

The **2TB HDD** is used for general file storage and shared data across the network.

The **2TB SATA SSD** is dedicated to media content, allowing applications such as Plex to access media files quickly.

The **NVMe SSD** hosts the OpenMediaVault operating system and currently has additional capacity available. I've already setup the SSD to be used as additional storage but won't use it for now. In the future, unused space may be repurposed as a backup destination for important files and system snapshots.

![](/projects/nasserver/openmediavault.png)


# Network Shares

The NAS was configured to provide shared storage across the local network.

This allows files to be accessed centrally from multiple devices without relying on cloud services or external storage devices. Separating media and data storage also simplifies management and future expansion. In fact the plugin MiniDLNA, is used to share it across all platforms which include computer, phones, TV and consoles (as tested and worked).

![](/projects/nasserver/connection.png)


# Why Build Instead of Buy?

Dedicated NAS appliances can be expensive, particularly when storage drives are purchased separately.

By reusing existing hardware, the total cost of the project was significantly reduced while still providing:

> Centralised storage

> Media hosting

> Backup capabilities

> Upgrade flexibility

> Full control over the operating system and services

For many home users, a repurposed office PC provides more than enough performance for everyday NAS tasks. I can also turn it off when not in use to keep it more secure. Furthermore, I have setup magic packets so that I can turn on the server from my phone, rather then physically heading to turn on the power button.

![](/projects/nasserver/plex.png)

# Conclusion

This project demonstrates how a used Dell Small Form Factor PC can be repurposed into a capable NAS server using a combination of SSD and HDD storage. By installing Debian Linux on an NVMe SSD and utilising both a hard drive and SATA SSD for dedicated storage roles, the system provides a practical and cost-effective alternative to a dedicated NAS appliance.

From a home-lab perspective, the project highlights how older hardware can continue to provide value through self-hosted storage, media services, and future backup solutions while remaining significantly cheaper than purpose-built NAS hardware.

![](/projects/nasserver/nasoverview.png)
