---
title: Teams met bescherming voor vertrouwelijke gegevens configureren
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
recommendations: false
description: Informatie over het implementeren van teams met bescherming voor vertrouwelijke gegevens.
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788340"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="6b5a9-103">Teams met bescherming voor vertrouwelijke gegevens configureren</span><span class="sxs-lookup"><span data-stu-id="6b5a9-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="6b5a9-104">In dit artikel kijken we naar het opzetten van een team met een gevoelig beschermingsniveau.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="6b5a9-105">Zorg ervoor dat u de stappen hebt voltooid in [teams implementeren met basisbeveiliging](configure-teams-baseline-protection.md) voordat u de stappen in dit artikel uitvoert.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="6b5a9-106">De gevoelige laag biedt de volgende extra bescherming boven op de basislaag:</span><span class="sxs-lookup"><span data-stu-id="6b5a9-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="6b5a9-p102">Een gevoeligheidslabel voor het team waarmee u het delen van gasten kunt in- of uitschakelen en de toegang tot SharePoint-inhoud beperkt tot alleen-internet voor onbeheerde apparaten. Dit label kan ook worden gebruikt om bestanden te classificeren.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="6b5a9-109">Een meer beperkend standaardkoppelingstype voor delen</span><span class="sxs-lookup"><span data-stu-id="6b5a9-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="6b5a9-110">Alleen teameigenaren kunnen persoonlijke kanalen maken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="6b5a9-111">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="6b5a9-111">Video demonstration</span></span>

<span data-ttu-id="6b5a9-112">Bekijk deze video voor een overzicht van de procedures die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="6b5a9-113">Delen met gasten</span><span class="sxs-lookup"><span data-stu-id="6b5a9-113">Guest sharing</span></span>

<span data-ttu-id="6b5a9-114">Afhankelijk van de aard van uw bedrijf, wilt u het delen met gasten mogelijk niet inschakelen voor teams die gevoelige gegevens bevatten.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="6b5a9-115">Als u van plan bent om met personen buiten uw organisatie samen te werken in het team, raden we aan om delen met gasten in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="6b5a9-116">Microsoft 365 bevat diverse functies voor beveiliging en compliance waarmee u vertrouwelijke inhoud veilig kunt delen.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="6b5a9-117">Dit is over het algemeen een veiliger optie dan inhoud rechtstreeks naar mensen buiten uw organisatie te e-mailen.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="6b5a9-118">Voor meer informatie over delen met gasten kunt u de volgende bronnen raadplegen:</span><span class="sxs-lookup"><span data-stu-id="6b5a9-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="6b5a9-119">Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie</span><span class="sxs-lookup"><span data-stu-id="6b5a9-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="6b5a9-120">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="6b5a9-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="6b5a9-121">Om delen met gasten toe te staan of te blokkeren, gebruiken we een combinatie van een gevoeligheidslabel voor het team en besturingselementen voor delen op siteniveau voor de bijbehorende SharePoint-site, die beide later worden besproken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="6b5a9-122">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="6b5a9-122">Sensitivity labels</span></span>

