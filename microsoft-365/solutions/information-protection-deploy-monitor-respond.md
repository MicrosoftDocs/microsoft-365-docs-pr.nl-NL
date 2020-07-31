---
title: Incidenten met gegevensprivacy in uw organisatie monitoren en erop reageren
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
- m365solution-infoprotection
ms.custom: ''
description: Gebruik controle- en waarschuwingsbeleid en verzoeken van gegevensbesantwoorden om incidenten met persoonsgegevens te monitoren en erop te reageren.
ms.openlocfilehash: 8fdba5799ca9ee97a013c1322e5e79f6bf38764a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522071"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="4f2ed-103">Incidenten met gegevensprivacy in uw organisatie monitoren en erop reageren</span><span class="sxs-lookup"><span data-stu-id="4f2ed-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="4f2ed-104">Microsoft 365-functies zijn beschikbaar om u te helpen bij het monitoren, onderzoeken en reageren op privacyincidenten in uw organisatie terwijl u gerelateerde mogelijkheden operationaliseert.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="4f2ed-105">Het hebben van processen, procedures en andere documentatie voor elk van deze kan ook belangrijk zijn om aan te tonen dat regelgevende instanties aan de regels voldoen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="4f2ed-106">Dit zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="4f2ed-106">These include:</span></span> 

