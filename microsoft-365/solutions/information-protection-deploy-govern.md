---
title: Informatie regelen die onderworpen is aan de privacywetgeving
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
description: Gebruik microsoft 365-bewaarlabels en -beleidsregels om persoonlijke gegevens in uw Microsoft 365-omgeving te beheren.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522299"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="9090d-103">Informatie regelen die onderworpen is aan de privacywetgeving</span><span class="sxs-lookup"><span data-stu-id="9090d-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="9090d-104">Informatie governance controles kunnen worden gebruikt in uw omgeving om te helpen bij het aanpakken van de naleving van gegevens privacy behoeften, met inbegrip van een nummer dat specifiek is voor de Algemene Verordening Gegevensbescherming (GDPR), HIPAA-HITECH (de Verenigde Staten privacy wet), California Consumer Protection Act (CCPA), en de Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="9090d-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="9090d-105">Deze controles vallen voornamelijk in de volgende oplossingsgebieden:</span><span class="sxs-lookup"><span data-stu-id="9090d-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="9090d-106">Bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="9090d-106">Retention policies</span></span>
- <span data-ttu-id="9090d-107">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="9090d-107">Retention labels</span></span>
- <span data-ttu-id="9090d-108">Records Management</span><span class="sxs-lookup"><span data-stu-id="9090d-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="9090d-109">Regelgeving voor gegevensprivacy die van invloed is op de controles op informatiebeheer</span><span class="sxs-lookup"><span data-stu-id="9090d-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="9090d-110">Hier is een voorbeeld van regelgeving voor gegevensprivacy die betrekking kunnen hebben op controles op informatiebeheer:</span><span class="sxs-lookup"><span data-stu-id="9090d-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="9090d-111">GDPR-artikel (13,2) onder a)</span><span class="sxs-lookup"><span data-stu-id="9090d-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="9090d-112">AVG-artikel (5, lid 1, onder f)</span><span class="sxs-lookup"><span data-stu-id="9090d-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="9090d-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="9090d-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="9090d-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="9090d-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="9090d-115">HIPAA-HITECH (45 CFR 164.316(b)(1)ii))</span><span class="sxs-lookup"><span data-stu-id="9090d-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="9090d-116">LGPD Artikel 46</span><span class="sxs-lookup"><span data-stu-id="9090d-116">LGPD Article 46</span></span>

