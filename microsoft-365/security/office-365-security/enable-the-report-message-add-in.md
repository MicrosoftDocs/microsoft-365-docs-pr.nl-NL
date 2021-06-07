---
title: Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Meer informatie over het inschakelen van het rapportbericht of de phishing-invoegvoegingen voor Outlook en Outlook op internet, voor individuele gebruikers of voor uw hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25c4f7d67fd4fa876544a17df0f4bc1abfd7b3e7
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782931"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="09ffc-103">Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="09ffc-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="09ffc-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="09ffc-104">**Applies to**</span></span>
- [<span data-ttu-id="09ffc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="09ffc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="09ffc-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="09ffc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="09ffc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09ffc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="09ffc-108">Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="09ffc-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="09ffc-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="09ffc-110">Met de invoegvoegingen Rapportbericht en Phishing melden voor Outlook en Outlook op het web (voorheen bekend als Outlook Web App) kunnen personen eenvoudig onwaar positieven (goede e-mail gemarkeerd als slecht) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.</span><span class="sxs-lookup"><span data-stu-id="09ffc-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="09ffc-111">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="09ffc-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="09ffc-112">Stel dat mensen veel berichten rapporteren met de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="09ffc-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="09ffc-113">Deze informatie wordt in het beveiligingsdashboard en andere rapporten opgedoken.</span><span class="sxs-lookup"><span data-stu-id="09ffc-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="09ffc-114">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat anti-phishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="09ffc-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="09ffc-115">U kunt de invoeging Rapportbericht of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="09ffc-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="09ffc-116">Als u wilt dat uw gebruikers zowel spam- als phishingberichten rapporteren, implementeert u de invoeging Rapportbericht in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="09ffc-117">Zie De invoegvoegapp Rapportbericht inschakelen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="09ffc-118">De invoegoptie Rapportbericht biedt de optie om zowel spam- als phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="09ffc-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="09ffc-119">Beheerders kunnen de invoeging Rapportbericht voor de organisatie inschakelen en afzonderlijke gebruikers kunnen het zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="09ffc-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="09ffc-120">De invoegvoegvoegoptie Phishing melden biedt de optie om alleen phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="09ffc-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="09ffc-121">Beheerders kunnen de invoeging Phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="09ffc-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="09ffc-122">Als u een individuele gebruiker bent, kunt u beide invoegvoegingen voor uzelf inschakelen.</span><span class="sxs-lookup"><span data-stu-id="09ffc-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="09ffc-123">Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoeging Rapportbericht en de invoeging Phishingrapport voor uw organisatie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="09ffc-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="09ffc-124">Beide invoegvoegingen zijn nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="09ffc-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="09ffc-125">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="09ffc-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="09ffc-126">Zowel de invoeging Rapportbericht als de invoeging Phishing-rapport werkt met de meeste Microsoft 365 en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="09ffc-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="09ffc-127">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="09ffc-127">Outlook on the web</span></span>
  - <span data-ttu-id="09ffc-128">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="09ffc-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="09ffc-129">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="09ffc-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="09ffc-130">Outlook opgenomen in Microsoft 365 apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="09ffc-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="09ffc-131">Outlook app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="09ffc-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="09ffc-132">Beide invoegvakken zijn niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange organisaties.</span><span class="sxs-lookup"><span data-stu-id="09ffc-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="09ffc-133">Uw bestaande webbrowser moet werken met zowel de invoegvoegingen Rapportbericht als Phishing melden. Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="09ffc-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="09ffc-134">Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="09ffc-135">Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="09ffc-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="09ffc-136">Beheerders moeten lid zijn van de rollengroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="09ffc-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="09ffc-137">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="09ffc-138">Zie Fout-positieven en onwaar negatieven rapporteren in Outlook voor meer informatie over het rapporteren van een bericht met de [functie Rapportbericht.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="09ffc-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="09ffc-139">De invoegvoegvoegvoeging Rapportbericht ontvangen</span><span class="sxs-lookup"><span data-stu-id="09ffc-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="09ffc-140">De invoeging voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="09ffc-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="09ffc-141">Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="09ffc-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="09ffc-142">Als u rechtstreeks naar de invoeging Rapportbericht wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="09ffc-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="09ffc-143">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-143">Click **GET IT NOW**.</span></span>

   ![Rapportbericht - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="09ffc-145">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="09ffc-146">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="09ffc-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="09ffc-147">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="09ffc-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="09ffc-148">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="09ffc-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="09ffc-149">![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="09ffc-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="09ffc-150">In Outlook op internet ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="09ffc-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="09ffc-151">![Outlook invoegpictogram rapportbericht op het web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="09ffc-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="09ffc-152">De invoeging voor uw organisatie krijgen</span><span class="sxs-lookup"><span data-stu-id="09ffc-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="09ffc-153">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="09ffc-154">Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="09ffc-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="09ffc-155">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="09ffc-156">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegingen in het Microsoft 365 beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="09ffc-158">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="09ffc-159">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-159">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="09ffc-161">Klik in het vak Zoeken op de  pagina Selecteer **invoegbericht** dat wordt weergegeven, voer **Rapportbericht** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="09ffc-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="09ffc-162">Zoek rapportbericht in de lijst met **resultaten** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="09ffc-164">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="09ffc-165">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="09ffc-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="09ffc-166">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="09ffc-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="09ffc-167">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="09ffc-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="09ffc-168">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="09ffc-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="09ffc-169">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="09ffc-169">**Just me**</span></span>

   - <span data-ttu-id="09ffc-170">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="09ffc-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="09ffc-171">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="09ffc-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="09ffc-172">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="09ffc-173">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="09ffc-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   <span data-ttu-id="09ffc-175">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="09ffc-176">Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegvoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="09ffc-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="09ffc-177">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="09ffc-177">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="09ffc-179">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="09ffc-181">Instellingen controleren of bewerken voor de invoegvoegbewerking Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="09ffc-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="09ffc-182">Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="09ffc-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="09ffc-183">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="09ffc-185">Zoek en selecteer de **invoeging Rapportbericht.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="09ffc-186">In het **flyout Rapportbericht bewerken** dat wordt weergegeven, controleert en bewerkt u de instellingen die geschikt zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="09ffc-187">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="09ffc-187">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoeging Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="09ffc-189">De invoeging Phishing melden</span><span class="sxs-lookup"><span data-stu-id="09ffc-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="09ffc-190">De invoeging voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="09ffc-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="09ffc-191">Ga naar de Microsoft AppSource op <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="09ffc-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="09ffc-192">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="09ffc-193">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="09ffc-194">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="09ffc-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="09ffc-195">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="09ffc-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="09ffc-196">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="09ffc-196">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegvoeging melden voor Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="09ffc-198">In Outlook op internet ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="09ffc-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="09ffc-199">![Outlook het pictogram Phishing-invoegvoegbericht op het web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="09ffc-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="09ffc-200">De invoeging voor uw organisatie krijgen</span><span class="sxs-lookup"><span data-stu-id="09ffc-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="09ffc-201">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09ffc-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="09ffc-202">Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="09ffc-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="09ffc-203">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="09ffc-204">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegingen in het Microsoft 365 beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="09ffc-206">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="09ffc-207">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-207">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="09ffc-209">Klik in het vak Zoeken op de  **pagina** Invoeg toevoegen selecteren die wordt weergegeven, voer **Rapport phishing** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="09ffc-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="09ffc-210">Zoek in de lijst met resultaten **naar Rapport phishing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="09ffc-211">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="09ffc-212">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="09ffc-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="09ffc-213">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="09ffc-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="09ffc-214">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="09ffc-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="09ffc-215">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="09ffc-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="09ffc-216">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="09ffc-216">**Just me**</span></span>

   - <span data-ttu-id="09ffc-217">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="09ffc-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="09ffc-218">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="09ffc-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="09ffc-219">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="09ffc-220">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="09ffc-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="09ffc-221">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="09ffc-222">Op de **pagina Rapport phishing implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="09ffc-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="09ffc-223">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="09ffc-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="09ffc-224">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="09ffc-225">Instellingen controleren of bewerken voor de invoeging Phishingrapport</span><span class="sxs-lookup"><span data-stu-id="09ffc-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="09ffc-226">Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="09ffc-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="09ffc-227">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="09ffc-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="09ffc-228">Zoek en selecteer de **invoeging Phishing** melden.</span><span class="sxs-lookup"><span data-stu-id="09ffc-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="09ffc-229">In het **flyout Rapport phishing bewerken** dat de instellingen voor uw organisatie wordt weergegeven, controleren en bewerken.</span><span class="sxs-lookup"><span data-stu-id="09ffc-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="09ffc-230">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="09ffc-230">When you're finished, click **Save**.</span></span>
