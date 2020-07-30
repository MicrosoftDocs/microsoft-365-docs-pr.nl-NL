---
title: Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u een postvak configureert om spam en phishing-e-mail te verzamelen die door gebruikers worden gerapporteerd.
ms.openlocfilehash: 0be1a4efa04d3e7a7968880b2a1cca108fdd34f9
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503089"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="c6e13-103">Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c6e13-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="c6e13-104">In Microsoft 365-organisaties met Exchange Online-postvakken u een postvak opgeven om berichten te ontvangen die gebruikers melden als kwaadaardig of niet kwaadaardig.</span><span class="sxs-lookup"><span data-stu-id="c6e13-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="c6e13-105">Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportageopties, u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak verzenden) of kopieën van berichten te ontvangen (verzenden naar het aangepaste postvak en Microsoft).</span><span class="sxs-lookup"><span data-stu-id="c6e13-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="c6e13-106">Deze functie werkt met de volgende opties voor berichtrapportage:</span><span class="sxs-lookup"><span data-stu-id="c6e13-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="c6e13-107">De invoegtoepassing Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="c6e13-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="c6e13-108">[Ingebouwde rapportage in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) van Outlook (voorheen Outlook Web App genoemd)</span><span class="sxs-lookup"><span data-stu-id="c6e13-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="c6e13-109">Ingebouwde rapportage in Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="c6e13-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="c6e13-110">Als de rapportage [is uitgeschakeld in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)van Outlook, worden de inzendingen van gebruikers hier overschrijven en kunnen gebruikers berichten in de webversie van Outlook opnieuw rapporteren.</span><span class="sxs-lookup"><span data-stu-id="c6e13-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="c6e13-111">U ook hulpprogramma's voor berichtrapportage van derden configureren om berichten door te sturen naar het postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="c6e13-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="c6e13-112">Door gerapporteerde gebruikersberichten te leveren aan een aangepast postvak in plaats van rechtstreeks aan Microsoft, kunnen uw beheerders selectief en handmatig berichten rapporteren aan Microsoft met behulp van [admin-indiening.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c6e13-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6e13-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="c6e13-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6e13-114">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c6e13-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c6e13-115">Als u rechtstreeks naar de pagina **Inzendingen van** gebruikers wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="c6e13-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="c6e13-116">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6e13-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c6e13-117">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6e13-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c6e13-118">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="c6e13-118">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="c6e13-119">Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="c6e13-119">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c6e13-120">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c6e13-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c6e13-121">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c6e13-121">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="c6e13-122">Voor alleen-lezen toegang tot gebruikersinzendingen moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="c6e13-122">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c6e13-123">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c6e13-123">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c6e13-124">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c6e13-124">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="c6e13-125">Gebruik het Security & Compliance Center om het postvak voor gebruikersinzendingen te configureren</span><span class="sxs-lookup"><span data-stu-id="c6e13-125">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="c6e13-126">Ga in het Security & Compliance Center naar **Gebruikersinzendingen voor** \> **Policy** \> **bedreigingsbeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="c6e13-126">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="c6e13-127">Selecteer op de pagina **Gebruikersinzendingen** die wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="c6e13-127">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="c6e13-128">a.</span><span class="sxs-lookup"><span data-stu-id="c6e13-128">a.</span></span> <span data-ttu-id="c6e13-129">**De functie Rapportbericht voor Outlook inschakelen (Aanbevolen)**: Selecteer deze optie als u de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook gebruikt en configureer vervolgens de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="c6e13-129">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="c6e13-130">**Het bevestigingsbericht van de eindgebruiker aanpassen**: Klik op deze link.</span><span class="sxs-lookup"><span data-stu-id="c6e13-130">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="c6e13-131">Configureer in de flyout **bevestigingsbericht aanpassen** die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="c6e13-131">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="c6e13-132">**Vóór indiening**: Voer in de vakken **Bericht en** **Bevestiging** de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtoepassing Bericht rapporteren.</span><span class="sxs-lookup"><span data-stu-id="c6e13-132">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="c6e13-133">U het variabele type %% gebruiken om het indieningstype (junk, niet junk, phish, enz.) op te nemen.</span><span class="sxs-lookup"><span data-stu-id="c6e13-133">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="c6e13-134">Zoals opgemerkt, als u een optie selecteert die de gerapporteerde berichten naar Microsoft verzendt, wordt ook de volgende tekst aan de melding toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="c6e13-134">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="c6e13-135">Uw e-mail wordt als nu naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="c6e13-135">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="c6e13-136">Sommige e-mails kunnen persoonlijke of gevoelige informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="c6e13-136">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="c6e13-137">**Na indiening**: Klik op ![ pictogram Uitvouwen ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="c6e13-137">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="c6e13-138">Voer in de vakken **Bericht en** **Bevestiging** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gemeld met de invoegtoepassing Bericht rapporteren.</span><span class="sxs-lookup"><span data-stu-id="c6e13-138">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="c6e13-139">U het variabele type %% gebruiken om het indieningstype op te nemen.</span><span class="sxs-lookup"><span data-stu-id="c6e13-139">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="c6e13-140">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="c6e13-140">When you're finished, click **Save**.</span></span> <span data-ttu-id="c6e13-141">Als u deze waarden wilt wissen, klikt u op **Terugzetten** op de pagina **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="c6e13-141">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="c6e13-142">**Stuur de gerapporteerde berichten naar**: Maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="c6e13-142">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="c6e13-143">**Microsoft (Aanbevolen)**: Het postvak voor gebruikersinzendingen wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).</span><span class="sxs-lookup"><span data-stu-id="c6e13-143">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="c6e13-144">**Microsoft en een aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in.</span><span class="sxs-lookup"><span data-stu-id="c6e13-144">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="c6e13-145">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="c6e13-145">Distribution groups are not allowed.</span></span> <span data-ttu-id="c6e13-146">Gebruikersinzendingen gaan naar zowel Microsoft voor analyse als naar het aangepaste postvak dat uw beheerders- of beveiligingsteam kan analyseren.</span><span class="sxs-lookup"><span data-stu-id="c6e13-146">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="c6e13-147">**Aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in.</span><span class="sxs-lookup"><span data-stu-id="c6e13-147">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="c6e13-148">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="c6e13-148">Distribution groups are not allowed.</span></span> <span data-ttu-id="c6e13-149">Gebruik deze optie als u wilt dat het bericht alleen naar een beheerder of het beveiligingsteam gaat voor analyse eerst.</span><span class="sxs-lookup"><span data-stu-id="c6e13-149">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="c6e13-150">Berichten gaan niet naar Microsoft, tenzij de beheerder het zelf doorstuurt.</span><span class="sxs-lookup"><span data-stu-id="c6e13-150">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c6e13-151">Organisaties van de Amerikaanse overheid (GCC, GCC-H en DoD) kunnen alleen **aangepast postvak**configureren.</span><span class="sxs-lookup"><span data-stu-id="c6e13-151">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="c6e13-152">De andere twee opties zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6e13-152">The other two options are disabled.</span></span> 

      <span data-ttu-id="c6e13-153">Klik op **Bevestigen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c6e13-153">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="c6e13-154">Als u [de rapportage over ongewenste e-mail in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook hebt uitgeschakeld met het beleid voor outlook voor webpostvak, maar u een van de vorige instellingen configureert om berichten aan Microsoft te rapporteren, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met behulp van de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="c6e13-154">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="c6e13-155">**De functie Rapportbericht voor Outlook uitschakelen:** Selecteer deze optie als u rapportagehulpprogramma's van derden gebruikt in plaats van de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook en configureer vervolgens de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="c6e13-155">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="c6e13-156">Selecteer **Dit aangepaste postvak gebruiken om door gebruikers gerapporteerde inzendingen te ontvangen.**</span><span class="sxs-lookup"><span data-stu-id="c6e13-156">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="c6e13-157">Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand postvak dat zich al in Office 365 bevindt.</span><span class="sxs-lookup"><span data-stu-id="c6e13-157">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="c6e13-158">Dit moet een bestaand postvak in Exchange Online zijn dat e-mail kan ontvangen.</span><span class="sxs-lookup"><span data-stu-id="c6e13-158">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="c6e13-159">Klik op **Bevestigen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c6e13-159">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="c6e13-160">Indeling voor het indienen van berichten</span><span class="sxs-lookup"><span data-stu-id="c6e13-160">Message submission format</span></span>

