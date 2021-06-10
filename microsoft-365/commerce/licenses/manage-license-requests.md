---
title: Licentieaanvragen beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Meer informatie over het controleren en goedkeuren of weigeren van licentieaanvragen van gebruikers voor uw Microsoft 365 voor bedrijven-abonnement.
ms.date: 08/07/2020
ms.openlocfilehash: 6cbfd81f4f6deba642729f1fef0b826b07a99f56
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535672"
---
# <a name="manage-license-requests"></a><span data-ttu-id="b3d6c-103">Licentieaanvragen beheren</span><span class="sxs-lookup"><span data-stu-id="b3d6c-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="b3d6c-104">De informatie in dit artikel is alleen van toepassing op selfservice aangeschafte producten.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="b3d6c-105">Zie Veelgestelde vragen over [selfservice-aankopen voor meer informatie.](../subscriptions/self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="b3d6c-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="b3d6c-106">Als u selfserviceaankopen in uw organisatie uit schakelt, kunt u licentiesaanvragen gebruiken om het proces voor het aanvragen van licenties voor uw gebruikers te beheren.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="b3d6c-107">Wanneer een gebruiker een selfserviceaankoop probeert te doen voor een product dat u hebt geblokkeerd, kan hij of zij een aanvraag voor een licentie indienen bij u, de beheerder. Wanneer ze een aanvraag indienen, kunnen ze de namen toevoegen van andere gebruikers die ook licenties nodig hebben voor het product.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="b3d6c-108">Als u blokkeert dat gebruikers selfservice-aankopen doen, verzendt Microsoft geen marketing-e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="b3d6c-109">Als ze een proefversie van een product gebruiken, zien ze ook geen aanwijzingen om het te kopen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="b3d6c-110">Zie [SelfService-aankopen beheren (Beheerder) voor meer informatie.](../subscriptions/manage-self-service-purchases-admins.md)</span><span class="sxs-lookup"><span data-stu-id="b3d6c-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="b3d6c-111">Voor het bekijken en beheren van licentieaanvragen gebruikt de beheerder **het** tabblad Aanvragen op de **pagina Licentieverlening.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="b3d6c-112">De lijst bevat de naam van het product dat wordt aangevraagd, de naam van de persoon die een licentie aanvraagt, de aangevraagde datum en de status van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="b3d6c-113">Beheerders kunnen de lijst filteren om aanvragen weer te geven die in behandeling of voltooid zijn.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="b3d6c-114">Aanvragen worden 30 dagen gehouden.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b3d6c-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b3d6c-115">Before you begin</span></span>

<span data-ttu-id="b3d6c-116">U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="b3d6c-117">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="b3d6c-118">Uw eigen aanvraagproces gebruiken</span><span class="sxs-lookup"><span data-stu-id="b3d6c-118">Use your own request process</span></span>

<span data-ttu-id="b3d6c-119">Als uw organisatie een eigen aanvraagprocedure heeft, kunt u deze in plaats daarvan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="b3d6c-120">U maakt een bericht dat wordt weergegeven voor gebruikers wanneer ze een licentie aanvragen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3d6c-121">Als u uw eigen aanvraagprocedure gebruikt, worden er geen aanvragen weergegeven op het **tabblad** Aanvragen. Bestaande aanvragen van voordat u het bericht hebt toegevoegd, blijven verschijnen totdat u deze goedkeurt of weigert.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="b3d6c-122">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties</a> en selecteer vervolgens het **tabblad Aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="b3d6c-123">Selecteer **In plaats daarvan uw bestaande aanvraagproces gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="b3d6c-124">Typ in het rechterdeelvenster in **het** vak Bericht het bericht dat gebruikers moeten zien wanneer ze een licentie aanvragen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="b3d6c-125">Als u ook een koppeling naar uw organisatiebeleid of andere documentatie wilt opnemen, voert u de URL in het tekstvak Koppeling naar **documentatie (optioneel)** in.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="b3d6c-126">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-126">Select **Save**.</span></span>

<span data-ttu-id="b3d6c-127">Wanneer u terugkeert naar de lijst **Aanvragen,** ziet u het bericht **U gebruikt uw eigen licentieaanvraagproces.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="b3d6c-128">Als u wijzigingen wilt aanbrengen in het bericht dat naar gebruikers wordt verzonden, selecteert u In plaats daarvan **Uw bestaande aanvraagproces gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="b3d6c-129">Stoppen met het gebruik van uw eigen aanvraagproces</span><span class="sxs-lookup"><span data-stu-id="b3d6c-129">Stop using your own request process</span></span>

1. <span data-ttu-id="b3d6c-130">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties</a> en selecteer vervolgens het **tabblad Aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="b3d6c-131">Selecteer **In plaats daarvan uw bestaande aanvraagproces gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="b3d6c-132">In het rechterdeelvenster kunt u het selectievakje **Aanvraagproces** van mijn organisatie gebruiken uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="b3d6c-133">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="b3d6c-134">Een licentieaanvraag goedkeuren of weigeren</span><span class="sxs-lookup"><span data-stu-id="b3d6c-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="b3d6c-135">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties</a> en selecteer vervolgens het **tabblad Aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="b3d6c-136">Selecteer de rij met de aanvraag die u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="b3d6c-137">In het rechterdeelvenster ziet u details over welke gebruikers licenties voor het product willen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="b3d6c-138">Als u de hele aanvraag wilt weigeren, **selecteert** u Niet goedkeuren en selecteert u in het dialoogvenster **Niet goedkeuren.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="b3d6c-139">Als u sommige gebruikers voor de aanvraag wilt weigeren, maar anderen wilt goedkeuren, selecteert u de X op de naam van de gebruikers die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="b3d6c-140">Hun namen worden verplaatst onder **Niet toewijzen aan deze gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="b3d6c-141">Als u meer dan één product hebt, selecteert u onder **Selecteer een product** het product dat u wilt gebruiken om licenties voor toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="b3d6c-142">Als u gebruikers de toegang tot bepaalde apps en services wilt weigeren, vouwt u Apps en **services** in- of uitschakelen uit en schakelt u de selectievakjes uit voor de apps die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="b3d6c-143">Typ onder aan het deelvenster een optioneel bericht in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="b3d6c-144">Wanneer u klaar bent, selecteert u **Goedkeuren.**</span><span class="sxs-lookup"><span data-stu-id="b3d6c-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="b3d6c-145">In het rechterdeelvenster ziet u de details van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="b3d6c-146">Sluit het rechterdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-146">Close the right pane.</span></span>
    <span data-ttu-id="b3d6c-147">Gebruikers ontvangen een e-mailbericht met de informatie dat hun aanvraag is goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="b3d6c-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="b3d6c-148">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b3d6c-148">Related content</span></span>

<span data-ttu-id="b3d6c-149">[Licenties toewijzen aan gebruikers](../../admin/manage/assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b3d6c-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="b3d6c-150">[Gebruikers verplaatsen naar een ander abonnement](../subscriptions/move-users-different-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b3d6c-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="b3d6c-151">[Abonnementslicenties kopen of verwijderen](buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b3d6c-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
