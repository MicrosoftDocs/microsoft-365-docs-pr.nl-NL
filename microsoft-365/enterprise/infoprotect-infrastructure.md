---
title: 'Fase 6: Gegevensbeveiliging'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: De stappen om de gegevensbeveiligingsinfrastructuur voor Microsoft 365 Enterprise te implementeren.
ms.openlocfilehash: d6e3501e8262a0c3245c6e13da6633ac465276fb
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268301"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="e0feb-103">Fase 6: Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e0feb-103">Phase 6: Information protection</span></span>

![Fase 6: Gegevensbeveiliging](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="e0feb-105">Gegevensbeveiliging is een reeks beleidsregels en technologieën waarmee wordt bepaald hoe u gevoelige informatie verzendt, opslaat en verwerkt.</span><span class="sxs-lookup"><span data-stu-id="e0feb-105">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information.</span></span> <span data-ttu-id="e0feb-106">In fase 6 gaat u door de beveiligingsinstellingen en -functies van Microsoft 365 Enterprise die u helpen gegevens te beveiligen voor uw cloudworkloads.</span><span class="sxs-lookup"><span data-stu-id="e0feb-106">In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads.</span></span>

>[!Note]
><span data-ttu-id="e0feb-107">Als u al gegevensbeveiliging hebt geïmplementeerd, bekijkt u het [afsluitcriterium](infoprotect-exit-criteria.md) voor deze fase om er zeker van te zijn dat er wordt voldaan aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e0feb-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="e0feb-108">Uw Microsoft 365 Enterprise-gegevensbeveiligingsinfrastructuur plannen en implementeren.</span><span class="sxs-lookup"><span data-stu-id="e0feb-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="e0feb-109">Het is belangrijk om samen te werken met uw juridische en complianceteams om te bepalen of uw organisatie aan compliancestandaarden, zoals HIPPA, CJIS of AVG, moet voldoen.</span><span class="sxs-lookup"><span data-stu-id="e0feb-109">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR.</span></span> <span data-ttu-id="e0feb-110">U moet ook werken met uw beveiligingsgroep om de gegevensbeveiligingsdoelen vast te stellen voor uw organisatie en voor afdelingen of groepen waarvoor extra beveiliging is vereist.</span><span class="sxs-lookup"><span data-stu-id="e0feb-110">You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="e0feb-111">Gebruik vervolgens de volgende stappen om gegevensbeveiliging voor Microsoft 365 Enterprise te ontwikkelen.</span><span class="sxs-lookup"><span data-stu-id="e0feb-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="e0feb-113">Beveiligings- en gegevensbeschermingsniveaus definiëren</span><span class="sxs-lookup"><span data-stu-id="e0feb-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![Stap 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="e0feb-115">Classificatie voor uw omgeving configureren</span><span class="sxs-lookup"><span data-stu-id="e0feb-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![Stap 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="e0feb-117">Verbeterde beveiliging voor Microsoft 365 configureren</span><span class="sxs-lookup"><span data-stu-id="e0feb-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![Stap 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="e0feb-119">Windows Information Protection configureren</span><span class="sxs-lookup"><span data-stu-id="e0feb-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![Stap 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="e0feb-121">Preventie van gegevensverlies configureren</span><span class="sxs-lookup"><span data-stu-id="e0feb-121">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![Stap 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="e0feb-123">E-mailversleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="e0feb-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![Stap 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="e0feb-125">Privileged Access Management  voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="e0feb-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="e0feb-126">Wanneer u deze stappen hebt voltooid, gaat u naar het [afsluitcriterium](infoprotect-exit-criteria.md) voor deze fase om er zeker van te zijn dat u voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e0feb-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="e0feb-127">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e0feb-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e0feb-128">Lees hoe IT-specialisten bij Microsoft [Azure Information Protection gebruiken en gegevens beveiligen](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span><span class="sxs-lookup"><span data-stu-id="e0feb-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="e0feb-129">Hoe Contoso Microsoft 365 Enterprise gebruikt</span><span class="sxs-lookup"><span data-stu-id="e0feb-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e0feb-130">Bekijk hoe Contoso Corporation, een fictieve maar representatieve multinational, [gegevensbeveiliging heeft geïmplementeerd](contoso-info-protect.md) met Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="e0feb-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="e0feb-132">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e0feb-132">Next step</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="e0feb-134">Beveiligings- en gegevensbeschermingsniveaus definiëren</span><span class="sxs-lookup"><span data-stu-id="e0feb-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

