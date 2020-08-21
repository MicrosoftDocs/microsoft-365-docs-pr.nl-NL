---
title: Een postvak opgeven voor de verzending van spam en malafide berichten in de gebruikers
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u een postvak configureert om spam en phishing-e-mail te verzamelen die door gebruikers worden gerapporteerd.
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826739"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="de38f-103">Een postvak opgeven voor de verzending van spam en phishing-berichten in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de38f-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="de38f-104">In Microsoft 365-organisaties met postvakken van Exchange Online kunt u een postvak opgeven voor het ontvangen van berichten die gebruikers als schadelijk of niet schadelijk melden.</span><span class="sxs-lookup"><span data-stu-id="de38f-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="de38f-105">Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportopties, kunt u dit postvak gebruiken om berichten te onderscheppen (alleen verzenden naar het aangepaste postvak) of kopieën van berichten ontvangen (verzenden naar het aangepaste postvak en Microsoft).</span><span class="sxs-lookup"><span data-stu-id="de38f-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="de38f-106">Deze functie werkt met de volgende opties voor het rapporteren van berichten:</span><span class="sxs-lookup"><span data-stu-id="de38f-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="de38f-107">De invoegtoepassing bericht melden</span><span class="sxs-lookup"><span data-stu-id="de38f-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="de38f-108">[Ingebouwde rapporten in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen Outlook Web app)</span><span class="sxs-lookup"><span data-stu-id="de38f-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="de38f-109">Ingebouwde rapporten in Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="de38f-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="de38f-110">Als het rapporteren is [uitgeschakeld in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), wordt deze instelling vervangen door gebruikers die de instelling en de mogelijkheid bieden om berichten te rapporteren in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="de38f-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="de38f-111">U kunt ook hulpmiddelen voor het rapporteren van SMS-berichten configureren voor het doorsturen van berichten naar het postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="de38f-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="de38f-112">Door gebruiker gerapporteerde berichten te verzenden naar een aangepast postvak in plaats van rechtstreeks aan Microsoft kunnen uw beheerders berichten selectief en handmatig rapporteren aan Microsoft via de [beheerder](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="de38f-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de38f-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="de38f-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de38f-114">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="de38f-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="de38f-115">Als u direct naar de pagina voor het aanvragen van **gebruikers** wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="de38f-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="de38f-116">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="de38f-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="de38f-117">Als u de configuratie van gebruikers inzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="de38f-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="de38f-118">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="de38f-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="de38f-119">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="de38f-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="de38f-120">Voor alleen-lezen toegang tot gebruikers inzendingen moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="de38f-120">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="de38f-121">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="de38f-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="de38f-122">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="de38f-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="de38f-123">De beveiligings & voor nalevings centrum gebruiken om het postvak voor de gebruiker te configureren</span><span class="sxs-lookup"><span data-stu-id="de38f-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="de38f-124">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **risicobeheer** \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="de38f-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="de38f-125">Selecteer een van de volgende opties op de pagina **gebruikers items** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="de38f-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="de38f-126">a.</span><span class="sxs-lookup"><span data-stu-id="de38f-126">a.</span></span> <span data-ttu-id="de38f-127">**De functie bericht rapporteren voor Outlook inschakelen (aanbevolen)**: Selecteer deze optie als u de invoegtoepassing bericht rapporteren of de ingebouwde rapporten in de webversie van Outlook gebruikt en de volgende instellingen configureert:</span><span class="sxs-lookup"><span data-stu-id="de38f-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="de38f-128">**Het bevestigingsbericht voor eindgebruikers aanpassen**: Klik op deze link.</span><span class="sxs-lookup"><span data-stu-id="de38f-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="de38f-129">Configureer de volgende instellingen in het vervolgmenu met **bevestigingsberichten aanpassen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="de38f-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="de38f-130">**Voordat u gaat verzenden**: Typ in de vakken **titel** en **bevestiging** de beschrijvende tekst die gebruikers zien voordat ze een bericht rapporteren met behulp van de invoegtoepassing bericht melden.</span><span class="sxs-lookup"><span data-stu-id="de38f-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="de38f-131">U kunt de variabele% type% gebruiken voor het inzendings type (ongewenst, geen ongewenste e-mail, phishing, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="de38f-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="de38f-132">Zoals u ziet, wordt de volgende tekst ook toegevoegd aan de melding wanneer u een optie selecteert waarmee de gerapporteerde berichten naar Microsoft worden verzonden:</span><span class="sxs-lookup"><span data-stu-id="de38f-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="de38f-133">Uw e-mailbericht wordt verzonden naar Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="de38f-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="de38f-134">Sommige e-mailberichten kunnen persoonlijke of gevoelige informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="de38f-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="de38f-135">**Na verzending**: Klik op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="de38f-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="de38f-136">Voer in de vakken **titel** en **bevestigingsbericht** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gerapporteerd via de invoegtoepassing bericht rapporteren.</span><span class="sxs-lookup"><span data-stu-id="de38f-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="de38f-137">U kunt de variabele% type% gebruiken om het type levering op te nemen.</span><span class="sxs-lookup"><span data-stu-id="de38f-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="de38f-138">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="de38f-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="de38f-139">Als u deze waarden wilt wissen, klikt u op de pagina voor het **aanbrengen** van **gebruikers** op terug herstellen.</span><span class="sxs-lookup"><span data-stu-id="de38f-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="de38f-140">**Verstuur de gerapporteerde berichten naar**: Voer een van de volgende opties in:</span><span class="sxs-lookup"><span data-stu-id="de38f-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="de38f-141">**Microsoft (aanbevolen)**: het postvak voor de gebruiker wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).</span><span class="sxs-lookup"><span data-stu-id="de38f-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="de38f-142">**Microsoft en een aangepast postvak**: in het vak dat wordt weergegeven, voert u het e-mailadres van een bestaand Exchange Online-postvak in.</span><span class="sxs-lookup"><span data-stu-id="de38f-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="de38f-143">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="de38f-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="de38f-144">Gebruikers inzendingen gaan naar Microsoft for Analysis en naar het aangepaste postvak voor uw beheerder of beveiligingsactiviteiten team om dit te analyseren.</span><span class="sxs-lookup"><span data-stu-id="de38f-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="de38f-145">**Aangepast postvak**: Typ in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak.</span><span class="sxs-lookup"><span data-stu-id="de38f-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="de38f-146">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="de38f-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="de38f-147">Gebruik deze optie als u wilt dat het bericht eerst naar een beheerder of het beveiligings werkactiviteiten team gaat voor analyse.</span><span class="sxs-lookup"><span data-stu-id="de38f-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="de38f-148">Berichten gaan niet naar Microsoft, tenzij deze door de beheerder zelf worden doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="de38f-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="de38f-149">US Government-organisaties (GCC, GCC-H en DoD) kunnen alleen **aangepaste postvak**configureren.</span><span class="sxs-lookup"><span data-stu-id="de38f-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="de38f-150">De andere twee opties zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="de38f-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="de38f-151">Wanneer u klaar bent, klikt u op **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="de38f-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="de38f-152">Als u de [rapportage van ongewenste e-mail in de webversie van Outlook hebt uitgeschakeld](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) met behulp van de beleidsregels voor het postvak in de webversie van Outlook, maar u de volgende instellingen voor het melden van berichten naar Microsoft hebt uitgeschakeld, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met behulp van de invoegtoepassing berichten rapporteren.</span><span class="sxs-lookup"><span data-stu-id="de38f-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="de38f-153">**De functie voor het melden van berichten voor Outlook uitschakelen**: Selecteer deze optie als u rapportagehulpmiddelen van derden gebruikt in plaats van de invoegtoepassing berichten rapporteren of de ingebouwde rapporten in de webversie van Outlook en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="de38f-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="de38f-154">Selecteer **dit aangepaste postvak gebruiken om door de gebruiker gerapporteerde inzendingen te ontvangen**.</span><span class="sxs-lookup"><span data-stu-id="de38f-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="de38f-155">In het vak dat wordt weergegeven, voert u het e-mailadres in van een bestaand postvak dat zich al in Office 365 bevindt.</span><span class="sxs-lookup"><span data-stu-id="de38f-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="de38f-156">Dit moet een bestaand postvak zijn in Exchange Online, dat e-mailberichten kan ontvangen.</span><span class="sxs-lookup"><span data-stu-id="de38f-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="de38f-157">Wanneer u klaar bent, klikt u op **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="de38f-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="de38f-158">Opmaak van berichten indienen</span><span class="sxs-lookup"><span data-stu-id="de38f-158">Message submission format</span></span>

