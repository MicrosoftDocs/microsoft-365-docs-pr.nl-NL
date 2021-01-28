---
title: De invoegtoepassing voor het melden van rapporten inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Meer informatie over het inschakelen van de invoegtoepassing voor het melden van rapporten voor Outlook en de webversie van Outlook voor afzonderlijke gebruikers of voor de hele organisatie.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029136"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="56329-103">De invoegtoepassing Phishing rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="56329-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="56329-104">Als u een beheerder bent van een Microsoft 365-organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="56329-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="56329-105">Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="56329-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="56329-106">Met de functie voor het melden van e-mailberichten en het rapporteren van phishing-invoegtoepassingen voor Outlook en de webversie van Outlook (voorheen Outlook Web app) kunnen mensen eenvoudig onjuiste positief (goede e-mailberichten als beschadigd) melden</span><span class="sxs-lookup"><span data-stu-id="56329-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="56329-107">Microsoft gebruikt deze inzendingen om de effectiviteit van de technologieën voor e-mail beveiliging te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="56329-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="56329-108">Stel dat mensen veel berichten rapporteren met behulp van de phishing-invoegtoepassing voor rapporten.</span><span class="sxs-lookup"><span data-stu-id="56329-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="56329-109">Deze informatie vlakken zijn te zien in het [beveiligings dashboard](security-dashboard.md) en andere rapporten.</span><span class="sxs-lookup"><span data-stu-id="56329-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="56329-110">Het beveiligingsteam van uw organisatie kan deze gegevens gebruiken, omdat er mogelijk een anti-phishing beleid moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="56329-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="56329-111">U kunt de invoegtoepassing voor het melden van een bericht of rapport installeren.</span><span class="sxs-lookup"><span data-stu-id="56329-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="56329-112">Als u wilt dat gebruikers zowel spam als phishingberichten kunnen rapporteren, moet u de invoegtoepassing bericht rapporteren in uw organisatie implementeren.</span><span class="sxs-lookup"><span data-stu-id="56329-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="56329-113">Zie [de invoegtoepassing bericht rapporteren inschakelen](enable-the-report-message-add-in.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="56329-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="56329-114">De invoegtoepassing voor het melden van rapporten biedt de mogelijkheid alleen phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="56329-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="56329-115">Beheerders kunnen de invoegtoepassing voor het melden van rapporten inschakelen voor de organisatie en afzonderlijke gebruikers kunnen de app voor zichzelf installeren.</span><span class="sxs-lookup"><span data-stu-id="56329-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="56329-116">Als u een individuele gebruiker bent, kunt u [de invoegtoepassing voor phishing voor uzelf inschakelen](#get-the-report-phishing-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="56329-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="56329-117">Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor gebruik van OAuth-verificatie, kunt u [de invoegtoepassing voor Phishingfilter voor uw organisatie inschakelen](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="56329-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="56329-118">De phishing-Add-In voor het rapport is nu beschikbaar via [gecentraliseerde implementatie](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="56329-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="56329-119">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="56329-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="56329-120">De invoegtoepassing voor het melden van rapporten werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="56329-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="56329-121">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="56329-121">Outlook on the web</span></span>
  - <span data-ttu-id="56329-122">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="56329-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="56329-123">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="56329-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="56329-124">Outlook inbegrepen in Microsoft 365 apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="56329-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="56329-125">De invoegtoepassing voor het melden van rapporten is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="56329-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="56329-126">U kunt gerapporteerde berichten configureren voor kopiëren of omleiden naar een door u opgegeven postvak.</span><span class="sxs-lookup"><span data-stu-id="56329-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="56329-127">Zie voor meer informatie [beleidsregels voor gebruikers ingediend](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="56329-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="56329-128">De bestaande webbrowser moet samenwerken met de phishing-invoegtoepassing voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="56329-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="56329-129">Als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, kunt u een andere browser proberen.</span><span class="sxs-lookup"><span data-stu-id="56329-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="56329-130">Voor installaties via een organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="56329-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="56329-131">Zie [bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](../../admin/manage/centralized-deployment-of-add-ins.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="56329-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="56329-132">Beheerders moeten lid zijn van de rollen groep globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="56329-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="56329-133">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="56329-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="56329-134">De invoegtoepassing voor het melden van rapporten voor uzelf weergeven</span><span class="sxs-lookup"><span data-stu-id="56329-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="56329-135">Ga naar de website van Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> en zoek de invoegtoepassing Phishingfilter.</span><span class="sxs-lookup"><span data-stu-id="56329-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="56329-136">Klik op **Nu kopen**.</span><span class="sxs-lookup"><span data-stu-id="56329-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="56329-137">In het dialoogvenster dat wordt weergegeven, bekijkt u de gebruiksvoorwaarden en het privacybeleid en klikt u vervolgens op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="56329-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="56329-138">Meld u aan met uw werk-of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="56329-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="56329-139">Nadat de invoegtoepassing is geïnstalleerd en is ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="56329-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="56329-140">Het pictogram in Outlook ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="56329-140">In Outlook, the icon looks like this:</span></span>

  ![Pictogram voor phishing-invoegtoepassing voor Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="56329-142">Het pictogram in de webversie van Outlook ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="56329-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram voor phishing-invoegtoepassing voor Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="56329-144">De invoegtoepassing voor Phishingfilter voor uw organisatie inschakelen en inschakelen</span><span class="sxs-lookup"><span data-stu-id="56329-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="56329-145">Het kan 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="56329-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="56329-146">Ga in het Microsoft 365-Beheercentrum naar de pagina **instellingen** voor \> **invoegtoepassingen** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> weergeven als u de pagina **met invoegtoepassingen** niet ziet, gaat u naar de link invoegtoepassingen voor de instellingen van de invoegtoepassing voor de **instellingen** op de koppeling naar de \>  \> pagina **met**  geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="56329-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="56329-147">Selecteer **invoegtoepassing implementeren** boven aan de pagina en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="56329-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina met Services en invoegtoepassingen in het Microsoft 365-Beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="56329-149">Controleer de informatie in het vervolgmenu **een nieuwe invoegtoepassing implementeren** die wordt weergegeven en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="56329-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="56329-150">Op de volgende pagina klikt u op **kiezen uit de Store**.</span><span class="sxs-lookup"><span data-stu-id="56329-150">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe pagina met invoegtoepassingen implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="56329-152">Klik op de pagina **invoegtoepassing selecteren** die wordt weergegeven in het vak **zoeken** , typ **phishing melden** en klik vervolgens op **Zoek** ![ actie zoeken ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="56329-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="56329-153">Zoek in de lijst met resultaten de resultaten van **rapporten** en klik vervolgens op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="56329-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="56329-154">In het dialoogvenster dat wordt weergegeven, bekijkt u de licentie-en privacygegevens en klikt u vervolgens op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="56329-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="56329-155">Configureer de volgende instellingen op de pagina **invoegtoepassing configureren** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="56329-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="56329-156">**Toegewezen gebruikers**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="56329-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="56329-157">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="56329-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="56329-158">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="56329-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="56329-159">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="56329-159">**Just me**</span></span>

   - <span data-ttu-id="56329-160">**Implementatiemethode**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="56329-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="56329-161">**Fixed (standaardinstelling)**: de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan de invoegtoepassing niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="56329-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="56329-162">**Beschikbaar**: gebruikers kunnen de invoegtoepassing installeren bij de beheerder van de **Startpagina** \> **invoegtoepassingen** \> **beheren**.</span><span class="sxs-lookup"><span data-stu-id="56329-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="56329-163">**Optioneel**: de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen de optie wel verwijderen.</span><span class="sxs-lookup"><span data-stu-id="56329-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="56329-164">Wanneer u klaar bent, klikt u op **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="56329-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="56329-165">Op de pagina voor het implementeren van een **rapport** dat wordt weergegeven, wordt een voortgangsrapport weergegeven, gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="56329-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="56329-166">Nadat u de gegevens hebt gelezen, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="56329-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="56329-167">Controleer de gegevens op de pagina **aangekondigde invoegtoepassing** die wordt weergegeven en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="56329-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="56329-168">Meer informatie over het gebruik van de invoegtoepassing voor phishing-rapporten</span><span class="sxs-lookup"><span data-stu-id="56329-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="56329-169">Voor personen aan wie de invoegtoepassing is toegewezen, worden de volgende pictogrammen weergegeven:</span><span class="sxs-lookup"><span data-stu-id="56329-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="56329-170">Het pictogram in Outlook ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="56329-170">In Outlook, the icon looks like this:</span></span>

  ![Pictogram voor phishing-invoegtoepassing voor Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="56329-172">Het pictogram in de webversie van Outlook ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="56329-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram voor phishing-invoegtoepassing voor Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="56329-174">Instellingen voor de invoegtoepassing voor het melden van rapporten bekijken of bewerken</span><span class="sxs-lookup"><span data-stu-id="56329-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="56329-175">Ga in het Microsoft 365-Beheercentrum naar de pagina **instellingen** voor \> **invoegtoepassingen** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> weergeven als u de pagina **met invoegtoepassingen** niet ziet, gaat u naar de link invoegtoepassingen voor de instellingen van de invoegtoepassing voor de **instellingen** op de koppeling naar de \>  \> pagina **met**  geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="56329-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="56329-176">Zoek en selecteer de invoegtoepassing voor het melden van de **phishing** .</span><span class="sxs-lookup"><span data-stu-id="56329-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="56329-177">Ga in het leesvenster voor het **bewerken van rapporten** dat geschikt is voor uw organisatie, naar wens weer en controleer en bewerk de instellingen.</span><span class="sxs-lookup"><span data-stu-id="56329-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="56329-178">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="56329-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="56329-179">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="56329-179">View and review reported messages</span></span>

<span data-ttu-id="56329-180">Als u berichten wilt weergeven die gebruikers bij Microsoft rapporteren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="56329-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="56329-181">Gebruik de portal van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="56329-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="56329-182">Zie voor meer informatie [gebruikers items weergeven in Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="56329-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="56329-183">Maak een e-mail stroom regel (ook wel een transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="56329-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="56329-184">Zie voor instructies [de regels voor e-mail stroom gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="56329-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>