- <span data-ttu-id="4f2ed-107">Controle- en waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="4f2ed-107">Auditing and alert policies</span></span>
- <span data-ttu-id="4f2ed-108">Verzoeken van betrokkenen (inclusief zoeken naar inhoud en eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="4f2ed-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="4f2ed-109">Aanvullende onderzoeksinstrumenten en rapportages</span><span class="sxs-lookup"><span data-stu-id="4f2ed-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="4f2ed-110">Regelgeving voor gegevensprivacy die van invloed is op het gebruik van monitoring- en responstools</span><span class="sxs-lookup"><span data-stu-id="4f2ed-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="4f2ed-111">Hier is een voorbeeld van regelgeving voor gegevensprivacy die betrekking kunnen hebben op controles op informatiebeheer:</span><span class="sxs-lookup"><span data-stu-id="4f2ed-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="4f2ed-112">LGPD Artikel 46</span><span class="sxs-lookup"><span data-stu-id="4f2ed-112">LGPD Article 46</span></span>
- <span data-ttu-id="4f2ed-113">LGPD Artikel 48</span><span class="sxs-lookup"><span data-stu-id="4f2ed-113">LGPD Article 48</span></span>
- <span data-ttu-id="4f2ed-114">AVG-artikel (5, lid 1, onder f)</span><span class="sxs-lookup"><span data-stu-id="4f2ed-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="4f2ed-115">GDPR-artikel (15), lid 1, onder e)</span><span class="sxs-lookup"><span data-stu-id="4f2ed-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="4f2ed-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="4f2ed-117">164.308(a)(1) (ii)(D))</span><span class="sxs-lookup"><span data-stu-id="4f2ed-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="4f2ed-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="4f2ed-119">164.308(a)(6)</span><span class="sxs-lookup"><span data-stu-id="4f2ed-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="4f2ed-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="4f2ed-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="4f2ed-121">164.312(b))</span></span>
- <span data-ttu-id="4f2ed-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="4f2ed-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="4f2ed-123">Zie De [privacyrisico's van gegevens beoordelen en gevoelige informatie identificeren](information-protection-deploy-assess.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="4f2ed-124">De regelgeving inzake gegevensprivacy vraagt over het algemeen om het volgende voor monitoring en respons:</span><span class="sxs-lookup"><span data-stu-id="4f2ed-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="4f2ed-125">Auditing, signalering en rapportage voor activiteiten in verband met de opslag, het delen en verwerken van persoonsgegevens</span><span class="sxs-lookup"><span data-stu-id="4f2ed-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="4f2ed-126">De mogelijkheid om te reageren op een verzoek om een betrokkene (DSR) en in sommige gevallen onderzoekende en andere administratieve maatregelen te nemen om aan dergelijke verzoeken te voldoen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="4f2ed-127">Uw organisatie kan ook controle- en reactieactiviteiten willen uitvoeren voor andere doeleinden, zoals andere nalevingsbehoeften of om zakelijke redenen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="4f2ed-128">Het opzetten van uw monitoring- en responsschema voor gegevensprivacy moet worden uitgevoerd als onderdeel van de algehele planning, implementatie en beheer van de algemene monitoring en respons.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="4f2ed-129">Om u te helpen aan de slag te gaan met een monitoring- en responsschema in Microsoft 365 voor regelgeving voor gegevensprivacy, bevat dit artikel nuttige mogelijkheden in Microsoft 365 om vragen te beantwoorden, zoals:</span><span class="sxs-lookup"><span data-stu-id="4f2ed-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="4f2ed-130">Wat voor dagelijkse bewakings-, onderzoeks- en rapportagetechnieken zijn beschikbaar voor de verschillende gegevenstypen en -bronnen?</span><span class="sxs-lookup"><span data-stu-id="4f2ed-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="4f2ed-131">Welke mechanismen zijn nodig om verzoeken van betrokkenen (DSR's) en eventuele corrigerende acties, zoals anonimisering, redactie en verwijdering, te behandelen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="4f2ed-132">Controle- en waarschuwingsbeleid in het Beveiligings- en Compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="4f2ed-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="4f2ed-133">Zie deze artikelen voor het instellen van controle-, geavanceerde controle- en waarschuwingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="4f2ed-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="4f2ed-134">Geïntegreerde controle</span><span class="sxs-lookup"><span data-stu-id="4f2ed-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="4f2ed-135">Postvakcontrole</span><span class="sxs-lookup"><span data-stu-id="4f2ed-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="4f2ed-136">Geavanceerde audit</span><span class="sxs-lookup"><span data-stu-id="4f2ed-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="4f2ed-137">Waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="4f2ed-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="4f2ed-138">Verzoeken van betrokkenen voor de AVG en CCPA</span><span class="sxs-lookup"><span data-stu-id="4f2ed-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="4f2ed-139">Zie [Verzoeken van gegevens over de AVG en CCPA](../compliance/gdpr-dsr-office365.md) voor informatie over het reageren op een DSR in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="4f2ed-140">Verwijderde gebruikers beheren in Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4f2ed-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="4f2ed-141">Wanneer een gebruiker voor Microsoft Stream wordt verwijderd uit Azure Active Directory (Azure AD), blijft zijn of haar naam voorafgaand aan dat punt gekoppeld aan een geposte Stream-video.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="4f2ed-142">Zie [Verwijderde gebruikers beheren uit Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) om deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="4f2ed-143">Aanvullende onderzoeksinstrumenten</span><span class="sxs-lookup"><span data-stu-id="4f2ed-143">Additional investigative tools</span></span>

<span data-ttu-id="4f2ed-144">Hier volgen twee extra tools die nuttig kunnen zijn voor het bewaken, onderzoeken en herstellen van gegevensprivacygerelateerde incidenten in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="4f2ed-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="4f2ed-145">[Insider-risicobeheer in Microsoft 365](../compliance/insider-risk-management.md), een functie van het Microsoft Compliance-beheercentrum om interne risico's te minimaliseren door dat u risicovolle activiteiten in uw organisatie detecteren, onderzoeken en actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="4f2ed-146">[Gegevensonderzoeken in Microsoft 365](../compliance/overview-data-investigations.md), een functie van het Microsoft Compliance-beheercentrum om te zoeken naar gevoelige, schadelijke of misplaatste gegevens in Microsoft 365, en vervolgens te onderzoeken wat er is gebeurd om de juiste maatregelen te nemen om het incident te herstellen.</span><span class="sxs-lookup"><span data-stu-id="4f2ed-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
