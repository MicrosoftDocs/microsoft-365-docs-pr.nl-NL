---
title: Teamsites maken - Ontwikkel- en testomgeving voor politieke campagnes
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Overzicht: Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8a7002b7d482c987f77907787c5233dcb8d11e9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929382"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="0838c-103">Maak teamsites in een ontwikkel- en testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="0838c-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0838c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="0838c-104">**Applies to**</span></span>

- [<span data-ttu-id="0838c-105">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0838c-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- 
 <span data-ttu-id="0838c-106">**Overzicht:** Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne.</span><span class="sxs-lookup"><span data-stu-id="0838c-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
   
<span data-ttu-id="0838c-107">Gebruik de instructies in dit artikel om een ontwikkel-/testomgeving te maken met vier verschillende soorten SharePoint Online-teamsites voor de [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)-oplossing.</span><span class="sxs-lookup"><span data-stu-id="0838c-107">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="0838c-108">Deze sites worden uitgebreid beschreven in onderwerp 10, getiteld **SharePoint en OneDrive voor Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="0838c-108">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="0838c-109">Fase 1: Een ontwikkel- en testomgeving voor uw politieke campagnes maken</span><span class="sxs-lookup"><span data-stu-id="0838c-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="0838c-110">Volg eerst de instructies in [Groepen en gebruikers configureren voor een ontwikkel-/testomgeving voor uw politieke campagne](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) om uw abonnementen, gebruikers en groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="0838c-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="0838c-111">Fase 2: Labels maken</span><span class="sxs-lookup"><span data-stu-id="0838c-111">Phase 2: Create labels</span></span>

<span data-ttu-id="0838c-112">In deze fase maakt u de labels voor de verschillende beveiligingsniveaus van documentenmappen op de SharePoint Online-teamsite.</span><span class="sxs-lookup"><span data-stu-id="0838c-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="0838c-113">Indien nodig meldt u zich aan bij het beheercentrum met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0838c-113">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="0838c-114">Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="0838c-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="0838c-115">Klik op het tabblad **Microsoft Office Home** op de tegel **Beheerder**.</span><span class="sxs-lookup"><span data-stu-id="0838c-115">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>

3. <span data-ttu-id="0838c-116">Klik op het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Beheercentra > Beveiliging en compliance**.</span><span class="sxs-lookup"><span data-stu-id="0838c-116">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>

4. <span data-ttu-id="0838c-117">Klik op het nieuwe tabblad **Start - Beveiliging en compliance** van uw browser op **Classificaties > Labels**.</span><span class="sxs-lookup"><span data-stu-id="0838c-117">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>

5. <span data-ttu-id="0838c-118">Klik in het deelvenster **Start > Labels** op **Label maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-118">From the **Home > Labels** pane, click **Create a label**.</span></span>

6. <span data-ttu-id="0838c-119">Typ in het deelvenster **Uw label een naam geven** **Intern** in en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-119">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>

7. <span data-ttu-id="0838c-120">Klik in het deelvenster **Labelinstellingen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-120">On the **Label settings** pane, click **Next**.</span></span>

8. <span data-ttu-id="0838c-121">Klik in het deelvenster **Bekijk uw instellingen** op **Dit label maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-121">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

9. <span data-ttu-id="0838c-122">Herhaal de stappen 5-8 voor deze extra labels:</span><span class="sxs-lookup"><span data-stu-id="0838c-122">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="0838c-123">Privé</span><span class="sxs-lookup"><span data-stu-id="0838c-123">Private</span></span>
   - <span data-ttu-id="0838c-124">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="0838c-124">Sensitive</span></span>
   - <span data-ttu-id="0838c-125">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="0838c-125">Highly Confidential</span></span>

10. <span data-ttu-id="0838c-126">Klik in het deelvenster **Start > Labels** op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="0838c-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>

11. <span data-ttu-id="0838c-127">Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="0838c-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

12. <span data-ttu-id="0838c-128">Klik op het deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.</span><span class="sxs-lookup"><span data-stu-id="0838c-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

13. <span data-ttu-id="0838c-129">Klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0838c-129">Click **Done**.</span></span>

14. <span data-ttu-id="0838c-130">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-130">On the **Choose labels to publish** pane, click **Next**.</span></span>

15. <span data-ttu-id="0838c-131">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-131">On the **Choose locations** pane, click **Next**.</span></span>

16. <span data-ttu-id="0838c-132">Typ in het deelvenster **Uw beleid een naam geven** **Campagne** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-132">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

17. <span data-ttu-id="0838c-133">Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="0838c-134">Fase 3: Uw SharePoint Online-teamsites maken</span><span class="sxs-lookup"><span data-stu-id="0838c-134">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="0838c-135">In deze fase kunt u SharePoint Online-teamsites voor uw politieke campagne maken en configureren die overeenkomen met de vier typen SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="0838c-135">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="0838c-136">Teamsite voor de hele campagne</span><span class="sxs-lookup"><span data-stu-id="0838c-136">Campaign wide team site</span></span>

<span data-ttu-id="0838c-137">Als u een openbare SharePoint Online-teamsite wilt maken, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="0838c-137">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="0838c-138">Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-138">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="0838c-139">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0838c-139">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0838c-140">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-140">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="0838c-141">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="0838c-141">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="0838c-142">Typ bij **Sitenaam\*\*\*\*Gehele campagne** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-142">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="0838c-143">Typ bij **Beschrijving van de teamsite** in **SharePoint-site voor de gehele campagne**.</span><span class="sxs-lookup"><span data-stu-id="0838c-143">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="0838c-144">Selecteer bij **Privacy-instellingen** **Publiek: iedereen in de organisatie kan toegang krijgen tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-144">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="0838c-145">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="0838c-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="0838c-146">Configureer vervolgens de map met documenten van de teamsite voor de gehele campagne voor het interne label.</span><span class="sxs-lookup"><span data-stu-id="0838c-146">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="0838c-147">Klik in het **Gehele campagne-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-147">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="0838c-148">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-148">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="0838c-149">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="0838c-150">Selecteer bij **Instellingen-Label toepassen** de optie **Intern** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0838c-150">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="0838c-151">Teamsite project 1 campagne</span><span class="sxs-lookup"><span data-stu-id="0838c-151">Campaign project 1 team site</span></span>

<span data-ttu-id="0838c-152">Ga als volgt te werk om een privé SharePoint Online-teamsite voor een basislijn van een project in de campagne te maken:</span><span class="sxs-lookup"><span data-stu-id="0838c-152">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="0838c-153">Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-153">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="0838c-154">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0838c-154">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0838c-155">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-155">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="0838c-156">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="0838c-156">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="0838c-157">Typ bij **Sitenaam\*\*\*\*Campagneproject 1** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-157">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="0838c-158">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor Campagneproject 1** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-158">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="0838c-159">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-159">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="0838c-160">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="0838c-160">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="0838c-161">Configureer vervolgens de map met documenten van Campagneproject 1 voor het privélabel.</span><span class="sxs-lookup"><span data-stu-id="0838c-161">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="0838c-162">Klik in het **Campagneproject 1-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-162">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="0838c-163">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-163">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="0838c-164">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="0838c-165">Selecteer in **Instellingen-Label toepassen** de optie **Privé** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0838c-165">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="0838c-166">Teamsite voor marketing van de campagne</span><span class="sxs-lookup"><span data-stu-id="0838c-166">Campaign marketing team site</span></span>

<span data-ttu-id="0838c-167">Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite op gevoelig niveau wilt maken marketingresources van de campagne:</span><span class="sxs-lookup"><span data-stu-id="0838c-167">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="0838c-168">Gebruik een browser op je lokale computer om je aan te melden bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-168">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="0838c-169">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0838c-169">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0838c-170">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-170">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="0838c-171">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="0838c-171">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="0838c-172">Typ bij **Naam van de team site\*\*\*\*Marketing voor campagne** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-172">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="0838c-173">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor marketing van de campagne (gevoelig)** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-173">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="0838c-174">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-174">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="0838c-175">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="0838c-175">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="0838c-176">Klik in het nieuwe **Marketing voor campagne**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-176">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="0838c-177">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-177">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="0838c-178">Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-178">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="0838c-179">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit, typ **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** in bij **Alle toegangsaanvragen verzenden** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-179">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="0838c-180">Klik op **Leden marketing voor campagne** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0838c-180">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="0838c-181">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0838c-181">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="0838c-182">Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-182">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="0838c-183">Herhaal de stappen 14 en 15 voor de groep **Analytische medewerkers** en het **Regular1**-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-183">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="0838c-184">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="0838c-184">Click the back button on your browser.</span></span>

18. <span data-ttu-id="0838c-185">Klik op **Eigenaren marketing voor campagne** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0838c-185">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="0838c-186">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0838c-186">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="0838c-187">Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-187">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="0838c-188">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="0838c-188">Click the back button on your browser.</span></span>

22. <span data-ttu-id="0838c-189">Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Marketing voor campagne-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.</span><span class="sxs-lookup"><span data-stu-id="0838c-189">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="0838c-190">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="0838c-190">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="0838c-191">De SharePoint-groep **Marketing voor campagne-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1), de groep **Marketing voor campagne** (deze bevat het gebruikersaccount van de globale beheerder), de groep **Analytisch personeel** (deze bevat het DataScientist1-gebruikersaccount) en het **Regular1**-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-191">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="0838c-192">De SharePoint-groep **Marketing voor campagne-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).</span><span class="sxs-lookup"><span data-stu-id="0838c-192">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="0838c-193">De SharePoint-groep **Marketing voor campagne-Bezoekers** bevat geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0838c-193">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="0838c-194">Leden kunnen geen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Marketing voor campagne-Eigenaren**).</span><span class="sxs-lookup"><span data-stu-id="0838c-194">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="0838c-195">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende bronnen, maar kunnen wel toegang tot de site vragen, waardoor een e-mail wordt verzonden naar het postvak van het ITAdmin1-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-195">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="0838c-196">Configureer vervolgens de map met documenten van de teamsite van de marketing voor de campagne voor het interne label.</span><span class="sxs-lookup"><span data-stu-id="0838c-196">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="0838c-197">Klik in het **Marketing voor campagne-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-197">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="0838c-198">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-198">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="0838c-199">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="0838c-200">Selecteer bij **Instellingen-Label toepassen** de optie **Gevoelig** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0838c-200">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="0838c-201">Configureer vervolgens een beleid voor de preventie van gegevensverlies dat gebruikers een melding stuurt wanneer ze een document van de SharePoint Online-teamsite met het label Gevoelig buiten de organisatie delen.</span><span class="sxs-lookup"><span data-stu-id="0838c-201">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span></span> <span data-ttu-id="0838c-202">Dit DLP-beleid wordt toegepast op resources op de site van de marketing voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="0838c-202">This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="0838c-203">Klik op het tabblad **Microsoft Office Home** van uw browser op de tegel **Beveiliging en compliance**.</span><span class="sxs-lookup"><span data-stu-id="0838c-203">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="0838c-204">Klik op het nieuwe tabblad **Beveiliging en compliance** in uw browser op **Preventie van gegevensverlies > Beleid**.</span><span class="sxs-lookup"><span data-stu-id="0838c-204">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="0838c-205">Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-205">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="0838c-206">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-206">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="0838c-207">Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint Online-teamsites** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-207">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="0838c-208">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-208">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="0838c-209">Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-209">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="0838c-210">Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-210">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="0838c-211">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="0838c-211">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="0838c-212">Klik in het deelvenster **Labels** op **+Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0838c-212">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="0838c-213">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0838c-213">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="0838c-214">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-214">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="0838c-215">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-215">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="0838c-216">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-216">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="0838c-217">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="0838c-217">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="0838c-218">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="0838c-218">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="0838c-219">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="0838c-219">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="0838c-220">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="0838c-220">Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="0838c-221">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-221">Click **OK**.</span></span>

