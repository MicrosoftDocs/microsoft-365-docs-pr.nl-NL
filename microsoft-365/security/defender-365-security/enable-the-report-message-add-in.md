---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Meer informatie over het inschakelen van de invoegversie van rapportbericht voor de webversie van Outlook en Outlook, voor individuele gebruikers of uw hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e85af902eaaa41eb82acf8d4b4baedc538e7888
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058526"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="5b6bc-103">De invoegtoepassing Bericht rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="5b6bc-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5b6bc-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-104">**Applies to**</span></span>
- [<span data-ttu-id="5b6bc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5b6bc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5b6bc-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5b6bc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5b6bc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b6bc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="5b6bc-108">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5b6bc-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="5b6bc-110">Met de invoegvoegingen Rapportbericht en Rapport phishing voor de webversie van Outlook en Outlook (voorheen Bekend als Outlook Web App) kunnen personen eenvoudig onwaar-positieven (goede e-mail die als slecht is gemarkeerd) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="5b6bc-111">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="5b6bc-112">Als mensen bijvoorbeeld een groot aantal berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als Geen ongewenste [e-mail](configure-your-spam-filter-policies.md)met behulp van de invoegmap Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk antispambeleid aanpassen.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5b6bc-113">U kunt de invoeging Rapportbericht of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="5b6bc-114">Als u wilt dat uw gebruikers alleen phishingberichten rapporteren, implementeert u de invoeging Phishing melden in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="5b6bc-115">Zie De [invoeging Phishing melden inschakelen voor meer informatie.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="5b6bc-116">De invoegoptie Rapportbericht biedt de optie om zowel spam- als phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="5b6bc-117">Beheerders kunnen de invoeging Rapportbericht voor de organisatie inschakelen en afzonderlijke gebruikers kunnen het zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="5b6bc-118">Als u een individuele gebruiker bent, kunt u de invoeging [Rapportbericht voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="5b6bc-119">Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoegvoeging [Rapportbericht inschakelen voor uw organisatie.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="5b6bc-120">Het rapportbericht Add-In is nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-120">The Report Message Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5b6bc-121">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5b6bc-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5b6bc-122">De invoegvoegapp Rapportbericht werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="5b6bc-123">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="5b6bc-123">Outlook on the web</span></span>
  - <span data-ttu-id="5b6bc-124">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="5b6bc-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="5b6bc-125">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="5b6bc-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="5b6bc-126">Outlook inbegrepen bij Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="5b6bc-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="5b6bc-127">Outlook-app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="5b6bc-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="5b6bc-128">De invoeging Rapportbericht is niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-128">The Report Message add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="5b6bc-129">U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="5b6bc-130">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="5b6bc-131">Uw bestaande webbrowser moet werken met de invoeging Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="5b6bc-132">Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="5b6bc-133">Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="5b6bc-134">Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="5b6bc-135">Beheerders moeten lid zijn van de rollengroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="5b6bc-136">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="5b6bc-137">De invoeging Rapportbericht voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="5b6bc-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="5b6bc-138">Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="5b6bc-139">Als u rechtstreeks naar de invoeging Rapportbericht wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="5b6bc-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="5b6bc-140">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-140">Click **GET IT NOW**.</span></span>

   ![Rapportbericht - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="5b6bc-142">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="5b6bc-143">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="5b6bc-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="5b6bc-144">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="5b6bc-145">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-145">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="5b6bc-147">In de webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Rapportbericht van Outlook op het web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="5b6bc-149">Zie De invoeging Rapportbericht gebruiken voor meer informatie over het gebruik van [de invoeging.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="5b6bc-150">De invoeging Rapportbericht voor uw organisatie ontvangen en inschakelen</span><span class="sxs-lookup"><span data-stu-id="5b6bc-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="5b6bc-151">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="5b6bc-152">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen invoegvoegingen op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="5b6bc-153">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegvoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="5b6bc-155">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="5b6bc-156">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-156">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="5b6bc-158">Klik in het vak Zoeken op de  pagina Selecteer **invoegbericht** dat wordt weergegeven, voer **Rapportbericht** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="5b6bc-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="5b6bc-159">Zoek rapportbericht in de lijst met **resultaten** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="5b6bc-161">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="5b6bc-162">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5b6bc-163">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="5b6bc-164">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="5b6bc-165">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="5b6bc-166">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-166">**Just me**</span></span>

   - <span data-ttu-id="5b6bc-167">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="5b6bc-168">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="5b6bc-169">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="5b6bc-170">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   <span data-ttu-id="5b6bc-172">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="5b6bc-173">Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegvoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="5b6bc-174">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-174">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="5b6bc-176">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="5b6bc-178">Meer informatie over het gebruik van de invoeging Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="5b6bc-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="5b6bc-179">Personen aan wie de invoegvoeging is toegewezen, zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="5b6bc-180">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-180">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="5b6bc-182">In de webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Bericht van outlook op het webrapport](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="5b6bc-184">Wanneer u gebruikers op de hoogte stelt van de invoegvoegapp Rapportbericht, voegt u een koppeling toe aan De invoeging [Rapportbericht gebruiken.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="5b6bc-185">Instellingen controleren of bewerken voor de invoegvoegbewerking Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="5b6bc-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="5b6bc-186">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen invoegvoegingen op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="5b6bc-188">Zoek en selecteer de **invoeging Rapportbericht.**</span><span class="sxs-lookup"><span data-stu-id="5b6bc-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="5b6bc-189">In het **flyout Rapportbericht bewerken** dat wordt weergegeven, controleert en bewerkt u de instellingen die geschikt zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="5b6bc-190">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-190">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoeging Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="5b6bc-192">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="5b6bc-192">View and review reported messages</span></span>

<span data-ttu-id="5b6bc-193">Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="5b6bc-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="5b6bc-194">Gebruik de portal Beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="5b6bc-195">Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="5b6bc-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="5b6bc-196">Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="5b6bc-197">Zie Regels voor [e-mailstroom gebruiken voor](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)instructies om te zien wat uw gebruikers rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b6bc-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
