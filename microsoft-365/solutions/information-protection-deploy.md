---
title: Informatiebescherming implementeren voor regelgeving voor gegevensprivacy met Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configureer de beveiligings- en service-infrastructuur om uw gegevens te beschermen en zich te houden aan de privacyvoorschriften van gegevens.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695104"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="c8aa2-103">Informatiebescherming implementeren voor regelgeving voor gegevensprivacy met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8aa2-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="c8aa2-104">Deze oplossing biedt richtlijnen voor het plannen en beschermen van persoonsgegevens die zijn opgeslagen in Microsoft 365-services en mogelijk onderworpen zijn aan regelgeving inzake gegevensprivacy, zoals de Algemene Verordening Gegevensbescherming (AVG) van de Europese Unie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="c8aa2-105">Deze oplossing richt zich op de toepasselijke microsoft-functies voor informatiebescherming en naleving, Microsoft Compliance Score en beoordelingstools om u te helpen uw gegevens te kennen.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="c8aa2-106">Aanvullende informatie wordt ook verstrekt over het gebruik van Microsoft-besturingselementen voor identiteits-, apparaat- en bedreigingsbeveiliging voor uw gegevensprivacybehoeften, evenals hulpmiddelen voor het ontdekken en reageren op gegevensincidenten.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="c8aa2-107">Organisatie van dit begeleidingsmateriaal</span><span class="sxs-lookup"><span data-stu-id="c8aa2-107">Organization of this guidance material</span></span>