17. <span data-ttu-id="0838c-222">Schakel in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** het selectievakje **Delen door personen niet toestaan en toegang tot gedeelde inhoud beperken** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-222">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="0838c-223">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-223">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="0838c-224">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-224">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="0838c-225">Teamsite voor Campagnestrategie</span><span class="sxs-lookup"><span data-stu-id="0838c-225">Campaign strategy team site</span></span>

<span data-ttu-id="0838c-226">Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite wilt maken op het niveau van zeer vertrouwelijke informatie voor de resources van de campagnestrategie:</span><span class="sxs-lookup"><span data-stu-id="0838c-226">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="0838c-227">Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0838c-227">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="0838c-228">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0838c-228">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0838c-229">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-229">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="0838c-230">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="0838c-230">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="0838c-231">Typ bij **Naam van de teamsite\*\*\*\*Campagnestrategie** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-231">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="0838c-232">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor campagnestrategie (zeer vertrouwelijk)** in.</span><span class="sxs-lookup"><span data-stu-id="0838c-232">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="0838c-233">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-233">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="0838c-234">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="0838c-234">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="0838c-235">Klik in het nieuwe **Campagnestrategie**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-235">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="0838c-236">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-236">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="0838c-237">Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-237">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="0838c-238">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit (zodat alle drie de selectievakjes leeg zijn) en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-238">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="0838c-239">Klik op **Leden campagnestrategie** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0838c-239">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="0838c-240">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0838c-240">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="0838c-241">Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-241">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="0838c-242">Klik op **Eigenaren campagnestrategie** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0838c-242">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="0838c-243">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0838c-243">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="0838c-244">Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-244">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="0838c-245">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="0838c-245">Click the back button on your browser.</span></span>

