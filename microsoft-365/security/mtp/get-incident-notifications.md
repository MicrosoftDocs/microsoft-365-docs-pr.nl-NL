---
title: Meldingen over incidenten ontvangen in Microsoft 365 Defender
description: Informatie over het maken van regels om e-mailmeldingen te ontvangen voor incidenten in Microsoft 365 Defender
keywords: incident, e-mail, e-mailbevestigingen, configureren, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
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
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930976"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="3047d-104">Ontvang incidentenmeldingen per e-mail</span><span class="sxs-lookup"><span data-stu-id="3047d-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3047d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3047d-105">**Applies to:**</span></span>
- <span data-ttu-id="3047d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3047d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3047d-107">U kunt Microsoft 365 Defender zo instellen dat u per e-mail op de hoogte wordt gehouden wanneer er nieuwe incidenten of nieuwe updates van bestaande incidenten zijn.</span><span class="sxs-lookup"><span data-stu-id="3047d-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="3047d-108">U kunt ervoor kiezen om meldingen te ontvangen op basis van de ernst van het incident of per apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="3047d-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="3047d-109">U kunt er ook voor kiezen om alleen bij de eerste update per incident een melding te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="3047d-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="3047d-110">U kunt geadresseerden toevoegen aan of verwijderen uit de e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="3047d-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="3047d-111">Pas toegevoegde geadresseerden ontvangen een melding over incidenten nadat ze zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="3047d-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="3047d-112">De e-mailmelding bevat belangrijke details over het incident, zoals de naam van het incident, de ernst en categorieën.</span><span class="sxs-lookup"><span data-stu-id="3047d-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="3047d-113">U kunt ook rechtstreeks naar incidenten gaan, zodat u meteen een onderzoek kunt starten.</span><span class="sxs-lookup"><span data-stu-id="3047d-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="3047d-114">Zie Incidenten in [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)onderzoeken voor meer informatie over het onderzoeken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="3047d-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="3047d-115">U hebt machtigingen voor het beheren van beveiligingsinstellingen nodig om instellingen voor e-mailmeldingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="3047d-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="3047d-116">Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met de rollen Beveiligingsbeheerder of Globale beheerder e-mailmeldingen voor u configureren.</span><span class="sxs-lookup"><span data-stu-id="3047d-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="3047d-117">En als uw organisatie toegangsbeheer op basis van rollen gebruikt, kunt u alleen meldingen maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.</span><span class="sxs-lookup"><span data-stu-id="3047d-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="3047d-118">Regels maken voor incidentenmeldingen</span><span class="sxs-lookup"><span data-stu-id="3047d-118">Create rules for incident notifications</span></span>

<span data-ttu-id="3047d-119">Als u uw eerste e-mailmelding voor incidenten wilt instellen, maakt u een nieuwe regel en past u instellingen voor e-mailmeldingen aan.</span><span class="sxs-lookup"><span data-stu-id="3047d-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="3047d-120">Selecteer in het navigatiedeelvenster **E-mailmeldingen**  >  **instellingen-incident.**</span><span class="sxs-lookup"><span data-stu-id="3047d-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="3047d-121">Selecteer **Item toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="3047d-121">Select **Add item**.</span></span>
3. <span data-ttu-id="3047d-122">Geef de regel een naam in **Naam** en geef een **beschrijving op.**</span><span class="sxs-lookup"><span data-stu-id="3047d-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Venster Regel maken voor e-mailincidenten](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="3047d-124">Selecteer **Volgende om** naar Instellingen voor meldingen te **gaan.**</span><span class="sxs-lookup"><span data-stu-id="3047d-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="3047d-125">Hier kunt u het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="3047d-125">Here you can specify:</span></span>
    - <span data-ttu-id="3047d-126">**Ernst van de waarschuwing:** kies de ernst van de waarschuwing die een incidentmelding activeert.</span><span class="sxs-lookup"><span data-stu-id="3047d-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="3047d-127">Als u bijvoorbeeld alleen op de hoogte wilt zijn van incidenten met hoge ernst, selecteert u Hoog.</span><span class="sxs-lookup"><span data-stu-id="3047d-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="3047d-128">**Bereik van apparaatgroep:** in deze vervolgkeuzen ziet u alle apparaatgroepen waar de gebruiker toegang toe heeft.</span><span class="sxs-lookup"><span data-stu-id="3047d-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="3047d-129">Selecteer voor welke apparaatgroepen u de meldingsregels voor incidenten maakt.</span><span class="sxs-lookup"><span data-stu-id="3047d-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="3047d-130">**Alleen melden bij eerste exemplaar per incident.** Als u deze optie selecteert, wordt alleen een e-mailmelding verzonden die overeenkomt met uw andere selecties.</span><span class="sxs-lookup"><span data-stu-id="3047d-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="3047d-131">Latere updates of waarschuwingen met betrekking tot het incident activeren geen melding.</span><span class="sxs-lookup"><span data-stu-id="3047d-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="3047d-132">**De naam van de organisatie** opnemen: hiermee wordt aangegeven of de naam van de klant al dan niet in de e-mailmelding wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3047d-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="3047d-133">**Inclusief tenantspecifieke portalkoppeling:** hiermee voegt u een koppeling met de tenant-id toe voor toegang tot een specifieke tenant.</span><span class="sxs-lookup"><span data-stu-id="3047d-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Venster Notif-instellingen voor notif-instellingen voor e-mailincidenten](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="3047d-135">Selecteer **Volgende** om naar de sectie **Geadresseerden te** gaan.</span><span class="sxs-lookup"><span data-stu-id="3047d-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="3047d-136">Hier kunt u e-mailadressen opgeven die de e-mailmeldingen voor het incident ontvangen.</span><span class="sxs-lookup"><span data-stu-id="3047d-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="3047d-137">Selecteer **Een geadresseerde toevoegen nadat** u elk e-mailadres hebt typen.</span><span class="sxs-lookup"><span data-stu-id="3047d-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Venster Geadresseerden toevoegen voor notifs voor incidentele e-mail](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="3047d-139">Selecteer ten slotte **Volgende om** naar de regel Controleren **te gaan,** zodat u alle instellingen ziet die aan de nieuwe regel zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="3047d-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="3047d-140">Geadresseerden ontvangen incidentmeldingen via e-mail op basis van de instellingen.</span><span class="sxs-lookup"><span data-stu-id="3047d-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="3047d-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3047d-141">See also</span></span>
- [<span data-ttu-id="3047d-142">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3047d-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="3047d-143">Prioriteit geven aan incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3047d-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="3047d-144">Incidenten in Microsoft 365 Defender onderzoeken</span><span class="sxs-lookup"><span data-stu-id="3047d-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

