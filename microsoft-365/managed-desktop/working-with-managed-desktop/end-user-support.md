---
title: Gebruikersondersteuning voor Microsoft Managed Desktop
description: Hoe gebruikers hulp kunnen krijgen bij de service en apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362604"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="87d3a-104">Hulp aanvragen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="87d3a-104">Getting help for users</span></span>

<span data-ttu-id="87d3a-105">Als u het punt in de [werkstroom](../service-description/user-support.md) hebt bereikt waarop u toegang tot een verhoogd apparaat of escalatie bij Microsoft moet aanvragen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="87d3a-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="87d3a-106">Deze ondersteuningsopties zijn niet beschikbaar voor apparaten in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="87d3a-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="87d3a-107">Hoogte-aanvragen</span><span class="sxs-lookup"><span data-stu-id="87d3a-107">Elevation requests</span></span>

<span data-ttu-id="87d3a-108">Voordat u verhoogde toegang tot een apparaat aanvraagt, kunt u het beste bekijken welke acties het meest geschikt zijn.</span><span class="sxs-lookup"><span data-stu-id="87d3a-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="87d3a-109">**Typische acties** zijn waarvoor dit proces is bedoeld en worden routinematig uitgevoerd tijdens het oplossen van problemen met Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="87d3a-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="87d3a-110">Voorbeelden hiervan zijn:</span><span class="sxs-lookup"><span data-stu-id="87d3a-110">Examples include:</span></span>
    - <span data-ttu-id="87d3a-111">Ingebouwde probleemoplossers voor het systeem, de opdrachtprompt of de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87d3a-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="87d3a-112">Problemen met zakelijke toepassingen oplossen</span><span class="sxs-lookup"><span data-stu-id="87d3a-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="87d3a-113">Een tijdelijke oplossing gebruiken om iets te corrigeren dat automatisch moet werken (zoals BitLocker-activering of systeemtijd die niet wordt bijgewerkt)</span><span class="sxs-lookup"><span data-stu-id="87d3a-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="87d3a-114">Apparaatbeheer verheffen om dingen te doen zoals stuurprogramma's bijwerken, een apparaat verwijderen of nieuwe wijzigingen scannen</span><span class="sxs-lookup"><span data-stu-id="87d3a-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="87d3a-115">**Acties die niet worden aanbevolen, zijn** de volgende:</span><span class="sxs-lookup"><span data-stu-id="87d3a-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="87d3a-116">Software of browsers installeren</span><span class="sxs-lookup"><span data-stu-id="87d3a-116">Installing software or browsers</span></span>
    - <span data-ttu-id="87d3a-117">Stuurprogramma's installeren buiten Windows instellingen, inclusief stuurprogramma's voor randapparatuur</span><span class="sxs-lookup"><span data-stu-id="87d3a-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="87d3a-118">Bestanden .msi of .exe installeren</span><span class="sxs-lookup"><span data-stu-id="87d3a-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="87d3a-119">Functies voor Windows installeren</span><span class="sxs-lookup"><span data-stu-id="87d3a-119">Installing Windows features</span></span>

- <span data-ttu-id="87d3a-120">**Acties die niet worden ondersteund,** zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="87d3a-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="87d3a-121">Software of functies installeren die conflicteren met Microsoft Managed Desktop beveiligings- of beheerfuncties of -bewerkingen</span><span class="sxs-lookup"><span data-stu-id="87d3a-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="87d3a-122">Een functie Windows uitschakelen die is vereist voor Microsoft Managed Desktop, zoals BitLocker</span><span class="sxs-lookup"><span data-stu-id="87d3a-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="87d3a-123">Instellingen wijzigen die worden beheerd door uw organisatie</span><span class="sxs-lookup"><span data-stu-id="87d3a-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="87d3a-124">Hoogte aanvragen</span><span class="sxs-lookup"><span data-stu-id="87d3a-124">To request elevation</span></span>