20. <span data-ttu-id="0838c-246">Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Campagnestrategie-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.</span><span class="sxs-lookup"><span data-stu-id="0838c-246">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="0838c-247">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="0838c-247">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="0838c-248">De SharePoint-groep **Campagnestrategie-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1) en de groep **Campagnestrategie** (deze bevat het alleen gebruikersaccount van de globale beheerder).</span><span class="sxs-lookup"><span data-stu-id="0838c-248">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="0838c-249">De SharePoint-groep **Campagnestrategie-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).</span><span class="sxs-lookup"><span data-stu-id="0838c-249">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="0838c-250">De SharePoint-groep **Campagnestrategie-Bezoekers** bevat geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0838c-250">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="0838c-251">Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Campagnestrategie-Eigenaren**).</span><span class="sxs-lookup"><span data-stu-id="0838c-251">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="0838c-252">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="0838c-252">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="0838c-253">Aanvullende machtigingen voor de site moeten worden uitgevoerd door de globale beheerder of door een lid van de groep **Campagnestrategie-Eigenaren**.</span><span class="sxs-lookup"><span data-stu-id="0838c-253">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="0838c-254">Configureer vervolgens de documentenmap van de Campagnestrategie-teamsite voor het label Zeer vertrouwelijk.</span><span class="sxs-lookup"><span data-stu-id="0838c-254">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="0838c-255">Klik in het tabblad **Campagnestrategie-Start** in uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-255">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="0838c-256">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-256">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="0838c-257">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-257">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="0838c-258">Selecteer in **Instellingen-Label toepassen** de optie **Zeer vertrouwelijk** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0838c-258">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="0838c-259">Configureer vervolgens een beleid voor de preventie van gegevensverlies dat gebruikers blokkeert wanneer ze een document van de SharePoint Online-teamsite met het label Zeer vertrouwelijk buiten de organisatie delen.</span><span class="sxs-lookup"><span data-stu-id="0838c-259">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span></span> <span data-ttu-id="0838c-260">Dit beleid wordt toegepast op resources op de site van de Campagnestrategie.</span><span class="sxs-lookup"><span data-stu-id="0838c-260">This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="0838c-261">Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum (<https://admin.microsoft.com>) met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="0838c-261">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="0838c-262">Klik op het tabblad **Microsoft Office Home** van uw browser op de tegel **Beveiliging en compliance**.</span><span class="sxs-lookup"><span data-stu-id="0838c-262">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="0838c-263">Klik op het nieuwe tabblad **Beveiliging en compliance** in uw browser op **Preventie van gegevensverlies > Beleid**.</span><span class="sxs-lookup"><span data-stu-id="0838c-263">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="0838c-264">Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-264">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="0838c-265">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-265">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="0838c-266">Typ in het deelvenster **Uw beleid een naam geven** **Label Zeer vertrouwelijk voor SharePoint-sites** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-266">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="0838c-267">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-267">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="0838c-268">Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-268">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="0838c-269">Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-269">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="0838c-270">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="0838c-270">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="0838c-271">Klik in het deelvenster **Labels** op **+ Toevoegen**, selecteer het label **Zeer Vertrouwelijk**, klik op **Toevoegen** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0838c-271">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="0838c-272">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0838c-272">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="0838c-273">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-273">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="0838c-274">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-274">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="0838c-275">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-275">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="0838c-276">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="0838c-276">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="0838c-277">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="0838c-277">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="0838c-278">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="0838c-278">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="0838c-279">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="0838c-279">Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="0838c-280">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-280">Click **OK**.</span></span>

