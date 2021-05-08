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
description: E-mail doorsturen naar een of meer e-mailaccounts instellen met Office365.
ms.openlocfilehash: b5612a915fce21e9e9865fca6cb2275d8af17bd2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242406"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="e3b28-103">E-mail doorsturen configureren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3b28-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="e3b28-104">Als beheerder van een organisatie hebt u mogelijk bedrijfsvereisten voor het instellen van e-mail doorsturen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e3b28-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="e3b28-105">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="e3b28-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3b28-106">U kunt beleidsregels voor uitgaand spamfilter gebruiken om automatische doorsturen naar externe geadresseerden te controleren.</span><span class="sxs-lookup"><span data-stu-id="e3b28-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="e3b28-107">Zie Automatische externe e-mail doorsturen [in](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3b28-107">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="e3b28-108">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="e3b28-108">Configure email forwarding</span></span>

<span data-ttu-id="e3b28-109">Voordat u het doorsturen van e-mail in stelt, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="e3b28-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="e3b28-110">Nadat u het doorsturen van e-mail hebt ingesteld, worden alleen **nieuwe** e-mailberichten doorgestuurd die naar het  *postvak*  vandaan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="e3b28-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="e3b28-111">Voor het doorsturen van  *e-mail moet het*  van account een licentie hebben.</span><span class="sxs-lookup"><span data-stu-id="e3b28-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="e3b28-112">Als u e-mail doorsturen instelt omdat de gebruiker uw organisatie heeft verlaten, kunt u het postvak ook converteren [naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="e3b28-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="e3b28-113">Op deze manier hebben meerdere personen toegang tot de toegang.</span><span class="sxs-lookup"><span data-stu-id="e3b28-113">This way several people can access it.</span></span> <span data-ttu-id="e3b28-114">Een gedeeld postvak mag echter niet groter zijn dan 50 GB.</span><span class="sxs-lookup"><span data-stu-id="e3b28-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="e3b28-115">U moet een beheerder Exchange globale beheerder in Microsoft 365 om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e3b28-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="e3b28-116">Zie het onderwerp Over [beheerdersrollen voor meer informatie.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e3b28-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="e3b28-117">Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="e3b28-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="e3b28-118">Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="e3b28-118">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e3b28-119">Selecteer op **het** tabblad E-mail **de optie E-mail doorsturen beheren.**</span><span class="sxs-lookup"><span data-stu-id="e3b28-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="e3b28-120">Selecteer op de pagina e-mail doorsturen de optie Alle e-mailberichten doorsturen die naar dit postvak zijn verzonden, voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="e3b28-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e3b28-121">Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="e3b28-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e3b28-122">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e3b28-122">Select **Save changes**.</span></span>

    <span data-ttu-id="e3b28-123">**Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="e3b28-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e3b28-124">Zie Regels gebruiken om berichten automatisch door te sturen voor [meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="e3b28-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="e3b28-125">Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e3b28-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e3b28-126">Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie!</span><span class="sxs-lookup"><span data-stu-id="e3b28-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e3b28-127">Als u dit doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="e3b28-127">If you do, email forwarding will stop.</span></span>