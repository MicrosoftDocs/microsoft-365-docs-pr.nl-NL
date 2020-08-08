---
title: Licentie aanvragen beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Lees hoe u licentie aanvragen controleert en goedkeurt of afwijst van gebruikers voor uw Microsoft 365 for Business-abonnement.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597652"
---
# <a name="manage-license-requests"></a><span data-ttu-id="2e45e-103">Licentie aanvragen beheren</span><span class="sxs-lookup"><span data-stu-id="2e45e-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="2e45e-104">De informatie in dit artikel is alleen van toepassing op self-service gekochte producten.</span><span class="sxs-lookup"><span data-stu-id="2e45e-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="2e45e-105">Voor meer informatie raadpleegt u [Veelgestelde vragen over self-service aankopen](../subscriptions/self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="2e45e-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="2e45e-106">Als u selfservice aankopen uitschakelt voor uw organisatie, kunt u licentie aanvragen gebruiken voor het beheren van het licentieaanvraag proces voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="2e45e-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="2e45e-107">Wanneer een gebruiker een selfservice aankoop wil maken voor een product dat u hebt geblokkeerd, kunnen ze een aanvraag indienen voor een licentie voor u, de beheerder. Wanneer ze een aanvraag doen, kunnen ze de namen van andere gebruikers toevoegen die ook licenties voor het product nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="2e45e-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="2e45e-108">Als u wilt voorkomen dat gebruikers selfservice aankopen doen, verzendt Microsoft ze geen marketing-e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="2e45e-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="2e45e-109">Als ze een evaluatieversie van een product gebruiken, worden deze niet meer weergegeven om de prompt te kopen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="2e45e-110">Zie [selfservice aankopen beheren (beheerder)](../subscriptions/manage-self-service-purchases-admins.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e45e-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="2e45e-111">Voor het weergeven en beheren van licentie aanvragen gebruikt de beheerder het tabblad **aanvragen** op de pagina **licentie** .</span><span class="sxs-lookup"><span data-stu-id="2e45e-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="2e45e-112">In deze lijst wordt de naam weergegeven van het product dat u nodig hebt, de naam van de persoon die een licentie aanvraagt, de gevraagde datum en de status van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2e45e-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="2e45e-113">Beheerders kunnen de lijst filteren om aanvragen weer te geven die in behandeling zijn of die zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="2e45e-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="2e45e-114">Aanvragen worden 30 dagen lang gehouden.</span><span class="sxs-lookup"><span data-stu-id="2e45e-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2e45e-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="2e45e-115">Before you begin</span></span>

<span data-ttu-id="2e45e-116">U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2e45e-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="2e45e-117">Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e45e-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="2e45e-118">Uw eigen aanvraagproces gebruiken</span><span class="sxs-lookup"><span data-stu-id="2e45e-118">Use your own request process</span></span>

<span data-ttu-id="2e45e-119">Als uw organisatie een eigen aanvraagproces heeft, kunt u dit in plaats daarvan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2e45e-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="2e45e-120">U maakt een bericht dat wordt weergegeven voor gebruikers wanneer ze een licentie aanvragen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e45e-121">Als u uw eigen aanvraagproces gebruikt, worden er geen aanvragen weergegeven op het tabblad **aanvragen** . bestaande aanvragen van voordat u het bericht hebt toegevoegd, worden pas weergegeven wanneer u ze goedkeurt of afwijst.</span><span class="sxs-lookup"><span data-stu-id="2e45e-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="2e45e-122">Ga in het Beheercentrum naar de pagina **factuur**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> en selecteer het tabblad **aanvragen** .</span><span class="sxs-lookup"><span data-stu-id="2e45e-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="2e45e-123">Selecteer **in plaats daarvan uw bestaande aanvraagproces gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="2e45e-124">Typ in het rechterdeelvenster **het bericht dat** gebruikers moeten zien wanneer ze een licentie aanvragen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="2e45e-125">Als u ook een koppeling naar het beleid van uw organisatie of andere documentatie wilt opnemen, typt u de URL in het tekstvak **koppeling naar documentatie (optioneel)** .</span><span class="sxs-lookup"><span data-stu-id="2e45e-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="2e45e-126">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-126">Select **Save**.</span></span>

<span data-ttu-id="2e45e-127">Wanneer u terugkeert naar de lijst **aanvragen** , wordt het bericht weergegeven **dat u uw eigen licentie verwerkingsproces gebruikt**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="2e45e-128">Als u wijzigingen wilt aanbrengen in het bericht dat naar gebruikers wordt verzonden, selecteert u **in plaats daarvan uw bestaande aanvraagproces**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="2e45e-129">Uw eigen aanvraagproces beëindigen</span><span class="sxs-lookup"><span data-stu-id="2e45e-129">Stop using your own request process</span></span>

1. <span data-ttu-id="2e45e-130">Ga in het Beheercentrum naar de pagina **factuur**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> en selecteer het tabblad **aanvragen** .</span><span class="sxs-lookup"><span data-stu-id="2e45e-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="2e45e-131">Selecteer **in plaats daarvan uw bestaande aanvraagproces gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="2e45e-132">Schakel in het rechterdeelvenster het selectievakje de **verzoeken van mijn organisatie gebruiken** uit.</span><span class="sxs-lookup"><span data-stu-id="2e45e-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="2e45e-133">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="2e45e-134">Een licentieaanvraag goedkeuren of weigeren</span><span class="sxs-lookup"><span data-stu-id="2e45e-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="2e45e-135">Ga in het Beheercentrum naar de pagina **factuur**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> en selecteer het tabblad **aanvragen** .</span><span class="sxs-lookup"><span data-stu-id="2e45e-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="2e45e-136">Selecteer de rij met de aanvraag die u wilt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="2e45e-137">Het rechterdeelvenster bevat details over welke gebruikerslicenties voor het product willen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="2e45e-138">Als u de hele aanvraag wilt weigeren, selecteert u **niet goedkeuren**en selecteert u **niet goedkeuren**in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="2e45e-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="2e45e-139">Als u bepaalde gebruikers voor de aanvraag wilt blokkeren, maar anderen wilt goedkeuren, selecteert u de X op de naam van de gebruikers die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="2e45e-140">De namen worden verplaatst onder **niet toewijzen aan deze gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="2e45e-141">Als u meer dan één product hebt, selecteert u onder **Selecteer een product**de persoon voor wie u een licentie wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="2e45e-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="2e45e-142">Als u wilt dat gebruikers toegang hebben tot bepaalde apps en services, schakelt u **apps en services in of uit**en schakelt u vervolgens de selectievakjes uit voor de items die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="2e45e-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="2e45e-143">Typ onder in het deelvenster een optioneel bericht in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="2e45e-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="2e45e-144">Wanneer u klaar bent, selecteert u **goedkeuren**.</span><span class="sxs-lookup"><span data-stu-id="2e45e-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="2e45e-145">Het rechterdeelvenster toont de details van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2e45e-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="2e45e-146">Sluit het rechterdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="2e45e-146">Close the right pane.</span></span>
    <span data-ttu-id="2e45e-147">Gebruikers ontvangen een e-mailbericht met de mededeling dat hun verzoek is goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="2e45e-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="2e45e-148">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2e45e-148">Related content</span></span>

<span data-ttu-id="2e45e-149">[Licenties toewijzen aan gebruikers](../../admin/manage/assign-licenses-to-users.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="2e45e-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="2e45e-150">[Gebruikers verplaatsen naar een ander abonnement](../subscriptions/move-users-different-subscription.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="2e45e-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="2e45e-151">[Abonnementslicenties kopen of verwijderen](buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2e45e-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>