<span data-ttu-id="c8aa2-108">Om u inzicht te geven in de Microsoft 365-hulpprogramma's die beschikbaar zijn voor het identificeren, beheren, beheren en controleren van persoonsgegevens die onderworpen zijn aan een of meer privacygerelateerde voorschriften, is deze richtlijnen ingedeeld in secties.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Informatiebescherming implementeren voor regelgeving inzake gegevensprivacy](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="c8aa2-110">Elk van deze secties komt overeen met een apart artikel in deze oplossing.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="c8aa2-111">Als u al bekend bent met uw privacyverplichtingen en uitvoert tegen een bestaand abonnement, u zich richten op de richtlijnen Voor voorkomen, beschermen, behouden en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="c8aa2-112">Als u deze richtlijnen volgen, voldoet u niet noodzakelijkerwijs aan de regelgeving voor gegevensprivacy, vooral gezien het aantal vereiste stappen dat buiten de context van de functies valt.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="c8aa2-113">U bent verantwoordelijk voor het waarborgen van uw compliance en het raadplegen van uw juridische en compliance teams of om advies en advies in te winnen bij derden die gespecialiseerd zijn in compliance.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="c8aa2-114">Plan: De privacyrisico's van gegevens beoordelen en gevoelige items identificeren</span><span class="sxs-lookup"><span data-stu-id="c8aa2-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="c8aa2-115">Het beoordelen van de privacyvoorschriften en -risico's waaraan uw organisatie is onderworpen, is een belangrijke eerste stap voordat u begint met het implementeren van verbeteringen, waaronder die welke mogelijk zijn via de Microsoft 365-configuratie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="c8aa2-116">Dit kan een algemene beoordeling van de gereedheid of identificatie van bepaalde gevoelige informatietypen zijn die onderworpen zijn aan wettelijke controles waaraan uw organisatie moet voldoen, evenals het optreden ervan in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="c8aa2-117">Zie De [privacyrisico's van gegevens beoordelen en gevoelige items identificeren](information-protection-deploy-assess.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="c8aa2-118">Track: Compliance Score en Compliance Manager gebruiken</span><span class="sxs-lookup"><span data-stu-id="c8aa2-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="c8aa2-119">Compliance Score en Compliance Manager bieden een geïntegreerde set tools die beschikbaar zijn in het Microsoft 365 Compliance-beheercentrum en servicesvertrouwensportal.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="c8aa2-120">Samen bieden deze tools u een ingebouwde mogelijkheid om verbeteringsacties in het algemeen bij te houden en te beheren, evenals die met betrekking tot de regelgeving inzake meerdere gegevensprivacy waaraan u wordt onderworpen.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="c8aa2-121">Met de tools u ook gebruikmaken van ingebouwde beoordelingssjablonen die specifiek zijn voor elke verordening, waarbij u actiepunten voor elke geselecteerde beoordelingssjabloon bijhouden en specifieke regelgevingscontroles bekijken en deze relateren aan specifieke acties.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="c8aa2-122">Zie [Compliance Score en Compliance Manager gebruiken om verbeteracties te beheren voor](information-protection-deploy-compliance.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="c8aa2-123">Voorkomen: identiteits-, apparaat- en bedreigingsbescherming gebruiken voor regelgeving voor gegevensprivacy</span><span class="sxs-lookup"><span data-stu-id="c8aa2-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="c8aa2-124">Microsoft 365 biedt een aantal mogelijkheden voor identiteits-, apparaat- en bedreigingsbescherming die u gebruiken om te voldoen aan de naleving van de naleving van de privacy van gegevens.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="c8aa2-125">Zie [Identiteits-, apparaat- en bedreigingsbescherming gebruiken voor de regelgeving op het spel](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="c8aa2-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="c8aa2-126">In dit artikel wordt kort beschreven waar de regelgeving voor gegevensprivacy in deze gebieden over het algemeen om vraagt en wordt een lijst gegeven van gerelateerde Microsoft 365-oplossingen, met links naar meer informatie om u te helpen eventuele implementatievereisten aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="c8aa2-127">Informatie beschermen die onderworpen is aan de privacywetgeving van gegevens</span><span class="sxs-lookup"><span data-stu-id="c8aa2-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="c8aa2-128">De regelgeving inzake gegevensprivacy dicteert een aantal controles op de bescherming van persoonsgegevens die in uw omgeving kunnen worden gebruikt, waaronder meer dan veertig beschermingsinformatiecontroles voor alleen de vier voorschriften inzake gegevensprivacy in onze voorbeeldset van GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (Us Health Care Privacy Act) en de Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="c8aa2-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="c8aa2-129">Zie [Informatie beveiligen onder voorbehoud van de privacyregelgeving van gegevens in uw organisatie voor](information-protection-deploy-protect-information.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="c8aa2-130">In dit artikel worden de belangrijkste controleschema's uiteengezet die kunnen worden gebruikt voor het aanpakken van informatiebeschermingsbehoeften voor gegevensprivacy in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="c8aa2-131">Behouden: Informatie regelen die onderworpen is aan de privacywetgeving</span><span class="sxs-lookup"><span data-stu-id="c8aa2-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="c8aa2-132">De regelgeving inzake gegevensprivacy vraagt om controles op het beheer van persoonlijke gegevens die in uw omgeving kunnen worden gebruikt, waaronder meer dan vierentwintig controles in de vier regelgeving inzake gegevensprivacy in onze voorbeeldset van GDPR, CCPA, HIPAA-HITECH en LGPD.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="c8aa2-133">Zie [Informatie beheren die onderworpen is aan de privacyregelgeving van gegevens in uw organisatie](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="c8aa2-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="c8aa2-134">Hoewel de regelgeving inzake gegevensprivacy vaag kan zijn met betrekking tot &mdash; informatiebeheer, zoals doelgerichte bewaring, het verwijderen en archiveren van &mdash; dit artikel, worden de primaire controleschema's vastgelegd die u gebruiken om adresbeheerbehoeften voor gegevensprivacy in uw organisatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="c8aa2-135">Onderzoek: Monitor en reageer onder voorbehoud van de privacywetgeving</span><span class="sxs-lookup"><span data-stu-id="c8aa2-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="c8aa2-136">Er zijn Microsoft 365-functies beschikbaar om u te helpen bij het monitoren, onderzoeken en reageren op privacyincidenten in uw organisatie terwijl u gerelateerde mogelijkheden operationaliseert.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="c8aa2-137">Het hebben van processen, procedures en andere documentatie voor elk van deze kan belangrijk zijn om aan te tonen dat regelgevende instanties aan de regels voldoen.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="c8aa2-138">Zie [Gegevensprivacy-incidenten in uw organisatie controleren en reageren op gegevensprivacy](information-protection-deploy-monitor-respond.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8aa2-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
