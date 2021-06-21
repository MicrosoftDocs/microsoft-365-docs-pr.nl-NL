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
ms.openlocfilehash: fcba6e2f3939115d6dfbaae80d322246bdeadee9
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029895"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="07e13-103">Maak teamsites in een ontwikkel- en testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="07e13-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="07e13-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="07e13-104">**Applies to**</span></span>

- [<span data-ttu-id="07e13-105">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="07e13-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="07e13-106">**Overzicht:** Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne.</span><span class="sxs-lookup"><span data-stu-id="07e13-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="07e13-107">Gebruik de instructies in dit artikel om een ontwikkel-/testomgeving te maken met vier verschillende soorten SharePoint Online-teamsites voor de [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)-oplossing.</span><span class="sxs-lookup"><span data-stu-id="07e13-107">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="07e13-108">Deze sites worden uitgebreid beschreven in onderwerp 10, getiteld **SharePoint en OneDrive voor Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="07e13-108">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="07e13-109">Fase 1: Een ontwikkel- en testomgeving voor uw politieke campagnes maken</span><span class="sxs-lookup"><span data-stu-id="07e13-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="07e13-110">Volg eerst de instructies in [Groepen en gebruikers configureren voor een ontwikkel-/testomgeving voor uw politieke campagne](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) om uw abonnementen, gebruikers en groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="07e13-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="07e13-111">Fase 2: Labels maken</span><span class="sxs-lookup"><span data-stu-id="07e13-111">Phase 2: Create labels</span></span>

<span data-ttu-id="07e13-112">In deze fase maakt u de labels voor de verschillende beveiligingsniveaus van documentenmappen op de SharePoint Online-teamsite.</span><span class="sxs-lookup"><span data-stu-id="07e13-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="07e13-113">Indien nodig meldt u zich aan bij het Microsoft 365-beheercentrum (<https://admin.microsoft.com>) met de referenties van het globale beheerdersaccount van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="07e13-113">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="07e13-114">Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="07e13-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="07e13-115">Klik op de **startpagina** waar u begint op **Alle weergeven**.</span><span class="sxs-lookup"><span data-stu-id="07e13-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="07e13-116">Klik in de sectie **Beheercentra** die wordt weergegeven op **Naleving**.</span><span class="sxs-lookup"><span data-stu-id="07e13-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="07e13-117">Ga op de **startpagina** van het Microsoft 365-compliancecentrum naar de sectie **Oplossingen** \> **Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="07e13-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="07e13-118">Via <https://compliance.microsoft.com//informationprotection> gaat u rechtstreeks naar de pagina **Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="07e13-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="07e13-119">Controleer op de pagina **Information Protection** of de tag **Label** is geselecteerd en klik vervolgens op ![Een labelpictogram maken](../../media/m365-cc-sc-create-icon.png) **Een label maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="07e13-120">De wizard **Nieuw vertrouwelijkheidslabel** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="07e13-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="07e13-121">Voer in de stap **Naam en beschrijving** de volgende waarden in:</span><span class="sxs-lookup"><span data-stu-id="07e13-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="07e13-122">**Naam**: type **Intern**.</span><span class="sxs-lookup"><span data-stu-id="07e13-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="07e13-123">**Weergavenaam**</span><span class="sxs-lookup"><span data-stu-id="07e13-123">**Display name**</span></span>
   - <span data-ttu-id="07e13-124">**Beschrijving voor gebruikers**</span><span class="sxs-lookup"><span data-stu-id="07e13-124">**Description for users**</span></span>

   <span data-ttu-id="07e13-125">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="07e13-126">Klik in het deelvenster **Labelinstellingen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="07e13-127">Klik in het deelvenster **Bekijk uw instellingen** op **Dit label maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="07e13-128">Herhaal de stappen 5-8 voor deze extra labels:</span><span class="sxs-lookup"><span data-stu-id="07e13-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="07e13-129">Privé</span><span class="sxs-lookup"><span data-stu-id="07e13-129">Private</span></span>
   - <span data-ttu-id="07e13-130">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="07e13-130">Sensitive</span></span>
   - <span data-ttu-id="07e13-131">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="07e13-131">Highly Confidential</span></span>

9. <span data-ttu-id="07e13-132">Klik in het deelvenster **Start > Labels** op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="07e13-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="07e13-133">Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="07e13-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="07e13-134">Klik op het deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.</span><span class="sxs-lookup"><span data-stu-id="07e13-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="07e13-135">Klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="07e13-135">Click **Done**.</span></span>

13. <span data-ttu-id="07e13-136">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="07e13-137">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="07e13-138">Typ in het deelvenster **Uw beleid een naam geven** **Campagne** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="07e13-139">Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="07e13-140">Fase 3: Uw SharePoint Online-teamsites maken</span><span class="sxs-lookup"><span data-stu-id="07e13-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="07e13-141">In deze fase kunt u SharePoint Online-teamsites voor uw politieke campagne maken en configureren die overeenkomen met de vier typen SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="07e13-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="07e13-142">Teamsite voor de hele campagne</span><span class="sxs-lookup"><span data-stu-id="07e13-142">Campaign wide team site</span></span>

<span data-ttu-id="07e13-143">Als u een openbare SharePoint Online-teamsite wilt maken, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="07e13-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="07e13-144">Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="07e13-145">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="07e13-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="07e13-146">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="07e13-147">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="07e13-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="07e13-148">Typ bij **Sitenaam\*\*\*\*Gehele campagne** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="07e13-149">Typ bij **Beschrijving van de teamsite** in **SharePoint-site voor de gehele campagne**.</span><span class="sxs-lookup"><span data-stu-id="07e13-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="07e13-150">Selecteer bij **Privacy-instellingen** **Publiek: iedereen in de organisatie kan toegang krijgen tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="07e13-151">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="07e13-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="07e13-152">Configureer vervolgens de map met documenten van de teamsite voor de gehele campagne voor het interne label.</span><span class="sxs-lookup"><span data-stu-id="07e13-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="07e13-153">Klik in het **Gehele campagne-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="07e13-154">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="07e13-155">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="07e13-156">Selecteer bij **Instellingen-Label toepassen** de optie **Intern** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="07e13-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="07e13-157">Teamsite project 1 campagne</span><span class="sxs-lookup"><span data-stu-id="07e13-157">Campaign project 1 team site</span></span>

<span data-ttu-id="07e13-158">Ga als volgt te werk om een privé SharePoint Online-teamsite voor een basislijn van een project in de campagne te maken:</span><span class="sxs-lookup"><span data-stu-id="07e13-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="07e13-159">Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="07e13-160">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="07e13-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="07e13-161">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="07e13-162">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="07e13-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="07e13-163">Typ bij **Sitenaam\*\*\*\*Campagneproject 1** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="07e13-164">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor Campagneproject 1** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="07e13-165">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="07e13-166">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="07e13-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="07e13-167">Configureer vervolgens de map met documenten van Campagneproject 1 voor het privélabel.</span><span class="sxs-lookup"><span data-stu-id="07e13-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="07e13-168">Klik in het **Campagneproject 1-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="07e13-169">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="07e13-170">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="07e13-171">Selecteer in **Instellingen-Label toepassen** de optie **Privé** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="07e13-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="07e13-172">Teamsite voor marketing van de campagne</span><span class="sxs-lookup"><span data-stu-id="07e13-172">Campaign marketing team site</span></span>

<span data-ttu-id="07e13-173">Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite op gevoelig niveau wilt maken marketingresources van de campagne:</span><span class="sxs-lookup"><span data-stu-id="07e13-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="07e13-174">Gebruik een browser op je lokale computer om je aan te melden bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="07e13-175">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="07e13-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="07e13-176">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="07e13-177">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="07e13-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="07e13-178">Typ bij **Naam van de team site\*\*\*\*Marketing voor campagne** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="07e13-179">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor marketing van de campagne (gevoelig)** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="07e13-180">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="07e13-181">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="07e13-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="07e13-182">Klik in het nieuwe **Marketing voor campagne**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="07e13-183">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="07e13-184">Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="07e13-185">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit, typ **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** in bij **Alle toegangsaanvragen verzenden** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="07e13-186">Klik op **Leden marketing voor campagne** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="07e13-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="07e13-187">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="07e13-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="07e13-188">Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="07e13-189">Herhaal de stappen 14 en 15 voor de groep **Analytische medewerkers** en het **Regular1**-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="07e13-190">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="07e13-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="07e13-191">Klik op **Eigenaren marketing voor campagne** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="07e13-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="07e13-192">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="07e13-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="07e13-193">Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="07e13-194">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="07e13-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="07e13-195">Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Marketing voor campagne-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.</span><span class="sxs-lookup"><span data-stu-id="07e13-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="07e13-196">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="07e13-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="07e13-197">De SharePoint-groep **Marketing voor campagne-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1), de groep **Marketing voor campagne** (deze bevat het gebruikersaccount van de globale beheerder), de groep **Analytisch personeel** (deze bevat het DataScientist1-gebruikersaccount) en het **Regular1**-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="07e13-198">De SharePoint-groep **Marketing voor campagne-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).</span><span class="sxs-lookup"><span data-stu-id="07e13-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="07e13-199">De SharePoint-groep **Marketing voor campagne-Bezoekers** bevat geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="07e13-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="07e13-200">Leden kunnen geen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Marketing voor campagne-Eigenaren**).</span><span class="sxs-lookup"><span data-stu-id="07e13-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="07e13-201">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende bronnen, maar kunnen wel toegang tot de site vragen, waardoor een e-mail wordt verzonden naar het postvak van het ITAdmin1-gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="07e13-202">Configureer vervolgens de map met documenten van de teamsite van de marketing voor de campagne voor het interne label.</span><span class="sxs-lookup"><span data-stu-id="07e13-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="07e13-203">Klik in het **Marketing voor campagne-Start**-tabblad van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="07e13-204">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="07e13-205">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="07e13-206">Selecteer bij **Instellingen-Label toepassen** de optie **Gevoelig** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="07e13-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="07e13-p106">Configureer vervolgens een DLP-beleid (preventie van gegevensverlies) dat gebruikers informeert wanneer ze een document op een SharePoint Online-teamsite delen met het label Gevoelig buiten de organisatie. Dit DLP-beleid is van toepassing op resources op de marketingsite van de campagne.</span><span class="sxs-lookup"><span data-stu-id="07e13-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="07e13-209">Klik op het tabblad **Microsoft Office Home** van uw browser op de tegel **Beveiliging en compliance**.</span><span class="sxs-lookup"><span data-stu-id="07e13-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="07e13-210">Klik op het nieuwe tabblad **Beveiliging en compliance** in uw browser op **Preventie van gegevensverlies > Beleid**.</span><span class="sxs-lookup"><span data-stu-id="07e13-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="07e13-211">Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="07e13-212">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="07e13-213">Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint Online-teamsites** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="07e13-214">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="07e13-215">Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="07e13-216">Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="07e13-217">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="07e13-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="07e13-218">Klik in het deelvenster **Labels** op **+Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="07e13-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="07e13-219">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="07e13-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="07e13-220">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="07e13-221">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="07e13-222">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="07e13-223">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="07e13-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="07e13-224">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="07e13-224">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="07e13-225">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="07e13-225">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="07e13-226">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="07e13-226">Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="07e13-227">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-227">Click **OK**.</span></span>

