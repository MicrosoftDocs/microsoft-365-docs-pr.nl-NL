---
title: Bepalen welke informatie onderworpen is aan de regelgeving voor data privacy
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
description: U kunt de Microsoft 365-Bewaar labels en-beleidsregels gebruiken voor het beheren van persoonlijke gegevens in uw Microsoft 365-omgeving.
ms.openlocfilehash: 766995b9c758d4ae8cbf7140fb259d208cfb7771
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949250"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="e2f9b-103">Bepalen welke informatie onderworpen is aan de regelgeving voor data privacy</span><span class="sxs-lookup"><span data-stu-id="e2f9b-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="e2f9b-104">De beheerfuncties voor informatiebeheer kunnen in uw omgeving worden gebruikt om gegevens aan te vullen ter informatie, waaronder een nummer dat specifiek bedoeld is voor de algemene verordening gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse gezondheids verzorging van de gezondheids verzorging), Californië voor consumentenbescherming (CCPA) en de wet Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="e2f9b-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="e2f9b-105">De volgende besturingselementen zijn in eerste instantie ingedeeld in de volgende oplossings gebieden:</span><span class="sxs-lookup"><span data-stu-id="e2f9b-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="e2f9b-106">Bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="e2f9b-106">Retention policies</span></span>
- <span data-ttu-id="e2f9b-107">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="e2f9b-107">Retention labels</span></span>
- <span data-ttu-id="e2f9b-108">Records Management</span><span class="sxs-lookup"><span data-stu-id="e2f9b-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="e2f9b-109">Voorschriften voor de privacy van gegevensbeheer</span><span class="sxs-lookup"><span data-stu-id="e2f9b-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="e2f9b-110">Hieronder ziet u een voorbeeld van een lijst met voorschriften voor de privacy van gegevens die in verband met informatiebeheer kunnen worden beheerd:</span><span class="sxs-lookup"><span data-stu-id="e2f9b-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="e2f9b-111">AVG artikel (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="e2f9b-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="e2f9b-112">AVG artikel (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="e2f9b-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="e2f9b-113">HIPAA-HITECH (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="e2f9b-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="e2f9b-114">HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="e2f9b-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="e2f9b-115">HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))</span><span class="sxs-lookup"><span data-stu-id="e2f9b-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="e2f9b-116">LGPD artikel 46</span><span class="sxs-lookup"><span data-stu-id="e2f9b-116">LGPD Article 46</span></span>

<span data-ttu-id="e2f9b-117">Zie voor meer informatie over deze voorschriften het [artikel privacyinstellingen voor gegevens en identificeren van gevoelige informatie](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="e2f9b-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="e2f9b-118">Voor informatiebeheer: voor informatiebeheer worden meestal de volgende gegevens verzameld:</span><span class="sxs-lookup"><span data-stu-id="e2f9b-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="e2f9b-119">U dient een technisch stelsel te gebruiken voor bewaren en verwijderen van persoonlijke gegevens die zijn opgeslagen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="e2f9b-120">Als u persoonlijke gegevens wilt opslaan, kunt u het onderwerp van de hoeveelheid werk dat de gegevens bevat, op de front-endwebservers toepassen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="e2f9b-121">Persoonlijke gegevens moeten tegen onbedoelde verwerking, verlies of wijziging via verifieerbare methoden beschermd worden.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="e2f9b-122">Elke actie die wordt uitgevoerd met persoonlijke gegevens moet worden gedocumenteerd en de documentatie moet worden bewaard gedurende een bepaalde periode.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="e2f9b-123">Aangezien de regelgeving voor gegevensbescherming niet zeer specifiek is voor het bewaren en verwijderen van gegevens, moeten andere factoren in rekening worden gebracht waarbij informatie over de beleidsregels voor informatiebeheer voor persoonlijke gegevens die zijn opgeslagen in uw abonnement op Microsoft 365, kunnen worden gedicteerd.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="e2f9b-124">Hier volgen enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="e2f9b-124">Here are a few examples:</span></span>

- <span data-ttu-id="e2f9b-125">Verouderde consumenten accounts na 5 jaar inactiviteit en vereist het verwijderen of anonimiseren van rekeninggegevens na dit punt, waarbij de gegevens en werkstromen die zijn gekoppeld aan meldingen en andere automatisering, worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="e2f9b-126">Het instellen van regels voor het behoud van beleid en procedures met betrekking tot AVG rond drie jaar nadat deze zijn vervangen, wat is uitgelijnd met het bewaarschema van de organisatie voor beleidsregels en procedures.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="e2f9b-127">Het onderhouden van een apart abonnement voor het communiceren met consumenten via zijn ondersteunings organisatie.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="e2f9b-128">Alle e-mailberichten werden na twee weken bewaard en verwijderd om de privacy van buildup in het systeem te verminderen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="e2f9b-129">U kunt op de volgende belangrijke vragen beantwoorden:</span><span class="sxs-lookup"><span data-stu-id="e2f9b-129">A key question to answer is:</span></span> 

- <span data-ttu-id="e2f9b-130">Hoelang is informatie die persoonlijke gegevens bevat, moet worden bewaard voor geldige zakelijke redenen om te voorkomen dat u de functie permanent houdt.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="e2f9b-131">Dit moet evenwichtig zijn met de Bewaar behoeften voor bedrijfscontinuïteit.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="e2f9b-132">Ongeacht de juridische en zakelijke redenen voor het behoud van persoonlijke gegevens rond of te verwijderen, biedt Microsoft een aantal mogelijkheden om uw gegevensbeheer schema te implementeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="e2f9b-133">Information governance beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2f9b-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="e2f9b-134">Zie [Gegevensbeheer](../compliance/manage-information-governance.md) en [gegevens behoud, verwijdering en vernietiging beheren in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)als u wilt beginnen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="e2f9b-135">Schema voor het bewaren van gegevens voor containers, e-mail en inhoud ontwikkelen</span><span class="sxs-lookup"><span data-stu-id="e2f9b-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="e2f9b-136">Houd het volgende in gedachten:</span><span class="sxs-lookup"><span data-stu-id="e2f9b-136">Keep the following in mind:</span></span>

- <span data-ttu-id="e2f9b-137">Het maken van een bewaarschema voor gegevens voor gedefinieerde gegevenstypen moet als vereiste gelden voor het implementeren van een bewaarschema of een verwijderings schema.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="e2f9b-138">Op basis van het aantal gegevenstypen dat de meeste organisaties belangrijk achten en de bijbehorende bewaarschema's voor uitgebreide records die samen met hen doen, moet u de plannings-en beheer strategie voor gegevens en recordbeheer implementeren.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="e2f9b-139">De sleutel voor het opzetten van een effectieve strategie voor gegevensbeheer van dit type is de nadruk op de zakelijke functies met de hoogste prioriteit, en gegevenstypen die een formeler beheer vereisen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="e2f9b-140">Voorbeelden hiervan zijn juridische contracten, financiële overzichten en documentatie over regelgevings naleving.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="e2f9b-141">U kunt voorkomen dat er een apart Bewaarschema voor elk afzonderlijk gegevenstype wordt weergeven.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="e2f9b-142">U kunt zo veel mogelijk algemene categorieën gebruiken, bijvoorbeeld met bewaarschema's van 7 jaar voor algemene bedrijfs inhoud.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="e2f9b-143">Wanneer de typen persoonlijke gegevens in uw omgeving beter bekend zijn, kunt u schema's voor het bewaren en verwijderen van bestanden vastleggen, en de informatiearchitectuur aanpassen om het beheer van deze gegevens te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="e2f9b-144">U kunt bijvoorbeeld persoonlijke gegevens op afzonderlijke sites, bibliotheken of mappen isoleren met Controlled Access.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="e2f9b-145">Bewaarbeleid en labels voor bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="e2f9b-145">Retention policies and retention labels</span></span>

<span data-ttu-id="e2f9b-146">Gebruik [bewaarbeleid en labels voor bewaarbeleid](../compliance/retention.md) om inhoud te behouden of te verwijderen in microsoft 365 met of naar verwachting om persoonlijke gegevens te bevatten.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="e2f9b-147">Records Management</span><span class="sxs-lookup"><span data-stu-id="e2f9b-147">Records management</span></span>

<span data-ttu-id="e2f9b-148">Labels voor bewaarbeleid gebruiken waarmee inhoud een record wordt gedeclareerd om een [oplossing voor recordbeheer](../compliance/records-management.md) voor gegevens te implementeren in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="e2f9b-149">Voor de privacy van gegevens (DSRs) die door de juridische afdeling worden ontvangen, wordt een record gedeclareerd en kan hij voor het behoud van het behoud van de regelgeving voorbehoud van de regelgeving van de juridische afdeling een record indienen.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

