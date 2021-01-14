---
title: Incident meldingen ontvangen in Microsoft 365 Defender
description: Leer hoe u regels maakt voor het ontvangen van e-mail meldingen voor incidenten in Microsoft 365 Defender
keywords: incident, e-mail, e-notfications, configureren, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848889"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="dbd1c-104">Incident meldingen ontvangen via e-mail</span><span class="sxs-lookup"><span data-stu-id="dbd1c-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dbd1c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="dbd1c-105">**Applies to:**</span></span>
- <span data-ttu-id="dbd1c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbd1c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dbd1c-107">U kunt Microsoft 365 Defender zo instellen dat u per e-mail op de hoogte wordt gesteld wanneer er nieuwe incidenten of nieuwe updates zijn voor bestaande incidenten.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="dbd1c-108">U kunt ervoor kiezen om meldingen te ontvangen op basis van de ernst van het incident of de groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="dbd1c-109">U kunt er ook voor kiezen om een melding te ontvangen bij de eerste update per incident.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="dbd1c-110">U kunt geadresseerden toevoegen aan of verwijderen uit de e-mail meldingen.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="dbd1c-111">Toegevoegde geadresseerden ontvangen een melding over incidenten nadat ze zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="dbd1c-112">De e-mail melding bevat belangrijke informatie over het incident, zoals de naam van het incident, de ernst en de categorieën.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="dbd1c-113">U kunt ook rechtstreeks naar incidenten gaan, zodat u direct aan de slag kunt met uw onderzoek.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="dbd1c-114">Zie [incidenten onderzoeken in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)voor meer informatie over het onderzoeken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="dbd1c-115">U wilt de machtigingen van de beveiligingsinstellingen beheren om instellingen voor e-mail meldingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="dbd1c-116">Als u hebt gekozen voor het gebruik van basismachtigingen beheer, kunnen gebruikers met beveiligingsbeheerders of globale beheerdersrollen e-mail meldingen voor u configureren.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="dbd1c-117">Ook als uw organisatie gebruikmaakt van een toegangsbeheer op basis van rollen, kunt u alleen een bericht maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="dbd1c-118">Regels voor incident meldingen maken</span><span class="sxs-lookup"><span data-stu-id="dbd1c-118">Create rules for incident notifications</span></span>

<span data-ttu-id="dbd1c-119">Als u uw eerste e-mail melding voor incidenten wilt instellen, maakt u een nieuwe regel en wijzigt u de instellingen voor e-mail meldingen.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="dbd1c-120">Selecteer in het navigatiedeelvenster **instellingen** voor  >  **e-mail meldingen van incidenten**.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="dbd1c-121">Selecteer **item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-121">Select **Add item**.</span></span>
3. <span data-ttu-id="dbd1c-122">Geef een **naam op voor** de regel en typ een **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Het venster regel maken voor e-mail notifs voor incidenten](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="dbd1c-124">Selecteer **volgende** om naar de **instellingen voor meldingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="dbd1c-125">Hier kunt u het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="dbd1c-125">Here you can specify:</span></span>
    - <span data-ttu-id="dbd1c-126">**Ernst van waarschuwing** : Kies de ernst van de waarschuwing waarmee de melding van een incident wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="dbd1c-127">Als u bijvoorbeeld alleen op de hoogte wilt blijven van hoge urgentie, selecteert u hoog.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="dbd1c-128">**Bereik van apparaat** : in deze vervolgkeuzelijst worden alle apparaatgroepen weergegeven waartoe de gebruiker toegang kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="dbd1c-129">Selecteer voor welke apparaatgroepen u de regels voor incident meldingen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="dbd1c-130">**Alleen op de hoogte van het eerste exemplaar per voorval melden** : als u deze optie selecteert, wordt een e-mail melding alleen verzonden bij de eerste waarschuwing die overeenkomt met uw andere keuzes.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="dbd1c-131">Later updates of waarschuwingen met betrekking tot het incident veroorzaken geen meldingen.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="dbd1c-132">**Naam van organisatie opnemen** : geeft aan of de naam van de klant wordt weergegeven in de e-mail melding of niet.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="dbd1c-133">**Tenant-specifieke Portal koppeling toevoegen** : Hiermee wordt een koppeling met de Tenant-id toegevoegd om toegang tot een specifieke Tenant mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Venster met instellingen voor e-mailbericht voor e-mail notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="dbd1c-135">Selecteer **volgende** om naar de sectie **geadresseerden** te gaan.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="dbd1c-136">Hier kunt u e-mailadressen opgeven waarop e-mail meldingen van incidenten worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="dbd1c-137">Selecteer **een geadresseerde toevoegen na het** typen van elk e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Venster geadresseerden toevoegen voor e-mail notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="dbd1c-139">Selecteer ten slotte **volgende** om naar de **regel controleren** te gaan zodat u alle instellingen kunt zien van de nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="dbd1c-140">Geadresseerden ontvangen via e-mail incident meldingen via e-mail, op basis van de instellingen.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbd1c-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dbd1c-141">See also</span></span>
- [<span data-ttu-id="dbd1c-142">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbd1c-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="dbd1c-143">Incidenten prioriteren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbd1c-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="dbd1c-144">Gebeurtenissen onderzoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbd1c-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

