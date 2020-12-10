---
title: Teams met basisbescherming configureren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Leer teams met een basisbescherming te implementeren.
ms.openlocfilehash: 16f37175c3aa7b420745e6126de1aa96368d618a
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613440"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="9d8ff-103">Teams met basisbescherming configureren</span><span class="sxs-lookup"><span data-stu-id="9d8ff-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="9d8ff-104">In dit artikel leest u hoe u teams met een basisbescherming kunt implementeren.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="9d8ff-105">Gebruikers kunnen bij een basisbescherming een groot aantal opties voor samenwerking gebruiken terwijl het beheer van machtigingen wordt verbeterd en er beveiliging tegen te veel delen wordt geboden.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="9d8ff-106">Aanbevolen beveiliging voor de basisbescherming bestaat onder andere uit beleidsregels voor apparaattoegang en beveiliging tegen malware.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="9d8ff-107">Daarnaast kunt u eventueel beleid voor voorwaardelijke toegang en bescherming tegen gegevensverlies toepassen.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="9d8ff-108">Initiële bescherming</span><span class="sxs-lookup"><span data-stu-id="9d8ff-108">Initial protections</span></span>

<span data-ttu-id="9d8ff-109">Als eerste stap wordt u aangeraden basisbeleid voor identiteiten en apparaattoegang te configureren.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="9d8ff-110">Zie [Beleidsaanbevelingen voor het beveiligen van Teams-chats, -groepen en -bestanden](../security/office-365-security/teams-access-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="9d8ff-111">We raden u ook aan de basisfuncties van Defender voor Office 365 in te schakelen voor de bescherming tegen malware in documenten, bijlagen en koppelingen.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="9d8ff-112">We adviseren u om de opties in de volgende tabel in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="9d8ff-113">Optie</span><span class="sxs-lookup"><span data-stu-id="9d8ff-113">Option</span></span>|<span data-ttu-id="9d8ff-114">Informatie</span><span class="sxs-lookup"><span data-stu-id="9d8ff-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="9d8ff-115">Veilige bijlagen voor SPO, OneDrive en Teams</span><span class="sxs-lookup"><span data-stu-id="9d8ff-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="9d8ff-116">Veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="9d8ff-116">Safe Attachments</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[<span data-ttu-id="9d8ff-117">Defender voor Office 365 - SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d8ff-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|<span data-ttu-id="9d8ff-118">Veilige documenten</span><span class="sxs-lookup"><span data-stu-id="9d8ff-118">Safe Documents</span></span>|[<span data-ttu-id="9d8ff-119">Veilige documenten in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9d8ff-119">Safe Documents in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|<span data-ttu-id="9d8ff-120">Veilige koppelingen voor Teams</span><span class="sxs-lookup"><span data-stu-id="9d8ff-120">Safe Links for Teams</span></span>|[<span data-ttu-id="9d8ff-121">Veilige Office 365-koppelingen in Teams</span><span class="sxs-lookup"><span data-stu-id="9d8ff-121">Office 365 Safe Links in Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[<span data-ttu-id="9d8ff-122">Veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="9d8ff-122">Safe Links</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="9d8ff-123">Delen met gasten in Teams</span><span class="sxs-lookup"><span data-stu-id="9d8ff-123">Teams guest sharing</span></span>

<span data-ttu-id="9d8ff-124">In elk van de lagen kan er worden gedeeld met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="9d8ff-125">Voor de gevoelige en zeer gevoelige lagen kan het delen met gasten worden uitgeschakeld op teamniveau door gevoeligheidslabels te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="9d8ff-126">Maar de instelling voor het delen met gasten op organisatieniveau moet zijn ingeschakeld om het delen met gasten in Teams te kunnen laten werken.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="9d8ff-128">Instellingen voor gasttoegang in Teams instellen</span><span class="sxs-lookup"><span data-stu-id="9d8ff-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="9d8ff-129">Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9d8ff-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="9d8ff-130">Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="9d8ff-131">Klik onder **Beheercentra** op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="9d8ff-132">Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="9d8ff-133">Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="9d8ff-134">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9d8ff-135">Het kan 24 uur duren voordat de instelling voor gasten in Teams actief wordt nadat u deze hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="9d8ff-136">Delen met gasten is standaard ingeschakeld voor Office 365-groepen en SharePoint, maar als u eerder een van de instellingen voor het delen met gasten hebt gewijzigd voor uw organisatie, wordt u aangeraden [Samenwerken met gasten in een team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) te controleren om ervoor te zorgen dat de functie voor het delen met gasten beschikbaar is in Teams.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="9d8ff-137">Sites en bestanden delen</span><span class="sxs-lookup"><span data-stu-id="9d8ff-137">Site and file sharing</span></span>

<span data-ttu-id="9d8ff-138">Als u het risico van het onbedoeld delen van bestanden of mappen met personen buiten uw organisatie wilt beperken, kunt u het beste de standaardkoppeling voor delen voor SharePoint wijzigen in *Alleen personen in uw organisatie*.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="9d8ff-139">(Als gebruikers extern moeten kunnen delen en u het delen met gasten hebt ingeschakeld, kunnen ze het koppelingstype nog steeds wijzigen wanneer ze delen.)</span><span class="sxs-lookup"><span data-stu-id="9d8ff-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="9d8ff-140">De standaardkoppeling voor delen wijzigen</span><span class="sxs-lookup"><span data-stu-id="9d8ff-140">To change the default sharing link</span></span>
1. <span data-ttu-id="9d8ff-141">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="9d8ff-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9d8ff-142">Klik onder **Beleid** op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="9d8ff-143">Selecteer onder **Koppelingen naar bestanden en mappen** de optie **Alleen personen binnen uw organisatie**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="9d8ff-144">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-144">Click **Save**.</span></span>

<span data-ttu-id="9d8ff-145">Voor de beste ervaring voor het delen met gasten wordt u ook aangeraden om [SharePoint- en OneDrive-integratie met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="9d8ff-146">Een team maken</span><span class="sxs-lookup"><span data-stu-id="9d8ff-146">Create a team</span></span>

<span data-ttu-id="9d8ff-147">Er wordt een extra configuratie uitgevoerd voor de basisbescherming in de SharePoint-site die is gekoppeld aan een team.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="9d8ff-148">[Maak een openbaar of persoonlijk team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) voordat u verder gaat met de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="9d8ff-149">Instellingen voor het delen van een site</span><span class="sxs-lookup"><span data-stu-id="9d8ff-149">Site sharing settings</span></span>

<span data-ttu-id="9d8ff-150">Leden van een SharePoint-site kunnen standaard anderen uitnodigen voor de site.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="9d8ff-151">Wanneer een site deel uitmaakt van een team, worden teamleden opgenomen als siteleden.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="9d8ff-152">Personen die rechtstreeks aan de site worden toegevoegd, hebben echter geen toegang tot de rest van het team.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="9d8ff-153">Om deze reden wordt u aangeraden machtigingen uitsluitend te beheren via het team.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="9d8ff-154">Om u te helpen bij het beheer van machtigingen wordt u aangeraden de bijbehorende site zo te configureren dat alleen eigenaren zelf de site mogen delen.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="9d8ff-155">Dit vereenvoudigt het beheer van machtigingen en helpt voorkomen dat anderen toegang krijgen zonder dat de eigenaar hiervan op de hoogte is.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="9d8ff-156">Doe dit voor elk team waarvoor basisbescherming is vereist.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="9d8ff-157">De instellingen voor het delen van een site bijwerken</span><span class="sxs-lookup"><span data-stu-id="9d8ff-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="9d8ff-158">Klik op de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="9d8ff-159">Klik op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="9d8ff-160">Klik op de werkbalk van de SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="9d8ff-161">Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-161">In the **Site permissions** pane, under **Sharing settings**, click **Change sharing settings**.</span></span>
5. <span data-ttu-id="9d8ff-162">Selecteer onder **Machtigingen voor delen** de optie **Site-eigenaren en leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="9d8ff-163">Aanvullende beveiligingsmaatregelen</span><span class="sxs-lookup"><span data-stu-id="9d8ff-163">Additional protections</span></span>

<span data-ttu-id="9d8ff-164">Microsoft 365 biedt aanvullende methoden voor het beveiligen van uw inhoud.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="9d8ff-165">Overweeg of de volgende opties de beveiliging van uw organisatie zouden kunnen verbeteren.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="9d8ff-166">Laat uw gastgebruikers akkoord gaan met de [gebruiksrechtenovereenkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span><span class="sxs-lookup"><span data-stu-id="9d8ff-166">Have guests agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="9d8ff-167">Configureer een [beleid voor de time-out van een sessie](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) voor gasten.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-167">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="9d8ff-168">Maak [typen voor gevoelige informatie](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) en gebruik [gegevensverliesbeveiliging](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) om beleid in te stellen rond toegang tot gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-168">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d8ff-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9d8ff-169">See Also</span></span>

[<span data-ttu-id="9d8ff-170">Vergaderingsbeleid beheren in Teams</span><span class="sxs-lookup"><span data-stu-id="9d8ff-170">Manage meeting policies in Teams</span></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="9d8ff-171">Aan de slag met insider-risicobeheer</span><span class="sxs-lookup"><span data-stu-id="9d8ff-171">Get started with insider risk management</span></span>](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
