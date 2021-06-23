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
description: Informatie over het inschakelen van het rapportbericht of de phishing-invoegvoegingen voor Outlook en webversie van Outlook, voor individuele gebruikers of voor uw hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5e336dcab9e3787d8c5245cdbe32855c59021f7
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082766"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="71f92-103">Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="71f92-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="71f92-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="71f92-104">**Applies to**</span></span>
- [<span data-ttu-id="71f92-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="71f92-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="71f92-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="71f92-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="71f92-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71f92-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="71f92-108">Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden  we u aan de pagina Inzendingen te gebruiken in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="71f92-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the **Submissions** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="71f92-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="71f92-110">Met de invoegvoegingen Rapportbericht en Phishing melden voor Outlook en webversie van Outlook (voorheen bekend als Outlook Web App) kunnen personen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.</span><span class="sxs-lookup"><span data-stu-id="71f92-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="71f92-111">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="71f92-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="71f92-112">Stel dat mensen veel berichten rapporteren met de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="71f92-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="71f92-113">Deze informatie wordt in het beveiligingsdashboard en andere rapporten opgedoken.</span><span class="sxs-lookup"><span data-stu-id="71f92-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="71f92-114">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat anti-phishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="71f92-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="71f92-115">U kunt de invoeging Rapportbericht of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="71f92-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="71f92-116">Als u wilt dat uw gebruikers zowel spam- als phishingberichten rapporteren, implementeert u de invoeging Rapportbericht in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="71f92-117">Zie De invoegvoegapp Rapportbericht inschakelen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-117">For more information, see Enable the Report Message add-in.</span></span>

<span data-ttu-id="71f92-118">De invoegoptie Rapportbericht biedt de optie om zowel spam- als phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="71f92-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="71f92-119">Beheerders kunnen de invoeging Rapportbericht voor de organisatie inschakelen en afzonderlijke gebruikers kunnen het zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="71f92-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="71f92-120">De invoegvoegvoegoptie Phishing melden biedt de optie om alleen phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="71f92-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="71f92-121">Beheerders kunnen de invoeging Phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="71f92-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="71f92-122">Als u een individuele gebruiker bent, kunt u beide invoegvoegingen voor uzelf inschakelen.</span><span class="sxs-lookup"><span data-stu-id="71f92-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="71f92-123">Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoeging Rapportbericht en de invoeging Phishingrapport voor uw organisatie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="71f92-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="71f92-124">Beide invoegvoegingen zijn nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="71f92-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="71f92-125">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="71f92-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="71f92-126">Zowel de invoeging Rapportbericht als de invoeging Phishing-rapport werkt met de meeste Microsoft 365 en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="71f92-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="71f92-127">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="71f92-127">Outlook on the web</span></span>
  - <span data-ttu-id="71f92-128">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="71f92-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="71f92-129">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="71f92-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="71f92-130">Outlook opgenomen in Microsoft 365 apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="71f92-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="71f92-131">Outlook app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="71f92-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="71f92-132">Beide invoegvakken zijn niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange organisaties.</span><span class="sxs-lookup"><span data-stu-id="71f92-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="71f92-133">Uw bestaande webbrowser moet werken met zowel de invoegvoegingen Rapportbericht als Phishing melden. Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="71f92-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="71f92-134">Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="71f92-135">Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="71f92-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="71f92-136">Beheerders moeten lid zijn van de rollengroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="71f92-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="71f92-137">Zie [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="71f92-138">Zie Fout-positieven en onwaar negatieven rapporteren in Outlook voor meer informatie over het rapporteren van een bericht met de [functie Rapportbericht.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="71f92-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71f92-139">We raden u de ingebouwde rapportageervaring in Outlook omdat het beleid voor het indienen van gebruikers niet [kan worden gebruikt.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="71f92-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="71f92-140">We raden u aan in plaats daarvan de invoeging Rapportbericht of de invoeging Phishing melden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="71f92-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="71f92-141">De invoegvoegvoegvoeging Rapportbericht ontvangen</span><span class="sxs-lookup"><span data-stu-id="71f92-141">Get the Report Message add-in</span></span>

### <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="71f92-142">De invoeging Rapportbericht voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="71f92-142">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="71f92-143">Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="71f92-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="71f92-144">Als u rechtstreeks naar de invoeging Rapportbericht wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="71f92-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="71f92-145">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="71f92-145">Click **GET IT NOW**.</span></span>

   ![Rapportbericht - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="71f92-147">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71f92-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="71f92-148">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="71f92-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="71f92-149">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="71f92-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="71f92-150">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71f92-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71f92-151">![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="71f92-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="71f92-152">In webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71f92-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71f92-153">![webversie van Outlook Pictogram Berichtrapport](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="71f92-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="71f92-154">De invoegvoegvoeging Rapportbericht voor uw organisatie ontvangen</span><span class="sxs-lookup"><span data-stu-id="71f92-154">Get the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="71f92-155">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="71f92-156">Ga in Microsoft 365-beheercentrum naar de pagina **Instellingen** \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71f92-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71f92-157">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71f92-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="71f92-158">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71f92-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegingen in de Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="71f92-160">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71f92-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="71f92-161">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="71f92-161">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="71f92-163">Klik in het vak Zoeken op de  pagina Selecteer **invoegbericht** dat wordt weergegeven, voer **Rapportbericht** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="71f92-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="71f92-164">Zoek rapportbericht in de lijst met **resultaten** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="71f92-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="71f92-166">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71f92-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="71f92-167">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="71f92-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="71f92-168">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71f92-168">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="71f92-169">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="71f92-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="71f92-170">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="71f92-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="71f92-171">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="71f92-171">**Just me**</span></span>

   - <span data-ttu-id="71f92-172">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71f92-172">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="71f92-173">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="71f92-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="71f92-174">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="71f92-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="71f92-175">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71f92-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   <span data-ttu-id="71f92-177">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="71f92-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="71f92-178">Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegvoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="71f92-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="71f92-179">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="71f92-179">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="71f92-181">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="71f92-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="71f92-183">Instellingen controleren of bewerken voor de invoegvoegbewerking Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="71f92-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="71f92-184">Ga in Microsoft 365-beheercentrum naar de pagina  Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71f92-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71f92-185">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71f92-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheer Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="71f92-187">Zoek en selecteer de **invoeging Rapportbericht.**</span><span class="sxs-lookup"><span data-stu-id="71f92-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="71f92-188">In het **flyout Rapportbericht bewerken** dat wordt weergegeven, controleert en bewerkt u de instellingen die geschikt zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="71f92-189">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="71f92-189">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoeging Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="71f92-191">De invoeging Phishing melden</span><span class="sxs-lookup"><span data-stu-id="71f92-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="71f92-192">De invoeging Report Phishing voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="71f92-192">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="71f92-193">Ga naar de Microsoft AppSource op <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="71f92-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="71f92-194">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="71f92-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="71f92-195">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71f92-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="71f92-196">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="71f92-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="71f92-197">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="71f92-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="71f92-198">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71f92-198">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegvoeging melden voor Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="71f92-200">In webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="71f92-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71f92-201">![webversie van Outlook Pictogram Phishing-invoeging melden](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="71f92-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="71f92-202">De invoeging Phishingrapport voor uw organisatie ontvangen</span><span class="sxs-lookup"><span data-stu-id="71f92-202">Get the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="71f92-203">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71f92-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="71f92-204">Ga in Microsoft 365-beheercentrum naar de pagina  Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71f92-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71f92-205">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71f92-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="71f92-206">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71f92-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegingen in de Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="71f92-208">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="71f92-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="71f92-209">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="71f92-209">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="71f92-211">Klik in het vak Zoeken op de  **pagina** Invoeg toevoegen selecteren die wordt weergegeven, voer **Rapport phishing** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="71f92-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="71f92-212">Zoek in de lijst met resultaten **naar Rapport phishing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="71f92-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="71f92-213">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="71f92-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="71f92-214">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="71f92-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="71f92-215">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71f92-215">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="71f92-216">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="71f92-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="71f92-217">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="71f92-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="71f92-218">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="71f92-218">**Just me**</span></span>

   - <span data-ttu-id="71f92-219">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="71f92-219">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="71f92-220">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="71f92-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="71f92-221">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="71f92-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="71f92-222">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71f92-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="71f92-223">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="71f92-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="71f92-224">Op de **pagina Rapport phishing implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="71f92-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="71f92-225">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="71f92-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="71f92-226">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="71f92-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="71f92-227">Instellingen controleren of bewerken voor de invoeging Phishingrapport</span><span class="sxs-lookup"><span data-stu-id="71f92-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="71f92-228">Ga in Microsoft 365-beheercentrum naar de pagina  Instellingen \> **invoegvoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="71f92-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="71f92-229">Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**</span><span class="sxs-lookup"><span data-stu-id="71f92-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="71f92-230">Zoek en selecteer de **invoeging Phishing** melden.</span><span class="sxs-lookup"><span data-stu-id="71f92-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="71f92-231">In het **flyout Rapport phishing bewerken** dat de instellingen voor uw organisatie wordt weergegeven, controleren en bewerken.</span><span class="sxs-lookup"><span data-stu-id="71f92-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="71f92-232">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="71f92-232">When you're finished, click **Save**.</span></span>