1. <span data-ttu-id="87d3a-125">Ga naar de portal bij [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) en meld u aan met uw Azure Active Directory referenties.</span><span class="sxs-lookup"><span data-stu-id="87d3a-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="87d3a-126">Selecteer **Nieuwe hoogte-aanvraag.**</span><span class="sxs-lookup"><span data-stu-id="87d3a-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="87d3a-127">Geef deze details op:</span><span class="sxs-lookup"><span data-stu-id="87d3a-127">Provide these details:</span></span>
    - <span data-ttu-id="87d3a-128">**Ondersteuningsticket-id** van uw eigen ondersteuningsticketsysteem.</span><span class="sxs-lookup"><span data-stu-id="87d3a-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="87d3a-129">**Apparaatnaam:** voer het serienummer van het apparaat in en selecteer het apparaat in het menu.</span><span class="sxs-lookup"><span data-stu-id="87d3a-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="87d3a-130">**Categorie:** Selecteer de categorie die het beste bij uw probleem past.</span><span class="sxs-lookup"><span data-stu-id="87d3a-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="87d3a-131">Als er geen optie lijkt te sluiten, **selecteert** u Overige en geeft u meer informatie op in de velden **Titel** en **Plan van** actie.</span><span class="sxs-lookup"><span data-stu-id="87d3a-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="87d3a-132">U kunt het beste een categorie selecteren als dat mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="87d3a-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="87d3a-133">**Subcategorie:** Selecteer de categorie die het beste bij het probleem past.</span><span class="sxs-lookup"><span data-stu-id="87d3a-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="87d3a-134">Als er geen optie lijkt te sluiten, **selecteert** u Overige en geeft u een korte beschrijving op in **Titel.**</span><span class="sxs-lookup"><span data-stu-id="87d3a-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="87d3a-135">Geef **in Plan van actie** de stappen voor het oplossen van problemen op die u wilt ondernemen zodra de hoogte is verleend.</span><span class="sxs-lookup"><span data-stu-id="87d3a-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="87d3a-136">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="87d3a-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="87d3a-137">Escalatieaanvragen</span><span class="sxs-lookup"><span data-stu-id="87d3a-137">Escalation requests</span></span>


<span data-ttu-id="87d3a-138">Als u een probleem [wilt escaleren](../service-description/user-support.md#escalation-portal) naar Microsoft, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="87d3a-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="87d3a-139">Ga naar de portal bij [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) en meld u aan met uw Azure Active Directory referenties.</span><span class="sxs-lookup"><span data-stu-id="87d3a-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="87d3a-140">Selecteer **Escalatieaanvragen** en selecteer vervolgens **Nieuwe escalatieaanvraag.**</span><span class="sxs-lookup"><span data-stu-id="87d3a-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="87d3a-141">Geef deze details op:</span><span class="sxs-lookup"><span data-stu-id="87d3a-141">Provide these details:</span></span>
    - <span data-ttu-id="87d3a-142">**Categorie:** Selecteer de categorie die het beste bij uw probleem past.</span><span class="sxs-lookup"><span data-stu-id="87d3a-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="87d3a-143">**Titel:** Geef een zeer korte beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="87d3a-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="87d3a-144">**Beschrijving:** Voeg aanvullende details toe die ons team kunnen helpen het probleem te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="87d3a-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="87d3a-145">Als u bestanden wilt toevoegen, kunt u dit doen door terug te keren naar de aanvraag nadat u deze hebt ingediend.</span><span class="sxs-lookup"><span data-stu-id="87d3a-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="87d3a-146">**Primaire contactgegevens:** geef informatie over hoe u contact op kunt nemen met de hoofdpersoon die verantwoordelijk is voor het werken met ons team.</span><span class="sxs-lookup"><span data-stu-id="87d3a-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="87d3a-147">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="87d3a-147">Select **Submit**.</span></span>
5. <span data-ttu-id="87d3a-148">Bekijk het ticket opnieuw in dezelfde portal om met ons team te communiceren.</span><span class="sxs-lookup"><span data-stu-id="87d3a-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="87d3a-149">Alleen problemen met ernst C kunnen via dit pad worden geëscaleerd.</span><span class="sxs-lookup"><span data-stu-id="87d3a-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="87d3a-150">Neem voor andere problemen contact op met uw IT-beheerder om de aanvraag in te sturen via de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="87d3a-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>