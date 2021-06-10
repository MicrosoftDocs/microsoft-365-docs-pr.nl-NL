---
title: Microsoft Defender voor Eindpunt beheren met Configuration Manager
description: Meer informatie over het beheren van Microsoft Defender voor Eindpunt met Configuration Manager
keywords: post-migration, manage, operations, maintenance, utilization, Configuration Manager, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 71ad8f52fd9347abdf0146969bb84a19d8883262
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843057"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="8c686-104">Microsoft Defender voor eindpunt beheren met Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c686-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c686-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8c686-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c686-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8c686-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c686-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c686-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c686-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8c686-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c686-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8c686-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="8c686-110">We raden u aan [Microsoft Endpoint Manager](/mem)te gebruiken, waaronder [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) en [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) voor het beheren van de beveiligingsfuncties voor bedreigingen van uw organisatie voor apparaten (ook wel eindpunten genoemd).</span><span class="sxs-lookup"><span data-stu-id="8c686-110">We recommend using We recommend using [Microsoft Endpoint Manager](/mem), which includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="8c686-111">Meer informatie over Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8c686-111">Learn more about Endpoint Manager</span></span>](/mem/endpoint-manager-overview)
- [<span data-ttu-id="8c686-112">Co-manage Microsoft Defender for Endpoint op Windows 10 apparaten met Configuration Manager en Intune</span><span class="sxs-lookup"><span data-stu-id="8c686-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="8c686-113">Microsoft Defender voor eindpunt configureren met Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c686-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="8c686-114">Taak</span><span class="sxs-lookup"><span data-stu-id="8c686-114">Task</span></span>  |<span data-ttu-id="8c686-115">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="8c686-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="8c686-116">**Installeer de Configuration Manager-console** als u deze nog niet hebt</span><span class="sxs-lookup"><span data-stu-id="8c686-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="8c686-117">*Als u de configuratie-mangerconsole nog niet hebt, gebruikt u deze bronnen om de bits op te halen en te installeren.*</span><span class="sxs-lookup"><span data-stu-id="8c686-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="8c686-118">Het installatiemedia</span><span class="sxs-lookup"><span data-stu-id="8c686-118">Get the installation media</span></span>](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="8c686-119">Configuratiebeheer-console installeren</span><span class="sxs-lookup"><span data-stu-id="8c686-119">Install the Configuration Manager console</span></span>](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="8c686-120">**Configuration Manager gebruiken om apparaten aan te nemen** bij Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8c686-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="8c686-121">*Als u apparaten (of eindpunten) nog niet hebt aan boord van Microsoft Defender voor Eindpunt, kunt u dat doen met Configuration Manager.*</span><span class="sxs-lookup"><span data-stu-id="8c686-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="8c686-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c686-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="8c686-123">**Antimalware-beleid beheren en Windows firewallbeveiliging voor** clientcomputers (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="8c686-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="8c686-124">*Configureer endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span><span class="sxs-lookup"><span data-stu-id="8c686-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="8c686-125">Configuration Manager: Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="8c686-125">Configuration Manager: Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="8c686-126">**Methoden kiezen voor het bijwerken van antimalware-updates** op de apparaten van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="8c686-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="8c686-127">*Met Endpoint Protection in Configuration Manager kunt u kiezen uit verschillende methoden om antimalwaredefinities up-to-date te houden op de apparaten van uw organisatie.*</span><span class="sxs-lookup"><span data-stu-id="8c686-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="8c686-128">Definitie-updates configureren voor Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="8c686-128">Configure definition updates for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="8c686-129">Configuration Manager gebruiken om definitie-updates te leveren</span><span class="sxs-lookup"><span data-stu-id="8c686-129">Use Configuration Manager to deliver definition updates</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="8c686-130">**Netwerkbeveiliging inschakelen** om te voorkomen dat werknemers apps gebruiken die schadelijke inhoud op internet bevatten</span><span class="sxs-lookup"><span data-stu-id="8c686-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="8c686-131">*Het is raadzaam eerst [de auditmodus](/microsoft-365/security/defender-endpoint/evaluate-network-protection) te gebruiken voor netwerkbeveiliging in een testomgeving om te zien welke apps worden geblokkeerd voordat ze worden uitgerold.*</span><span class="sxs-lookup"><span data-stu-id="8c686-131">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="8c686-132">Netwerkbeveiliging in- en uit te zetten met Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c686-132">Turn on network protection with Configuration Manager</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="8c686-133">**Beheerde maptoegang configureren om** te beschermen tegen ransomware</span><span class="sxs-lookup"><span data-stu-id="8c686-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="8c686-134">*Gecontroleerde maptoegang wordt ook wel antiransomwarebeveiliging genoemd.*</span><span class="sxs-lookup"><span data-stu-id="8c686-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="8c686-135">Endpoint protection: Gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="8c686-135">Endpoint protection: Controlled folder access</span></span>](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="8c686-136">Gecontroleerde maptoegang inschakelen in Microsoft Endpoint Configuration Manage</span><span class="sxs-lookup"><span data-stu-id="8c686-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="8c686-137">Uw Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8c686-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="8c686-138">Als u dit nog niet hebt gedaan, configureert u uw **Microsoft Defender-beveiligingscentrum** ( ) om waarschuwingen weer te geven, functies voor bedreigingsbeveiliging te configureren en gedetailleerde informatie weer te geven over de algehele beveiligingsstatus van uw [https://securitycenter.windows.com](https://securitycenter.windows.com) organisatie.</span><span class="sxs-lookup"><span data-stu-id="8c686-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="8c686-139">U kunt ook configureren of en welke functies eindgebruikers kunnen zien in de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8c686-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="8c686-140">Overzicht van de Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8c686-140">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="8c686-141">Eindpuntbeveiliging: Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8c686-141">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="8c686-142">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8c686-142">Next steps</span></span>

- [<span data-ttu-id="8c686-143">Een overzicht van Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="8c686-143">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="8c686-144">Ga naar het Microsoft Defender-beveiligingscentrum dashboard voor beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="8c686-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="8c686-145">Microsoft Defender voor eindpunt beheren met Intune</span><span class="sxs-lookup"><span data-stu-id="8c686-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
