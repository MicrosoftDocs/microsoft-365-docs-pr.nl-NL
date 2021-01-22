---
title: Doorsturen van e‑mail configureren
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Het doorsturen van e-mail naar een of meer e-mailaccounts instellen met Office365.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926640"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="7ee16-103">Doorsturen van e-mail configureren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ee16-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7ee16-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7ee16-104">The admin center is changing.</span></span> <span data-ttu-id="7ee16-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="7ee16-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="7ee16-106">Als beheerder van een organisatie hebt u misschien te maken met bedrijfsvereisten voor het instellen van het doorsturen van e-mail voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="7ee16-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="7ee16-107">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="7ee16-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ee16-108">U kunt uitgaand spamfilterbeleid gebruiken om automatische doorsturen naar externe geadresseerden te bepalen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="7ee16-109">Zie Automatische doorsturen van [externe e-mail instellen in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7ee16-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="7ee16-110">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="7ee16-110">Configure email forwarding</span></span>

<span data-ttu-id="7ee16-111">Houd rekening met het volgende voordat u het doorsturen van e-mail in stelt:</span><span class="sxs-lookup"><span data-stu-id="7ee16-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="7ee16-112">Wanneer u het doorsturen  van e-mail  hebt ingesteld, worden alleen nieuwe e-mailberichten doorgestuurd die naar het postvak van dat postvak worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="7ee16-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="7ee16-113">Voor het doorsturen van  *e-mail moet het*  account een licentie hebben.</span><span class="sxs-lookup"><span data-stu-id="7ee16-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="7ee16-114">Als u het doorsturen van e-mail instelt omdat de gebruiker uw organisatie heeft verlaten, kunt u het postvak converteren naar [een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="7ee16-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="7ee16-115">Op deze manier kunnen meerdere personen toegang krijgen tot de gegevens.</span><span class="sxs-lookup"><span data-stu-id="7ee16-115">This way several people can access it.</span></span> <span data-ttu-id="7ee16-116">Een gedeeld postvak mag echter niet groter zijn dan 50 GB.</span><span class="sxs-lookup"><span data-stu-id="7ee16-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="7ee16-117">U moet een Exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="7ee16-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="7ee16-118">Zie het onderwerp Over beheerdersrollen [voor meer informatie.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7ee16-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7ee16-119">Ga in het beheercentrum naar de **pagina Actieve** \> **[gebruikers van](https://go.microsoft.com/fwlink/p/?linkid=834822)** gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7ee16-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="7ee16-120">Selecteer de naam van de gebruiker van wie u het e-mailbericht wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="7ee16-121">Selecteer Op het **tabblad E-mail** de optie **Doorsturen van e-mail beheren.**</span><span class="sxs-lookup"><span data-stu-id="7ee16-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="7ee16-122">Selecteer op de pagina Voor het doorsturen van e-mail alle e-mailberichten doorsturen die naar dit postvak zijn verzonden, voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="7ee16-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7ee16-123">Als u deze optie niet ziet, zorg er dan voor dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="7ee16-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7ee16-124">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee16-124">Select **Save changes**.</span></span>

    <span data-ttu-id="7ee16-125">**Als u wilt doorsturen naar** meerdere e-mailadressen, kunt u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7ee16-126">Zie Regels gebruiken om berichten automatisch door te sturen [voor meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="7ee16-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="7ee16-127">Of maak in het beheercentrum een [](add-user-or-contact-to-distribution-list.md)distributiegroep, [](../setup/create-distribution-lists.md)voeg de adressen hieraan toe en stel doorsturen in om naar de distributiegroep te wijzen aan de hand van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="7ee16-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="7ee16-128">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijder de licentie niet.</span><span class="sxs-lookup"><span data-stu-id="7ee16-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7ee16-129">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="7ee16-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7ee16-130">Ga in het beheercentrum naar de **pagina Actieve** \> **[gebruikers van](https://go.microsoft.com/fwlink/p/?linkid=847686)** gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7ee16-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="7ee16-131">Selecteer de naam van de gebruiker van wie u het e-mailbericht wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="7ee16-132">Vouw **E-mailinstellingen** uit en selecteer Bewerken in de **sectie** E-mail **doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="7ee16-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="7ee16-133">Stel op de pagina voor het doorsturen van e-mail de optie Aan **in,** voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="7ee16-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7ee16-134">Als u deze optie niet ziet, zorg er dan voor dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="7ee16-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7ee16-135">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee16-135">Select **Save**.</span></span>

   <span data-ttu-id="7ee16-136">**Als u wilt doorsturen naar** meerdere e-mailadressen, kunt u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7ee16-137">Zie Regels gebruiken om berichten automatisch door te sturen [voor meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="7ee16-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="7ee16-138">Of maak in het beheercentrum een [](add-user-or-contact-to-distribution-list.md)distributiegroep, [](../setup/create-distribution-lists.md)voeg de adressen hieraan toe en stel doorsturen in om naar de distributiegroep te wijzen aan de hand van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="7ee16-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="7ee16-139">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijder de licentie niet.</span><span class="sxs-lookup"><span data-stu-id="7ee16-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7ee16-140">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="7ee16-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7ee16-141">Ga in het beheercentrum naar de **pagina Actieve** \> **[gebruikers van](https://go.microsoft.com/fwlink/p/?linkid=850628)** gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7ee16-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="7ee16-142">Selecteer de naam van de gebruiker van wie u het e-mailbericht wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="7ee16-143">Vouw **E-mailinstellingen** uit en selecteer Bewerken in de **sectie** E-mail **doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="7ee16-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="7ee16-144">Stel op de pagina voor het doorsturen van e-mail de optie Aan **in,** voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="7ee16-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7ee16-145">Als u deze optie niet ziet, zorg er dan voor dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="7ee16-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7ee16-146">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee16-146">Select **Save**.</span></span>

   <span data-ttu-id="7ee16-147">**Als u wilt doorsturen naar** meerdere e-mailadressen, kunt u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7ee16-148">Zie Regels gebruiken om berichten automatisch door te sturen [voor meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="7ee16-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="7ee16-149">Of maak in het beheercentrum een [](add-user-or-contact-to-distribution-list.md)distributiegroep, [](../setup/create-distribution-lists.md)voeg de adressen hieraan toe en stel doorsturen in om naar de distributiegroep te wijzen aan de hand van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="7ee16-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="7ee16-150">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijder de licentie niet.</span><span class="sxs-lookup"><span data-stu-id="7ee16-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7ee16-151">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="7ee16-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
