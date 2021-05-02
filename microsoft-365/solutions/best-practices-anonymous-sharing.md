---
title: Aanbevolen procedures voor niet-geverifieerd delen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: In dit artikel vindt u informatie over de aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers.
ms.openlocfilehash: 1e696611d37cd1b57f881457025464dccea54496
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114316"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="278e0-103">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="278e0-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="278e0-104">Niet-geverifieerd delen (*iedereen*-koppelingen) kunnen handig zijn en bruikbaar in verschillende scenario's.</span><span class="sxs-lookup"><span data-stu-id="278e0-104">Unauthenticated sharing (*Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="278e0-105">*Iedereen*-koppelingen zijn de gemakkelijkste manier om te delen: personen kunnen de koppeling zonder verificatie openen en deze aan anderen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="278e0-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="278e0-p102">Gewoonlijk is niet alle inhoud in een organisatie geschikt voor niet-geverifieerd delen. Dit artikel behandelt de beschikbare opties om u te helpen een omgeving te creëren waarin uw gebruikers niet-geverifieerd delen van bestanden en mappen kunnen gebruiken, maar waar er veiligheidsmaatregelen zijn getroffen om de inhoud van uw organisatie te helpen beschermen.</span><span class="sxs-lookup"><span data-stu-id="278e0-p102">Usually, not all content in an organization is appropriate for unauthenticated sharing. This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="278e0-108">Om niet-geverifieerd delen te laten werken, moet u dit inschakelen voor uw organisatie en voor de individuele site of het team dat u gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="278e0-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="278e0-109">Zie [samenwerken met personen buiten uw organisatie](collaborate-with-people-outside-your-organization.md) voor het scenario dat u wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="278e0-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="278e0-110">Een vervaldatum instellen voor koppelingen voor iedereen</span><span class="sxs-lookup"><span data-stu-id="278e0-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="278e0-111">Bestanden worden vaak gedurende lange perioden opgeslagen in sites, groepen en teams.</span><span class="sxs-lookup"><span data-stu-id="278e0-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="278e0-112">Af en toe zijn er beleidsregels voor het bewaren van gegevens die vereisen dat bestanden jaren worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="278e0-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="278e0-113">Als dergelijke bestanden worden gedeeld met niet-geverifieerde personen, kan dit leiden tot onverwachte toegang en wijzigingen in bestanden in de toekomst.</span><span class="sxs-lookup"><span data-stu-id="278e0-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="278e0-114">Om deze mogelijkheid te beperken, kunt u een vervaltijd configureren voor *iedereen*-koppelingen.</span><span class="sxs-lookup"><span data-stu-id="278e0-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="278e0-115">Wanneer een *iedereen*-koppeling verloopt, kan deze niet meer worden gebruikt voor toegang tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="278e0-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="278e0-116">Een vervaldatum instellen voor iedereen-koppelingen voor de gehele organisatie</span><span class="sxs-lookup"><span data-stu-id="278e0-116">To set an expiration date for Anyone links across the organization</span></span>

1. <span data-ttu-id="278e0-117">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="278e0-117">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="278e0-118">Klik in het navigatievenster aan de linkerkant op **delen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-118">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="278e0-119">Schakel onder **Opties voor verloop en machtigingen kiezen voor 'Iedereen'-koppelingen** het selectievakje **Deze koppelingen moeten binnen zoveel dagen verlopen** in.</span><span class="sxs-lookup"><span data-stu-id="278e0-119">Under **Choose expiration and permissions options for Anyone links**, select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="278e0-120">![Schermafbeelding van de verloopinstellingen van de Iedereen-koppelingen op organisatieniveau in SharePoint](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="278e0-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="278e0-121">Typ het aantal dagen in het vak en klik vervolgens op **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="278e0-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="278e0-122">Een vervaldatum instellen voor iedereen-koppelingen op een specifieke site</span><span class="sxs-lookup"><span data-stu-id="278e0-122">To set an expiration date for Anyone links on a specific site</span></span>

