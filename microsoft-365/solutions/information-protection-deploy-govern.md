---
title: Bepalen van gegevens die onderworpen zijn aan privacyregel voor gegevens
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
description: Gebruik microsoft 365 bewaarlabels en -beleid om persoonlijke gegevens te beheren in uw Microsoft 365-omgeving.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928434"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="a0eed-103">Bepalen van gegevens die onderworpen zijn aan privacyregel voor gegevens</span><span class="sxs-lookup"><span data-stu-id="a0eed-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="a0eed-104">Informatiebeheerbesturingselementen kunnen worden gebruikt in uw omgeving om te helpen bij het voldoen aan de nalevingsvereisten voor gegevensbescherming, waaronder een nummer dat specifiek is voor Algemene verordening gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse privacywet voor gezondheidszorg), de California Consumer Protection Act (CTPA) en de Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="a0eed-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="a0eed-105">Deze besturingselementen vallen voornamelijk onder de volgende oplossingsgebieden:</span><span class="sxs-lookup"><span data-stu-id="a0eed-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="a0eed-106">Bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="a0eed-106">Retention policies</span></span>
- <span data-ttu-id="a0eed-107">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="a0eed-107">Retention labels</span></span>
- <span data-ttu-id="a0eed-108">Records Management</span><span class="sxs-lookup"><span data-stu-id="a0eed-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="a0eed-109">Privacyregels voor gegevens die van invloed zijn op besturingselementen voor informatiebeheer</span><span class="sxs-lookup"><span data-stu-id="a0eed-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="a0eed-110">Hier vindt u een voorbeeld van de privacyregels voor gegevens die betrekking kunnen hebben op besturingselementen voor informatiebeheer:</span><span class="sxs-lookup"><span data-stu-id="a0eed-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="a0eed-111">AVG-artikel (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="a0eed-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="a0eed-112">AVG-artikel (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="a0eed-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="a0eed-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="a0eed-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="a0eed-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="a0eed-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="a0eed-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="a0eed-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="a0eed-116">LGPD-artikel 46</span><span class="sxs-lookup"><span data-stu-id="a0eed-116">LGPD Article 46</span></span>

<span data-ttu-id="a0eed-117">Zie het artikel Privacyrisico's voor gegevens beoordelen en gevoelige informatie identificeren voor meer [informatie over deze regelgeving.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="a0eed-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="a0eed-118">Voor informatiebeheer is de privacyregel voor gegevens meestal het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="a0eed-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="a0eed-119">U moet een technisch schema gebruiken voor het bewaren en verwijderen van persoonlijke gegevens die zijn opgeslagen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0eed-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="a0eed-120">Als u persoonlijke gegevens gaat opslaan, informeert u het onderwerp over hoe lang de gegevens worden opgeslagen, wat nu een standaardpraktijk is op front-endwebsystemen.</span><span class="sxs-lookup"><span data-stu-id="a0eed-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="a0eed-121">Persoonsgegevens moeten worden beschermd tegen onbedoelde verwerking, verlies of wijziging met behulp van controleerbare methoden.</span><span class="sxs-lookup"><span data-stu-id="a0eed-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="a0eed-122">Alle acties die worden uitgevoerd met betrekking tot persoonlijke gegevens, moeten worden gedocumenteerd en de documentatie moet voor een bepaalde periode worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="a0eed-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="a0eed-123">Omdat de privacyregels voor gegevens niet erg specifiek zijn als het gaat om het bewaren en verwijderen van gegevens, moet rekening worden gehouden met andere factoren die richtlijnen voor informatiebeheer kunnen dicteren voor persoonlijke gegevens die zijn opgeslagen in uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="a0eed-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="a0eed-124">Hier zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="a0eed-124">Here are a few examples:</span></span>

- <span data-ttu-id="a0eed-125">Veroudert consumentenaccounts na 5 jaar inactiviteit en vereist verwijdering of anonimisatie van accountgegevens na dat punt, waarbij het systeem de gegevens en werkstromen met betrekking tot meldingen en andere automatisering moet opslaan.</span><span class="sxs-lookup"><span data-stu-id="a0eed-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="a0eed-126">Het configureren van regels voor het behouden van beleidsregels en procedures met betrekking tot AVG is ongeveer drie jaar nadat ze zijn overdwars, wat in overeenstemming is met het bewaarschema van de organisatie voor beleid en procedures.</span><span class="sxs-lookup"><span data-stu-id="a0eed-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="a0eed-127">Het onderhouden van een afzonderlijk abonnement voor het communiceren met consumenten via de ondersteuningsorganisatie.</span><span class="sxs-lookup"><span data-stu-id="a0eed-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="a0eed-128">Alle e-mailcommunicatie is na twee weken bewaard en verwijderd om de opbouw van privacyschulden in het systeem te beperken.</span><span class="sxs-lookup"><span data-stu-id="a0eed-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="a0eed-129">Een belangrijke vraag die u moet beantwoorden is:</span><span class="sxs-lookup"><span data-stu-id="a0eed-129">A key question to answer is:</span></span> 

- <span data-ttu-id="a0eed-130">Hoe lang moeten gegevens met persoonlijke gegevens worden bewaard om geldige zakelijke redenen om te voorkomen dat er 'voor altijd' wordt gebruikt?</span><span class="sxs-lookup"><span data-stu-id="a0eed-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="a0eed-131">Dit moet worden afgewogen met de bewaarbehoeften voor bedrijfscontinuïteit.</span><span class="sxs-lookup"><span data-stu-id="a0eed-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="a0eed-132">Ongeacht de juridische en zakelijke redenen voor het bewaren van persoonlijke gegevens of het verwijderen ervan, biedt Microsoft een aantal mogelijkheden voor het implementeren van uw gegevensbeheerschema in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0eed-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="a0eed-133">Informatiebeheer beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a0eed-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="a0eed-134">Zie Informatiebeheer en [gegevensretentie,](../compliance/manage-information-governance.md) verwijdering en vernietiging beheren [in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)om te beginnen.</span><span class="sxs-lookup"><span data-stu-id="a0eed-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="a0eed-135">Planningen voor het bewaren van gegevens ontwikkelen voor containers, e-mail en inhoud</span><span class="sxs-lookup"><span data-stu-id="a0eed-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="a0eed-136">Houd het volgende in gedachten:</span><span class="sxs-lookup"><span data-stu-id="a0eed-136">Keep the following in mind:</span></span>

- <span data-ttu-id="a0eed-137">Het opstellen van een planning voor het bewaren van gegevens voor gedefinieerde informatietypen moet worden beschouwd als een vereiste voor het implementeren van een bewaar- of verwijderingsschema.</span><span class="sxs-lookup"><span data-stu-id="a0eed-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="a0eed-138">Gezien het aantal informatietypen dat de meeste organisaties belangrijk vinden en de bijbehorende grote bewaarschema's voor records die daarbij horen, is het implementeren van een strategie voor gegevensretentie en recordbeheer planning vereist.</span><span class="sxs-lookup"><span data-stu-id="a0eed-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="a0eed-139">De sleutel tot het tot stand brengen van een effectieve strategie voor gegevensbeheer van dit type is de focus op de hoogste prioriteit voor zakelijke functies en informatietypen waarvoor een formeler beheer vereist is.</span><span class="sxs-lookup"><span data-stu-id="a0eed-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="a0eed-140">Voorbeelden hiervan zijn juridische contracten, financiële overzichten en documentatie over naleving van regelgeving.</span><span class="sxs-lookup"><span data-stu-id="a0eed-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="a0eed-141">Vermijd een afzonderlijk bewaarschema voor elk gegevenstype.</span><span class="sxs-lookup"><span data-stu-id="a0eed-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="a0eed-142">Probeer algemene categorieën zo veel mogelijk te gebruiken, bijvoorbeeld met bewaarschema's van 7 jaar voor algemene zakelijke inhoud.</span><span class="sxs-lookup"><span data-stu-id="a0eed-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="a0eed-143">Zodra de typen persoonlijke gegevens in uw omgeving beter bekend zijn, stelt u bewaar- en verwijderingsschema's in voor dit type inhoud en past u uw informatiearchitectuur aan om het beheer van dit soort informatie te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="a0eed-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="a0eed-144">U kunt bijvoorbeeld persoonlijke gegevens isoleren in afzonderlijke sites, bibliotheken of mappen met gecontroleerde toegang.</span><span class="sxs-lookup"><span data-stu-id="a0eed-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="a0eed-145">Bewaarbeleid en retentielabels</span><span class="sxs-lookup"><span data-stu-id="a0eed-145">Retention policies and retention labels</span></span>

<span data-ttu-id="a0eed-146">Gebruik [bewaarbeleid en bewaarlabels om](../compliance/retention.md) inhoud in Microsoft 365 te behouden of te verwijderen die persoonlijke gegevens bevat of naar verwachting bevat.</span><span class="sxs-lookup"><span data-stu-id="a0eed-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="a0eed-147">Records Management</span><span class="sxs-lookup"><span data-stu-id="a0eed-147">Records management</span></span>

<span data-ttu-id="a0eed-148">Gebruik bewaarlabels die inhoud als record declareeren om een [recordbeheeroplossing](../compliance/records-management.md) voor gegevens in Microsoft 365 te implementeren.</span><span class="sxs-lookup"><span data-stu-id="a0eed-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="a0eed-149">Voor gegevensbescherming worden verzoeken van gegevensonderwerpen (DSR's) die door de juridische afdeling zijn ontvangen, als record gedeclareerd en kunnen ze voor onbepaalde tijd worden opgeslagen of met bewijs worden verwijderd, om te voldoen aan de bewaarspecificaties voor regelgevingsactiviteit.</span><span class="sxs-lookup"><span data-stu-id="a0eed-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>