<span data-ttu-id="de38f-159">Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke e-mail indeling voor het verzenden volgen.</span><span class="sxs-lookup"><span data-stu-id="de38f-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="de38f-160">Het onderwerp (envelop titel) van de indiening moet de volgende indeling hebben:</span><span class="sxs-lookup"><span data-stu-id="de38f-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="de38f-161">SafetyAPIAction is een van de volgende gehele waarden:</span><span class="sxs-lookup"><span data-stu-id="de38f-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="de38f-162">1: ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="de38f-162">1: Junk</span></span>
- <span data-ttu-id="de38f-163">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="de38f-163">2: NotJunk</span></span>
- <span data-ttu-id="de38f-164">3: phishing</span><span class="sxs-lookup"><span data-stu-id="de38f-164">3: Phish</span></span>

<span data-ttu-id="de38f-165">In het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="de38f-165">In the following example:</span></span>

- <span data-ttu-id="de38f-166">Het bericht wordt als phishing gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="de38f-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="de38f-167">De netwerkbericht-ID is 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="de38f-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="de38f-168">Het IP-adres van de afzender is 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="de38f-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="de38f-169">Het van-adres is test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="de38f-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="de38f-170">De onderwerpregel van het bericht is "phishing testen"</span><span class="sxs-lookup"><span data-stu-id="de38f-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="de38f-171">Berichten die niet op deze indeling volgen, worden niet correct weergegeven in de portal voor ingediende items.</span><span class="sxs-lookup"><span data-stu-id="de38f-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
