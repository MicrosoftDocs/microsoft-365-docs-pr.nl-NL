---
title: Ongewenste e-mail en phishing in Outlook op internet
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor het rapporteren van ongewenste e-mail, geen ongewenste e-mail en phishing in Outlook op het web (Outlook Web App) in Exchange Online en hoe u deze rapportageopties voor gebruikers uit kunt schakelen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788305"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="90580-103">Meld ongewenste e-mail en phishing-Outlook op internet in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="90580-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90580-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="90580-104">**Applies to**</span></span>
- [<span data-ttu-id="90580-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="90580-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="90580-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="90580-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="90580-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90580-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="90580-108">In Microsoft 365 organisaties met postvakken in Exchange Online of on-premises postvakken met hybride moderne [verificatie,](../../enterprise/hybrid-modern-auth-overview.md)kunt u fout-positieven (goede e-mail gemarkeerd als spam), onwaar negatieven (slechte e-mail toegestaan) en phishingberichten verzenden naar Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="90580-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90580-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="90580-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90580-110">We raden u aan de invoeging Rapportbericht of de invoeging Phishing melden voor gebruikersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="90580-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="90580-111">Zie Het rapportbericht inschakelen of de phishing-invoegvoegingen rapporteren [voor meer informatie.](./enable-the-report-message-add-in.md) We raden u de ingebouwde rapportageervaring in Outlook omdat het beleid voor het indienen van gebruikers niet [kan worden gebruikt.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="90580-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="90580-112">Als u een beheerder bent in een organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="90580-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="90580-113">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90580-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="90580-114">Beheerders kunnen de mogelijkheid uitschakelen of inschakelen voor gebruikers om berichten te rapporteren aan Microsoft in Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="90580-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="90580-115">Zie de sectie Ongewenste e-mail uitschakelen of [inschakelen in](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) Outlook sectie op het web verder in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90580-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="90580-116">U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="90580-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="90580-117">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="90580-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="90580-118">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="90580-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="90580-119">Rapportage over ongewenste e-mail uitschakelen of inschakelen in Outlook op internet</span><span class="sxs-lookup"><span data-stu-id="90580-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="90580-120">Gebruikers kunnen standaard spam-fout-positieven, onwaar negatieven en phishingberichten aan Microsoft rapporteren voor analyse in Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="90580-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="90580-121">Beheerders kunnen Outlook beleidsregels voor webpostvakken configureren in Exchange Online PowerShell om te voorkomen dat gebruikers fout-positieve e-mail en ongewenste ongewenste e-mail rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90580-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="90580-122">U kunt de mogelijkheid voor gebruikers om phishingberichten bij Microsoft te melden niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="90580-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90580-123">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="90580-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90580-124">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90580-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="90580-125">Voordat u de procedures in dit artikel kunt uitvoeren, moet Exchange Online machtigingen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="90580-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="90580-126">U hebt met name de rollen **Geadresseerdenbeleid** of  E-mailontvangers nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer en Geadresseerdenbeheer.  </span><span class="sxs-lookup"><span data-stu-id="90580-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="90580-127">Zie Machtigingen [in](/exchange/permissions-exo/permissions-exo) Exchange Online en Rolgroepen Exchange Online wijzigen in Exchange Online voor meer informatie over [rollengroepen in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="90580-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="90580-128">Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u kunt aangepaste beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="90580-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="90580-129">Aangepaste beleidsregels worden toegepast op gebruikers met een bereik vóór het standaardbeleid.</span><span class="sxs-lookup"><span data-stu-id="90580-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="90580-130">Zie het beleid voor Outlook webpostvak in Exchange Online voor meer informatie over Outlook beleidsregels [voor webpostvakken.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="90580-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="90580-131">Als u rapportage over ongewenste e-mail uitwijst, wordt de mogelijkheid om een bericht te markeren als ongewenste e-mail niet verwijderd in Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="90580-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="90580-132">Als u een bericht selecteert in de map Ongewenste e-mail en op Geen **ongewenste** e-mail klikt, wordt het bericht nog steeds \>  verplaatst naar het Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="90580-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="90580-133">Als u een bericht selecteert in een andere e-mailmap en op **Ongewenste e-mail** klikt, wordt het bericht nog steeds \>  verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="90580-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="90580-134">Wat niet meer beschikbaar is, is de optie om het bericht aan Microsoft te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="90580-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="90580-135">Gebruik Exchange Online PowerShell om rapportage van ongewenste e-mail uit te schakelen of in te schakelen in Outlook op internet</span><span class="sxs-lookup"><span data-stu-id="90580-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="90580-136">Voer de volgende opdracht uit Outlook voor het zoeken naar uw bestaande Outlook beleidsregels voor het webpostvak en de status van rapportage van ongewenste e-mail:</span><span class="sxs-lookup"><span data-stu-id="90580-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="90580-137">Gebruik de volgende syntaxis om het rapporteren van ongewenste e-mail in Outlook op internet uit te schakelen of in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="90580-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="90580-138">In dit voorbeeld wordt rapportage van ongewenste e-mail uitgeschakeld in het standaardbeleid.</span><span class="sxs-lookup"><span data-stu-id="90580-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="90580-139">In dit voorbeeld kunt u melding maken van ongewenste e-mail in het aangepaste beleid met de naam Contoso-managers.</span><span class="sxs-lookup"><span data-stu-id="90580-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="90580-140">Zie Get-OwaMailboxPolicy and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy) [(Get-OwaMailboxPolicy)](/powershell/module/exchange/get-owamailboxpolicy) voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="90580-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="90580-141">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="90580-141">How do you know this worked?</span></span>

<span data-ttu-id="90580-142">Als u wilt controleren of u het rapporteren van ongewenste e-mail hebt ingeschakeld of uitgeschakeld in Outlook op internet, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="90580-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="90580-143">Voer Exchange Online PowerShell de volgende opdracht uit en controleer de **eigenschapswaarde ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="90580-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="90580-144">Open het postvak van een betrokken gebruiker in Outlook op internet, selecteer  een bericht in het Postvak IN, klik op Ongewenste e-mail en controleer of de prompt om het bericht aan Microsoft te melden wel of niet wordt \>  weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="90580-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="90580-145">Open het postvak van een betrokken gebruiker in Outlook op internet, selecteer  een bericht in de map Ongewenste e-mail, klik op Ongewenste e-mail en controleer of de prompt om het bericht aan Microsoft te melden wel of niet wordt \>  weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="90580-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="90580-146"><sup>\*</sup> Gebruikers kunnen de prompt voor het rapporteren van het bericht verbergen terwijl ze het bericht nog steeds rapporteren.</span><span class="sxs-lookup"><span data-stu-id="90580-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="90580-147">U kunt deze instelling controleren in Outlook op internet:</span><span class="sxs-lookup"><span data-stu-id="90580-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="90580-148">Klik **Instellingen** ![ Outlook op het pictogram Webinstellingen Alle Outlook instellingen Ongewenste ](../../media/owa-settings-icon.png) \> **e-mail** \> **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="90580-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="90580-149">Controleer in **de sectie** Rapportage de waarde: Vraag het mij voordat u een **rapport verstuurt.**</span><span class="sxs-lookup"><span data-stu-id="90580-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook instellingen voor het rapporteren van ongewenste e-mail op het web](../../media/owa-junk-email-reporting-options.png)