<span data-ttu-id="9090d-117">Voor meer informatie over deze regelgeving, zie de [beoordeling van de privacy van gegevens risico's en identificeren gevoelige informatie artikel](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="9090d-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="9090d-118">Voor informatiegovernance vragen gegevensprivacyregelgeving doorgaans om het volgende:</span><span class="sxs-lookup"><span data-stu-id="9090d-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="9090d-119">U moet een technische regeling hanteren voor bewaring en verwijdering van persoonsgegevens die zijn opgeslagen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9090d-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="9090d-120">Als u persoonlijke gegevens gaat opslaan, informeer dan het onderwerp van hoe lang de gegevens worden opgeslagen, wat nu een standaardpraktijk is op front-end websystemen.</span><span class="sxs-lookup"><span data-stu-id="9090d-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="9090d-121">Persoonsgegevens moeten worden beschermd tegen onbedoelde verwerking, verlies of wijziging met behulp van verifieerbare methoden.</span><span class="sxs-lookup"><span data-stu-id="9090d-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="9090d-122">Elke actie die tegen persoonsgegevens wordt uitgevoerd, moet worden gedocumenteerd en dat documentatie gedurende een bepaalde periode moet worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="9090d-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="9090d-123">Omdat de regelgeving voor gegevensprivacy niet erg specifiek is als het gaat om het bewaren en verwijderen van gegevens, moeten andere factoren in aanmerking worden genomen die richtlijnen voor informatiebeheer kunnen dicteren voor persoonlijke gegevens die zijn opgeslagen in uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="9090d-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="9090d-124">Hier zijn een paar voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="9090d-124">Here are a few examples:</span></span>

- <span data-ttu-id="9090d-125">Het verouderen van consumentenaccounts na 5 jaar inactiviteit en vereist verwijdering of anonimisering van accountgegevens na dat punt, waarbij orkestratie tussen het systeem moet worden opgeslagen en de gegevens en workflows die verband houden met meldingen en andere automatisering.</span><span class="sxs-lookup"><span data-stu-id="9090d-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="9090d-126">Het configureren van regels voor het bijhouden van beleid en procedures met betrekking tot gdpr gedurende drie jaar nadat ze zijn vervangen, wat overeenkomt met het bewaarschema van de organisatie voor beleid en procedures.</span><span class="sxs-lookup"><span data-stu-id="9090d-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="9090d-127">Het onderhouden van een apart abonnement voor communicatie met consumenten via de ondersteuningsorganisatie.</span><span class="sxs-lookup"><span data-stu-id="9090d-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="9090d-128">Alle e-mailcommunicatie werd na twee weken bewaard en verwijderd om eventuele opbouw van privacyschulden in het systeem te verminderen.</span><span class="sxs-lookup"><span data-stu-id="9090d-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="9090d-129">Een belangrijke vraag om te beantwoorden is:</span><span class="sxs-lookup"><span data-stu-id="9090d-129">A key question to answer is:</span></span> 

- <span data-ttu-id="9090d-130">Hoe lang moet informatie met persoonsgegevens worden bewaard om geldige zakelijke redenen om te voorkomen dat het voor altijd wordt bewaard?</span><span class="sxs-lookup"><span data-stu-id="9090d-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="9090d-131">Dit moet in evenwicht worden gebracht met de retentiebehoeften voor bedrijfscontinuïteit.</span><span class="sxs-lookup"><span data-stu-id="9090d-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="9090d-132">Ongeacht de juridische en zakelijke redenen om persoonlijke gegevens rond te houden of te verwijderen, biedt Microsoft een aantal mogelijkheden om uw gegevensbeheerschema in Microsoft 365 te implementeren.</span><span class="sxs-lookup"><span data-stu-id="9090d-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="9090d-133">Informatiebeheer beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9090d-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="9090d-134">Zie [Informatiebeheer](../compliance/manage-information-governance.md) en [gegevensbewaring, verwijdering en vernietiging beheren in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)als u wilt beginnen.</span><span class="sxs-lookup"><span data-stu-id="9090d-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="9090d-135">Bewaarschema's voor gegevens voor containers, e-mail en inhoud ontwikkelen</span><span class="sxs-lookup"><span data-stu-id="9090d-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="9090d-136">Houd het volgende in gedachten:</span><span class="sxs-lookup"><span data-stu-id="9090d-136">Keep the following in mind:</span></span>

- <span data-ttu-id="9090d-137">Het opstellen van een gegevensbewaringsschema voor gedefinieerde informatietypen moet worden beschouwd als een voorwaarde voor de uitvoering van een bewaar- of verwijderingsschema.</span><span class="sxs-lookup"><span data-stu-id="9090d-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="9090d-138">Gezien het aantal informatietypen dat de meeste organisaties belangrijk vinden en de bijbehorende grote bewaarschema's voor records die daarbij passen, vereist het implementeren van een strategie voor het bewaren van gegevens en recordsbeheer planning.</span><span class="sxs-lookup"><span data-stu-id="9090d-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="9090d-139">De sleutel tot het opzetten van een effectieve data governance strategie van dit type is om zich te concentreren op de hoogste prioriteit zakelijke functies en informatietypen die meer formeel beheer vereisen.</span><span class="sxs-lookup"><span data-stu-id="9090d-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="9090d-140">Voorbeelden zijn juridische contracten, jaarrekeningen en documentatie over naleving van de regelgeving.</span><span class="sxs-lookup"><span data-stu-id="9090d-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="9090d-141">Probeer te voorkomen dat u een apart bewaarschema voor elk informatietype hebt.</span><span class="sxs-lookup"><span data-stu-id="9090d-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="9090d-142">Probeer algemene categorieën zoveel mogelijk te gebruiken, bijvoorbeeld met bewaarschema's van 7 jaar voor algemene bedrijfsinhoud.</span><span class="sxs-lookup"><span data-stu-id="9090d-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="9090d-143">Zodra de typen persoonlijke gegevens in uw omgeving beter bekend zijn, stelt u bewaar- en verwijderingsschema's voor dit type inhoud vast en past u uw informatiearchitectuur aan om het beheer van dit soort informatie gemakkelijker te maken.</span><span class="sxs-lookup"><span data-stu-id="9090d-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="9090d-144">Dit is bijvoorbeeld het isoleren van persoonlijke gegevens in afzonderlijke sites, bibliotheken of mappen met gecontroleerde toegang.</span><span class="sxs-lookup"><span data-stu-id="9090d-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="9090d-145">Bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="9090d-145">Retention policies</span></span>

<span data-ttu-id="9090d-146">[Retentiebeleid](../compliance/retention-policies.md) maken en implementeren voor inhoud in sites die automatisch worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="9090d-146">Create and deploy [retention policies](../compliance/retention-policies.md) for content in sites that are automatically applied.</span></span>

<span data-ttu-id="9090d-147">Voor gegevensprivacy voor sites die persoonsgegevens bevatten of naar verwachting bevatten, moet u bewaar- of verwijderingsregels opgeven om aan de organisatienormen te voldoen.</span><span class="sxs-lookup"><span data-stu-id="9090d-147">For data privacy for sites that contain or are expected to contain personal data, specify retention or deletion rules to address organizational standards.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="9090d-148">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="9090d-148">Retention labels</span></span>

<span data-ttu-id="9090d-149">[Retentielabels](../compliance/labels.md) maken en implementeren voor inhoud en e-mail.</span><span class="sxs-lookup"><span data-stu-id="9090d-149">Create and deploy [retention labels](../compliance/labels.md) for content and email.</span></span>

<span data-ttu-id="9090d-150">Voor gegevensprivacy voor sites, bibliotheken, mappen en e-mail die persoonlijke gegevens bevatten of naar verwachting bevatten, worden regels voor automatisch bewaren of verwijderen opgegeven om aan de organisatienormen te voldoen.</span><span class="sxs-lookup"><span data-stu-id="9090d-150">For data privacy for sites, libraries, folders, and email that contain or are expected to contain personal data, specify auto retention or deletion rules to address organizational standards.</span></span>

### <a name="records-management"></a><span data-ttu-id="9090d-151">Records Management</span><span class="sxs-lookup"><span data-stu-id="9090d-151">Records management</span></span>

<span data-ttu-id="9090d-152">Retentielabels maken en implementeren voor recordsbeheer op basis van een bewaarschema en bestandsplan voor records.</span><span class="sxs-lookup"><span data-stu-id="9090d-152">Create and deploy retention labels for records management based on a records retention schedule and file plan.</span></span>

<span data-ttu-id="9090d-153">Voor gegevensprivacy worden verzoeken van betrokkenen (DSR's) die door de juridische afdeling zijn ontvangen, als record gedeclareerd en voor onbepaalde tijd opgeslagen om te voldoen aan de specificaties voor het bewaren van activiteiten in de regelgeving.</span><span class="sxs-lookup"><span data-stu-id="9090d-153">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and stored indefinitely to adhere to regulatory activity retention specifications.</span></span>

<span data-ttu-id="9090d-154">Zie deze bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="9090d-154">See these resources for more information:</span></span> 

- [<span data-ttu-id="9090d-155">Records Management</span><span class="sxs-lookup"><span data-stu-id="9090d-155">Records Management</span></span>](../compliance/records-management.md)
- [<span data-ttu-id="9090d-156">Bestandsplanbeheer</span><span class="sxs-lookup"><span data-stu-id="9090d-156">File plan manager</span></span>](../compliance/file-plan-manager.md)
- [<span data-ttu-id="9090d-157">Op gebeurtenissen gebaseerde retentie voor recordsbeheer</span><span class="sxs-lookup"><span data-stu-id="9090d-157">Event-based retention for records management</span></span>](../compliance/automate-event-driven-retention.md)
- [<span data-ttu-id="9090d-158">Inhoudsverklaring</span><span class="sxs-lookup"><span data-stu-id="9090d-158">Disposition of content</span></span>](../compliance/disposition-reviews.md)