18. <span data-ttu-id="0838c-281">In het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?**, selecteert u **Een zakelijke reden vereisen om te overschrijven** en klikt u vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-281">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="0838c-282">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0838c-282">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="0838c-283">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0838c-283">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="0838c-284">Gebruik de instructies in [Azure RMS activeren met het Microsoft 365-beheercentrum](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="0838c-284">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="0838c-285">Configureer vervolgens Azure Information Protection met een nieuw beleid en een sublabel voor bescherming en machtigingen met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="0838c-285">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="0838c-286">Meld u aan met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="0838c-286">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="0838c-287">Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="0838c-287">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="0838c-288">Open een afzonderlijk tabblad in je browser en ga naar de Microsoft Azure-portal (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="0838c-288">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="0838c-289">Typ in het deelvenster **informatie** en klik vervolgens op **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="0838c-289">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="0838c-290">Klik op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="0838c-290">Click **Labels**.</span></span>

5. <span data-ttu-id="0838c-291">Klik met de rechtermuisknop op het **Zeer vertrouwelijk**-label en klik vervolgens op **Voeg een sublabel toe**.</span><span class="sxs-lookup"><span data-stu-id="0838c-291">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="0838c-292">Typ **CampagneStrategie** in bij **Naam** en **Label voor documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="0838c-292">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="0838c-293">Klik bij **Machtigingen instellen voor documenten en e-mail met dit label** op **Beveiligen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-293">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="0838c-294">Klik in de sectie **Bescherming** op **Azure (cloud key)**.</span><span class="sxs-lookup"><span data-stu-id="0838c-294">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="0838c-295">Klik in het **Bescherming**-tabblad onder **Beschermingsinstellingen** op **+ Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-295">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="0838c-296">Klik in het **Machtigingen toevoegen**-tabblad onder **Gebruikers en groepen specificeren** op **+ Adreslijst zoeken**.</span><span class="sxs-lookup"><span data-stu-id="0838c-296">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="0838c-297">Selecteer in het deelvenster **AAD-gebruikers en -groepen** **Senior en strategisch personeel** en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="0838c-297">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="0838c-298">Klik onder **Kies vooraf ingestelde of aangepaste machtigingen** op **Aangepast** en klik vervolgens op de selectievakjes **Weergaverechten**, **Inhoud bewerken**, **Opslaan**, **Beantwoorden** en **Allen beantwoorden**.</span><span class="sxs-lookup"><span data-stu-id="0838c-298">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="0838c-299">Klik tweemaal op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-299">Click **OK** twice.</span></span>