1. <span data-ttu-id="278e0-123">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="278e0-123">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="278e0-124">Vouw in het navigatievenster aan de linkerkant **Sites** uit en klik vervolgens op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="278e0-124">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="278e0-125">Selecteer de site die u wilt wijzigen en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-125">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="278e0-126">Schakel onder **Geavanceerde instellingen voor Iedereen-koppelingen** onder **Vervaldatum voor Iedereen-koppelingen** het selectievakje **Hetzelfde als instellingen op organisatieniveau** uit.</span><span class="sxs-lookup"><span data-stu-id="278e0-126">Under **Advanced settings for Anyone links**, under **Expiration of Anyone links**, clear the **Same as organization-level setting** check box.</span></span></br>
   <span data-ttu-id="278e0-127">![Schermafbeelding van de verloopinstellingen van de Iedereen-koppelingen op siteniveau in SharePoint](../media/sharepoint-organization-anyone-link-expiration-site.png)</span><span class="sxs-lookup"><span data-stu-id="278e0-127">![Screenshot of SharePoint site-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration-site.png)</span></span>
5. <span data-ttu-id="278e0-128">Selecteer de optie **Deze koppelingen moeten verlopen binnen dit aantal dagen** en typ het aantal dagen in het vak.</span><span class="sxs-lookup"><span data-stu-id="278e0-128">Select the **These links must expire within this many days** option, and type a number of days in the box.</span></span>
6. <span data-ttu-id="278e0-129">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="278e0-129">Click **Save**.</span></span>