<span data-ttu-id="6b5a9-123">Voor het gevoelige beveiligingsniveau wordt een gevoeligheidslabel gebruikt om het team te classificeren.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="6b5a9-124">Dit label kan ook worden gebruikt om afzonderlijke bestanden in deze of andere teams te classificeren, of in andere bestandslocaties zoals SharePoint of OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="6b5a9-125">Als eerste stap moet u gevoeligheidslabels voor Teams inschakelen.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="6b5a9-126">Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Office 365-groepen en SharePoint-sites](../compliance/sensitivity-labels-teams-groups-sites.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="6b5a9-127">Als u al gevoeligheidslabels in uw organisatie hebt geïmplementeerd, kunt u overwegen hoe dit label past in uw algemene labelstrategie.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="6b5a9-128">U kunt de naam of instellingen zo nodig wijzigen om tegemoet te komen aan de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="6b5a9-129">Wanneer u gevoeligheidslabels voor Teams hebt ingeschakeld, is de volgende stap het maken van het label.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="6b5a9-130">Een gevoeligheidslabel maken</span><span class="sxs-lookup"><span data-stu-id="6b5a9-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="6b5a9-131">Open het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6b5a9-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="6b5a9-132">Klik onder **Oplossingen** op **Informatiebeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="6b5a9-133">Klik op **Een label maken**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="6b5a9-134">Geef een naam op voor het label.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-134">Give the label a name.</span></span> <span data-ttu-id="6b5a9-135">We stellen **Gevoelig** voor, maar u kunt een andere naam kiezen als die al in gebruik is.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="6b5a9-136">Voeg een weergavenaam en een beschrijving toe en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="6b5a9-137">Selecteer op de **pagina Het bereik voor dit label definiëren** de opties **Bestanden en e-mailberichten** en **Groepen en sites** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="6b5a9-138">Klik op de pagina **Beveiligingsinstellingen voor bestanden en e-mailberichten kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="6b5a9-139">Klik op de pagina *Automatische labeling voor bestanden en e-mailberichten* op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="6b5a9-140">Selecteer op de pagina **Beveiligingsinstellingen voor groepen en sites definiëren** de opties **Instellingen voor privacy en toegang voor externe gebruikers** en **Instellingen voor toegang tot apparaten en instellingen voor extern delen** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="6b5a9-141">Selecteer op de pagina **Instellingen voor privacy en toegang voor externe gebruikers definiëren** onder **Privacy** de optie **Privé**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="6b5a9-142">Als je gasttoegang wilt toestaan, selecteer je onder **Toegang voor externe gebruikers** de optie **Laat Microsoft 365-groepseigenaren personen van buiten de organisatie als gast aan de groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="6b5a9-143">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-143">Click **Next**.</span></span>
13. <span data-ttu-id="6b5a9-144">Selecteer op de pagina **Instellingen voor extern delen en instellingen voor toegang tot het apparaat definiëren** de optie **Extern delen beheren via gelabelde SharePoint-sites**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="6b5a9-145">Onder **Inhoud kan worden gedeeld met** kiest u **Nieuwe en bestaande gasten** als u gasttoegang wilt toestaan of **Alleen personen van de organisatie** als u dat niet wilt.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="6b5a9-146">Kies onder **Toegang tot niet-beheerde apparaten** de optie **Beperkte toegang tot alleen internet toestaan**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="6b5a9-147">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-147">Click **Next**.</span></span>
17. <span data-ttu-id="6b5a9-148">Klik op de pagina **Automatische labeling voor databasekolommen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="6b5a9-149">Klik op **Label maken** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="6b5a9-150">Nadat u het label heeft gemaakt, moet u het publiceren voor de gebruikers die het zullen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="6b5a9-151">Voor gevoelige bescherming maken we het label beschikbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="6b5a9-152">U kunt het label publiceren in het Microsoft 365-compliancecentrum, op het tabblad **Labelbeleid** op de pagina **Informatiebeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="6b5a9-153">Als u een bestaand beleid hebt dat van toepassing is op alle gebruikers, kunt u dit label toevoegen aan dat beleid.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="6b5a9-154">Als u een nieuw beleid wilt maken, raadpleegt u [Gevoeligheidslabels publiceren door een labelbeleid te maken](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="6b5a9-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="6b5a9-155">Een team maken</span><span class="sxs-lookup"><span data-stu-id="6b5a9-155">Create a team</span></span>

<span data-ttu-id="6b5a9-156">Verdere configuratie van het gevoelige scenario wordt uitgevoerd op de SharePoint-site die aan het team is gekoppeld, dus de volgende stap is het maken van een team.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="6b5a9-157">Een team maken voor vertrouwelijke informatie</span><span class="sxs-lookup"><span data-stu-id="6b5a9-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="6b5a9-158">Klik links in Teams op **Teams** en klik onderaan de lijst met teams op **Deelnemen aan een team of een team maken**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="6b5a9-159">Klik op **Team maken** (eerste kaart, linkerbovenhoek).</span><span class="sxs-lookup"><span data-stu-id="6b5a9-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="6b5a9-160">Kies **Een volledig nieuw team maken**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="6b5a9-161">Kies in de lijst **gevoeligheid** het label **gevoelig** dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="6b5a9-162">Klik onder **privacy** op **persoonlijk**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="6b5a9-163">Typ een naam voor het team en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="6b5a9-164">Voeg gebruikers toe aan het team en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="6b5a9-165">Instellingen voor privékanaal</span><span class="sxs-lookup"><span data-stu-id="6b5a9-165">Private channel settings</span></span>

<span data-ttu-id="6b5a9-166">In deze fase wordt u aangeraden het maken van privé-kanalen tot teameigenaren te beperken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="6b5a9-167">Het maken van een persoonlijk kanaal beperken</span><span class="sxs-lookup"><span data-stu-id="6b5a9-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="6b5a9-168">In het team klikt u op **Meer opties** en klikt u vervolgens op **Team beheren**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="6b5a9-169">Vouw op het tabblad **Instellingen** de optie **Machtigingen voor leden** uit.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="6b5a9-170">Schakel het selectievakje **Leden toestaan privékanalen te maken** uit.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="6b5a9-171">U kunt ook [teambeleid](/MicrosoftTeams/teams-policies) gebruiken om te bepalen wie persoonlijke kanalen kan maken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="6b5a9-172">SharePoint-instellingen</span><span class="sxs-lookup"><span data-stu-id="6b5a9-172">SharePoint settings</span></span>

<span data-ttu-id="6b5a9-173">Telkens wanneer u een nieuw team met het gevoelige label maakt, moet u twee stappen uitvoeren in SharePoint:</span><span class="sxs-lookup"><span data-stu-id="6b5a9-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="6b5a9-174">Werk de instellingen voor het delen van gasten voor de site in het SharePoint-beheercentrum bij om de standaardkoppeling voor delen bij te werken naar *Specifieke personen*.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="6b5a9-175">Werk de instellingen voor het delen van sites op de site zelf bij om te voorkomen dat leden de site delen.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="6b5a9-176">Standaardinstellingen voor site delen</span><span class="sxs-lookup"><span data-stu-id="6b5a9-176">Site default sharing link settings</span></span>

<span data-ttu-id="6b5a9-177">Standaardinstellingen voor site delen bijwerken</span><span class="sxs-lookup"><span data-stu-id="6b5a9-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="6b5a9-178">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="6b5a9-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="6b5a9-179">Klik onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="6b5a9-180">Klik op de site die is gekoppeld aan het team.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="6b5a9-181">Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="6b5a9-182">Schakel onder Standaard koppelingstype voor delen het selectievakje **hetzelfde als instelling op organisatieniveau** uit en selecteer **specifieke personen (alleen de personen die door de gebruiker worden opgegeven)**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="6b5a9-183">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-183">Click **Save**.</span></span>

<span data-ttu-id="6b5a9-184">Als u dit wilt scripten als onderdeel van het proces voor het maken van een team, kunt u [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) gebruiken met de `-DefaultSharingLinkType Direct` parameter om de standaardlink voor delen te wijzigen in *Specifieke personen*.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="6b5a9-185">Privékanalen</span><span class="sxs-lookup"><span data-stu-id="6b5a9-185">Private channels</span></span>

<span data-ttu-id="6b5a9-186">Als u privékanalen aan het team toevoegt, maakt elk privékanaal een nieuwe SharePoint-site met de standaardinstellingen voor delen.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="6b5a9-187">Deze sites zijn niet zichtbaar in het SharePoint-beheercentrum, dus u moet de PowerShell-cmdlet Set-SPOSite gebruiken om de instellingen voor het delen van gasten bij te werken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="6b5a9-188">Standaardinstellingen voor het delen van een site</span><span class="sxs-lookup"><span data-stu-id="6b5a9-188">Site sharing settings</span></span>

<span data-ttu-id="6b5a9-189">Om ervoor te zorgen dat de SharePoint-site niet wordt gedeeld met personen die geen deel uitmaken van het team, beperken we het delen ervan tot eigenaren.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="6b5a9-190">Om het delen van sites voor alleen-eigenaren te configureren</span><span class="sxs-lookup"><span data-stu-id="6b5a9-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="6b5a9-191">Ga in Teams naar het tabblad **Algemeen** van het team dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="6b5a9-192">Klik op de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="6b5a9-193">Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="6b5a9-194">Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="6b5a9-195">Klik in het deelvenster **Site-machtigingen** onder **Delen van een site** op **Wijzigen hoe leden kunnen delen**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="6b5a9-196">Selecteer onder **machtigingen voor delen** de optie **site-eigenaren en leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen** en klik vervolgens op **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6b5a9-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="6b5a9-197">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6b5a9-197">See Also</span></span>

[<span data-ttu-id="6b5a9-198">Gevoeligheidslabels en hun beleid maken en configureren</span><span class="sxs-lookup"><span data-stu-id="6b5a9-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
