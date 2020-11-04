---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
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
description: Meer informatie over het inschakelen van de invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook voor afzonderlijke gebruikers of voor de hele organisatie.
ms.openlocfilehash: baed46e500e58702b7031db5aa5ff376a4eafcb5
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877751"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="3c6a0-103">De invoegtoepassing Bericht rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="3c6a0-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="3c6a0-104">Als u een beheerder bent van een Microsoft 365-organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3c6a0-105">Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="3c6a0-106">Met de invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook (voorheen Outlook Web app) kunnen gebruikers eenvoudig onjuiste positieven melden (goede e-mailberichten die als beschadigd zijn gemarkeerd) of fout-negatieven (onjuiste e-mail toegestaan) aan Microsoft en zijn gelieerde ondernemingen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="3c6a0-107">Microsoft gebruikt deze inzendingen om de effectiviteit van de technologieën voor e-mail beveiliging te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="3c6a0-108">Stel dat personen een heleboel berichten als phishing rapporteren.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="3c6a0-109">Deze informatie vlakken zijn te zien in het [beveiligings dashboard](security-dashboard.md) en andere rapporten.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="3c6a0-110">Het beveiligingsteam van uw organisatie kan deze gegevens gebruiken, omdat er mogelijk een anti-phishing beleid moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="3c6a0-111">Of als personen een heleboel berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als niet-ongewenste e-mail met behulp van de invoegtoepassing berichten rapporteren, moet het beveiligingsteam van uw organisatie het [Antispambeleid](configure-your-spam-filter-policies.md)wellicht aanpassen.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3c6a0-112">Als uw organisatie gebruikmaakt van [Microsoft Defender voor Office 365 (abonnement 1](office-365-atp.md) of [abonnement 2](office-365-ti.md)), biedt de invoegtoepassing bericht melden het beveiligingsteam van uw organisatie nuttige informatie die kan worden gebruikt om beveiligingsbeleid te controleren en bij te werken.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-112">In addition, if your organization is using [Microsoft Defender for Office 365 Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="3c6a0-113">Beheerders kunnen de invoegtoepassing bericht rapporteren voor de organisatie inschakelen en afzonderlijke gebruikers kunnen de invoegtoepassing voor zichzelf installeren.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="3c6a0-114">Als u een individuele gebruiker bent, kunt u [de invoegtoepassing bericht rapporteren voor uzelf inschakelen](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="3c6a0-115">Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u [de invoegtoepassing bericht rapporteren voor uw organisatie inschakelen](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="3c6a0-116">De Add-In rapportberichten is nu beschikbaar via [gecentraliseerde implementatie](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3c6a0-117">Wat moet je weten voordat je begint?</span><span class="sxs-lookup"><span data-stu-id="3c6a0-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3c6a0-118">De invoegtoepassing bericht rapporteren werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="3c6a0-119">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="3c6a0-119">Outlook on the web</span></span>
  - <span data-ttu-id="3c6a0-120">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="3c6a0-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="3c6a0-121">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="3c6a0-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="3c6a0-122">Outlook inbegrepen in Microsoft 365 apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c6a0-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="3c6a0-123">De invoegtoepassing bericht rapporteren is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="3c6a0-124">U kunt gerapporteerde berichten configureren voor kopiëren of omleiden naar een door u opgegeven postvak.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="3c6a0-125">Zie voor meer informatie [beleidsregels voor gebruikers ingediend](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="3c6a0-126">De bestaande webbrowser moet werken met de invoegtoepassing bericht melden.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="3c6a0-127">Als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, kunt u een andere browser proberen.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="3c6a0-128">Voor installaties via een organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="3c6a0-129">Zie [bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](../../admin/manage/centralized-deployment-of-add-ins.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="3c6a0-130">Beheerders moeten lid zijn van de rollen groep globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="3c6a0-131">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="3c6a0-132">De invoegtoepassing bericht rapporteren voor uzelf weergeven</span><span class="sxs-lookup"><span data-stu-id="3c6a0-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="3c6a0-133">Ga naar de Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoegtoepassing bericht melden.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="3c6a0-134">Als u rechtstreeks naar de invoegtoepassing bericht rapporteren wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="3c6a0-135">Klik op **Nu kopen**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-135">Click **GET IT NOW**.</span></span>

   ![Rapportbericht-nu kopen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="3c6a0-137">In het dialoogvenster dat wordt weergegeven, bekijkt u de gebruiksvoorwaarden en het privacybeleid en klikt u vervolgens op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="3c6a0-138">Meld u aan met uw werk-of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="3c6a0-139">Nadat de invoegtoepassing is geïnstalleerd en is ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="3c6a0-140">Het pictogram in Outlook ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-140">In Outlook, the icon looks like this:</span></span>

  ![Pictogram van invoegtoepassing voor berichten rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="3c6a0-142">Het pictogram in de webversie van Outlook ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram voor de melding van de invoegtoepassing in de webversie van Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="3c6a0-144">Zie [de invoegtoepassing bericht rapporteren gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)voor informatie over het gebruik van de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="3c6a0-145">De invoegtoepassing bericht rapporteren voor uw organisatie weergeven en inschakelen</span><span class="sxs-lookup"><span data-stu-id="3c6a0-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="3c6a0-146">Het kan 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="3c6a0-147">Ga in het Microsoft 365-Beheercentrum naar de pagina **instellingen, geïntegreerde Apps & invoegtoepassingen** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> en klik op **invoegtoepassing implementeren**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-147">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Pagina met Services en invoegtoepassingen in het Microsoft 365-Beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="3c6a0-149">Controleer de informatie in het vervolgmenu **een nieuwe invoegtoepassing implementeren** die wordt weergegeven en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="3c6a0-150">Op de volgende pagina klikt u op **kiezen uit de Store**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-150">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe pagina met invoegtoepassingen implementeren](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="3c6a0-152">Klik op de pagina **invoegtoepassing selecteren** die wordt weergegeven in het **zoekvak** , Voer **rapportbericht** in en klik vervolgens op **Zoek** ![ actie zoeken ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message** , and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="3c6a0-153">Zoek in de lijst met resultaten naar **rapport** en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Zoekresultaten van invoegtoepassing selecteren](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="3c6a0-155">In het dialoogvenster dat wordt weergegeven, bekijkt u de licentie-en privacygegevens en klikt u vervolgens op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="3c6a0-156">Configureer de volgende instellingen op de pagina **invoegtoepassing configureren** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3c6a0-157">**Toegewezen gebruikers** : Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-157">**Assigned users** : Select one of the following values:</span></span>

     - <span data-ttu-id="3c6a0-158">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="3c6a0-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="3c6a0-159">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="3c6a0-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="3c6a0-160">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="3c6a0-160">**Just me**</span></span>

   - <span data-ttu-id="3c6a0-161">**Implementatiemethode** : Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-161">**Deployment method** : Select one of the following values:</span></span>

     - <span data-ttu-id="3c6a0-162">**Fixed (standaardinstelling)** : de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan de invoegtoepassing niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-162">**Fixed (Default)** : The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="3c6a0-163">**Beschikbaar** : gebruikers kunnen de invoegtoepassing installeren bij de beheerder van de **Startpagina** \> **invoegtoepassingen** \> **beheren**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-163">**Available** : Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="3c6a0-164">**Optioneel** : de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen de optie wel verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-164">**Optional** : The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Pagina invoegtoepassing configureren](../../media/configure-add-in.png)

   <span data-ttu-id="3c6a0-166">Wanneer u klaar bent, klikt u op **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="3c6a0-167">Op de pagina **rapportbericht implementeren** dat wordt weergegeven, ziet u een voortgangsrapport gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="3c6a0-168">Nadat u de gegevens hebt gelezen, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-168">After you read the information, click **Next**.</span></span>

   ![Pagina rapportbericht implementeren](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="3c6a0-170">Controleer de gegevens op de pagina **aangekondigde invoegtoepassing** die wordt weergegeven en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina voor het aankondigen van invoegtoepassingen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="3c6a0-172">Meer informatie over het gebruik van de invoegtoepassing bericht melden</span><span class="sxs-lookup"><span data-stu-id="3c6a0-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="3c6a0-173">Voor personen aan wie de invoegtoepassing is toegewezen, worden de volgende pictogrammen weergegeven:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="3c6a0-174">Het pictogram in Outlook ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-174">In Outlook, the icon looks like this:</span></span>

  ![Pictogram van invoegtoepassing voor berichten rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="3c6a0-176">Het pictogram in de webversie van Outlook ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram voor de melding van de invoegtoepassing in de webversie van Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="3c6a0-178">Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing bericht rapporteren, kunt u een koppeling opnemen om [de invoegtoepassing bericht rapporteren te gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="3c6a0-179">Instellingen voor de invoegtoepassing bericht rapporteren controleren of bewerken</span><span class="sxs-lookup"><span data-stu-id="3c6a0-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="3c6a0-180">Ga in het Microsoft 365-Beheercentrum naar de pagina **Services & invoegtoepassingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Pagina Services en Add-Ins in het nieuwe Microsoft 365-Beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="3c6a0-182">Zoek en selecteer de invoegtoepassing **bericht rapporteren** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="3c6a0-183">Controleer en bewerk in het vervolgmenu met **berichten bewerken** dat wordt weergegeven, wat van toepassing is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="3c6a0-184">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-184">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoegtoepassing bericht melden](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="3c6a0-186">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="3c6a0-186">View and review reported messages</span></span>

<span data-ttu-id="3c6a0-187">Als u berichten wilt weergeven die gebruikers bij Microsoft rapporteren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="3c6a0-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="3c6a0-188">Gebruik de portal van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="3c6a0-189">Zie voor meer informatie [gebruikers items weergeven in Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="3c6a0-190">Maak een e-mail stroom regel (ook wel een transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="3c6a0-191">Zie voor instructies [de regels voor e-mail stroom gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
