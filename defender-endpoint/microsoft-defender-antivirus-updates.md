---
title: Microsoft Defender Antivirus security intelligence and product updates
description: Manage how Microsoft Defender Antivirus receives protection and product updates.
ms.service: defender-endpoint
ms.localizationpriority: high
ms.date: 08/08/2024
audience: ITPro
ms.topic: reference
author: siosulli
ms.author: siosulli
ms.custom: nextgen
ms.reviewer: pahuijbr, tudobril, yongrhee
manager: deniseb
ms.subservice: ngp
ms.collection: 
- m365-security
- tier2
- mde-ngp
search.appverid: met150
---

# Microsoft Defender Antivirus security intelligence and product updates

**Applies to:**

- [Microsoft Defender for Endpoint Plans 1 and 2](microsoft-defender-endpoint.md)
- Microsoft Defender Antivirus

**Platforms**

- Windows

Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques. Update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md). This article includes information about the two types of updates for keeping Microsoft Defender Antivirus current:

- [Security intelligence updates](#security-intelligence-updates)
- [Product updates](#product-updates)

This article also includes:

- [Microsoft Defender Antivirus platform support](#microsoft-defender-antivirus-platform-and-engine-support)
- [How to roll back an update](#how-to-roll-back-an-update) (if necessary)
- [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)
- [Updates for Deployment Image Servicing and Management (DISM)](#updates-for-deployment-image-servicing-and-management-dism)

To see the most current engine, platform, and signature date, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

[!INCLUDE [MDE automated setup guide](../includes/security-analyzer-setup-guide.md)]

## Security intelligence updates

Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the *Microsoft Advanced Protection Service*, or MAPS) and periodically downloads dynamic security intelligence updates to provide more protection. These dynamic updates don't take the place of regular security intelligence updates via security intelligence update KB2267602.

> [!NOTE]
> Updates are released under the following KBs:
>
> - Microsoft Defender Antivirus: KB2267602
> - System Center Endpoint Protection: KB2461484

Cloud-delivered protection is always on and requires an active connection to the Internet to function. Security intelligence updates occur on a scheduled cadence (configurable via policy). For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).

For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

Engine updates are included with security intelligence updates and are released on a monthly cadence.

## Product updates

Microsoft Defender Antivirus requires monthly updates (KB4052623) known as *platform updates*.

You can manage the distribution of updates through one of the following methods:

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- The usual methods you use to deploy Microsoft and Windows updates to endpoints in your network.

For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

### Important points about product updates

- Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).

- This article lists changes that are included in the broad release channel. [See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).

- To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).

- To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

- If you're looking for a list of Microsoft Defender processes, see the spreadsheet provided at [Enable access to Microsoft Defender for Endpoint service URLs in the proxy server](configure-environment.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). The sheet also lists the services and their associated URLs that your network must be able to connect to.

- Platform updates can be temporarily postponed if other protection features, such as [Endpoint DLP](/Microsoft-365/compliance/endpoint-dlp-getting-started) or [Device Control](device-control-report.md) are actively monitoring running processes. Platform updates are retried after a reboot or when all monitored services are stopped.

- In the **Microsoft Endpoint Configuration Manager / Windows Server Update Services** (MECM/WSUS) catalog, the _category_ **Microsoft Defender for Endpoint** includes updates for the MSSense service in [KB5005292](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5005292). KB5005292 includes updates and fixes to the Microsoft Defender for Endpoint **endpoint detection and response** (EDR) sensor. For more information, see [Microsoft Defender for Endpoint update for EDR Sensor](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) and [What's new in Microsoft Defender for Endpoint on Windows](windows-whatsnew.md).

## Monthly platform and engine versions

All our updates contain:

- Performance improvements
- Serviceability improvements
- Integration improvements (Cloud, [Microsoft Defender XDR](/defender-xdr/microsoft-365-defender))

### July-2024 (Platform: 4.18.24070.5 | Engine: 1.1.24070.3)

- Security intelligence update version: **1.417.14.0**
- Release date: **August 7, 2024** (Engine and Platform)
- Platform: **4.18.24070.5**
- Engine: **1.1.24070.3**
- Support phase: **Security and Critical Updates**

### What's new

- False positive detections are no longer reported as `ThreatNotFound` in the Microsoft Defender portal. 
- Optimized Network Protection calls to the backend that occur as a result of suspicious connection checks.
- Fixed the [PerformanceModeStatus](/windows/client-management/mdm/defender-csp#configurationperformancemodestatus) configuration key in Defender CSP so changing this value in the console takes effect on the endpoint. 
- Resolved an issue where File Evidence Location was not always captured in scenarios where the Remote Location is inaccessible. 
- New event log added (5016) to report Microsoft Defender Antivirus self-healed when a deadlock is detected during shutdown. 
- Fixed a prioritization issue with full scans initiated from the portal that resulted in longer than expected full scan duration.

### June-2024 (Platform: 4.18.24060.7 | Engine: 1.1.24060.5)

- Security intelligence update version: **1.415.1.0**
- Release date: **July 9, 2024** (Engine) / **July 15, 2024** (Platform)
- Platform: **4.18.24060.7**
- Engine: **1.1.24060.5**
- Support phase: **Security and Critical Updates**

### What's new

- Fixed issue where Microsoft Defender Antivirus was not properly changing state when non-Microsoft antivirus/antimalware software was installed and [Windows Defender Application Control](/windows/security/application-security/application-control/windows-defender-application-control/wdac) (WDAC) with [Intelligent Security Graph](/windows/security/application-security/application-control/windows-defender-application-control/design/use-wdac-with-intelligent-security-graph) were enabled.
- Fixed deadlock issue on [VDI](deployment-vdi-microsoft-defender-antivirus.md) that occurred when loading corrupted update files from UNC share.
- Custom scans started with [Start-MpScan](/powershell/module/defender/start-mpscan) are now reported in the event log.
- Fixed potential deadlock that occurred on volume mount scanning.
- Fixed issue where Microsoft Defender Antivirus did not allow applications to clean up temporary files.
- Fixed potentially packet loss due to [network protection](network-protection.md) shutdown that could lead to deadlock.
- Implemented performance improvements for scenarios where WDAC is enabled with Intelligent Security Graph.
- Fixed an issue where an Outlook exclusion for the ASR rule [Block Office applications from injecting code into other processes](/defender-endpoint/attack-surface-reduction-rules-reference#block-office-applications-from-injecting-code-into-other-processes) was not honored.
- Fixed a race condition during the startup of [endpoint data loss prevention](/purview/endpoint-dlp-getting-started) such that, in certain environments, some system files could be corrupted.

### May-2024 (Engine: 1.1.24050.5 | Platform: 4.18.24050.7)

- Security intelligence update version: **1.413.1.0**
- Release date: **May 30, 2024** (Engine) / **June 4, 2024** (Platform)
- Engine: **1.1.24050.5**
- Platform: **4.18.24050.7**
- Support phase: **Security and Critical Updates**

#### What's new

- Improved performance when running configuration queries.
- Optimized how scans are prioritized.
- Fixed a crash caused by a race condition with a device control driver.
- Added Event Viewer Logging for scan start event where the scan originates from PowerShell.

### Previous version updates: Technical upgrade support only

After a new package version is released, support for the previous two versions is reduced to technical support only. For more information about previous versions, see [Microsoft Defender Antivirus updates: Previous versions for technical upgrade support](msda-updates-previous-versions-technical-upgrade-support.md).

## Microsoft Defender Antivirus platform and engine support

Platform and engine updates are provided on a monthly cadence. To be fully supported, keep current with the latest platform and engine updates. Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform and engine version:

- **Security and Critical Updates servicing phase** - When running the latest platform and engine version, you're eligible to receive both Security and Critical updates to the anti-malware platform.

- **Technical Support (Only) phase** - After a new platform and engine version is released, support for older versions (N-2) reduce to [technical support only](msda-updates-previous-versions-technical-upgrade-support.md). Platform and engine versions older than N-2 are no longer supported. Technical support continues to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.

During the technical support (only) phase, commercially reasonable support incidents are provided through Microsoft Customer Service & Support and Microsoft's managed support offerings (such as Premier Support). If a support incident requires escalation to development for further guidance, requires a nonsecurity update, or requires a security update, customers are asked to upgrade to the latest platform version or an intermediate update (*).

> [!NOTE]
> If you are manually deploying Microsoft Defender Antivirus Platform Update, or if you are using a script or a non-Microsoft management product to deploy Microsoft Defender Antivirus Platform Update, make sure that version `4.18.2001.10` is installed from the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=4.18.2001.10) before the latest version of Platform Update (N-2) is installed.

## How to roll back an update

In the unfortunate event that you encounter issues after a platform update, you can roll back to the previous or the inbox version of the Microsoft Defender platform.  

- To roll back to the previous version, run the following command:

   `"%programdata%\Microsoft\Windows Defender\Platform\<version>\MpCmdRun.exe" -RevertPlatform`

- To roll back this update to the version shipped with the Operating System ("%ProgramFiles%\Windows Defender")

   `"%programdata%\Microsoft\Windows Defender\Platform\<version>\MpCmdRun.exe" -ResetPlatform`

## Platform version included with Windows 10 releases

The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:

|Windows 10 release  |Platform version  |Engine version |Support phase |
|:---|:---|:---|:---|
|2004  (20H1/20H2) | `4.18.1909.6` | `1.1.17000.2` | Technical upgrade support (only) |
|1909  (19H2) |`4.18.1902.5` |`1.1.16700.3` | Technical upgrade support (only) |
|1903  (19H1) |`4.18.1902.5` |`1.1.15600.4` | Technical upgrade support (only) |
|1809  (RS5) |`4.18.1807.5` |`1.1.15000.2` | Technical upgrade support (only) |
|1803  (RS4) |`4.13.17134.1` |`1.1.14600.4` | Technical upgrade support (only) |
|1709  (RS3) |`4.12.16299.15` |`1.1.14104.0` | Technical upgrade support (only) |
|1703  (RS2) |`4.11.15603.2` |`1.1.13504.0` | Technical upgrade support (only) |
|1607 (RS1) |`4.10.14393.3683` |`1.1.12805.0` | Technical upgrade support (only) |

For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).
  
> [!NOTE]  
> Windows Server 2016 ships with the same Platform version as RS1 and falls under the same support phase: Technical upgrade support (only)  
> Windows Server 2019 ships with the same Platform version as RS5 and falls under the same support phase: Technical upgrade support (only)  

## Updates for Deployment Image Servicing and Management (DISM)

To avoid a gap in protection, keep your OS installation images up to date with the latest antivirus and antimalware updates. Updates are available for:

- Windows 10 and 11 (Enterprise, Pro, and Home editions)
- Windows Server 2022, Windows Server 2019, Windows Server 2016, and Windows Server 2012 R2
- WIM and VHD(x) files 

Updates are released for x86, x64, and ARM64 Windows architecture.

For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

After a new package version is released, support for the previous two versions is reduced to technical support only.

### 1.415.235.0

- Defender package version: `1.415.235.0`
- Security intelligence version: `1.415.235.0`
- Engine version: `1.24070.1`
- Platform version: `4.18.24070.5`

#### Fixes

- None

#### Additional information

- None

### 1.411.111.0

- Defender package version: `1.411.111.0`
- Security intelligence version: `1.411.111.0`
- Engine version: `1.24050.2`
- Platform version: `4.18.24050.7`

#### Fixes

- None

#### Additional information

- None

### 1.411.9.0

- Defender package version: `1.411.9.0`
- Security intelligence version: `1.411.9.0`
- Engine version: `1.24040.1`
- Platform version: `4.18.24040.4`

#### Fixes

- None

#### Additional information

- None

## More resources

| Article | Description  |
|:---|:---|
|[Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Review antimalware update packages for your OS installation images (WIM and VHD files). Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, Windows Server 2022, Windows Server 2016, and Windows Server 2012 R2 installation images.  |
|[Manage how protection updates are downloaded and applied](manage-protection-updates-microsoft-defender-antivirus.md) | Protection updates can be delivered through many sources. |
|[Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) | You can schedule when protection updates should be downloaded. |
|[Manage updates for endpoints that are out of date](manage-outdated-endpoints-microsoft-defender-antivirus.md) | If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in. |
|[Manage event-based forced updates](manage-event-based-updates-microsoft-defender-antivirus.md) | You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events. |
|[Manage updates for mobile devices and virtual machines (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| You can specify settings, such as whether updates should occur on battery power that 's especially useful for mobile devices and virtual machines. |
| [Microsoft Defender for Endpoint update for EDR Sensor](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) | You can update the EDR sensor (MsSense.exe) that's included in the new Microsoft Defender for Endpoint unified solution package released in 2021.   |

> [!TIP]
> If you're looking for Antivirus related information for other platforms, see:
> - [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md)
> - [Microsoft Defender for Endpoint on Mac](microsoft-defender-endpoint-mac.md)
> - [macOS Antivirus policy settings for Microsoft Defender Antivirus for Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [Configure Defender for Endpoint on Android features](android-configure.md)
> - [Configure Microsoft Defender for Endpoint on iOS features](ios-configure-features.md)


[!INCLUDE [Microsoft Defender for Endpoint Tech Community](../includes/defender-mde-techcommunity.md)]
