---
title: In quarantaine geplaatste berichten van gedeelde postvakken weergeven en vrijgeven
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gebruikers kunnen informatie krijgen over het weergeven en reageren op in quarantaine geplaatste berichten die zijn verzonden naar gedeelde postvakken en die ze machtigingen hebben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931444"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="02125-103">In quarantaine geplaatste berichten van gedeelde postvakken weergeven en vrijgeven</span><span class="sxs-lookup"><span data-stu-id="02125-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="02125-104">De functies die in dit artikel worden beschreven, zijn momenteel in de Preview-versie beschikbaar, zijn niet voor iedereen beschikbaar en kunnen worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="02125-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="02125-105">Gebruikers kunnen in quarantaine geplaatste berichten beheren als ze een van de geadresseerden zijn, zoals beschreven in Berichten in quarantaine zoeken en als gebruiker [in EOP vrijgeven.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="02125-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="02125-106">Maar hoe zit het met gedeelde postvakken waarvoor de gebruiker de machtigingEn Volledige toegang en Verzenden als of Verzenden namens voor het postvak heeft, zoals wordt beschreven in Gedeelde postvakken [in Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="02125-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="02125-107">Voorheen was de mogelijkheid voor gebruikers om in quarantaine geplaatste berichten te beheren die naar een gedeeld postvak zijn verzonden, vereist dat beheerders automatisch toewijzen ingeschakeld laten voor het gedeelde postvak (dit is standaard ingeschakeld wanneer een beheerder een gebruiker toegang geeft tot een ander postvak).</span><span class="sxs-lookup"><span data-stu-id="02125-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="02125-108">Afhankelijk van de grootte en het aantal postvakken dat de gebruiker kan gebruiken,  kan dit echter de prestaties beïnvloeden als Outlooks probeert alle postvakken te openen die de gebruiker toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="02125-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="02125-109">Daarom kiezen veel beheerders ervoor om automatisch toewijzen voor gedeelde postvakken [te verwijderen.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="02125-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="02125-110">Automatischemapping is nu niet meer vereist voor gebruikers die in quarantaine geplaatste berichten beheren die naar gedeelde postvakken zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="02125-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="02125-111">Het werkt gewoon.</span><span class="sxs-lookup"><span data-stu-id="02125-111">It just works.</span></span> <span data-ttu-id="02125-112">Er zijn twee verschillende methoden om in quarantaine geplaatste berichten te openen die naar een gedeeld postvak zijn verzonden:</span><span class="sxs-lookup"><span data-stu-id="02125-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="02125-113">Als de beheerder [spammeldingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) voor eindgebruikers heeft ingeschakeld in antispambeleid, kan elke gebruiker die toegang heeft  tot de spammeldingen voor eindgebruikers in het gedeelde postvak, op de knop Controleren in de melding klikken om in quarantaine te gaan in het beveiligings- &-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="02125-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="02125-114">Met deze methode kunnen gebruikers alleen in quarantaine geplaatste berichten beheren die naar het gedeelde postvak zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="02125-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="02125-115">Gebruikers kunnen in deze context hun eigen quarantaineberichten niet beheren.</span><span class="sxs-lookup"><span data-stu-id="02125-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="02125-116">De gebruiker kan [naar de quarantaine gaan in het & Compliancecentrum.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="02125-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="02125-117">Standaard worden alleen berichten weergegeven die naar de gebruiker zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="02125-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="02125-118">De gebruiker kan de resultaten van  Sorteren **(de** knop Bericht-id standaard) echter wijzigen in  het e-mailadres geadresseerde, het e-mailadres van het gedeelde postvak invoeren en vervolgens op Vernieuwen klikken om de in quarantaine geplaatste berichten te bekijken die naar het gedeelde postvak zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="02125-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Berichten in quarantaine sorteren op e-mailadres van geadresseerde.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="02125-120">Ongeacht de methode kunnen gebruikers verwarring voorkomen door de kolom **Geadresseerde** voor berichten in quarantaine op te nemen.</span><span class="sxs-lookup"><span data-stu-id="02125-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="02125-121">Het maximum aantal weer te geven kolommen is 7. De gebruiker moet dus op Kolommen wijzigen  **klikken,** een  bestaande kolom verwijderen (bijvoorbeeld Beleidstype), Ontvanger selecteren en vervolgens op Opslaan of Opslaan als standaard **klikken.**</span><span class="sxs-lookup"><span data-stu-id="02125-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Verwijder de kolom Beleidstype en voeg de kolom Recipient toe aan quarantaine.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="02125-123">Dingen waar u rekening mee moet houden</span><span class="sxs-lookup"><span data-stu-id="02125-123">Things to keep in mind</span></span>

- <span data-ttu-id="02125-124">De eerste gebruiker die in quarantaine wordt geplaatst, bepaalt het samenslot van het bericht voor iedereen die het gedeelde postvak gebruikt.</span><span class="sxs-lookup"><span data-stu-id="02125-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="02125-125">Als een gedeeld postvak bijvoorbeeld door tien gebruikers wordt gebruikt en een gebruiker besluit het quarantainebericht te verwijderen, wordt het bericht voor alle tien gebruikers verwijderd.</span><span class="sxs-lookup"><span data-stu-id="02125-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="02125-126">Evenzo geldt dat als een gebruiker besluit het bericht vrij te geven, dit wordt vrijgegeven aan het gedeelde postvak en toegankelijk is voor alle andere gebruikers van het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="02125-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="02125-127">Momenteel is de **knop Afzender blokkeren** niet beschikbaar in de flyout **Details** voor in quarantaine geplaatste berichten die naar het gedeelde postvak zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="02125-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="02125-128">Als u in quarantaine geplaatste berichten voor het gedeelde postvak in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)wilt beheren, moet de eindgebruiker de cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) gebruiken met het e-mailadres van het gedeelde postvak voor de waarde van de parameter _RecipientAddress_ om de berichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="02125-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="02125-129">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="02125-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="02125-130">Vervolgens kan de eindgebruiker een in quarantaine geplaatst bericht selecteren in de lijst om het weer te geven of actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="02125-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="02125-131">In dit voorbeeld worden alle in quarantaine geplaatste berichten weergegeven die naar het gedeelde postvak zijn verzonden en wordt vervolgens het eerste bericht in de lijst van quarantaine vrijgegeven (het eerste bericht in de lijst is 0, het tweede is 1, etc.).</span><span class="sxs-lookup"><span data-stu-id="02125-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="02125-132">Zie de volgende onderwerpen voor gedetailleerde syntaxis- en parameterinformatie:</span><span class="sxs-lookup"><span data-stu-id="02125-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="02125-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="02125-133">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="02125-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="02125-134">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="02125-135">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="02125-135">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="02125-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="02125-136">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
