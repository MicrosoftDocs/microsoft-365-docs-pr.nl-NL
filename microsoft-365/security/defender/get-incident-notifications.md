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
ms.openlocfilehash: 72a1f8fe71efcfa7f4f73671611576a454b508e6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861311"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="fcea1-104">Meldingen van incidenten per e-mail ontvangen</span><span class="sxs-lookup"><span data-stu-id="fcea1-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fcea1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fcea1-105">**Applies to:**</span></span>
- <span data-ttu-id="fcea1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcea1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fcea1-107">U kunt Microsoft 365 Defender instellen om uw personeel via een e-mail op de hoogte te stellen van nieuwe incidenten of updates voor bestaande incidenten.</span><span class="sxs-lookup"><span data-stu-id="fcea1-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="fcea1-108">U kunt ervoor kiezen om meldingen te ontvangen op basis van:</span><span class="sxs-lookup"><span data-stu-id="fcea1-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="fcea1-109">Incident ernst.</span><span class="sxs-lookup"><span data-stu-id="fcea1-109">Incident severity.</span></span>
- <span data-ttu-id="fcea1-110">Apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="fcea1-110">Device group.</span></span>
- <span data-ttu-id="fcea1-111">Alleen bij de eerste update per incident.</span><span class="sxs-lookup"><span data-stu-id="fcea1-111">Only on the first update per incident.</span></span>

<span data-ttu-id="fcea1-112">De e-mailmelding bevat belangrijke details over het incident, zoals de naam van het incident, de ernst en de categorieën.</span><span class="sxs-lookup"><span data-stu-id="fcea1-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="fcea1-113">U kunt ook rechtstreeks naar het incident gaan en uw onderzoek direct starten.</span><span class="sxs-lookup"><span data-stu-id="fcea1-113">You can also go directly to the incident and start your investigation right away.</span></span> <span data-ttu-id="fcea1-114">Zie Incidenten [onderzoeken voor meer informatie.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="fcea1-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="fcea1-115">U kunt geadresseerden toevoegen of verwijderen in de e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="fcea1-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="fcea1-116">Nieuwe geadresseerden krijgen een melding over incidenten nadat ze zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="fcea1-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="fcea1-117">U hebt de machtiging Beveiligingsinstellingen beheren nodig om instellingen voor e-mailmeldingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="fcea1-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="fcea1-118">Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met beveiligingsbeheerder- of globale beheerdersrollen e-mailmeldingen voor u configureren.</span><span class="sxs-lookup"><span data-stu-id="fcea1-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="fcea1-119">Als uw organisatie op rollen gebaseerd toegangsbeheer (RBAC) gebruikt, kunt u alleen meldingen maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.</span><span class="sxs-lookup"><span data-stu-id="fcea1-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="fcea1-120">Een regel maken voor e-mailmeldingen</span><span class="sxs-lookup"><span data-stu-id="fcea1-120">Create a rule for email notifications</span></span>

<span data-ttu-id="fcea1-121">Volg deze stappen om een nieuwe regel te maken en instellingen voor e-mailmeldingen aan te passen.</span><span class="sxs-lookup"><span data-stu-id="fcea1-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="fcea1-122">Selecteer in het navigatiedeelvenster **Instellingen > Microsoft 365 Defender > Meldingen van incidenten.**</span><span class="sxs-lookup"><span data-stu-id="fcea1-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="fcea1-123">Selecteer **Item toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fcea1-123">Select **Add item**.</span></span>
3. <span data-ttu-id="fcea1-124">Typ op **de** pagina Basisbeginselen de regelnaam en een beschrijving en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="fcea1-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="fcea1-125">Configureer **op de pagina** Meldingsinstellingen:</span><span class="sxs-lookup"><span data-stu-id="fcea1-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="fcea1-126">**Ernst van waarschuwing:** kies de ernst van de waarschuwing die een melding van een incident veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="fcea1-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="fcea1-127">Als u bijvoorbeeld alleen op de hoogte wilt zijn van incidenten met hoge ernst, selecteert u **Hoog**.</span><span class="sxs-lookup"><span data-stu-id="fcea1-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="fcea1-128">**Bereik van apparaatgroep:** u kunt alle apparaatgroepen opgeven of selecteren in de lijst met apparaatgroepen in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="fcea1-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="fcea1-129">**Alleen een melding bij eerste gebeurtenis per incident-** Selecteer of u alleen een melding wilt ontvangen bij de eerste waarschuwing die overeenkomt met uw andere selecties.</span><span class="sxs-lookup"><span data-stu-id="fcea1-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="fcea1-130">Latere updates of waarschuwingen met betrekking tot het incident sturen geen extra meldingen.</span><span class="sxs-lookup"><span data-stu-id="fcea1-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="fcea1-131">**Naam van organisatie opnemen in het e-mailbericht:** selecteer of de naam van uw organisatie moet worden weergegeven in de e-mailmelding.</span><span class="sxs-lookup"><span data-stu-id="fcea1-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="fcea1-132">**Tenantspecifieke portalkoppeling** opnemen: selecteer of u een koppeling met de tenant-id wilt toevoegen in de e-mailmelding voor toegang tot een specifieke Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="fcea1-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Meldingsinstellingen voor meldingen van incidenten":::

5. <span data-ttu-id="fcea1-134">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fcea1-134">Select **Next**.</span></span> <span data-ttu-id="fcea1-135">Voeg op **de pagina** Geadresseerden de e-mailadressen toe die de incidentenmeldingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="fcea1-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="fcea1-136">Selecteer **Toevoegen nadat** u elk nieuw e-mailadres hebt typen.</span><span class="sxs-lookup"><span data-stu-id="fcea1-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="fcea1-137">Als u meldingen wilt testen en wilt controleren of de geadresseerden deze ontvangen in de Postvak IN, selecteert u **Test-e-mail verzenden.**</span><span class="sxs-lookup"><span data-stu-id="fcea1-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="fcea1-138">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fcea1-138">Select **Next**.</span></span> <span data-ttu-id="fcea1-139">Controleer op **de pagina** Regel controleren de instellingen van de regel en selecteer regel **maken.**</span><span class="sxs-lookup"><span data-stu-id="fcea1-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="fcea1-140">Geadresseerden ontvangen incidentmeldingen via e-mail op basis van de instellingen.</span><span class="sxs-lookup"><span data-stu-id="fcea1-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="fcea1-141">Als u een bestaande regel wilt bewerken, selecteert u deze in de lijst met regels.</span><span class="sxs-lookup"><span data-stu-id="fcea1-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="fcea1-142">Selecteer regel bewerken in het  deelvenster met de regelnaam en wijzig de regels op de pagina's Basisbeginselen, Instellingen voor meldingen **en** **Geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="fcea1-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="fcea1-143">Als u een bestaande regel wilt bewerken, selecteert u deze in de lijst met regels.</span><span class="sxs-lookup"><span data-stu-id="fcea1-143">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="fcea1-144">Selecteer verwijderen in het deelvenster met de **regelnaam.**</span><span class="sxs-lookup"><span data-stu-id="fcea1-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcea1-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fcea1-145">See also</span></span>
- [<span data-ttu-id="fcea1-146">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="fcea1-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fcea1-147">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="fcea1-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="fcea1-148">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="fcea1-148">Investigate incidents</span></span>](investigate-incidents.md)
