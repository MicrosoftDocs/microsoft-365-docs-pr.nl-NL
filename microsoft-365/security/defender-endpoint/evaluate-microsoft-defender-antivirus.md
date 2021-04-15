---
title: Microsoft Defender Antivirus evalueren
description: Bedrijven van alle groottes kunnen deze handleiding gebruiken om de beveiliging te evalueren en te testen die wordt geboden door Microsoft Defender Antivirus in Windows 10.
keywords: Microsoft Defender Antivirus, cloudbeveiliging, cloud, antimalware, beveiliging, defender, evalueren, testen, beschermen, vergelijken, realtime beveiliging
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764829"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="182ba-104">Microsoft Defender Antivirus evalueren</span><span class="sxs-lookup"><span data-stu-id="182ba-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="182ba-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="182ba-105">**Applies to:**</span></span>

- [<span data-ttu-id="182ba-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="182ba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="182ba-107">Gebruik deze handleiding om te bepalen hoe goed Microsoft Defender Antivirus u beschermt tegen virussen, malware en mogelijk ongewenste toepassingen.</span><span class="sxs-lookup"><span data-stu-id="182ba-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="182ba-108">U kunt ook naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen [dat](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) de volgende functies werken en te zien hoe ze werken:</span><span class="sxs-lookup"><span data-stu-id="182ba-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="182ba-109">Beveiliging in de cloud</span><span class="sxs-lookup"><span data-stu-id="182ba-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="182ba-110">Snel leren (inclusief Blok op het eerste gezicht)</span><span class="sxs-lookup"><span data-stu-id="182ba-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="182ba-111">Mogelijk ongewenste blokkering van toepassingen</span><span class="sxs-lookup"><span data-stu-id="182ba-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="182ba-112">Hier worden de belangrijke volgende generatie beveiligingsfuncties van Microsoft Defender Antivirus uitgelegd die beschikbaar zijn voor zowel kleine als grote ondernemingen en hoe ze de detectie en beveiliging van malware in uw netwerk vergroten.</span><span class="sxs-lookup"><span data-stu-id="182ba-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="182ba-113">U kunt ervoor kiezen om elke instelling onafhankelijk of allemaal tegelijk te configureren en te evalueren.</span><span class="sxs-lookup"><span data-stu-id="182ba-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="182ba-114">We hebben vergelijkbare instellingen gegroepeerd op basis van normale evaluatiescenario's en bevatten instructies voor het gebruik van PowerShell om de instellingen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="182ba-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="182ba-115">De handleiding is beschikbaar in PDF-indeling voor offlineweergave:</span><span class="sxs-lookup"><span data-stu-id="182ba-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="182ba-116">De handleiding downloaden in PDF-indeling</span><span class="sxs-lookup"><span data-stu-id="182ba-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="182ba-117">U kunt ook een PowerShell downloaden waarmee alle instellingen die in de handleiding worden beschreven, automatisch worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="182ba-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="182ba-118">U kunt het script verkrijgen naast de pdf-download hierboven of afzonderlijk uit powershellgalerie:</span><span class="sxs-lookup"><span data-stu-id="182ba-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="182ba-119">Het PowerShell-script downloaden om de instellingen automatisch te configureren</span><span class="sxs-lookup"><span data-stu-id="182ba-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="182ba-120">De handleiding is momenteel bedoeld voor een evaluatie op één computer van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="182ba-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="182ba-121">Het inschakelen van alle instellingen in deze handleiding is mogelijk niet geschikt voor implementatie in de echte wereld.</span><span class="sxs-lookup"><span data-stu-id="182ba-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="182ba-122">Zie Microsoft [Defender Antivirus implementeren](deploy-manage-report-microsoft-defender-antivirus.md)voor de meest recente aanbevelingen voor implementatie en monitoring van Microsoft Defender Antivirus in een netwerk.</span><span class="sxs-lookup"><span data-stu-id="182ba-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="182ba-123">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="182ba-123">Related topics</span></span>

- [<span data-ttu-id="182ba-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="182ba-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="182ba-125">Microsoft Defender Antivirus implementeren</span><span class="sxs-lookup"><span data-stu-id="182ba-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)