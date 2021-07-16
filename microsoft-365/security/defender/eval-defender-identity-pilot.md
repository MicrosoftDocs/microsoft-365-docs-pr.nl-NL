---
title: Test Microsoft Defender voor identiteit, stel configuratiebenchmarks, standaarden, richtlijnen in en maak zelfstudies over het detecteren en herstellen van verschillende identiteitsbedreigingen, zoals verkenning, gecompromitteerde referenties, laterale beweging, domeindominantie en exfiltratiewaarschuwingen, het uitvoeren van gebruikers-, computer-, entiteits- en zijbewegingspaden.
description: Test Microsoft Defender voor identiteit, stel benchmarks in, maak zelfstudies over verkenning, gecompromitteerde referenties, zijbewegingen, domeindominantie en exfiltrationwaarschuwingen, onder andere.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457766"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="a3a18-103">Test Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="a3a18-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="a3a18-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a3a18-104">**Applies to:**</span></span>
- <span data-ttu-id="a3a18-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3a18-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="a3a18-106">Dit artikel is [stap 3 van 3](eval-defender-identity-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor identiteit.</span><span class="sxs-lookup"><span data-stu-id="a3a18-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="a3a18-107">Zie het [overzichtsartikel](eval-defender-identity-overview.md)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="a3a18-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="a3a18-108">Gebruik de volgende stappen om de pilot voor Microsoft Defender voor identiteit in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="a3a18-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="a3a18-109">Houd er rekening mee dat de aanbevelingen geen pilotgroep bevatten.</span><span class="sxs-lookup"><span data-stu-id="a3a18-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="a3a18-110">De beste manier is om door te gaan en de sensor te installeren op al uw servers waarop Active Directory Domain Services (AD DS) en Active Directory Federated Services (AD FS) worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a3a18-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Stappen voor het toevoegen van Microsoft Defender voor identiteit aan de evaluatieomgeving van Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="a3a18-112">In de volgende tabel worden de stappen in de afbeelding beschreven.</span><span class="sxs-lookup"><span data-stu-id="a3a18-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="a3a18-113">Stap 1: Benchmarkaanbevelingen configureren voor uw identiteitsomgeving</span><span class="sxs-lookup"><span data-stu-id="a3a18-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="a3a18-114">Stap 2: Mogelijkheden uitproberen: zelfstudies voor het identificeren en herstellen van verschillende aanvalstypen </span><span class="sxs-lookup"><span data-stu-id="a3a18-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="a3a18-115">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="a3a18-115">Step 1.</span></span> <span data-ttu-id="a3a18-116">Aanbevelingen voor benchmarks configureren voor uw identiteitsomgeving</span><span class="sxs-lookup"><span data-stu-id="a3a18-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="a3a18-117">Microsoft biedt aanbevelingen voor beveiligingsbenchmarks voor klanten die Microsoft Cloud-services gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a3a18-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="a3a18-118">De [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) bevat beschrijvende aanbevolen procedures en aanbevelingen om de beveiliging van werkbelastingen, gegevens en services in Azure te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="a3a18-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="a3a18-119">Deze benchmarkaanbevelingen omvatten [Azure-beveiligingslijn voor Microsoft Defender voor identiteit.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)</span><span class="sxs-lookup"><span data-stu-id="a3a18-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="a3a18-120">Het kan enige tijd duren om deze aanbevelingen te implementeren.</span><span class="sxs-lookup"><span data-stu-id="a3a18-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="a3a18-121">Hoewel hiermee de beveiliging van uw identiteitsomgeving sterk wordt vergroot, mogen ze niet verhinderen dat u Microsoft Defender voor identiteit blijft evalueren en implementeren.</span><span class="sxs-lookup"><span data-stu-id="a3a18-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="a3a18-122">Deze zijn hier beschikbaar voor uw aandacht.</span><span class="sxs-lookup"><span data-stu-id="a3a18-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="a3a18-123">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="a3a18-123">Step 2.</span></span> <span data-ttu-id="a3a18-124">Mogelijkheden uitproberen: zelfstudies voor het identificeren en herstellen van verschillende aanvalstypen</span><span class="sxs-lookup"><span data-stu-id="a3a18-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="a3a18-125">De documentatie van Microsoft Defender voor identiteit bevat een reeks zelfstudies die het proces van het identificeren en herstellen van verschillende aanvalstypen doorlopen.</span><span class="sxs-lookup"><span data-stu-id="a3a18-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="a3a18-126">Zelfstudies voor Defender voor identiteit uitproberen:</span><span class="sxs-lookup"><span data-stu-id="a3a18-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="a3a18-127">Verkenningswaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a3a18-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="a3a18-128">Waarschuwingen voor gecompromitteerde referenties</span><span class="sxs-lookup"><span data-stu-id="a3a18-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="a3a18-129">Waarschuwingen voor zijbewegingen</span><span class="sxs-lookup"><span data-stu-id="a3a18-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="a3a18-130">Waarschuwingen voor domeindominantie</span><span class="sxs-lookup"><span data-stu-id="a3a18-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="a3a18-131">Exfiltrationwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a3a18-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="a3a18-132">Een gebruiker onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a3a18-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="a3a18-133">Een computer onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a3a18-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="a3a18-134">Zijbewegingspaden onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a3a18-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="a3a18-135">Entiteiten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a3a18-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="a3a18-136">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a3a18-136">Next steps</span></span>

[<span data-ttu-id="a3a18-137">Microsoft Defender evalueren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a3a18-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="a3a18-138">Ga terug naar het overzicht voor [Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a3a18-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="a3a18-139">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a3a18-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>