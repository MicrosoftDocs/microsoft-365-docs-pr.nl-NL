---
title: Toezicht houden op het privacy van gebeurtenissen in uw organisatie en deze beantwoorden
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
- m365solution-scenario
ms.custom: ''
description: Gebruik controle-en waarschuwings beleid en verzoeken om gegevens te controleren en te reageren op persoonlijke gegevens.
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377197"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="7bd8e-103">Toezicht houden op het privacy van gebeurtenissen in uw organisatie en deze beantwoorden</span><span class="sxs-lookup"><span data-stu-id="7bd8e-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="7bd8e-104">Microsoft 365-functies zijn beschikbaar om u te helpen bij het controleren, onderzoeken en beantwoorden van gebeurtenissen in uw organisatie, zoals u operationalize gerelateerde mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="7bd8e-105">Het hebben van processen, procedures en andere documentatie voor elk van deze factoren kan ook belangrijk zijn om de naleving van de regelgevende instanties te illustreren.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="7bd8e-106">Dit zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-106">These include:</span></span> 

- <span data-ttu-id="7bd8e-107">Beleid voor controle en waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="7bd8e-107">Auditing and alert policies</span></span>
- <span data-ttu-id="7bd8e-108">Aanvragen voor gegevens, waaronder inhoud zoeken en eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7bd8e-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="7bd8e-109">Aanvullende hulpprogramma's voor onderzoek en rapportage</span><span class="sxs-lookup"><span data-stu-id="7bd8e-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="7bd8e-110">Voorschriften met betrekking tot de privacy van functies voor het gebruik van controle-en antwoord Programma's</span><span class="sxs-lookup"><span data-stu-id="7bd8e-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="7bd8e-111">Hieronder ziet u een voorbeeld van een lijst met voorschriften voor de privacy van gegevens die in verband met informatiebeheer kunnen worden beheerd:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="7bd8e-112">LGPD artikel 46</span><span class="sxs-lookup"><span data-stu-id="7bd8e-112">LGPD Article 46</span></span>
- <span data-ttu-id="7bd8e-113">LGPD artikel 48</span><span class="sxs-lookup"><span data-stu-id="7bd8e-113">LGPD Article 48</span></span>
- <span data-ttu-id="7bd8e-114">AVG artikel (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="7bd8e-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="7bd8e-115">AVG artikel (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="7bd8e-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="7bd8e-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="7bd8e-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="7bd8e-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="7bd8e-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="7bd8e-119">164.308 (a) (6) (II)</span><span class="sxs-lookup"><span data-stu-id="7bd8e-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="7bd8e-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="7bd8e-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="7bd8e-121">164.312(b))</span></span>
- <span data-ttu-id="7bd8e-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="7bd8e-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="7bd8e-123">Voor meer informatie raadpleegt u de [beoordeelde Risico's en gevoelige informatie voor gegevens](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="7bd8e-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="7bd8e-124">De informatie over de privacy van gegevens wordt in het algemeen naar het volgende gekeken voor bewaken en beantwoorden:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="7bd8e-125">Controleren, waarschuwen en rapporteren voor activiteiten met betrekking tot opslag, delen en verwerking van persoonlijke gegevens</span><span class="sxs-lookup"><span data-stu-id="7bd8e-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="7bd8e-126">De mogelijkheid om te reageren op een verzoek voor een data subject (DSR) en in sommige gevallen, onderzoek van onderzoek en andere administratieve maatregelen om aan dergelijke verzoeken te voldoen.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="7bd8e-127">Uw organisatie wil wellicht ook toezicht-en antwoord activiteiten uitvoeren voor andere doeleinden, zoals andere nalevings behoeften of voor zakelijke redenen.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="7bd8e-128">Het opzetten van uw toezicht-en antwoordschema voor de privacy van gegevens moet worden afgehandeld als onderdeel van de algemene controle-en antwoord planning, implementatie en beheer.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="7bd8e-129">Om u te helpen aan de slag te gaan met een monitoring-en antwoordschema in Microsoft 365 voor data privacy Regulations, bevat dit artikel nuttige functies in Microsoft 365 voor het beantwoorden van vragen, zoals:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="7bd8e-130">Welke soort dag-en rapportage technieken zijn er voor de verschillende gegevenstypen en bronnen beschikbaar?</span><span class="sxs-lookup"><span data-stu-id="7bd8e-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="7bd8e-131">Welke mechanismen nodig zijn voor het verwerken van aanvragen voor gegevens-subjecten (DSRs) en eventuele herstelbewerkingen, zoals anonimiseren, redactie en verwijdering.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="7bd8e-132">Beleidsregels voor controleren en waarschuwingen in het beveiligings-en nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="7bd8e-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="7bd8e-133">Zie de volgende artikelen voor het instellen van controle, geavanceerde controle en waarschuwings beleid:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="7bd8e-134">Geïntegreerde controle</span><span class="sxs-lookup"><span data-stu-id="7bd8e-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="7bd8e-135">Postvakcontrole</span><span class="sxs-lookup"><span data-stu-id="7bd8e-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="7bd8e-136">Geavanceerde controle</span><span class="sxs-lookup"><span data-stu-id="7bd8e-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="7bd8e-137">Waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="7bd8e-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="7bd8e-138">Aanvragen voor AVG en CCPA</span><span class="sxs-lookup"><span data-stu-id="7bd8e-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="7bd8e-139">Zie [aanvragen van AVG en CCPA](../compliance/gdpr-dsr-office365.md) voor meer informatie over het reageren op een DSR in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="7bd8e-140">Verwijderde gebruikers beheren in Microsoft stream</span><span class="sxs-lookup"><span data-stu-id="7bd8e-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="7bd8e-141">Voor Microsoft stream, wanneer een gebruiker wordt verwijderd uit Azure Active Directory (Azure AD), en het e-mailadres van de gebruiker vóór dat punt is gekoppeld aan de video, blijft het bijbehorende e-mailadres aan de video gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="7bd8e-142">Zie [Verwijderde gebruikers beheren vanuit Microsoft stream](https://docs.microsoft.com/stream/managing-deleted-users) om dit te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="7bd8e-143">Aanvullende hulpmiddelen voor onderzoek</span><span class="sxs-lookup"><span data-stu-id="7bd8e-143">Additional investigative tools</span></span>

<span data-ttu-id="7bd8e-144">Hier volgen nog twee extra hulpmiddelen waarmee u nuttige gebeurtenissen in verband met privacy in uw organisatie kunt volgen, onderzoeken en herstellen:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="7bd8e-145">[Insider Risk Management in Microsoft 365](../compliance/insider-risk-management.md), een functie van het Microsoft compliance-Beheercentrum om intern risico te minimaliseren, zodat u risico activiteiten in uw organisatie kunt detecteren, onderzoeken en ondernemen.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="7bd8e-146">[Gegevens onderzoek in Microsoft 365](../compliance/overview-data-investigations.md), een functie van het Microsoft compliance-Beheercentrum om te zoeken naar gevoelige, kwaadaardige of verkeerd geplaatste gegevens in microsoft 365 en onderzoek wat er is gebeurd om het incident te herstellen.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
