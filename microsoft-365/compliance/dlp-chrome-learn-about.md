---
title: Meer informatie over Microsoft compliance-extensie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: De Microsoft-compliance-extensie is een uitbreiding van de controle en het beheer van bestandsactiviteiten en beschermende maatregelen, voor de Google Chrome-browser
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843804"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="71a37-103">Meer informatie over Microsoft compliance-extensie</span><span class="sxs-lookup"><span data-stu-id="71a37-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="71a37-104">[Eindpunt-DLP (preventie van gegevensverlies)](endpoint-dlp-learn-about.md) is een uitbreiding voor de activiteitencontrole en beveiligingsmogelijkheden van [Microsoft 365 DLP (preventie van gegevensverlies)](dlp-learn-about-dlp.md) voor gevoelige items op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="71a37-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="71a37-105">Zodra apparaten zijn geregistreerd bij de Microsoft 365-complianceoplossingen, wordt de informatie over wat gebruikers met gevoelige items doen, zichtbaar in [Activiteitenverkenner](data-classification-activity-explorer.md) en kunt u beschermende maatregelen voor deze items afdwingen via [DLP-beleid](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="71a37-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="71a37-106">Zodra de Microsoft-compliance-extensie is geïnstalleerd op een Windows 10-apparaat, kunnen organisaties controleren wanneer een gebruiker een gevoelig item probeert te openen of te uploaden naar een cloudservice met behulp van Google Chrome. Vervolgens kunnen beschermende maatregelen worden afgedwongen via DLP.</span><span class="sxs-lookup"><span data-stu-id="71a37-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="71a37-107">Activiteiten die u kunt controleren en waarvoor u maatregelen kunt nemen</span><span class="sxs-lookup"><span data-stu-id="71a37-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="71a37-108">Met de Microsoft-compliance-extensie kunt u de typen activiteiten die gebruikers uitvoeren op gevoelige items, controleren en beheren op apparaten met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="71a37-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="71a37-109">activiteit</span><span class="sxs-lookup"><span data-stu-id="71a37-109">activity</span></span> |<span data-ttu-id="71a37-110">beschrijving</span><span class="sxs-lookup"><span data-stu-id="71a37-110">description</span></span>  | <span data-ttu-id="71a37-111">ondersteunde beleidsacties</span><span class="sxs-lookup"><span data-stu-id="71a37-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="71a37-112">bestand is gekopieerd naar de cloud</span><span class="sxs-lookup"><span data-stu-id="71a37-112">file copied to cloud</span></span>  | <span data-ttu-id="71a37-113">Hiermee wordt gedetecteerd wanneer een gebruiker probeert om een gevoelig item te uploaden naar een beperkt servicedomein via de Chrome-browser</span><span class="sxs-lookup"><span data-stu-id="71a37-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="71a37-114">controleren, blokkeren</span><span class="sxs-lookup"><span data-stu-id="71a37-114">audit, block</span></span>|
|<span data-ttu-id="71a37-115">bestand is afgedrukt</span><span class="sxs-lookup"><span data-stu-id="71a37-115">file printed</span></span>  |<span data-ttu-id="71a37-116">Hiermee wordt gedetecteerd wanneer een gebruiker een gevoelig item dat is geopend in de Chrome-browser, probeert af te drukken op een lokale printer of een netwerkprinter</span><span class="sxs-lookup"><span data-stu-id="71a37-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="71a37-117">controleren, blokkeren met overschrijven, blokkeren</span><span class="sxs-lookup"><span data-stu-id="71a37-117">audit, block with override, block</span></span>|
|<span data-ttu-id="71a37-118">bestand is gekopieerd naar het klembord</span><span class="sxs-lookup"><span data-stu-id="71a37-118">file copied to clipboard</span></span> |<span data-ttu-id="71a37-119">Hiermee wordt gedetecteerd wanneer een gebruiker informatie uit een gevoelig item dat wordt weergegeven in de Chrome-browser, probeert te kopiëren en vervolgens te plakken in een andere app, of in een ander proces of item.</span><span class="sxs-lookup"><span data-stu-id="71a37-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="71a37-120">controleren, blokkeren met overschrijven, blokkeren</span><span class="sxs-lookup"><span data-stu-id="71a37-120">audit, block with override, block</span></span>|
|<span data-ttu-id="71a37-121">bestand is gekopieerd naar verwisselbare opslag</span><span class="sxs-lookup"><span data-stu-id="71a37-121">file copied to removable storage</span></span>    | <span data-ttu-id="71a37-122">Hiermee wordt gedetecteerd wanneer een gebruiker een gevoelig item, of gevoelige informatie uit een gevoelig item dat is geopend in de Chrome-browser, probeert te kopiëren naar een verwisselbaar medium of USB-apparaat</span><span class="sxs-lookup"><span data-stu-id="71a37-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="71a37-123">controleren, blokkeren met overschrijven, blokkeren</span><span class="sxs-lookup"><span data-stu-id="71a37-123">audit, block with override, block</span></span>|
|<span data-ttu-id="71a37-124">bestand is gekopieerd naar netwerkshare</span><span class="sxs-lookup"><span data-stu-id="71a37-124">file copied to network share</span></span>  |<span data-ttu-id="71a37-125">Hiermee wordt gedetecteerd wanneer een gebruiker een gevoelig item, of gevoelige informatie uit een gevoelig item dat is geopend in de Chrome-browser, probeert te kopiëren naar een netwerkshare of een toegewezen netwerkstation.</span><span class="sxs-lookup"><span data-stu-id="71a37-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="71a37-126">controleren, blokkeren met overschrijven, blokkeren</span><span class="sxs-lookup"><span data-stu-id="71a37-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="71a37-127">Implementatieproces</span><span class="sxs-lookup"><span data-stu-id="71a37-127">Deployment process</span></span>
1. [<span data-ttu-id="71a37-128">Aan de slag met Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="71a37-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="71a37-129">Hulpprogramma’s en methoden voor onboarding voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="71a37-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="71a37-130">Installeer de extensie op uw Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="71a37-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="71a37-131">[Maak en bewerk DLP-beleidsregels](create-test-tune-dlp-policy.md) die uploaden naar een cloudservice en het verkrijgen van toegang via niet-toegestane browseracties beperken, en pas deze regels toe op uw Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="71a37-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="71a37-132">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="71a37-132">Next steps</span></span>

<span data-ttu-id="71a37-133">Raadpleeg [Aan de slag met de Microsoft-compliance-extensie](dlp-chrome-get-started.md) voor de volledige procedures en scenario's voor de implementatie.</span><span class="sxs-lookup"><span data-stu-id="71a37-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="71a37-134">Zie ook</span><span class="sxs-lookup"><span data-stu-id="71a37-134">See also</span></span>

- [<span data-ttu-id="71a37-135">Aan de slag met de Microsoft compliance-extensie</span><span class="sxs-lookup"><span data-stu-id="71a37-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="71a37-136">Meer informatie over Microsoft 365 Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="71a37-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="71a37-137">Aan de slag met Microsoft Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="71a37-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="71a37-138">Eindpunt-DLP gebruiken</span><span class="sxs-lookup"><span data-stu-id="71a37-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="71a37-139">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="71a37-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="71a37-140">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="71a37-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="71a37-141">Aan de slag met Activity Explorer</span><span class="sxs-lookup"><span data-stu-id="71a37-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="71a37-142">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="71a37-142">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="71a37-143">Insider Risk-beheer</span><span class="sxs-lookup"><span data-stu-id="71a37-143">Insider Risk management</span></span>](insider-risk-management.md)
