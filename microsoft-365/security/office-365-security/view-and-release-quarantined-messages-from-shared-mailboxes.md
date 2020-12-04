---
title: Geplaatste berichten van gedeelde postvakken weergeven en vrijgeven
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gebruikers kunnen informatie lezen over het weergeven van en werken met geplaatste berichten die zijn verzonden naar gedeelde postvakken waarnaar ze zijn gemachtigd.
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570940"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="9617c-103">Geplaatste berichten van gedeelde postvakken weergeven en vrijgeven</span><span class="sxs-lookup"><span data-stu-id="9617c-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="9617c-104">De functies die in dit artikel worden beschreven, zijn momenteel in de preview-versie, zijn niet beschikbaar voor iedereen en kunnen worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="9617c-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="9617c-105">Gebruikers kunnen berichten in quarantaine plaatsen waar ze een van de geadresseerden zijn, zoals beschreven in [gequarantinee berichten in quarantaine plaatsen en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9617c-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="9617c-106">Maar wat gebeurt er met gedeelde postvakken waarbij de gebruiker toegang heeft tot de machtigingen voor het postvak, zoals beschreven in [gedeelde postvakken in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span><span class="sxs-lookup"><span data-stu-id="9617c-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="9617c-107">Eerder is de mogelijkheid om gebruikers te gebruiken voor het beheren van berichten die zijn verzonden naar een gedeeld postvak vereist beheerders om automatisch toewijzingen voor het gedeelde Postvak in te schakelen (deze optie is standaard ingeschakeld wanneer een beheerder een gebruiker toegang geeft tot een ander postvak).</span><span class="sxs-lookup"><span data-stu-id="9617c-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="9617c-108">Afhankelijk van de grootte en het aantal postvakken waartoe de gebruiker toegang heeft, kan het echter even zijn voordat Outlook *alle* postvakken probeert te openen waartoe de gebruiker toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="9617c-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="9617c-109">Daarom kiezen een aantal beheerders om automatisch [toewijzen voor gedeelde postvakken te verwijderen](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9617c-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="9617c-110">Automatisch toewijzen is nu niet meer nodig voor gebruikers die quarantaine berichten beheren die naar gedeelde postvakken zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="9617c-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="9617c-111">Het werkt gewoon.</span><span class="sxs-lookup"><span data-stu-id="9617c-111">It just works.</span></span> <span data-ttu-id="9617c-112">Er zijn twee verschillende manieren om toegang te krijgen tot in quarantaine geplaatste berichten die zijn verzonden naar een gedeeld postvak:</span><span class="sxs-lookup"><span data-stu-id="9617c-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="9617c-113">Als de beheerder [meldingen voor spam van eindgebruikers heeft ingeschakeld](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in Antispambeleid, kan iedere gebruiker die toegang heeft tot de spam meldingen voor eindgebruikers in het gedeelde Postvak op de knop **controleren** klikken in de melding om naar Quarantine te gaan in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="9617c-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="9617c-114">Met deze methode kunnen gebruikers alleen quarantaine berichten beheren die naar het gedeelde Postvak zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="9617c-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="9617c-115">Gebruikers kunnen hun eigen Quarantine-berichten niet beheren in deze context.</span><span class="sxs-lookup"><span data-stu-id="9617c-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="9617c-116">De gebruiker kan [naar de quarantaine gaan in het beveiligings & nalevings centrum](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9617c-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="9617c-117">Standaard worden alleen de berichten weergegeven die naar de gebruiker zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="9617c-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="9617c-118">De gebruiker kan de **sorteerresultaten** (standaard **bericht-id** standaard) wijzigen in het **e-mailadres** van de geadresseerde, het e-mailadres van het gedeelde Postvak opgeven en vervolgens op **vernieuwen** klikken om de berichten in quarantaine weer te geven die naar het gedeelde Postvak zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="9617c-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Berichten in quarantaine sorteren op het e-mailadres van de geadresseerde.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="9617c-120">Ongeacht de methode kunnen gebruikers verwarring voorkomen door de kolom **geadresseerden** voor berichten in quarantaine op te nemen.</span><span class="sxs-lookup"><span data-stu-id="9617c-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="9617c-121">Het maximale aantal weer te geven kolommen is 7, dus de gebruiker moet op **kolommen wijzigen** klikken, een bestaande kolom verwijderen (bijvoorbeeld **type beleid**), selecteer **ontvanger** en klik vervolgens op **Opslaan** of **Opslaan als standaard**.</span><span class="sxs-lookup"><span data-stu-id="9617c-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Verwijder de kolomtype beleid en voeg de kolom geadresseerde toe aan Quarantine.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="9617c-123">Zaken waaraan u moet denken</span><span class="sxs-lookup"><span data-stu-id="9617c-123">Things to keep in mind</span></span>

- <span data-ttu-id="9617c-124">De eerste gebruiker die in het gequarantined bericht moet handelen, bepaalt het gedrag van het bericht voor iedereen die het gedeelde Postvak gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9617c-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="9617c-125">Als een gebruiker een gedeeld postvak bijvoorbeeld opent door 10 gebruikers en een gebruiker besluit om het quarantaine bericht te verwijderen, wordt het bericht verwijderd voor alle tien gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9617c-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="9617c-126">Ook als een gebruiker besluit het bericht vrij te geven, wordt het vrijgegeven voor het gedeelde Postvak en is dit toegankelijk voor alle andere gebruikers van het gedeelde Postvak.</span><span class="sxs-lookup"><span data-stu-id="9617c-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="9617c-127">Als een gebruiker op dit moment meerdere berichten in quarantaine selecteert die naar het gedeelde Postvak zijn verzonden, worden de volgende onjuiste fouten weergegeven wanneer de gebruiker klikt op **berichten vrijgeven** of **berichten verwijderen** in het vervolgmenu **bulk acties** :</span><span class="sxs-lookup"><span data-stu-id="9617c-127">Currently, if a user selects multiple quarantined messages that were sent to the shared mailbox, the following misleading errors are returned when the user clicks **Release messages** or **Delete messages** in the **Bulk actions** flyout:</span></span>

  > <span data-ttu-id="9617c-128">U bent niet gemachtigd om alle geselecteerde berichten in quarantaine te brengen.</span><span class="sxs-lookup"><span data-stu-id="9617c-128">You do not have permission to release all selected quarantined messages.</span></span>
  >
  > <span data-ttu-id="9617c-129">U bent niet gemachtigd om alle geselecteerde berichten in quarantaine te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9617c-129">You do not have permission to delete all selected quarantined messages.</span></span>

  <span data-ttu-id="9617c-130">Ongeacht de fout, wordt de actie uitgevoerd voor de berichten en kan de fout worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="9617c-130">Regardless of the error, the action is taken on the messages, and the error can be ignored.</span></span>

  ![Fout: fout bij het bulksgewijs uitbrengen of verwijderen van quarantaine berichten die zijn verzonden naar een gedeeld postvak.](../../media/quarantine-bulk-action-error.png)

- <span data-ttu-id="9617c-132">De knop **afzender blokkeren** is op dit moment niet beschikbaar in de flyout **Details** voor berichten in quarantaine die naar het gedeelde Postvak zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="9617c-132">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="9617c-133">Voor het beheren van berichten in quarantaine voor het gedeelde Postvak in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)moet de eindgebruiker de cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) gebruiken met het gedeelde Postvak voor de waarde van de _RecipientAddress_ -parameter om de berichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="9617c-133">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="9617c-134">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9617c-134">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="9617c-135">Vervolgens kan de eindgebruiker een in quarantaine geplaatste bericht selecteren in de lijst om op te geven of actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="9617c-135">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="9617c-136">In dit voorbeeld worden alle berichten in quarantaine weergegeven die naar het gedeelde Postvak zijn verzonden, en wordt het eerste bericht in de lijst uit quarantaine vrijgegeven (het eerste bericht in de lijst is 0, de tweede is 1, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="9617c-136">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="9617c-137">Zie de volgende onderwerpen voor gedetailleerde syntaxis- en parameterinformatie:</span><span class="sxs-lookup"><span data-stu-id="9617c-137">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="9617c-138">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9617c-138">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="9617c-139">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="9617c-139">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="9617c-140">Voorbeeld van QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9617c-140">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="9617c-141">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9617c-141">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
