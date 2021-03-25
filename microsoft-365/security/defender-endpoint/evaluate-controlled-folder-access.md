---
title: Beheerde maptoegang evalueren
description: Bekijk hoe beheerde maptoegang kan helpen om te beschermen dat bestanden worden gewijzigd door schadelijke apps.
keywords: Exploit protection, windows 10, windows defender, ransomware, protect, evaluate, test, demo, try
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218746"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="7dff7-104">Beheerde maptoegang evalueren</span><span class="sxs-lookup"><span data-stu-id="7dff7-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7dff7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7dff7-105">**Applies to:**</span></span>
- [<span data-ttu-id="7dff7-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="7dff7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7dff7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7dff7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7dff7-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7dff7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7dff7-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7dff7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="7dff7-110">[Gecontroleerde maptoegang](controlled-folders.md) is een functie waarmee u uw documenten en bestanden kunt beschermen tegen wijzigingen door verdachte of schadelijke apps.</span><span class="sxs-lookup"><span data-stu-id="7dff7-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="7dff7-111">Gecontroleerde maptoegang wordt ondersteund op Windows Server 2019- en Windows 10-clients.</span><span class="sxs-lookup"><span data-stu-id="7dff7-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="7dff7-112">Het is vooral handig om te beschermen tegen [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) die probeert uw bestanden te versleutelen en ze te laten gegijzeld.</span><span class="sxs-lookup"><span data-stu-id="7dff7-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="7dff7-113">In dit artikel kunt u gecontroleerde maptoegang evalueren.</span><span class="sxs-lookup"><span data-stu-id="7dff7-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="7dff7-114">Hier wordt uitgelegd hoe u de auditmodus inschakelen, zodat u de functie rechtstreeks in uw organisatie kunt testen.</span><span class="sxs-lookup"><span data-stu-id="7dff7-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="7dff7-115">U kunt ook naar de website voor demoscenario's van Microsoft Defender voor [Eindpunt](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com om te bevestigen dat de functie werkt en te zien hoe deze werkt.</span><span class="sxs-lookup"><span data-stu-id="7dff7-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="7dff7-116">Controlemodus gebruiken om de impact te meten</span><span class="sxs-lookup"><span data-stu-id="7dff7-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="7dff7-117">Schakel de gecontroleerde maptoegang in de auditmodus in om een record te zien van wat er zou zijn gebeurd als deze volledig was ingeschakeld. </span><span class="sxs-lookup"><span data-stu-id="7dff7-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="7dff7-118">Test hoe de functie in uw organisatie werkt om ervoor te zorgen dat deze geen invloed heeft op uw line-of-business-apps.</span><span class="sxs-lookup"><span data-stu-id="7dff7-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="7dff7-119">U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7dff7-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="7dff7-120">Gebruik de volgende PowerShell-cmdlet om de auditmodus in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="7dff7-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="7dff7-121">Als u volledig wilt controleren hoe beheerde maptoegang in uw organisatie werkt, moet u een beheerhulpmiddel gebruiken om deze instelling te implementeren op apparaten in uw netwerk(en).</span><span class="sxs-lookup"><span data-stu-id="7dff7-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="7dff7-122">U kunt ook Groepsbeleid, Intune, MDM (Mobile Device Management) of Microsoft Endpoint Manager gebruiken om de instelling te configureren en te implementeren, zoals wordt beschreven in het onderwerp Toegang tot hoofdbeheer van [mappen.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="7dff7-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="7dff7-123">Gecontroleerde maptoegangsgebeurtenissen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="7dff7-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="7dff7-124">De volgende beheerde maptoegangsgebeurtenissen worden weergegeven in Windows Event Viewer onder De map Microsoft/Windows/Windows Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="7dff7-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="7dff7-125">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="7dff7-125">Event ID</span></span> | <span data-ttu-id="7dff7-126">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7dff7-126">Description</span></span>
-|-
 <span data-ttu-id="7dff7-127">5007</span><span class="sxs-lookup"><span data-stu-id="7dff7-127">5007</span></span> | <span data-ttu-id="7dff7-128">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="7dff7-128">Event when settings are changed</span></span>
 <span data-ttu-id="7dff7-129">1124</span><span class="sxs-lookup"><span data-stu-id="7dff7-129">1124</span></span> | <span data-ttu-id="7dff7-130">Gecontroleerde gecontroleerde maptoegangsgebeurtenis</span><span class="sxs-lookup"><span data-stu-id="7dff7-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="7dff7-131">1123</span><span class="sxs-lookup"><span data-stu-id="7dff7-131">1123</span></span> | <span data-ttu-id="7dff7-132">Gebeurtenis Geblokkeerde gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="7dff7-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="7dff7-133">U kunt een [Windows Event Forwarding-abonnement configureren om](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) de logboeken centraal te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="7dff7-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="7dff7-134">Beveiligde mappen en apps aanpassen</span><span class="sxs-lookup"><span data-stu-id="7dff7-134">Customize protected folders and apps</span></span>

<span data-ttu-id="7dff7-135">Tijdens de evaluatie wilt u mogelijk toevoegen aan de lijst met beveiligde mappen of bepaalde apps toestaan bestanden te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7dff7-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="7dff7-136">Zie [Belangrijke mappen beveiligen](controlled-folders.md) met beheerde maptoegang voor het configureren van de functie met beheerhulpmiddelen, zoals Groepsbeleid, PowerShell en MDM-configuratieserviceproviders (CSP's).</span><span class="sxs-lookup"><span data-stu-id="7dff7-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="7dff7-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7dff7-137">See also</span></span>

* [<span data-ttu-id="7dff7-138">Belangrijke mappen beveiligen met gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="7dff7-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="7dff7-139">Microsoft Defender voor eindpunt evalueren</span><span class="sxs-lookup"><span data-stu-id="7dff7-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="7dff7-140">Controlemodus gebruiken</span><span class="sxs-lookup"><span data-stu-id="7dff7-140">Use audit mode</span></span>](audit-windows-defender.md)
