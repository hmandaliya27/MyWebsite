---
title: "Network Breach"
description: "Managing a Network Breach and Data Migration"
draft: false
dateString: December 2023
showToc: true
weight: 302
cover:
    image: "projects/breach/networkbreach.jpg"
--- 


# Effective Leadership in Cybersecurity: Managing a Network Breach and Data Migration
In the ever-evolving landscape of cyber threats, a network breach poses significant challenges. Here, we delve into a case study where a team of employees and contractors successfully navigated a department-wide network breach. The process involved the organisation of wiping and re-imaging 500 laptops and 120 desktops, and migrating over 10TB of user data from local storage to OneDrive in compliance with NHS data and security protocols.

![](/projects/breach/chart.jpg)

### Leading the Team Through the Network Breach
Immediate Response and Coordination
Upon discovering the network breach, swift action was paramount. The team was promptly mobilised, and responsibilities were clearly defined to ensure an organised and efficient response. The primary objective was to mitigate the breach, secure the network, and restore normal operations as quickly as possible.

### Wiping and Re-imaging Devices
To prevent further compromise, 500 laptops and 120 desktops were systematically wiped and re-imaged. This process involved ensuring all critical data was securely backed up, using secure methods to completely wipe the existing data, re-imaging the devices with clean, updated operating systems, and conducting thorough checks to ensure all devices were free of malware and functioning correctly post-re-image. **BitRaser** was utilised for data erasure, adhering to the **British HMG IS5 (Enhanced)** Data Erasure Standards, ensuring complete and secure removal of data. 

![](/projects/breach/bitraser.jpg)

### Migrating Data to OneDrive
Compliance with NHS Data and Security Protocols
The migration of over 10TB of user data to OneDrive was a critical step in enhancing data security and accessibility. This process adhered strictly to NHS data and security protocols to ensure compliance and protect sensitive information.

### Detailed Migration Process
The migration process began with assessing and categorising the data to determine the appropriate migration strategy. Next, the team ensured all data was appropriately formatted and ready for transfer. Using OneDrive's migration tools, the data was securely transferred from local storage to the cloud. Post-migration checks were conducted to ensure data integrity and accessibility.

### USB Hard Drive Data Scanning
Dedicated Scanning and Uploading Stations
The team established two sets of scanning computers and two dedicated uploading computers to handle external hard drive data scanning and uploading efficiently.

### Comprehensive Scan Process
The scanning process began by connecting the external hard drive to the first scanning computer, where the root username folder was scanned with Microsoft Defender. After confirming no errors, the drive was moved to the second scanning computer for a Sophos scan. Upon completion and confirmation of no errors, the drive was connected to the Malwarebytes scanning computer. The Malwarebytes app was opened, the 'Scanner' icon clicked, then 'Advanced Scanners', 'Configure Scan', and the external drive (usually D:) was selected for the scan.

### Data Upload to Target Share
> Secure Data Transfer with TeraCopy.

Upon completion of the scanning process, the external drive was connected to a dedicated managed laptop for uploading data to the network share. TeraCopy was utilised to transfer the data and verify its integrity. The external drive was connected to the managed laptop, and TeraCopy was used to transfer data to the network share, ensuring data integrity through TeraCopy’s built-in verification. Successfully transferred data was then moved into the organisation’s OneDrive.

# Conclusion
Effective leadership and a structured approach were crucial in managing this network breach and ensuring a seamless data migration. By adhering to stringent security protocols and utilising robust scanning and transfer tools, the team safeguarded data integrity and restored operational stability. This case study underscores the importance of preparedness, coordination, and compliance in mitigating the impact of cyber threats.