<span data-ttu-id="c6e13-161">Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke e-mailindeling volgen.</span><span class="sxs-lookup"><span data-stu-id="c6e13-161">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="c6e13-162">Het onderwerp (enveloptitel) van de indiening moet in deze vorm zijn:</span><span class="sxs-lookup"><span data-stu-id="c6e13-162">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="c6e13-163">waren SafetyAPIAction is een van de volgende gehele waarden:</span><span class="sxs-lookup"><span data-stu-id="c6e13-163">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="c6e13-164">1: Junk</span><span class="sxs-lookup"><span data-stu-id="c6e13-164">1: Junk</span></span>
- <span data-ttu-id="c6e13-165">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="c6e13-165">2: NotJunk</span></span>
- <span data-ttu-id="c6e13-166">3: Phish</span><span class="sxs-lookup"><span data-stu-id="c6e13-166">3: Phish</span></span>

<span data-ttu-id="c6e13-167">In het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c6e13-167">In the following example:</span></span>

- <span data-ttu-id="c6e13-168">Het bericht wordt gerapporteerd als Phish.</span><span class="sxs-lookup"><span data-stu-id="c6e13-168">The message is being reported as Phish.</span></span>
- <span data-ttu-id="c6e13-169">De Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="c6e13-169">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="c6e13-170">De Sender IP is 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="c6e13-170">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="c6e13-171">Het adres van Van is test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c6e13-171">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="c6e13-172">De onderwerpregel van het bericht is "test phish submission"</span><span class="sxs-lookup"><span data-stu-id="c6e13-172">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="c6e13-173">Berichten die deze indeling niet volgen, worden niet goed weergegeven in de portal Inzendingen.</span><span class="sxs-lookup"><span data-stu-id="c6e13-173">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
