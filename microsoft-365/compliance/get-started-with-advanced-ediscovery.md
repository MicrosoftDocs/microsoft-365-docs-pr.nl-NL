---
title: Een Advanced eDiscovery instellen in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u een Advanced eDiscovery zo kunt instellen dat u zaken kunt maken en beheren. Ook worden de vereiste Microsoft-abonnementen en -licenties beschreven. Nadat u een paar snelle stappen hebt voltooid, is Advanced eDiscovery klaar voor gebruik.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161983"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="62bcc-105">Een Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="62bcc-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="62bcc-106">Advanced eDiscovery in Microsoft 365 biedt een end-to-end werkstroom voor het bewaren, verzamelen, controleren, analyseren en exporteren van gegevens die reageren op interne en externe onderzoeken van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="62bcc-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="62bcc-107">Er is niets nodig om Advanced eDiscovery te implementeren, maar er zijn enkele vereiste taken die een IT-beheerder en eDiscovery-manager moeten uitvoeren voordat uw organisatie kan beginnen met het maken en gebruiken van Advanced eDiscovery-zaken om uw onderzoeken te beheren.</span><span class="sxs-lookup"><span data-stu-id="62bcc-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="62bcc-108">In dit artikel worden de volgende stappen beschreven die nodig zijn voor het instellen van Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="62bcc-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![Stappen voor het instellen van Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="62bcc-110">Dit omvat het waarborgen van de juiste licenties die nodig zijn voor toegang tot Advanced eDiscovery en het toevoegen van voogden aan zaken, en het toewijzen van machtigingen aan uw juridische en onderzoeksteam, zodat ze zaken kunnen openen en beheren.</span><span class="sxs-lookup"><span data-stu-id="62bcc-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="62bcc-111">Stap 1: De juiste licenties controleren en toewijzen</span><span class="sxs-lookup"><span data-stu-id="62bcc-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="62bcc-112">Licenties voor Advanced eDiscovery vereist het juiste organisatieabonnement en licenties per gebruiker.</span><span class="sxs-lookup"><span data-stu-id="62bcc-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="62bcc-113">Zie Abonnementen en licenties voor een lijst met licentievereisten voor Advanced eDiscovery [licenties.](overview-ediscovery-20.md#subscriptions-and-licensing)</span><span class="sxs-lookup"><span data-stu-id="62bcc-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="62bcc-114">Stap 2: eDiscovery-machtigingen toewijzen</span><span class="sxs-lookup"><span data-stu-id="62bcc-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="62bcc-115">Als u toegang Advanced eDiscovery of toegevoegd als lid van een Advanced eDiscovery geval, moet aan een gebruiker de juiste machtigingen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="62bcc-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="62bcc-116">Een gebruiker moet met name worden toegevoegd als lid van de rollengroep eDiscovery Manager in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="62bcc-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="62bcc-117">Leden van deze rollengroep kunnen een aantal Advanced eDiscovery maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="62bcc-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="62bcc-118">Ze kunnen leden toevoegen en verwijderen, beheerders en inhoudslocaties in de wacht zetten, meldingen over juridische wacht houden beheren, zoekopdrachten maken en bewerken die aan een zaak zijn gekoppeld, zoekresultaten toevoegen aan een revisieset, gegevens analyseren in een revisieset en exporteren en downloaden vanuit een Advanced eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="62bcc-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="62bcc-119">Volg de volgende stappen om gebruikers toe te voegen aan de rollengroep eDiscovery Manager:</span><span class="sxs-lookup"><span data-stu-id="62bcc-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="62bcc-120">Ga naar <https://protection.office.com/permissions> en meld u aan met de referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="62bcc-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="62bcc-121">Selecteer op **de pagina** Machtigingen de **rollengroep eDiscovery Manager.**</span><span class="sxs-lookup"><span data-stu-id="62bcc-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="62bcc-122">Klik op de flyoutpagina van eDiscovery Manager op **Bewerken** naast de **sectie eDiscovery Manager.**</span><span class="sxs-lookup"><span data-stu-id="62bcc-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="62bcc-123">Klik op **de pagina eDiscovery Manager** kiezen in de wizard Rollengroep bewerken op **EDiscovery Manager kiezen.**</span><span class="sxs-lookup"><span data-stu-id="62bcc-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="62bcc-124">Klik **op** Toevoegen en schakel het selectievakje in voor alle gebruikers die u wilt toevoegen aan de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="62bcc-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="62bcc-125">Klik **op Toevoegen** om de geselecteerde gebruikers toe te voegen en klik vervolgens op **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="62bcc-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="62bcc-126">Klik **op** Opslaan om de gebruikers toe te voegen aan de rollengroep en klik vervolgens op **Sluiten** om de stap te voltooien.</span><span class="sxs-lookup"><span data-stu-id="62bcc-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="62bcc-127">Meer informatie over de rollengroep eDiscovery Manager</span><span class="sxs-lookup"><span data-stu-id="62bcc-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="62bcc-128">Er zijn twee subgroepen in de rollengroep eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="62bcc-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="62bcc-129">Het verschil tussen deze subgroepen is gebaseerd op bereik.</span><span class="sxs-lookup"><span data-stu-id="62bcc-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="62bcc-130">**eDiscovery Manager:** kan de verschillende Advanced eDiscovery die ze maken of lid zijn van weergeven en beheren.</span><span class="sxs-lookup"><span data-stu-id="62bcc-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="62bcc-131">Als een andere eDiscovery Manager een zaak maakt, maar geen tweede eDiscovery Manager toevoegt als lid van die zaak, kan de tweede eDiscovery Manager de zaak niet weergeven of openen op de pagina Advanced eDiscovery in het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="62bcc-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="62bcc-132">Over het algemeen kunnen de meeste personen in uw organisatie worden toegevoegd aan de subgroep eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="62bcc-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="62bcc-133">**eDiscovery-beheerder:** kan alle casebeheertaken uitvoeren die een eDiscovery Manager kan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="62bcc-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="62bcc-134">Bovendien kan een eDiscovery-beheerder:</span><span class="sxs-lookup"><span data-stu-id="62bcc-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="62bcc-135">Bekijk alle zaken die worden weergegeven op de Advanced eDiscovery pagina.</span><span class="sxs-lookup"><span data-stu-id="62bcc-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="62bcc-136">Beheer hoe dan ook in de organisatie nadat ze zichzelf hebben toevoegen als lid van de zaak.</span><span class="sxs-lookup"><span data-stu-id="62bcc-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="62bcc-137">Toegang tot en export van casegegevens voor elk geval in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="62bcc-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="62bcc-138">Vanwege het grote bereik van toegang moet een organisatie slechts een paar beheerders hebben die lid zijn van de subgroep eDiscovery-beheerders.</span><span class="sxs-lookup"><span data-stu-id="62bcc-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="62bcc-139">Zie eDiscovery-machtigingen toewijzen voor meer informatie over [eDiscovery-machtigingen](assign-ediscovery-permissions.md)en een beschrijving van elke rol die is toegewezen aan de rollengroep eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="62bcc-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="62bcc-140">Stap 3: Algemene instellingen configureren voor Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="62bcc-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="62bcc-141">De laatste stap die moet worden voltooid voordat personen in uw organisatie zaken gaan maken en gebruiken, is het configureren van algemene instellingen die van toepassing zijn op alle zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="62bcc-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="62bcc-142">Op dit moment is de enige globale instelling de detectie van *advocaten-clientvoorrechten* (in de toekomst zijn er meer algemene instellingen beschikbaar).</span><span class="sxs-lookup"><span data-stu-id="62bcc-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="62bcc-143">Met deze instelling kan het privilegemodel voor advocatenclient worden uitgevoerd wanneer u gegevens in een revisieset analyseert.</span><span class="sxs-lookup"><span data-stu-id="62bcc-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="62bcc-144">Het model maakt gebruik van machine learning om de kans te bepalen dat een document inhoud bevat die juridisch van aard is.</span><span class="sxs-lookup"><span data-stu-id="62bcc-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="62bcc-145">Ook worden de deelnemers aan documenten vergeleken met een advocatenlijst (die u indient bij het instellen van het model) om te bepalen of een document ten minste één deelnemer heeft die een advocaat is.</span><span class="sxs-lookup"><span data-stu-id="62bcc-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="62bcc-146">Zie Detectie van advocaten-clientvoorrechten instellen in Advanced eDiscovery voor meer informatie over het instellen en gebruiken van het detectiemodel voor [advocaten-clientrechten.](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="62bcc-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="62bcc-147">Dit is een optionele stap die u op elk gewenst moment kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="62bcc-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="62bcc-148">Als u het detectiemodel voor advocaten-clientvoorrechten niet implementeert, kunt u geen nieuwe Advanced eDiscovery maken.</span><span class="sxs-lookup"><span data-stu-id="62bcc-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="62bcc-149">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="62bcc-149">Next steps</span></span>

<span data-ttu-id="62bcc-150">Nadat u een Advanced eDiscovery hebt ingesteld, kunt u een [zaak maken.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="62bcc-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>