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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Overzicht: Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne.'
ms.openlocfilehash: d22ada823877d4c0996be942c379e12929242eaf
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755234"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="dea30-103">Maak teamsites in een ontwikkel- en testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="dea30-103">Create team sites in a political campaign dev/test environment</span></span>

 <span data-ttu-id="dea30-104">**Overzicht:** Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne.</span><span class="sxs-lookup"><span data-stu-id="dea30-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="dea30-105">Gebruik de instructies in dit artikel om een ontwikkel-/testomgeving te maken met vier verschillende soorten SharePoint Online-teamsites voor de [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)-oplossing.</span><span class="sxs-lookup"><span data-stu-id="dea30-105">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="dea30-106">Deze sites worden uitgebreid beschreven in onderwerp 10, getiteld **SharePoint en OneDrive voor Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="dea30-106">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="dea30-107">Fase 1: Een ontwikkel- en testomgeving voor uw politieke campagnes maken</span><span class="sxs-lookup"><span data-stu-id="dea30-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="dea30-108">Volg eerst de instructies in [Groepen en gebruikers configureren voor een ontwikkel-/testomgeving voor uw politieke campagne](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) om uw abonnementen, gebruikers en groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="dea30-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-labels"></a><span data-ttu-id="dea30-109">Fase 2: Labels maken</span><span class="sxs-lookup"><span data-stu-id="dea30-109">Phase 2: Create labels</span></span>

<span data-ttu-id="dea30-110">In deze fase maakt u de labels voor de verschillende beveiligingsniveaus van documentenmappen op de SharePoint Online-teamsite.</span><span class="sxs-lookup"><span data-stu-id="dea30-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="dea30-111">Indien nodig meldt u zich aan bij het beheercentrum met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dea30-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="dea30-112">Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="dea30-112">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="dea30-113">Klik in het tabblad **Microsoft Office voor Thuisgebruik** op de tegel **Beheerder**.</span><span class="sxs-lookup"><span data-stu-id="dea30-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="dea30-114">Klik in het nieuwe **Microsoft 365-beheercentrum**-tabblad van uw browser op **Beheercentra > Beveiliging &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="dea30-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="dea30-115">Klik in het nieuwe **Start - Beveiliging &amp; Compliance**-tabblad van uw browser op **Classificaties > Labels**.</span><span class="sxs-lookup"><span data-stu-id="dea30-115">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="dea30-116">Klik in het deelvenster **Start > Labels** op **Label maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="dea30-117">Typ in het deelvenster **Uw label een naam geven** **Intern** in en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="dea30-118">Klik in het deelvenster **Labelinstellingen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-119">Klik in het deelvenster **Bekijk uw instellingen** op **Dit label maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="dea30-120">Herhaal de stappen 5-8 voor deze extra labels:</span><span class="sxs-lookup"><span data-stu-id="dea30-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="dea30-121">Privé</span><span class="sxs-lookup"><span data-stu-id="dea30-121">Private</span></span>
    
  - <span data-ttu-id="dea30-122">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="dea30-122">Sensitive</span></span>
    
  - <span data-ttu-id="dea30-123">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="dea30-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="dea30-124">Klik in het deelvenster **Start > Labels** op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="dea30-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="dea30-125">Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="dea30-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="dea30-126">Klik op het deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.</span><span class="sxs-lookup"><span data-stu-id="dea30-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="dea30-127">Klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="dea30-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="dea30-128">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="dea30-129">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="dea30-130">Typ in het deelvenster **Uw beleid een naam geven** **Campagne** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="dea30-131">Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="dea30-132">Fase 3: Uw SharePoint Online-teamsites maken</span><span class="sxs-lookup"><span data-stu-id="dea30-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="dea30-133">In deze fase kunt u SharePoint Online-teamsites voor uw politieke campagne maken en configureren die overeenkomen met de vier typen SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="dea30-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="dea30-134">Teamsite voor de hele campagne</span><span class="sxs-lookup"><span data-stu-id="dea30-134">Campaign wide team site</span></span>

