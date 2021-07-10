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
description: Met e-mail doorsturen kunt u e-mailberichten doorsturen die zijn verzonden naar een Microsoft 365 postvak van een gebruiker naar een ander postvak binnen of buiten uw organisatie.
ms.openlocfilehash: 9d645c2b36bdac2ab53dcb8af4ff6ebdbd0ee601
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363789"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="108d1-103">E-mail doorsturen configureren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="108d1-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="108d1-104">Als beheerder van een organisatie hebt u mogelijk bedrijfsvereisten voor het instellen van e-mail doorsturen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="108d1-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="108d1-105">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="108d1-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="108d1-106">U kunt beleidsregels voor uitgaand spamfilter gebruiken om automatische doorsturen naar externe geadresseerden te controleren.</span><span class="sxs-lookup"><span data-stu-id="108d1-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="108d1-107">Zie Automatische externe e-mail doorsturen [in](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="108d1-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="108d1-108">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="108d1-108">Configure email forwarding</span></span>

<span data-ttu-id="108d1-109">Voordat u het doorsturen van e-mail in stelt, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="108d1-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="108d1-110">Toestaan dat automatisch doorgestuurde berichten worden verzonden naar personen in het externe domein.</span><span class="sxs-lookup"><span data-stu-id="108d1-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="108d1-111">Zie [Externe domeinen beheren voor](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="108d1-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="108d1-112">Nadat u het doorsturen van e-mail hebt ingesteld, worden alleen **nieuwe** e-mailberichten doorgestuurd die naar het  *postvak*  vandaan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="108d1-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="108d1-113">Voor het doorsturen van  *e-mail moet het*  van account een licentie hebben.</span><span class="sxs-lookup"><span data-stu-id="108d1-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="108d1-114">Als u e-mail doorsturen instelt omdat de gebruiker uw organisatie heeft verlaten, kunt u het postvak ook converteren [naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="108d1-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="108d1-115">Op deze manier hebben meerdere personen toegang tot de toegang.</span><span class="sxs-lookup"><span data-stu-id="108d1-115">This way several people can access it.</span></span> <span data-ttu-id="108d1-116">Een gedeeld postvak mag echter niet groter zijn dan 50 GB.</span><span class="sxs-lookup"><span data-stu-id="108d1-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="108d1-117">U moet een beheerder Exchange globale beheerder in Microsoft 365 om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="108d1-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="108d1-118">Zie het onderwerp Over [beheerdersrollen voor meer informatie.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="108d1-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="108d1-119">Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="108d1-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="108d1-120">Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen en open vervolgens de eigenschappenpagina.</span><span class="sxs-lookup"><span data-stu-id="108d1-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="108d1-121">Selecteer op **het** tabblad E-mail **de optie E-mail doorsturen beheren.**</span><span class="sxs-lookup"><span data-stu-id="108d1-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="108d1-122">Selecteer op de pagina e-mail doorsturen de optie Alle e-mailberichten doorsturen die naar dit postvak zijn verzonden, voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="108d1-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="108d1-123">Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="108d1-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="108d1-124">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="108d1-124">Select **Save changes**.</span></span>

    <span data-ttu-id="108d1-125">**Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="108d1-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="108d1-126">Outlook  > **Home** > **Rules openen >** Selecteer Regels beheren & **waarschuwingen**  </span><span class="sxs-lookup"><span data-stu-id="108d1-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="108d1-127">Selecteer **Nieuwe regel** Selecteer Regel toepassen op het bericht dat ik ontvang onder aan de lijst en klik vervolgens op >  **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="108d1-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="108d1-128">Klik **op Ja** wanneer u daarom wordt gevraagd Deze regel wordt toegepast op elk bericht dat u ontvangt.</span><span class="sxs-lookup"><span data-stu-id="108d1-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="108d1-129">Selecteer in de volgende lijst de acties **omleiden naar personen of** openbare groepen en stop **met het verwerken van meer regels**</span><span class="sxs-lookup"><span data-stu-id="108d1-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="108d1-130">Klik op de onderstreepte **woordgroep personen of openbare groep** in het onderste deel van het venster.</span><span class="sxs-lookup"><span data-stu-id="108d1-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="108d1-131">Typ het **e-mailadres waar** u e-mail naar wilt doorsturen in het veld Aan en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="108d1-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="108d1-132">Voltooien **selecteren**</span><span class="sxs-lookup"><span data-stu-id="108d1-132">Select **Finish**</span></span>
    

     <span data-ttu-id="108d1-133">Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="108d1-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="108d1-134">Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie!</span><span class="sxs-lookup"><span data-stu-id="108d1-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="108d1-135">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="108d1-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="108d1-136">Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=847686)**</span><span class="sxs-lookup"><span data-stu-id="108d1-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="108d1-137">Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="108d1-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="108d1-138">Vouw **E-mailinstellingen** uit en selecteer bewerken in de sectie **E-mail** **doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="108d1-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="108d1-139">Stel op de pagina e-mail doorsturen de schakelknop in op **Aan,** voer het doorsturende adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="108d1-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="108d1-140">Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="108d1-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="108d1-141">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="108d1-141">Select **Save**.</span></span>

   <span data-ttu-id="108d1-142">**Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="108d1-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="108d1-143">Zie Regels gebruiken om berichten automatisch door te sturen voor [meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="108d1-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="108d1-144">Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="108d1-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="108d1-145">Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie!</span><span class="sxs-lookup"><span data-stu-id="108d1-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="108d1-146">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="108d1-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="108d1-147">Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=850628)**</span><span class="sxs-lookup"><span data-stu-id="108d1-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="108d1-148">Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="108d1-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="108d1-149">Vouw **E-mailinstellingen** uit en selecteer bewerken in de sectie **E-mail** **doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="108d1-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="108d1-150">Stel op de pagina e-mail doorsturen de schakelknop in op **Aan,** voer het doorsturende adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="108d1-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="108d1-151">Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="108d1-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="108d1-152">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="108d1-152">Select **Save**.</span></span>

   <span data-ttu-id="108d1-153">**Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="108d1-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="108d1-154">Zie Regels gebruiken om berichten automatisch door te sturen voor [meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="108d1-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="108d1-155">Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="108d1-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="108d1-156">Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie!</span><span class="sxs-lookup"><span data-stu-id="108d1-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="108d1-157">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="108d1-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="108d1-158">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="108d1-158">Related content</span></span> 

<span data-ttu-id="108d1-159">[Een gedeeld postvak](../email/create-a-shared-mailbox.md) maken (artikel)</span><span class="sxs-lookup"><span data-stu-id="108d1-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="108d1-160">[E-mail verzenden vanaf een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)</span><span class="sxs-lookup"><span data-stu-id="108d1-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="108d1-161">[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="108d1-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
