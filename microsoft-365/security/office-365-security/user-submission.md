---
title: Een postvak opgeven voor het inzenden van spam- en phishingberichten door gebruikers
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
description: Beheerders kunnen leren hoe u een postvak configureert om spam- en phishing-e-mail te verzamelen die door gebruikers wordt gerapporteerd.
ms.openlocfilehash: 38fa16b5270273813b4549b0c3c9baaa1b05b098
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224551"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="ed729-103">Een postvak opgeven voor het indienen van spam- en phishingberichten door gebruikers in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ed729-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="ed729-104">In Microsoft 365-organisaties met Exchange Online-postvakken u een postvak opgeven om berichten te ontvangen die gebruikers als kwaadaardig of niet kwaadaardig rapporteren.</span><span class="sxs-lookup"><span data-stu-id="ed729-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="ed729-105">Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportageopties, u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak verzenden) of kopieën van berichten ontvangen (verzenden naar het aangepaste postvak en Microsoft).</span><span class="sxs-lookup"><span data-stu-id="ed729-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="ed729-106">Deze functie werkt met de volgende opties voor berichtrapportage:</span><span class="sxs-lookup"><span data-stu-id="ed729-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="ed729-107">De invoegtoepassing Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="ed729-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="ed729-108">[Ingebouwde rapportage in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen bekend als Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="ed729-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="ed729-109">Als de rapportage is [uitgeschakeld in de webversie van Outlook,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)overschrijft het inschakelen van gebruikers hier die instelling en kunnen gebruikers berichten opnieuw rapporteren in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="ed729-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="ed729-110">U ook hulpprogramma's voor berichtrapportage van derden configureren om berichten door te sturen naar het postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="ed729-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="ed729-111">Door door de gebruiker gerapporteerde berichten naar een aangepast postvak te leveren in plaats van rechtstreeks aan Microsoft, kunnen uw beheerders selectief en handmatig berichten aan Microsoft rapporteren met behulp van [het indienen van beheerders.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ed729-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ed729-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ed729-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ed729-113">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ed729-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ed729-114">Als u rechtstreeks naar de pagina **Inzendingen van gebruiker** wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="ed729-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="ed729-115">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed729-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ed729-116">Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed729-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ed729-117">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ed729-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="ed729-118">Als u het postvak wilt configureren voor gebruikersinzendingen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="ed729-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ed729-119">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ed729-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="ed729-120">Het beveiligingscentrum & compliancecenter gebruiken om het postvak voor inzendingen van gebruikers te configureren</span><span class="sxs-lookup"><span data-stu-id="ed729-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="ed729-121">Ga in het Security & Compliance Center naar Inzendingen voor gebruikers van **het beleid voor** \> **Policy** \> **bedreigingen.**</span><span class="sxs-lookup"><span data-stu-id="ed729-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="ed729-122">Selecteer op de pagina **Gebruikersinzendingen** die wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="ed729-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="ed729-123">**De functie Rapportbericht voor Outlook inschakelen (Aanbevolen):** Selecteer deze optie als u de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook gebruikt en configureer vervolgens de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ed729-123">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="ed729-124">**Het bevestigingsbericht voor eindgebruikers aanpassen:** Klik op deze koppeling.</span><span class="sxs-lookup"><span data-stu-id="ed729-124">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="ed729-125">Configureer de volgende instellingen in de flyout **van bevestigingsbericht aanpassen:**</span><span class="sxs-lookup"><span data-stu-id="ed729-125">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="ed729-126">**Vóór indiening**: Voer in de vakken **Titel-** en **Bevestigingsbericht** de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="ed729-126">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="ed729-127">U het variabele %type% gebruiken om het onderwerpingstype op te nemen (junk, not junk, phish, enz.).</span><span class="sxs-lookup"><span data-stu-id="ed729-127">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="ed729-128">Zoals opgemerkt, wordt ook de volgende tekst aan de kennisgeving toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="ed729-128">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="ed729-129">Uw e-mail wordt ter analyse naar Microsoft verzonden.</span><span class="sxs-lookup"><span data-stu-id="ed729-129">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="ed729-130">Sommige e-mails kunnen persoonlijke of gevoelige informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="ed729-130">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="ed729-131">**Na indiening**: Klik op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ed729-131">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="ed729-132">Voer in de vakken **Titel-** en **Bevestigingsbericht** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gemeld met de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="ed729-132">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="ed729-133">U het variabele %type% gebruiken om het onderwerptype op te nemen.</span><span class="sxs-lookup"><span data-stu-id="ed729-133">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="ed729-134">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ed729-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="ed729-135">Als u deze waarden wilt wissen, klikt u op **Terugherstellen** op de pagina **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="ed729-135">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="ed729-136">**Stuur de gerapporteerde berichten naar**: Maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="ed729-136">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="ed729-137">**Microsoft (Aanbevolen)**: Het postvak voor inzendingen van gebruikers wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).</span><span class="sxs-lookup"><span data-stu-id="ed729-137">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="ed729-138">**Microsoft en een aangepast postvak**: voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in.</span><span class="sxs-lookup"><span data-stu-id="ed729-138">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="ed729-139">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ed729-139">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="ed729-140">**Aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in.</span><span class="sxs-lookup"><span data-stu-id="ed729-140">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="ed729-141">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ed729-141">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="ed729-142">Klik op **Bevestigen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="ed729-142">When you're finished, click **Confirm**.</span></span>

     ![Gerapporteerde berichten verzenden naar Microsoft en een aangepast postvak](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="ed729-144">**De functie Rapportbericht voor Outlook uitschakelen:** Selecteer deze optie als u rapportagehulpprogramma's van derden gebruikt in plaats van de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook en configureer vervolgens de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ed729-144">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="ed729-145">Selecteer **Dit aangepaste postvak gebruiken om gerapporteerde inzendingen van gebruikers te ontvangen.**</span><span class="sxs-lookup"><span data-stu-id="ed729-145">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="ed729-146">Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand postvak of het e-mailadres van het postvak dat u wilt maken in.</span><span class="sxs-lookup"><span data-stu-id="ed729-146">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="ed729-147">Klik op **Bevestigen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="ed729-147">When you're finished, click **Confirm**.</span></span>

     ![Gerapporteerde berichten verzenden naar een aangepast postvak met hulpprogramma's van derden](../../media/user-submission-disable-outlook-report-message.png)