<span data-ttu-id="dea30-135">Als u een openbare SharePoint Online-teamsite wilt maken, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="dea30-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="dea30-136">Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="dea30-137">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="dea30-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="dea30-138">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="dea30-139">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="dea30-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="dea30-140">Typ bij **Sitenaam\*\*\*\*Gehele campagne** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="dea30-141">Typ bij **Beschrijving van de teamsite**in **SharePoint-site voor de gehele campagne**.</span><span class="sxs-lookup"><span data-stu-id="dea30-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="dea30-142">Selecteer bij **Privacy-instellingen** **Publiek: iedereen in de organisatie kan toegang krijgen tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-143">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="dea30-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="dea30-144">Configureer vervolgens de map met documenten van de teamsite voor de gehele campagne voor het interne label.</span><span class="sxs-lookup"><span data-stu-id="dea30-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="dea30-145">Klik in het **Gehele campagne-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="dea30-146">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="dea30-147">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="dea30-148">Selecteer bij **Instellingen-Label toepassen** de optie **Intern** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dea30-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="dea30-149">Teamsite project 1 campagne</span><span class="sxs-lookup"><span data-stu-id="dea30-149">Campaign project 1 team site</span></span>

<span data-ttu-id="dea30-150">Ga als volgt te werk om een privé SharePoint Online-teamsite voor een basislijn van een project in de campagne te maken:</span><span class="sxs-lookup"><span data-stu-id="dea30-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="dea30-151">Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="dea30-152">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="dea30-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="dea30-153">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="dea30-154">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="dea30-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="dea30-155">Typ bij **Sitenaam\*\*\*\*Campagneproject 1** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="dea30-156">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor Campagneproject 1** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="dea30-157">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-158">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="dea30-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="dea30-159">Configureer vervolgens de map met documenten van Campagneproject 1 voor het privélabel.</span><span class="sxs-lookup"><span data-stu-id="dea30-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="dea30-160">Klik in het **Campagneproject 1-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="dea30-161">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="dea30-162">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="dea30-163">Selecteer in **Instellingen-Label toepassen** de optie **Privé**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dea30-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="dea30-164">Teamsite voor marketing van de campagne</span><span class="sxs-lookup"><span data-stu-id="dea30-164">Campaign marketing team site</span></span>

