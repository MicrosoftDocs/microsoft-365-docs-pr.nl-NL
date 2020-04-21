---
title: Wat komt er in Microsoft Secure Score?
description: Beschrijft de Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteringsacties
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583713"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="ffb62-104">Wat komt er in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="ffb62-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="ffb62-105">Om [van Microsoft Secure Score](microsoft-secure-score.md) een betere vertegenwoordiger te maken van uw beveiligingshouding en de bruikbaarheid te verbeteren, brengen we in de nabije toekomst enkele wijzigingen door.</span><span class="sxs-lookup"><span data-stu-id="ffb62-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="ffb62-106">Je score en de hoogst mogelijke score veranderen.</span><span class="sxs-lookup"><span data-stu-id="ffb62-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="ffb62-107">Dit impliceert echter geen verandering in uw beveiligingshouding.</span><span class="sxs-lookup"><span data-stu-id="ffb62-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="ffb62-108">Zie Nieuwe wijzigingen in Microsoft Secure Score voor meer informatie over recente [wijzigingen?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="ffb62-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="ffb62-109">21 april 2020</span><span class="sxs-lookup"><span data-stu-id="ffb62-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="ffb62-110">Het verwijderen van verbeteringsacties die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van de beveiligingshouding bieden</span><span class="sxs-lookup"><span data-stu-id="ffb62-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="ffb62-111">Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.</span><span class="sxs-lookup"><span data-stu-id="ffb62-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="ffb62-112">IRM-beveiligingen toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="ffb62-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="ffb62-113">Beleid ter voorkoming van gegevensverlies toepassen</span><span class="sxs-lookup"><span data-stu-id="ffb62-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="ffb62-114">Azure AD-verbeteringsactie toevoegen aan voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ffb62-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="ffb62-115">De volgende Azure Active Directory-verbeteringsactie toevoegen aan de [preview-release van Microsoft Secure Score:](microsoft-secure-score-preview.md)</span><span class="sxs-lookup"><span data-stu-id="ffb62-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="ffb62-116">Geef gebruikers geen toestemming voor onbeheerde toepassingen (momenteel beschikbaar in een vrijgegeven versie)</span><span class="sxs-lookup"><span data-stu-id="ffb62-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="ffb62-117">Azure ATP-verbeteringsacties toevoegen om een voorbeeld te bekijken</span><span class="sxs-lookup"><span data-stu-id="ffb62-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="ffb62-118">De volgende Azure Advanced Threat Protection-verbeteringsacties toevoegen aan de [preview-release van Microsoft Secure Score:](microsoft-secure-score-preview.md)</span><span class="sxs-lookup"><span data-stu-id="ffb62-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="ffb62-119">Afdrukspoolerservice uitschakelen op domeincontrollers</span><span class="sxs-lookup"><span data-stu-id="ffb62-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="ffb62-120">Onveilige Kerberos-delegaties wijzigen om imitatie te voorkomen</span><span class="sxs-lookup"><span data-stu-id="ffb62-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="ffb62-121">Lokale beheerderswachtwoorden beveiligen en beheren met Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="ffb62-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="ffb62-122">Risico op zijwaarts e-bewegens bewegingspad voor gevoelige entiteiten verminderen</span><span class="sxs-lookup"><span data-stu-id="ffb62-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="ffb62-123">Slapende accounts verwijderen uit gevoelige groepen</span><span class="sxs-lookup"><span data-stu-id="ffb62-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="ffb62-124">Onveilige SID-geschiedeniskenmerken verwijderen uit entiteiten</span><span class="sxs-lookup"><span data-stu-id="ffb62-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="ffb62-125">Onveilige accountkenmerken oplossen</span><span class="sxs-lookup"><span data-stu-id="ffb62-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="ffb62-126">De belichting met wissen van tekstreferenties stoppen</span><span class="sxs-lookup"><span data-stu-id="ffb62-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="ffb62-127">Verouderde protocollen communicatie stoppen</span><span class="sxs-lookup"><span data-stu-id="ffb62-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="ffb62-128">Stop zwak versleutelingsgebruik</span><span class="sxs-lookup"><span data-stu-id="ffb62-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="ffb62-129">Ondersteuning voor beveiligingsaanbevelingen van Microsoft Defender ATP Threat & Vulnerability Management (TVM) in preview</span><span class="sxs-lookup"><span data-stu-id="ffb62-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="ffb62-130">Alle vrijgegeven beveiligingsaanbevelingen geleverd door TVM zal nu ook beschikbaar zijn [de preview release van Microsoft Secure Score](microsoft-secure-score-preview.md).</span><span class="sxs-lookup"><span data-stu-id="ffb62-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