<span data-ttu-id="278e0-130">Wanneer een *Iedereen*-koppeling verloopt, kan het bestand of de map opnieuw worden gedeeld met een nieuwe *Iedereen*-koppeling.</span><span class="sxs-lookup"><span data-stu-id="278e0-130">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="278e0-131">U kunt de vervaldatum van een *Iedereen* koppeling voor een bepaalde OneDrive instellen door [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="278e0-131">You can set *Anyone* link expiration for a specific OneDrive by using [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="278e0-132">Koppelingsmachtigingen instellen</span><span class="sxs-lookup"><span data-stu-id="278e0-132">Set link permissions</span></span>

<span data-ttu-id="278e0-133">Met *Iedereen*-koppelingen naar een bestand kunnen mensen het bestand bewerken en met *Iedereen*-koppelingen naar een map kunnen mensen bestanden bewerken en bekijken en nieuwe bestanden naar de map uploaden.</span><span class="sxs-lookup"><span data-stu-id="278e0-133">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="278e0-134">U kunt deze machtigingen voor bestanden en mappen afzonderlijk wijzigen in alleen-weergeven.</span><span class="sxs-lookup"><span data-stu-id="278e0-134">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="278e0-135">Als u niet-geverifieerd delen wilt inschakelen, maar zich zorgen maakt over niet-geverifieerde personen die de inhoud van uw organisatie wijzigen, kunt u overwegen om de bestands- en mapmachtigingen in te stellen op **weergave**.</span><span class="sxs-lookup"><span data-stu-id="278e0-135">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="278e0-136">Machtigingen instellen voor iedereen-koppelingen voor de gehele organisatie</span><span class="sxs-lookup"><span data-stu-id="278e0-136">To set permissions for Anyone links across the organization</span></span>

1. <span data-ttu-id="278e0-137">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="278e0-137">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="278e0-138">Klik in het navigatievenster aan de linkerkant op **delen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-138">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="278e0-139">Selecteer onder **Geavanceerde instellingen voor iedereen-koppelingen** de bestands- en mapmachtigingen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="278e0-139">Under **Advanced settings for "Anyone" links**, select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="278e0-140">![Schermafbeelding van de instellingen van de koppelingsmachtigingen op organisatieniveau in SharePoint](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="278e0-140">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="278e0-141">Met *iedereen*-koppelingen die zijn ingesteld op **weergeven**, kunnen gebruikers nog steeds bestanden en mappen met gasten delen en hen machtigingen geven door koppelingen voor *specifieke personen* te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="278e0-141">With *Anyone* links set to **View**, users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="278e0-142">Deze koppelingen vereisen dat mensen buiten uw organisatie zich als gasten verifiëren, en u kunt gastactiviteiten volgen en controleren voor bestanden en mappen die met deze links worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="278e0-142">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="278e0-143">Standaardkoppelingstype instellen op alleen-werk voor personen in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="278e0-143">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="278e0-144">Als *Iedereen* delen is ingeschakeld voor uw organisatie, is de standaardkoppeling voor delen normaal ingesteld op **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-144">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="278e0-145">Hoewel dit handig kan zijn voor gebruikers, kan het risico op onbedoeld niet-geverifieerd delen toenemen.</span><span class="sxs-lookup"><span data-stu-id="278e0-145">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="278e0-146">Als een gebruiker het type koppeling vergeet te wijzigen terwijl een beperkt document wordt gedeeld, kan het zijn dat ze per ongeluk een koppeling voor delen maken waarvoor geen verificatie is vereist.</span><span class="sxs-lookup"><span data-stu-id="278e0-146">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="278e0-147">U kunt dit risico beperken door de standaardinstelling voor koppelingen te wijzigen in een koppeling die alleen geschikt is voor personen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="278e0-147">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="278e0-148">Gebruikers die willen delen met niet-geverifieerde personen, moeten deze optie specifiek selecteren.</span><span class="sxs-lookup"><span data-stu-id="278e0-148">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="278e0-149">De standaardkoppeling voor het delen van bestanden en mappen instellen voor de organisatie</span><span class="sxs-lookup"><span data-stu-id="278e0-149">To set the default file and folder sharing link for the organization</span></span>
1. <span data-ttu-id="278e0-150">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="278e0-150">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="278e0-151">Klik in het navigatievenster aan de linkerkant op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-151">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="278e0-152">Selecteer onder **Koppelingen voor bestanden en mappen** de optie **Alleen personen in uw organisatie**.</span><span class="sxs-lookup"><span data-stu-id="278e0-152">Under **File and folder links**, select **Only people in your organization**.</span></span>

   ![Schermafbeelding van instelling voor standaardkoppelingstype in SharePoint](../media/sharepoint-default-sharing-link-company-link.png)

4. <span data-ttu-id="278e0-154">Klik op **Opslaan**</span><span class="sxs-lookup"><span data-stu-id="278e0-154">Click **Save**</span></span>

<span data-ttu-id="278e0-155">De standaardkoppeling voor het delen van bestanden en mappen instellen voor een specifieke site</span><span class="sxs-lookup"><span data-stu-id="278e0-155">To set the default file and folder sharing link for a specific site</span></span>
1. <span data-ttu-id="278e0-156">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="278e0-156">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="278e0-157">Vouw in het navigatievenster aan de linkerkant **Sites** uit en klik vervolgens op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="278e0-157">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="278e0-158">Selecteer de site die u wilt wijzigen en klik vervolgens op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-158">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="278e0-159">Schakel onder **Standaard koppelingstype voor delen** het selectievakje **Hetzelfde als instelling op organisatieniveau** uit.</span><span class="sxs-lookup"><span data-stu-id="278e0-159">Under **Default sharing link type**,  clear the **Same as organization-level setting** check box.</span></span>

   ![Schermafbeelding van instelling voor standaardkoppelingstype op siteniveau in SharePoint](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. <span data-ttu-id="278e0-161">Schakel de optie **Alleen personen in uw organisatie** in en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="278e0-161">Select the **Only people in your organization** option and click **Save**.</span></span>

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a><span data-ttu-id="278e0-162">Niet-geverifieerd delen van gevoelige inhoud voorkomen</span><span class="sxs-lookup"><span data-stu-id="278e0-162">Prevent unauthenticated sharing of sensitive content</span></span>

<span data-ttu-id="278e0-163">U kunt [Preventie van gegevensverlies (DLP)](../compliance/dlp-learn-about-dlp.md) gebruiken om het niet-geverifieerd delen van gevoelige inhoud te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="278e0-163">You can use [data loss prevention (DLP)](../compliance/dlp-learn-about-dlp.md) to prevent unauthenticated sharing of sensitive content.</span></span> <span data-ttu-id="278e0-164">Preventie van gegevensverlies kan actie ondernemen op basis van het vertrouwelijkheidslabel of retentielabel van het bestand of van de gevoelige informatie in het bestand zelf.</span><span class="sxs-lookup"><span data-stu-id="278e0-164">Data loss prevention can take action based on a file's sensitivity label, retention label, or sensitive information in the file itself.</span></span>

<span data-ttu-id="278e0-165">Een DLP-regel maken</span><span class="sxs-lookup"><span data-stu-id="278e0-165">To create a DLP rule</span></span>
1. <span data-ttu-id="278e0-166">Ga in het Microsoft 365-compliancecentrum naar de pagina [Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention).</span><span class="sxs-lookup"><span data-stu-id="278e0-166">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="278e0-167">Klik op **Beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="278e0-167">Click **Create policy**.</span></span>
3. <span data-ttu-id="278e0-168">Kies **Aangepast** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="278e0-168">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="278e0-169">Typ een naam voor het beleid en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="278e0-169">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="278e0-170">Schakel op de pagina **Locaties waarop het beleid wordt toegepast** alle instellingen uit, behalve **SharePoint-sites** en **OneDrive-accounts** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="278e0-170">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="278e0-171">Klik op de pagina **Beleidsinstellingen definiëren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="278e0-171">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="278e0-172">Klik op de pagina **Geavanceerde DLP-regels aanpassen** op **Regel maken** en typ een naam voor de regel.</span><span class="sxs-lookup"><span data-stu-id="278e0-172">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="278e0-173">Klik onder **Voorwaarden** op **Voorwaarde toevoegen** en kies **Inhoud bevat**.</span><span class="sxs-lookup"><span data-stu-id="278e0-173">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="278e0-174">Klik op **Toevoegen** en kies het type informatie waarvoor u niet-geverifieerd delen wilt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="278e0-174">Click **Add** and choose the type of information for which you want to prevent unauthenticated sharing.</span></span>

   ![Schermafbeelding van voorwaardenopties, typen gevoelige info, vertrouwelijkheidslabels en retentielabels.](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="278e0-176">Klik onder **Acties** op **Een actie toevoegen** en kies vervolgens **Inhoud van de Microsoft 365-locaties versleutelen of de toegang beperken**.</span><span class="sxs-lookup"><span data-stu-id="278e0-176">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="278e0-177">Schakel het selectievakje **Inhoud van de Microsoft 365-locaties versleutelen of de toegang beperken** in en kies vervolgens de optie **Alleen personen die toegang hebben gekregen tot de inhoud via de opties voor 'Iedereen met de koppeling '**.</span><span class="sxs-lookup"><span data-stu-id="278e0-177">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people who were given access to the content through the "Anyone withe the link" options** option.</span></span>

      ![Schermafbeelding van de actieopties van de DLP-regel](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. <span data-ttu-id="278e0-179">Klik op **Opslaan** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="278e0-179">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="278e0-180">Kies de testopties en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="278e0-180">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="278e0-181">Klik op **Verzenden** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="278e0-181">Click **Submit**, and then click **Done**.</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="278e0-182">Beveiligen tegen schadelijke bestanden</span><span class="sxs-lookup"><span data-stu-id="278e0-182">Protect against malicious files</span></span>

<span data-ttu-id="278e0-183">Wanneer u anonieme gebruikers toestaat bestanden te uploaden, loopt u een groter risico dat iemand een schadelijk bestand uploadt.</span><span class="sxs-lookup"><span data-stu-id="278e0-183">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="278e0-184">In Microsoft 365 kunt u de functie *Veilige bijlagen* in Defender voor Office 365 gebruiken om geüploade bestanden automatisch te scannen en bestanden in quarantaine te plaatsen die als onveilig worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="278e0-184">In Microsoft 365, you can use the *Safe Attachments* feature in Defender for Office 365 to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="278e0-185">Veilige bijlagen inschakelen</span><span class="sxs-lookup"><span data-stu-id="278e0-185">To turn on safe attachments</span></span>
1. <span data-ttu-id="278e0-186">Open in het Beveiligings- en compliancecentrum de [pagina ATP Veilige bijlagen](https://protection.office.com/safeattachmentv2).</span><span class="sxs-lookup"><span data-stu-id="278e0-186">Open the [ATP Safe Attachments page](https://protection.office.com/safeattachmentv2) in the Security and Compliance admin center.</span></span>
2. <span data-ttu-id="278e0-187">Klik op **Algemene instellingen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-187">Click **Global settings**.</span></span>
3. <span data-ttu-id="278e0-188">Schakel ATP voor SharePoint, OneDrive en Microsoft Teams in.</span><span class="sxs-lookup"><span data-stu-id="278e0-188">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   ![Schermafbeelding van de instelling Veilige bijlagen in het Beveiligings- en compliancecentrum](../media/safe-attachments-setting.png)

4. <span data-ttu-id="278e0-190">Desgewenst kunt u ook Veilige documenten inschakelen en vervolgens op **Opslaan** klikken.</span><span class="sxs-lookup"><span data-stu-id="278e0-190">Optionally turn on Safe Documents as well, and then click **Save**</span></span>

<span data-ttu-id="278e0-191">Raadpleeg [ATP voor SharePoint, OneDrive en Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) en [ATP voor SharePoint, OneDrive en Microsoft teams inschakelen](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) voor meer hulp.</span><span class="sxs-lookup"><span data-stu-id="278e0-191">See [ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) for additional guidance.</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="278e0-192">Copyrightgegevens toevoegen aan uw bestanden</span><span class="sxs-lookup"><span data-stu-id="278e0-192">Add copyright information to your files</span></span>

<span data-ttu-id="278e0-193">Als u gevoeligheid-labels gebruikt in het Microsoft 365 -beheercentrum voor compliance, kunt u de labels zo configureren dat er automatisch een watermerk of kop- of voettekst wordt toegevoegd aan de Office-documenten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="278e0-193">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="278e0-194">Op deze manier kunt u ervoor zorgen dat gedeelde bestanden copyrightgegevens of andere eigendomsgegevens bevatten.</span><span class="sxs-lookup"><span data-stu-id="278e0-194">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="278e0-195">Een voettekst toevoegen aan een gelabeld bestand</span><span class="sxs-lookup"><span data-stu-id="278e0-195">To add a footer to a labeled file</span></span>

1. <span data-ttu-id="278e0-196">Open het [Microsoft 365-beheercentrum](https://compliance.microsoft.com) voor compliance.</span><span class="sxs-lookup"><span data-stu-id="278e0-196">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="278e0-197">Klik in het navigatievenster aan de linkerkant onder **Oplossingen** op **Informatiebeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="278e0-197">In the left navigation, under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="278e0-198">Klik op het label waaraan u een voettekst wilt toevoegen en klik vervolgens op **Label bewerken**.</span><span class="sxs-lookup"><span data-stu-id="278e0-198">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="278e0-199">Klik op **Volgende** om naar het tabblad **Inhoudsmarkering** te gaan en schakel vervolgens inhoudsmarkering **in**.</span><span class="sxs-lookup"><span data-stu-id="278e0-199">Click **Next** to reach the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="278e0-200">Schakel het selectievakje in voor het type tekst dat u wilt toevoegen en klik vervolgens op **tekst aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="278e0-200">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="278e0-201">Typ de tekst die u wilt toevoegen aan uw documenten, selecteer de gewenste tekstopties en klik vervolgens op **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="278e0-201">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="278e0-202">![Schermafbeelding van de instellingen voor het markeren van inhoud voor een gevoeligheidslabel](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="278e0-202">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="278e0-203">Klik op **Volgende** om naar het einde van de wizard te gaan en klik vervolgens op **Label opslaan**.</span><span class="sxs-lookup"><span data-stu-id="278e0-203">Click **Next** to reach the end of the wizard, and then click **Save label**.</span></span>

<span data-ttu-id="278e0-204">Als inhoudsmarkering voor het label is ingeschakeld, wordt de tekst die u hebt opgegeven toegevoegd aan Office-documenten wanneer een gebruiker dat label toepast.</span><span class="sxs-lookup"><span data-stu-id="278e0-204">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="278e0-205">Zie ook</span><span class="sxs-lookup"><span data-stu-id="278e0-205">See Also</span></span>

[<span data-ttu-id="278e0-206">Overzicht van gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="278e0-206">Overview of sensitivity labels</span></span>](/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="278e0-207">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="278e0-207">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="278e0-208">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="278e0-208">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)