---
title: Incidenten met gegevensbescherming in uw organisatie bewaken en hierop reageren
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
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
description: Gebruik controle- en waarschuwingsbeleid en verzoeken van gegevensonderwerpen om incidenten met persoonlijke gegevens te controleren en erop te reageren.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928422"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="eab3f-103">Incidenten met gegevensbescherming in uw organisatie bewaken en hierop reageren</span><span class="sxs-lookup"><span data-stu-id="eab3f-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="eab3f-104">Microsoft 365 functies zijn beschikbaar om u te helpen bij het bewaken, onderzoeken en reageren op incidenten met gegevensbescherming in uw organisatie terwijl u gerelateerde mogelijkheden operationeel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="eab3f-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="eab3f-105">Het hebben van processen, procedures en andere documentatie voor elk van deze procedures kan ook belangrijk zijn om naleving van regelgevende instanties aan te tonen.</span><span class="sxs-lookup"><span data-stu-id="eab3f-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="eab3f-106">Dit zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="eab3f-106">These include:</span></span> 

- <span data-ttu-id="eab3f-107">Controle- en waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="eab3f-107">Auditing and alert policies</span></span>
- <span data-ttu-id="eab3f-108">Aanvragen voor onderwerpen (inclusief zoeken naar inhoud en eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="eab3f-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="eab3f-109">Extra onderzoekshulpmiddelen en rapportage</span><span class="sxs-lookup"><span data-stu-id="eab3f-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="eab3f-110">Privacyregels voor gegevens die van invloed zijn op het gebruik van monitoring- en antwoordhulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="eab3f-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="eab3f-111">Hier vindt u een voorbeeld van de privacyregels voor gegevens die betrekking kunnen hebben op besturingselementen voor informatiebeheer:</span><span class="sxs-lookup"><span data-stu-id="eab3f-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="eab3f-112">LGPD-artikel 46</span><span class="sxs-lookup"><span data-stu-id="eab3f-112">LGPD Article 46</span></span>
- <span data-ttu-id="eab3f-113">LGPD-artikel 48</span><span class="sxs-lookup"><span data-stu-id="eab3f-113">LGPD Article 48</span></span>
- <span data-ttu-id="eab3f-114">AVG-artikel (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="eab3f-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="eab3f-115">AVG-artikel (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="eab3f-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="eab3f-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="eab3f-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="eab3f-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="eab3f-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="eab3f-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="eab3f-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="eab3f-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="eab3f-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="eab3f-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="eab3f-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="eab3f-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="eab3f-121">164.312(b))</span></span>
- <span data-ttu-id="eab3f-122">CTP (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="eab3f-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="eab3f-123">Zie Privacyrisico's voor [gegevens beoordelen en gevoelige informatie identificeren voor meer informatie.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="eab3f-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="eab3f-124">De privacyregels voor gegevens vragen over het algemeen om het volgende voor monitoring en antwoord:</span><span class="sxs-lookup"><span data-stu-id="eab3f-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="eab3f-125">Controle, waarschuwing en rapportage voor activiteiten met betrekking tot het opslaan, delen en verwerken van persoonsgegevens</span><span class="sxs-lookup"><span data-stu-id="eab3f-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="eab3f-126">De mogelijkheid om te reageren op een verzoek om een onderwerp (DSR) en in sommige gevallen onderzoekende en andere administratieve maatregelen uit te voeren om aan dergelijke verzoeken te voldoen.</span><span class="sxs-lookup"><span data-stu-id="eab3f-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="eab3f-127">Uw organisatie wil mogelijk ook monitoring- en antwoordactiviteiten uitvoeren voor andere doeleinden, zoals andere compliancebehoeften of om zakelijke redenen.</span><span class="sxs-lookup"><span data-stu-id="eab3f-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="eab3f-128">Het opstellen van uw monitoring- en antwoordschema voor gegevensbescherming moet worden uitgevoerd als onderdeel van de algemene monitoring- en antwoordplanning, implementatie en beheer.</span><span class="sxs-lookup"><span data-stu-id="eab3f-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="eab3f-129">Om u te helpen aan de slag te gaan met een monitoring- en antwoordschema in Microsoft 365 voor privacyregels voor gegevens, bevat dit artikel nuttige mogelijkheden in Microsoft 365 om vragen te beantwoorden, zoals:</span><span class="sxs-lookup"><span data-stu-id="eab3f-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="eab3f-130">Welke monitoring-, onderzoeks- en rapportagetechnieken zijn beschikbaar voor de verschillende gegevenstypen en bronnen?</span><span class="sxs-lookup"><span data-stu-id="eab3f-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="eab3f-131">Welke mechanismen zijn nodig voor het verwerken van aanvragen van gegevensonderwerpen (DSR's) en eventuele herstelacties, zoals anonimisatie, redaction en verwijdering.</span><span class="sxs-lookup"><span data-stu-id="eab3f-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="eab3f-132">Controle- en waarschuwingsbeleid in het beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="eab3f-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="eab3f-133">Zie deze artikelen voor het instellen van controle-, geavanceerde controle- en waarschuwingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="eab3f-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="eab3f-134">Geïntegreerde controle</span><span class="sxs-lookup"><span data-stu-id="eab3f-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="eab3f-135">Postvakcontrole</span><span class="sxs-lookup"><span data-stu-id="eab3f-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="eab3f-136">Geavanceerde audit</span><span class="sxs-lookup"><span data-stu-id="eab3f-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="eab3f-137">Waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="eab3f-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="eab3f-138">Verzoeken van gegevensonderwerpen voor de AVG en CTPA</span><span class="sxs-lookup"><span data-stu-id="eab3f-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="eab3f-139">Zie [Verzoeken van gegevensonderwerpen voor de AVG en CTPA](/compliance/regulatory/gdpr-dsr-Office365) voor informatie over het reageren op een DSR in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eab3f-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="eab3f-140">Verwijderde gebruikers beheren in Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="eab3f-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="eab3f-141">Als een gebruiker voor Microsoft Stream is verwijderd uit Azure Active Directory (Azure AD), als zijn naam is gekoppeld aan een geposte Stream-video vóór dat punt, blijft het e-mailadres van de gebruiker gekoppeld aan de video.</span><span class="sxs-lookup"><span data-stu-id="eab3f-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="eab3f-142">Zie [Verwijderde gebruikers beheren uit Microsoft Stream om](/stream/managing-deleted-users) deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="eab3f-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="eab3f-143">Insider risk management als een onderzoekshulpmiddel</span><span class="sxs-lookup"><span data-stu-id="eab3f-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="eab3f-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is een functie van het Microsoft Compliance-beheercentrum om u te helpen interne risico's te minimaliseren door u in staat te stellen risicovolle activiteiten in uw organisatie te detecteren, te onderzoeken en actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="eab3f-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>