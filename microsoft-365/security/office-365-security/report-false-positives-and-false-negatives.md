---
title: Fout-positieven en onwaar-negatieven rapporteren in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informatie over het rapporteren van onwaar positieven en onwaar negatieven in Outlook en het inschakelen van de invoegvoegingen Rapportbericht en Phishing melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065148"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="71de1-103">Fout-positieven en onwaar-negatieven rapporteren in Outlook</span><span class="sxs-lookup"><span data-stu-id="71de1-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="71de1-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="71de1-104">**Applies to**</span></span>
- [<span data-ttu-id="71de1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="71de1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="71de1-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="71de1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="71de1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71de1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="71de1-108">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="71de1-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="71de1-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="71de1-110">In Microsoft 365-organisaties met postvakken in Exchange Online of on-premises postvakken die gebruikmaken van hybride moderne verificatie, kunt u false positives (goede e-mail gemarkeerd als spam) en onwaar negatieven (slechte e-mail en phish toegestaan) indienen bij Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="71de1-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="71de1-111">Dingen die u moet onthouden voordat u de functie Rapportbericht gebruikt</span><span class="sxs-lookup"><span data-stu-id="71de1-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="71de1-112">Voor de beste gebruikersinzendingservaring gebruikt u de invoeging Rapportbericht of de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="71de1-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="71de1-113">Houd er rekening mee dat deze invoegtoepassing werkt voor Outlook op alle platforms, op het web, iOS, Android en desktop.</span><span class="sxs-lookup"><span data-stu-id="71de1-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="71de1-114">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, gebruikt u de portal Inzendingen in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="71de1-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="71de1-115">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="71de1-116">U kunt configureren om berichten rechtstreeks naar Microsoft te verzenden, een postvak dat u opgeeft of beide.</span><span class="sxs-lookup"><span data-stu-id="71de1-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="71de1-117">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="71de1-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="71de1-118">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="71de1-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="71de1-119">De functie Rapportbericht gebruiken</span><span class="sxs-lookup"><span data-stu-id="71de1-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="71de1-120">Ongewenste e-mailberichten en phishingberichten rapporteren</span><span class="sxs-lookup"><span data-stu-id="71de1-120">Report junk and phishing messages</span></span>

<span data-ttu-id="71de1-121">Voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, gebruikt u de volgende methode om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="71de1-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="71de1-122">Klik op **de** drie puntjes Meer acties in de rechterbovenhoek van het geselecteerde bericht, klik in de vervolgkeuzelijst op Bericht rapporteren en selecteer **vervolgens Ongewenste** e-mail of **Phishing.** </span><span class="sxs-lookup"><span data-stu-id="71de1-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71de1-123">![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71de1-124">![Rapportbericht - Ongewenste e-mail en phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="71de1-125">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="71de1-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="71de1-126">Verplaatst naar de map Ongewenste e-mail als deze is gerapporteerd als spam.</span><span class="sxs-lookup"><span data-stu-id="71de1-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="71de1-127">Verwijderd als dit is gerapporteerd als phishing.</span><span class="sxs-lookup"><span data-stu-id="71de1-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="71de1-128">Berichten rapporteren die geen ongewenste e-mail zijn</span><span class="sxs-lookup"><span data-stu-id="71de1-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="71de1-129">Klik op **de** drie puntjes Meer acties in de rechterbovenhoek van het geselecteerde bericht, klik in de vervolgkeuzelijst op Bericht rapporteren en klik vervolgens op **Geen ongewenste e-mail.** </span><span class="sxs-lookup"><span data-stu-id="71de1-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71de1-130">![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71de1-131">![Rapportbericht - Geen ongewenste e-mail](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="71de1-132">Het geselecteerde bericht wordt ter analyse naar Microsoft verzonden en verplaatst naar Postvak IN of een andere opgegeven map.</span><span class="sxs-lookup"><span data-stu-id="71de1-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="71de1-133">De invoegvoegingen Rapportbericht en Phishing melden inschakelen</span><span class="sxs-lookup"><span data-stu-id="71de1-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="71de1-134">Met de invoegvoegingen Rapportbericht en Rapport phishing voor de webversie van Outlook en Outlook (voorheen Bekend als Outlook Web App) kunnen personen eenvoudig onwaar-positieven (goede e-mail die als slecht is gemarkeerd) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.</span><span class="sxs-lookup"><span data-stu-id="71de1-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="71de1-135">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="71de1-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="71de1-136">Stel dat mensen veel berichten rapporteren met de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="71de1-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="71de1-137">Deze informatie wordt in het beveiligingsdashboard en andere rapporten opgedoken.</span><span class="sxs-lookup"><span data-stu-id="71de1-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="71de1-138">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat anti-phishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="71de1-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="71de1-139">U kunt de invoeging Rapportbericht of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="71de1-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="71de1-140">Als u wilt dat uw gebruikers zowel spam- als phishingberichten rapporteren, implementeert u de invoeging Rapportbericht in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="71de1-141">Zie De invoegvoegapp Rapportbericht inschakelen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="71de1-142">De invoegoptie Rapportbericht biedt de optie om zowel spam- als phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="71de1-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="71de1-143">Beheerders kunnen de invoeging Rapportbericht voor de organisatie inschakelen en afzonderlijke gebruikers kunnen het zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="71de1-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="71de1-144">De invoegvoegvoegoptie Phishing melden biedt de optie om alleen phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="71de1-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="71de1-145">Beheerders kunnen de invoeging Phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="71de1-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="71de1-146">Als u een individuele gebruiker bent, kunt u beide invoegvoegingen voor uzelf inschakelen.</span><span class="sxs-lookup"><span data-stu-id="71de1-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="71de1-147">f u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor OAuth-verificatie, u kunt de invoegvoeging Rapportbericht en de invoeging Phishing melden inschakelen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="71de1-148">Beide invoegvoegingen zijn nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="71de1-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="71de1-149">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="71de1-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="71de1-150">Zowel de invoeging Report Message als de invoeging Report Phishing werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="71de1-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="71de1-151">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="71de1-151">Outlook on the web</span></span>
  - <span data-ttu-id="71de1-152">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="71de1-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="71de1-153">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="71de1-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="71de1-154">Outlook inbegrepen bij Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="71de1-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="71de1-155">Outlook-app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="71de1-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="71de1-156">Beide invoegvakken zijn niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="71de1-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="71de1-157">Uw bestaande webbrowser moet werken met zowel de invoegvoegingen Rapportbericht als Phishing melden. Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="71de1-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="71de1-158">Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="71de1-159">Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="71de1-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="71de1-160">Beheerders moeten lid zijn van de rollengroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="71de1-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="71de1-161">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="71de1-162">De invoegvoegvoegvoeging Rapportbericht ontvangen</span><span class="sxs-lookup"><span data-stu-id="71de1-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="71de1-163">De invoeging voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="71de1-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="71de1-164">Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="71de1-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="71de1-165">Als u rechtstreeks naar de invoeging Rapportbericht wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="71de1-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="71de1-166">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="71de1-166">Click **GET IT NOW**.</span></span>

   ![Rapportbericht - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="71de1-168">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71de1-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="71de1-169">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="71de1-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="71de1-170">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="71de1-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="71de1-171">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71de1-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71de1-172">![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="71de1-173">In de webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71de1-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71de1-174">![Pictogram Rapportbericht van Outlook op het web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="71de1-175">De invoeging voor uw organisatie krijgen</span><span class="sxs-lookup"><span data-stu-id="71de1-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="71de1-176">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="71de1-177">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71de1-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71de1-178">Als u de invoegpagina niet ziet,  gaat u naar de koppeling Geïntegreerde apps met instellingen boven aan de pagina Geïntegreerde  \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71de1-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="71de1-179">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71de1-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegvoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="71de1-181">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71de1-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="71de1-182">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="71de1-182">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="71de1-184">Klik in het vak Zoeken op de  pagina Selecteer **invoegbericht** dat wordt weergegeven, voer **Rapportbericht** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="71de1-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="71de1-185">Zoek rapportbericht in de lijst met **resultaten** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="71de1-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="71de1-187">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71de1-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="71de1-188">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="71de1-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="71de1-189">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71de1-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="71de1-190">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="71de1-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="71de1-191">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="71de1-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="71de1-192">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="71de1-192">**Just me**</span></span>

   - <span data-ttu-id="71de1-193">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71de1-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="71de1-194">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="71de1-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="71de1-195">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="71de1-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="71de1-196">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71de1-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   <span data-ttu-id="71de1-198">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="71de1-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="71de1-199">Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegvoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="71de1-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="71de1-200">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="71de1-200">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="71de1-202">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="71de1-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="71de1-204">Instellingen controleren of bewerken voor de invoegvoegbewerking Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="71de1-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="71de1-205">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71de1-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71de1-206">Als u de invoegpagina niet ziet,  gaat u naar de koppeling Geïntegreerde apps met instellingen boven aan de pagina Geïntegreerde  \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71de1-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="71de1-208">Zoek en selecteer de **invoeging Rapportbericht.**</span><span class="sxs-lookup"><span data-stu-id="71de1-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="71de1-209">In het **flyout Rapportbericht bewerken** dat wordt weergegeven, controleert en bewerkt u de instellingen die geschikt zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="71de1-210">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="71de1-210">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoeging Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="71de1-212">De invoeging Phishing melden</span><span class="sxs-lookup"><span data-stu-id="71de1-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="71de1-213">De invoeging voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="71de1-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="71de1-214">Ga naar de Microsoft AppSource op <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="71de1-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="71de1-215">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="71de1-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="71de1-216">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71de1-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="71de1-217">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="71de1-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="71de1-218">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="71de1-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="71de1-219">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71de1-219">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegversie van Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="71de1-221">In de webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71de1-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71de1-222">![Pictogram Phishing-invoegversie van Outlook op het web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="71de1-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="71de1-223">De invoeging voor uw organisatie krijgen</span><span class="sxs-lookup"><span data-stu-id="71de1-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="71de1-224">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71de1-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="71de1-225">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71de1-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71de1-226">Als u de invoegpagina niet ziet,  gaat u naar de koppeling Geïntegreerde apps met instellingen boven aan de pagina Geïntegreerde  \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71de1-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="71de1-227">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71de1-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegvoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="71de1-229">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71de1-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="71de1-230">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="71de1-230">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="71de1-232">Klik in het vak Zoeken op de  **pagina** Invoeg toevoegen selecteren die wordt weergegeven, voer **Rapport phishing** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="71de1-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="71de1-233">Zoek in de lijst met resultaten **naar Rapport phishing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="71de1-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="71de1-234">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71de1-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="71de1-235">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="71de1-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="71de1-236">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71de1-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="71de1-237">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="71de1-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="71de1-238">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="71de1-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="71de1-239">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="71de1-239">**Just me**</span></span>

   - <span data-ttu-id="71de1-240">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71de1-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="71de1-241">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="71de1-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="71de1-242">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="71de1-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="71de1-243">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71de1-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="71de1-244">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="71de1-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="71de1-245">Op de **pagina Rapport phishing implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="71de1-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="71de1-246">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="71de1-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="71de1-247">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="71de1-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="71de1-248">Instellingen controleren of bewerken voor de invoeging Phishingrapport</span><span class="sxs-lookup"><span data-stu-id="71de1-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="71de1-249">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71de1-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71de1-250">Als u de invoegpagina niet ziet,  gaat u naar de koppeling Geïntegreerde apps met instellingen boven aan de pagina Geïntegreerde  \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71de1-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="71de1-251">Zoek en selecteer de **invoeging Phishing** melden.</span><span class="sxs-lookup"><span data-stu-id="71de1-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="71de1-252">In het **flyout Rapport phishing bewerken** dat de instellingen voor uw organisatie wordt weergegeven, controleren en bewerken.</span><span class="sxs-lookup"><span data-stu-id="71de1-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="71de1-253">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="71de1-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="71de1-254">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="71de1-254">View and review reported messages</span></span>

<span data-ttu-id="71de1-255">Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="71de1-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="71de1-256">Gebruik de portal Beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="71de1-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="71de1-257">Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="71de1-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="71de1-258">Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="71de1-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="71de1-259">Zie Regels voor [e-mailstroom gebruiken voor](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)instructies om te zien wat uw gebruikers rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71de1-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>