<span data-ttu-id="dea30-165">Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite op gevoelig niveau wilt maken marketingresources van de campagne:</span><span class="sxs-lookup"><span data-stu-id="dea30-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="dea30-166">Gebruik een browser op uw lokale computer om u aan te melden bij het beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="dea30-167">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="dea30-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="dea30-168">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="dea30-169">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="dea30-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="dea30-170">Typ bij **Naam van de team site\*\*\*\*Marketing voor campagne** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="dea30-171">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor marketing van de campagne (gevoelig)** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="dea30-172">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-173">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="dea30-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="dea30-174">Klik in het nieuwe **Marketing voor campagne**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="dea30-175">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="dea30-176">Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="dea30-177">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**-en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit, typ **ITAdmin1@**<your organization name> **.onmicrosoft.com** in bij **Alle toegangsaanvragen verzenden** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="dea30-178">Klik op **Leden marketing voor campagne** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="dea30-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="dea30-179">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="dea30-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="dea30-180">Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="dea30-181">Herhaal de stappen 14 en 15 voor de groep **Analytische medewerkers** en het **Regular1**-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="dea30-182">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="dea30-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="dea30-183">Klik op **Eigenaren marketing voor campagne** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="dea30-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="dea30-184">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="dea30-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="dea30-185">Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="dea30-186">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="dea30-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="dea30-187">Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Marketing voor campagne-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.</span><span class="sxs-lookup"><span data-stu-id="dea30-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="dea30-188">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="dea30-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="dea30-189">De SharePoint-groep **Marketing voor campagne-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1), de groep **Marketing voor campagne** (deze bevat het gebruikersaccount van de globale beheerder), de groep **Analytisch personeel** (deze bevat het DataScientist1-gebruikersaccount) en het **Regular1**-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="dea30-190">De SharePoint-groep **Marketing voor campagne-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).</span><span class="sxs-lookup"><span data-stu-id="dea30-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="dea30-191">De SharePoint-groep **Marketing voor campagne-Bezoekers** bevat geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="dea30-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="dea30-192">Leden kunnen geen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Marketing voor campagne-Eigenaren**).</span><span class="sxs-lookup"><span data-stu-id="dea30-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="dea30-193">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende bronnen, maar kunnen wel toegang tot de site vragen, waardoor een e-mail wordt verzonden naar het postvak van het ITAdmin1-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="dea30-194">Configureer vervolgens de map met documenten van de teamsite van de marketing voor de campagne voor het interne label.</span><span class="sxs-lookup"><span data-stu-id="dea30-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="dea30-195">Klik in het **Marketing voor campagne-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="dea30-196">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="dea30-197">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="dea30-198">Selecteer bij **Instellingen-Label toepassen** de optie **Gevoelig** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dea30-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="dea30-199">Configureer vervolgens een beleid voor de preventie van gegevensverlies dat gebruikers een melding stuurt wanneer ze een document van de SharePoint Online-teamsite met het label Gevoelig buiten de organisatie delen.</span><span class="sxs-lookup"><span data-stu-id="dea30-199">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span></span> <span data-ttu-id="dea30-200">Dit beleid wordt toegepast op resources op de site van de marketing voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="dea30-200">This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="dea30-201">Klik in het **Microsoft Office voor Thuisgebruik**-tabblad van uw browser op de tegel **Beveiliging &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="dea30-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="dea30-202">Klik in het nieuwe **Security &amp; Compliance**-tabblad in uw browser op **Preventie van gegevensverlies > Beleid**.</span><span class="sxs-lookup"><span data-stu-id="dea30-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="dea30-203">Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="dea30-204">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="dea30-205">Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint Online-teamsites** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="dea30-206">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="dea30-207">Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-208">Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="dea30-209">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="dea30-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="dea30-210">Klik in het deelvenster **Labels** op **+Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="dea30-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="dea30-211">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dea30-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="dea30-212">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="dea30-213">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="dea30-214">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="dea30-215">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="dea30-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="dea30-216">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="dea30-216">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="dea30-217">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="dea30-217">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="dea30-218">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="dea30-218">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="dea30-219">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="dea30-220">Schakel in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** het selectievakje **Delen door personen niet toestaan en toegang tot gedeelde inhoud beperken** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="dea30-221">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="dea30-222">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="dea30-223">Teamsite voor Campagnestrategie</span><span class="sxs-lookup"><span data-stu-id="dea30-223">Campaign strategy team site</span></span>