17. <span data-ttu-id="07e13-228">Schakel in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** het selectievakje **Delen door personen niet toestaan en toegang tot gedeelde inhoud beperken** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="07e13-229">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="07e13-230">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="07e13-231">Teamsite voor Campagnestrategie</span><span class="sxs-lookup"><span data-stu-id="07e13-231">Campaign strategy team site</span></span>

<span data-ttu-id="07e13-232">Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite wilt maken op het niveau van zeer vertrouwelijke informatie voor de resources van de campagnestrategie:</span><span class="sxs-lookup"><span data-stu-id="07e13-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="07e13-233">Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="07e13-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="07e13-234">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="07e13-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="07e13-235">Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="07e13-236">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="07e13-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="07e13-237">Typ bij **Naam van de teamsite\*\*\*\*Campagnestrategie** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="07e13-238">Typ bij **Beschrijving van de teamsite** **SharePoint-site voor campagnestrategie (zeer vertrouwelijk)** in.</span><span class="sxs-lookup"><span data-stu-id="07e13-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="07e13-239">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="07e13-240">Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="07e13-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="07e13-241">Klik in het nieuwe **Campagnestrategie**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="07e13-242">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="07e13-243">Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="07e13-244">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit (zodat alle drie de selectievakjes leeg zijn) en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="07e13-245">Klik op **Leden campagnestrategie** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="07e13-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="07e13-246">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="07e13-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="07e13-247">Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="07e13-248">Klik op **Eigenaren campagnestrategie** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="07e13-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="07e13-249">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="07e13-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="07e13-250">Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="07e13-251">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="07e13-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="07e13-252">Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Campagnestrategie-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.</span><span class="sxs-lookup"><span data-stu-id="07e13-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="07e13-253">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="07e13-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="07e13-254">De SharePoint-groep **Campagnestrategie-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1) en de groep **Campagnestrategie** (deze bevat het alleen gebruikersaccount van de globale beheerder).</span><span class="sxs-lookup"><span data-stu-id="07e13-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="07e13-255">De SharePoint-groep **Campagnestrategie-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).</span><span class="sxs-lookup"><span data-stu-id="07e13-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="07e13-256">De SharePoint-groep **Campagnestrategie-Bezoekers** bevat geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="07e13-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="07e13-257">Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Campagnestrategie-Eigenaren**).</span><span class="sxs-lookup"><span data-stu-id="07e13-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="07e13-258">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="07e13-258">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="07e13-259">Aanvullende machtigingen voor de site moeten worden uitgevoerd door de globale beheerder of door een lid van de groep **Campagnestrategie-Eigenaren**.</span><span class="sxs-lookup"><span data-stu-id="07e13-259">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="07e13-260">Configureer vervolgens de documentenmap van de Campagnestrategie-teamsite voor het label Zeer vertrouwelijk.</span><span class="sxs-lookup"><span data-stu-id="07e13-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="07e13-261">Klik in het tabblad **Campagnestrategie-Start** in uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="07e13-262">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="07e13-263">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="07e13-264">Selecteer in **Instellingen-Label toepassen** de optie **Zeer vertrouwelijk** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="07e13-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="07e13-p109">Configureer vervolgens een DLP-beleid dat gebruikers blokkeert wanneer ze een document delen op een SharePoint Online-teamsite met het label Zeer vertrouwelijk buiten de organisatie. Dit DLP-beleid is van toepassing op resources op de strategiesite van de campagne.</span><span class="sxs-lookup"><span data-stu-id="07e13-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="07e13-267">Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum (<https://admin.microsoft.com>) met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="07e13-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="07e13-268">Klik op het tabblad **Microsoft Office Home** van uw browser op de tegel **Beveiliging en compliance**.</span><span class="sxs-lookup"><span data-stu-id="07e13-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="07e13-269">Klik op het nieuwe tabblad **Beveiliging en compliance** in uw browser op **Preventie van gegevensverlies > Beleid**.</span><span class="sxs-lookup"><span data-stu-id="07e13-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="07e13-270">Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="07e13-271">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="07e13-272">Typ in het deelvenster **Uw beleid een naam geven** **Label Zeer vertrouwelijk voor SharePoint-sites** in bij **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="07e13-273">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="07e13-274">Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="07e13-275">Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="07e13-276">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="07e13-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="07e13-277">Klik in het deelvenster **Labels** op **+ Toevoegen**, selecteer het label **Zeer Vertrouwelijk**, klik op **Toevoegen** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="07e13-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="07e13-278">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="07e13-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="07e13-279">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="07e13-280">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="07e13-281">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="07e13-282">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="07e13-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="07e13-283">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="07e13-283">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="07e13-284">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="07e13-284">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="07e13-285">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="07e13-285">Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="07e13-286">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-286">Click **OK**.</span></span>

18. <span data-ttu-id="07e13-287">In het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?**, selecteert u **Een zakelijke reden vereisen om te overschrijven** en klikt u vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="07e13-288">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="07e13-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="07e13-289">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="07e13-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="07e13-290">Gebruik de instructies in [Azure RMS activeren met het Microsoft 365-beheercentrum](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="07e13-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="07e13-291">Configureer vervolgens Azure Information Protection met een nieuw beleid en een sublabel voor bescherming en machtigingen met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="07e13-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="07e13-292">Meld u aan met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="07e13-292">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="07e13-293">Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="07e13-293">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="07e13-294">Open een afzonderlijk tabblad in je browser en ga naar de Microsoft Azure-portal (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="07e13-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="07e13-295">Typ in het deelvenster **informatie** en klik vervolgens op **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="07e13-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="07e13-296">Klik op **Labels**.</span><span class="sxs-lookup"><span data-stu-id="07e13-296">Click **Labels**.</span></span>

5. <span data-ttu-id="07e13-297">Klik met de rechtermuisknop op het **Zeer vertrouwelijk**-label en klik vervolgens op **Voeg een sublabel toe**.</span><span class="sxs-lookup"><span data-stu-id="07e13-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="07e13-298">Typ **CampagneStrategie** in bij **Naam** en **Label voor documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="07e13-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="07e13-299">Klik bij **Machtigingen instellen voor documenten en e-mail met dit label** op **Beveiligen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="07e13-300">Klik in de sectie **Bescherming** op **Azure (cloud key)**.</span><span class="sxs-lookup"><span data-stu-id="07e13-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="07e13-301">Klik in het **Bescherming**-tabblad onder **Beschermingsinstellingen** op **+ Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="07e13-302">Klik in het **Machtigingen toevoegen**-tabblad onder **Gebruikers en groepen specificeren** op **+ Adreslijst zoeken**.</span><span class="sxs-lookup"><span data-stu-id="07e13-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="07e13-303">Selecteer in het deelvenster **AAD-gebruikers en -groepen** **Senior en strategisch personeel** en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="07e13-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="07e13-304">Klik onder **Kies vooraf ingestelde of aangepaste machtigingen** op **Aangepast** en klik vervolgens op de selectievakjes **Weergaverechten**, **Inhoud bewerken**, **Opslaan**, **Beantwoorden** en **Allen beantwoorden**.</span><span class="sxs-lookup"><span data-stu-id="07e13-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="07e13-305">Klik tweemaal op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="07e13-306">Klik in het **Sublabel**-tabblad op **Opslaan** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="07e13-307">Klik in het **Azure Information Protection**-tabblad op **Beleid > + Een nieuw beleid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="07e13-308">Typ **CampagneStrategie** in bij **Naam** en **Documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="07e13-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="07e13-309">Klik op **Selecteer de gebruikers of groepen aan wie u dit beleid wilt toewijzen > Gebruikers/groepen** en selecteer vervolgens **Senior en strategisch personeel**.</span><span class="sxs-lookup"><span data-stu-id="07e13-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="07e13-310">Klik vervolgens op **Selecteren \> OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="07e13-311">Klik op **Labels toevoegen of verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="07e13-311">Click **Add or remove labels**.</span></span> <span data-ttu-id="07e13-312">Klik in het deelvenster **Beleid: Labels toevoegen of verwijderen** op **CampagneStrategie** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-312">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="07e13-313">Klik op **Opslaan** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="07e13-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="07e13-314">U bent nu klaar om te beginnen met het maken van documenten op deze vier sites en het testen van de toegang hiertoe met verschillende gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="07e13-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="07e13-315">Als u een document met Azure Information Protection en dit nieuwe label wilt beveiligen, moet u [de Azure Information Protection-client installeren](/information-protection/rms-client/install-client-app) op een testcomputer, Office installeren vanuit het beheercentrum en u vervolgens aanmelden bij Microsoft Word met een account uit de groep **Senior en strategisch personeel** van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="07e13-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="07e13-316">Zie ook</span><span class="sxs-lookup"><span data-stu-id="07e13-316">See Also</span></span>

[<span data-ttu-id="07e13-317">Beveiligingsrichtlijnen van Microsoft voor politieke campagnes, non-profitorganisaties en andere agile organisaties</span><span class="sxs-lookup"><span data-stu-id="07e13-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="07e13-318">Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="07e13-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="07e13-319">Cloud adoption Test Lab Guides (TLGs)</span><span class="sxs-lookup"><span data-stu-id="07e13-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="07e13-320">Microsoft 365-oplossings- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="07e13-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)