14. <span data-ttu-id="0838c-300">Klik in het **Sublabel**-tabblad op **Opslaan** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-300">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="0838c-301">Klik in het **Azure Information Protection**-tabblad op **Beleid > + Een nieuw beleid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-301">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="0838c-302">Typ **CampagneStrategie** in bij **Naam** en **Documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="0838c-302">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="0838c-303">Klik op **Selecteer de gebruikers of groepen aan wie u dit beleid wilt toewijzen > Gebruikers/groepen** en selecteer vervolgens **Senior en strategisch personeel**.</span><span class="sxs-lookup"><span data-stu-id="0838c-303">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="0838c-304">Klik vervolgens op **Selecteren \> OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-304">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="0838c-305">Klik op **Labels toevoegen of verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0838c-305">Click **Add or remove labels**.</span></span> <span data-ttu-id="0838c-306">Klik in het deelvenster **Beleid: Labels toevoegen of verwijderen** op **CampagneStrategie** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-306">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="0838c-307">Klik op **Opslaan** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="0838c-307">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="0838c-308">U bent nu klaar om te beginnen met het maken van documenten op deze vier sites en het testen van de toegang hiertoe met verschillende gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0838c-308">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="0838c-309">Als u een document met Azure Information Protection en dit nieuwe label wilt beveiligen, moet u [de Azure Information Protection-client installeren](/information-protection/rms-client/install-client-app) op een testcomputer, Office installeren vanuit het beheercentrum en u vervolgens aanmelden bij Microsoft Word met een account uit de groep **Senior en strategisch personeel** van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0838c-309">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="0838c-310">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0838c-310">See Also</span></span>

[<span data-ttu-id="0838c-311">Beveiligingsrichtlijnen van Microsoft voor politieke campagnes, non-profitorganisaties en andere agile organisaties</span><span class="sxs-lookup"><span data-stu-id="0838c-311">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="0838c-312">Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="0838c-312">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="0838c-313">Cloud adoption Test Lab Guides (TLGs)</span><span class="sxs-lookup"><span data-stu-id="0838c-313">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="0838c-314">Microsoft 365-oplossings- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="0838c-314">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)