<span data-ttu-id="dea30-224">Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite wilt maken op het niveau van zeer vertrouwelijke informatie voor de resources van de campagnestrategie:</span><span class="sxs-lookup"><span data-stu-id="dea30-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="dea30-225">Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="dea30-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="dea30-226">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="dea30-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="dea30-227">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="dea30-228">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="dea30-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="dea30-229">Typ bij **Naam van de teamsite\*\*\*\*Campagnestrategie** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="dea30-230">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor campagnestrategie (zeer vertrouwelijk)** in.</span><span class="sxs-lookup"><span data-stu-id="dea30-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="dea30-231">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-232">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="dea30-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="dea30-233">Klik in het nieuwe **Campagnestrategie**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="dea30-234">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="dea30-235">Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="dea30-236">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit (zodat alle drie de selectievakjes leeg zijn) en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="dea30-237">Klik op **Leden campagnestrategie** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="dea30-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="dea30-238">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="dea30-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="dea30-239">Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="dea30-240">Klik op **Eigenaren campagnestrategie** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="dea30-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="dea30-241">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="dea30-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="dea30-242">Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="dea30-243">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="dea30-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="dea30-244">Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Campagnestrategie-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.</span><span class="sxs-lookup"><span data-stu-id="dea30-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="dea30-245">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="dea30-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="dea30-246">De SharePoint-groep **Campagnestrategie-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1) en de groep **Campagnestrategie** (deze bevat het alleen gebruikersaccount van de globale beheerder).</span><span class="sxs-lookup"><span data-stu-id="dea30-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="dea30-247">De SharePoint-groep **Campagnestrategie-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).</span><span class="sxs-lookup"><span data-stu-id="dea30-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="dea30-248">De SharePoint-groep **Campagnestrategie-Bezoekers** bevat geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="dea30-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="dea30-249">Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Campagnestrategie-Eigenaren**).</span><span class="sxs-lookup"><span data-stu-id="dea30-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="dea30-250">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="dea30-250">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="dea30-251">Aanvullende machtigingen voor de site moeten worden uitgevoerd door de globale beheerder of door een lid van de groep **Campagnestrategie-Eigenaren**.</span><span class="sxs-lookup"><span data-stu-id="dea30-251">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="dea30-252">Configureer vervolgens de documentenmap van de Campagnestrategie-teamsite voor het label Zeer vertrouwelijk.</span><span class="sxs-lookup"><span data-stu-id="dea30-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="dea30-253">Klik in het tabblad **Campagnestrategie-Start** in uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="dea30-254">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="dea30-255">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="dea30-256">Selecteer in **Instellingen-Label toepassen** de optie **Zeer vertrouwelijk** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dea30-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="dea30-257">Configureer vervolgens een beleid voor de preventie van gegevensverlies dat gebruikers blokkeert wanneer ze een document van de SharePoint Online-teamsite met het label Zeer vertrouwelijk buiten de organisatie delen.</span><span class="sxs-lookup"><span data-stu-id="dea30-257">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span></span> <span data-ttu-id="dea30-258">Dit beleid wordt toegepast op resources op de site van de Campagnestrategie.</span><span class="sxs-lookup"><span data-stu-id="dea30-258">This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="dea30-259">Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="dea30-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="dea30-260">Klik in het **Microsoft Office voor Thuisgebruik**-tabblad van uw browser op de tegel **Beveiliging &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="dea30-260">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="dea30-261">Klik in het nieuwe **Security &amp; Compliance**-tabblad in uw browser op **Preventie van gegevensverlies > Beleid**.</span><span class="sxs-lookup"><span data-stu-id="dea30-261">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="dea30-262">Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="dea30-263">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="dea30-264">Typ in het deelvenster **Uw beleid een naam geven** **Label Zeer vertrouwelijk voor SharePoint-sites** in bij **Naam**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="dea30-265">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dea30-266">Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="dea30-267">Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="dea30-268">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="dea30-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="dea30-269">Klik in het deelvenster **Labels** op **+ Toevoegen**, selecteer het label **Zeer Vertrouwelijk**, klik op **Toevoegen** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="dea30-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="dea30-270">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dea30-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="dea30-271">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="dea30-272">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="dea30-273">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="dea30-274">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="dea30-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="dea30-275">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="dea30-275">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="dea30-276">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="dea30-276">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="dea30-277">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="dea30-277">Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="dea30-278">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="dea30-279">In het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?**, selecteert u **Een zakelijke reden vereisen om te overschrijven** en klikt u vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="dea30-280">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dea30-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="dea30-281">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="dea30-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="dea30-282">Gebruik de instructies in [Azure RMS activeren met het Microsoft 365-beheercentrum](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="dea30-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="dea30-283">Configureer vervolgens Azure Information Protection met een nieuw beleid en een sublabel voor bescherming en machtigingen met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="dea30-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="dea30-284">Meld u aan met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="dea30-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="dea30-285">Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="dea30-285">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="dea30-286">Open een afzonderlijk tabblad in uw browser en ga naar de Microsoft Azure-portal ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="dea30-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="dea30-287">Typ in het deelvenster **informatie**en klik vervolgens op **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="dea30-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="dea30-288">Klik op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="dea30-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="dea30-289">Klik met de rechtermuisknop op het **Zeer vertrouwelijk**-label en klik vervolgens op **Voeg een sublabel toe**.</span><span class="sxs-lookup"><span data-stu-id="dea30-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="dea30-290">Typ **CampagneStrategie** in bij **Naam** en **Label voor documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="dea30-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="dea30-291">Klik bij **Machtigingen instellen voor documenten en e-mail met dit label** op **Beveiligen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="dea30-292">Klik in de sectie **Bescherming** op **Azure (cloud key)**.</span><span class="sxs-lookup"><span data-stu-id="dea30-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="dea30-293">Klik in het **Bescherming**-tabblad onder **Beschermingsinstellingen** op **+ Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="dea30-294">Klik in het **Machtigingen toevoegen**-tabblad onder **Gebruikers en groepen specificeren** op **+ Adreslijst zoeken**.</span><span class="sxs-lookup"><span data-stu-id="dea30-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="dea30-295">Selecteer in het deelvenster **AAD-gebruikers en -groepen** **Senior en strategisch personeel** en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="dea30-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="dea30-296">Klik onder **Kies vooraf ingestelde of aangepaste machtigingen** op **Aangepast** en klik vervolgens op de selectievakjes **Weergaverechten**, **Inhoud bewerken**, **Opslaan**, **Beantwoorden** en **Allen beantwoorden**.</span><span class="sxs-lookup"><span data-stu-id="dea30-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="dea30-297">Klik tweemaal op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="dea30-298">Klik in het **Sublabel**-tabblad op **Opslaan**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="dea30-299">Klik in het **Azure Information Protection**-tabblad op **Beleid > + Een nieuw beleid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="dea30-300">Typ **CampagneStrategie** in bij **Naam** en **Documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="dea30-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="dea30-301">Klik op **Selecteer de gebruikers of groepen aan wie u dit beleid wilt toewijzen > Gebruikers/groepen** en selecteer vervolgens **Senior en strategisch personeel**.</span><span class="sxs-lookup"><span data-stu-id="dea30-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="dea30-302">Klik vervolgens op **Selecteren > OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="dea30-303">Klik op **Labels toevoegen of verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="dea30-303">Click **Add or remove labels**.</span></span> <span data-ttu-id="dea30-304">Klik in het deelvenster **Beleid: Labels toevoegen of verwijderen** op **CampagneStrategie**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-304">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="dea30-305">Klik op **Opslaan** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="dea30-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="dea30-306">U bent nu klaar om te beginnen met het maken van documenten op deze vier sites en het testen van de toegang hiertoe met verschillende gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="dea30-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="dea30-307">Als u een document met Azure Information Protection en dit nieuwe label wilt beveiligen, moet u [de Azure Information Protection-client installeren](https://docs.microsoft.com/information-protection/rms-client/install-client-app) op een testcomputer, Office installeren vanuit het beheercentrum en u vervolgens aanmelden bij Microsoft Word met een account uit de groep **Senior en strategisch personeel** van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dea30-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dea30-308">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dea30-308">See Also</span></span>

[<span data-ttu-id="dea30-309">Beveiligingsrichtlijnen van Microsoft voor politieke campagnes, non-profitorganisaties en andere agile organisaties</span><span class="sxs-lookup"><span data-stu-id="dea30-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="dea30-310">Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="dea30-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="dea30-311">Cloud adoption Test Lab Guides (TLGs)</span><span class="sxs-lookup"><span data-stu-id="dea30-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="dea30-312">Cloud adoption and hybrid solutions</span><span class="sxs-lookup"><span data-stu-id="dea30-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




