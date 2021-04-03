---
title: Meldingen over incidenten in Microsoft 365 Defender ontvangen
description: Meer informatie over het maken van regels voor het ontvangen van e-mailmeldingen voor incidenten in Microsoft 365 Defender
keywords: incident, e-mail, e-mail notfications, configureren, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501074"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="41091-104">Meldingen van incidenten per e-mail ontvangen</span><span class="sxs-lookup"><span data-stu-id="41091-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="41091-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="41091-105">**Applies to:**</span></span>
- <span data-ttu-id="41091-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41091-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="41091-107">U kunt Microsoft 365 Defender zo instellen dat u per e-mail op de hoogte wordt gehouden wanneer er nieuwe incidenten of nieuwe updates voor bestaande incidenten zijn.</span><span class="sxs-lookup"><span data-stu-id="41091-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="41091-108">U kunt ervoor kiezen om meldingen te ontvangen op basis van de ernst van het incident of per apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="41091-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="41091-109">U kunt er ook voor kiezen om alleen een melding te ontvangen bij de eerste update per incident.</span><span class="sxs-lookup"><span data-stu-id="41091-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="41091-110">U kunt geadresseerden toevoegen of verwijderen in de e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="41091-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="41091-111">Nieuwe geadresseerden krijgen een melding over incidenten nadat ze zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="41091-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="41091-112">De e-mailmelding bevat belangrijke details over het incident, zoals de naam van het incident, de ernst en de categorieën.</span><span class="sxs-lookup"><span data-stu-id="41091-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="41091-113">U kunt ook rechtstreeks naar incidenten gaan, zodat u meteen een onderzoek kunt starten.</span><span class="sxs-lookup"><span data-stu-id="41091-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="41091-114">Zie Incidenten onderzoeken [in Microsoft 365 Defender](./investigate-incidents.md)voor meer informatie over het onderzoeken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="41091-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="41091-115">U hebt machtigingen voor beveiligingsinstellingen beheren nodig om instellingen voor e-mailmeldingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="41091-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="41091-116">Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met beveiligingsbeheerder- of globale beheerdersrollen e-mailmeldingen voor u configureren.</span><span class="sxs-lookup"><span data-stu-id="41091-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="41091-117">Als uw organisatie op rollen gebaseerd toegangsbeheer (RBAC) gebruikt, kunt u alleen meldingen maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.</span><span class="sxs-lookup"><span data-stu-id="41091-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="41091-118">Regels maken voor incidentenmeldingen</span><span class="sxs-lookup"><span data-stu-id="41091-118">Create rules for incident notifications</span></span>

<span data-ttu-id="41091-119">Als u uw eerste e-mailmelding voor incidenten wilt instellen, maakt u een nieuwe regel en past u de instellingen voor e-mailmeldingen aan.</span><span class="sxs-lookup"><span data-stu-id="41091-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="41091-120">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Incident-e-mailmeldingen**.</span><span class="sxs-lookup"><span data-stu-id="41091-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="41091-121">Selecteer **Item toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="41091-121">Select **Add item**.</span></span>
3. <span data-ttu-id="41091-122">Geef de regel een naam in **Naam en** geef een **beschrijving op.**</span><span class="sxs-lookup"><span data-stu-id="41091-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Regelvenster maken voor e-mailincidenten voor incidenten](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="41091-124">Selecteer **Volgende** om naar **Meldingsinstellingen te gaan.**</span><span class="sxs-lookup"><span data-stu-id="41091-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="41091-125">Hier kunt u opgeven:</span><span class="sxs-lookup"><span data-stu-id="41091-125">Here you can specify:</span></span>
    - <span data-ttu-id="41091-126">**Ernst van waarschuwing:** kies de ernst van de waarschuwing die een melding van een incident veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="41091-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="41091-127">Als u bijvoorbeeld alleen op de hoogte wilt zijn van incidenten met hoge ernst, selecteert u Hoog.</span><span class="sxs-lookup"><span data-stu-id="41091-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="41091-128">**Bereik van apparaatgroep:** in deze vervolgkeuzekeuze wordt alle apparaatgroepen weergegeven die de gebruiker kan openen.</span><span class="sxs-lookup"><span data-stu-id="41091-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="41091-129">Selecteer voor welke apparaatgroepen u de regels voor incidentenmelding maakt.</span><span class="sxs-lookup"><span data-stu-id="41091-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="41091-130">**Alleen een melding bij eerste incident:** als u deze optie selecteert, wordt alleen een e-mailmelding verzonden bij de eerste waarschuwing die overeenkomt met uw andere selecties.</span><span class="sxs-lookup"><span data-stu-id="41091-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="41091-131">Latere updates of waarschuwingen met betrekking tot het incident leiden niet tot een melding.</span><span class="sxs-lookup"><span data-stu-id="41091-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="41091-132">**Naam van organisatie opnemen:** geeft aan of de klantnaam wordt weergegeven in de e-mailmelding of niet.</span><span class="sxs-lookup"><span data-stu-id="41091-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="41091-133">**Tenantspecifieke portalkoppeling opnemen:** hiermee voegt u een koppeling met de tenant-id toe om toegang tot een specifieke tenant toe te staan.</span><span class="sxs-lookup"><span data-stu-id="41091-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="41091-135">Selecteer **Volgende** om naar de **sectie Geadresseerden te** gaan.</span><span class="sxs-lookup"><span data-stu-id="41091-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="41091-136">Hier kunt u e-mailadressen opgeven die de meldingen voor incident-e-mail ontvangen.</span><span class="sxs-lookup"><span data-stu-id="41091-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="41091-137">Selecteer **Een geadresseerde toevoegen nadat** u elk e-mailadres hebt typen.</span><span class="sxs-lookup"><span data-stu-id="41091-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Venster Geadresseerden toevoegen voor incidentele e-mailincidenten](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="41091-139">Selecteer ten slotte **Volgende om** naar Regel controleren **te gaan,** zodat u alle instellingen kunt zien die aan de nieuwe regel zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="41091-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="41091-140">Geadresseerden ontvangen incidentmeldingen via e-mail op basis van de instellingen.</span><span class="sxs-lookup"><span data-stu-id="41091-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="41091-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="41091-141">See also</span></span>
- [<span data-ttu-id="41091-142">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41091-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="41091-143">Prioriteit geven aan incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41091-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="41091-144">Incidenten in Microsoft 365 Defender onderzoeken</span><span class="sxs-lookup"><span data-stu-id="41091-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)
