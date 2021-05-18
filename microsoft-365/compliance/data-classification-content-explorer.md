---
title: Aan de slag met de inhoudsverkenner
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Met inhoudsverkenner kunt u items met een label standaard weergeven.
ms.openlocfilehash: b39dd09012e7cde6c19ea88a0915154da84c712a
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162949"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="f000e-103">Aan de slag met de inhoudsverkenner</span><span class="sxs-lookup"><span data-stu-id="f000e-103">Get started with content explorer</span></span>

<span data-ttu-id="f000e-104">Met de gegevensclassificatie-inhoudsverkenner kunt u de items die op de overzichtspagina zijn samengevat, standaard bekijken.</span><span class="sxs-lookup"><span data-stu-id="f000e-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![schermopname van inhoudsverkenner samengevouwen](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="f000e-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="f000e-106">Prerequisites</span></span>

<span data-ttu-id="f000e-107">Aan elk account dat toegang krijgt tot en gebruikmaakt van gegevensclassificatie moet een licentie zijn toegewezen vanuit een van deze abonnementen:</span><span class="sxs-lookup"><span data-stu-id="f000e-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="f000e-108">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f000e-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="f000e-109">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f000e-109">Office 365 (E5)</span></span>
- <span data-ttu-id="f000e-110">Geavanceerde hulpprogramma's voor compliance (E5) invoegtoepassing</span><span class="sxs-lookup"><span data-stu-id="f000e-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="f000e-111">Geavanceerde bedreigingsinformatie (E5) invoegtoepassing</span><span class="sxs-lookup"><span data-stu-id="f000e-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="f000e-112">Microsoft 365 E5/A5 Info Protection & Governance</span><span class="sxs-lookup"><span data-stu-id="f000e-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="f000e-113">Microsoft 365 E5/A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="f000e-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="f000e-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="f000e-114">Permissions</span></span>

<span data-ttu-id="f000e-115">Als u toegang wilt krijgen tot het tabblad Inhoudsverkenner, moet aan een account een lidmaatschap zijn toegewezen voor een van deze rollen of rollengroepen.</span><span class="sxs-lookup"><span data-stu-id="f000e-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="f000e-116">**Microsoft 365-rollengroepen**</span><span class="sxs-lookup"><span data-stu-id="f000e-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="f000e-117">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="f000e-117">Global administrator</span></span>
- <span data-ttu-id="f000e-118">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="f000e-118">Compliance administrator</span></span>
- <span data-ttu-id="f000e-119">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="f000e-119">Security administrator</span></span>
- <span data-ttu-id="f000e-120">Beheerder van nalevingsgegevens</span><span class="sxs-lookup"><span data-stu-id="f000e-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f000e-121">Lidmaatschap van deze rollengroepen betekent niet dat u de lijst met items in Inhoudsverkenner of de inhoud van de items in Inhoudsverkenner kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="f000e-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="f000e-122">Vereiste machtigingen voor toegang tot items in Inhoudsverkenner</span><span class="sxs-lookup"><span data-stu-id="f000e-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="f000e-123">Toegang tot Inhoudsverkenner wordt sterk beperkt omdat u hiermee de inhoud van gescande bestanden kunt lezen.</span><span class="sxs-lookup"><span data-stu-id="f000e-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f000e-124">Deze machtigingen bevatten machtigingen die lokaal zijn toegewezen aan de items, zodat de inhoud kan worden bekeken.</span><span class="sxs-lookup"><span data-stu-id="f000e-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="f000e-125">Er zijn twee rollen die toegang verlenen tot Inhoudsverkenner. Deze rollen wordt toegekend via het [Beveiligings- en compliancecentrum van Microsoft](https://protection.office.com/permissions):</span><span class="sxs-lookup"><span data-stu-id="f000e-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="f000e-126">**Inhoudsverkenner lijstweergave**: met lidmaatschap van deze rollengroep kunt u elk item en de locatie in de lijstweergave bekijken.</span><span class="sxs-lookup"><span data-stu-id="f000e-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="f000e-127">De `data classification list viewer`-rol is vooraf toegewezen aan deze rollengroep.</span><span class="sxs-lookup"><span data-stu-id="f000e-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="f000e-128">**Inhoudsverkenner inhoudsweergave**: met lidmaatschap van deze rollengroep kunt u de inhoud van elk item in de lijst bekijken.</span><span class="sxs-lookup"><span data-stu-id="f000e-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="f000e-129">De `data classification content viewer`-rol is vooraf toegewezen aan deze rollengroep.</span><span class="sxs-lookup"><span data-stu-id="f000e-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="f000e-130">Het account dat u gebruikt voor toegang tot Inhoudsverkenner, moet zich in een van de rollengroepen of in beide rollengroepen bevinden.</span><span class="sxs-lookup"><span data-stu-id="f000e-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="f000e-131">Dit zijn onafhankelijke rollengroepen en zijn niet cumulatief.</span><span class="sxs-lookup"><span data-stu-id="f000e-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="f000e-132">Als u bijvoorbeeld een account de mogelijkheid wilt bieden om de items en hun locaties alleen te bekijken, verleent u de viewerrechten voor de Inhoudsverkenner-lijst.</span><span class="sxs-lookup"><span data-stu-id="f000e-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="f000e-133">Als u wilt dat dit account ook de inhoud van de items in de lijst kan bekijken, verleent u inhoudsviewerrechten voor Inhoudsverkenner.</span><span class="sxs-lookup"><span data-stu-id="f000e-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="f000e-134">U kunt een van beide rollen of beide toewijzen aan een aangepaste rollengroep om de toegang tot Inhoudsverkenner aan te passen.</span><span class="sxs-lookup"><span data-stu-id="f000e-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="f000e-135">Een globale beheerder, compliancebeheerder of gegevensbeheerder kan het benodigde lidmaatschap van de Inhoudsverkenner-lijstviewer en inhoudsverkenner voor inhoudsviewer toewijzen.</span><span class="sxs-lookup"><span data-stu-id="f000e-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="f000e-136">Inhoudsverkenner</span><span class="sxs-lookup"><span data-stu-id="f000e-136">Content explorer</span></span>

<span data-ttu-id="f000e-137">Inhoudsverkenner toont een huidige weergave van de items met een vertrouwelijkheidslabel of retentielabel, en items die binnen uw organisatie zijn geclassificeerd als een type gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="f000e-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="f000e-138">Typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="f000e-138">Sensitive information types</span></span>

<span data-ttu-id="f000e-139">Met een [DLP-beleid](dlp-learn-about-dlp.md) wordt gevoelige informatie beschermd, die is gedefinieerd als een **type gevoelige informatie**.</span><span class="sxs-lookup"><span data-stu-id="f000e-139">A [DLP policy](dlp-learn-about-dlp.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="f000e-140">Microsoft 365 bevat [definities voor veelvoorkomende typen gevoelige informatie die](sensitive-information-type-entity-definitions.md) uit veel verschillende regio's die u direct kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f000e-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="f000e-141">Bijvoorbeeld een creditcardnummer, bankrekeningnummers, nationale identiteitsnummers en Windows Live ID-servicenummers.</span><span class="sxs-lookup"><span data-stu-id="f000e-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="f000e-142">Inhoudsverkenner scant momenteel niet op typen vertrouwelijke informatie in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f000e-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="f000e-143">Vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="f000e-143">Sensitivity labels</span></span>

<span data-ttu-id="f000e-144">Een [vertrouwelijkheidslabel](sensitivity-labels.md) is gewoon een label dat de waarde van het item voor uw organisatie aangeeft.</span><span class="sxs-lookup"><span data-stu-id="f000e-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="f000e-145">Dit kan handmatig of automatisch worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="f000e-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="f000e-146">Nadat het is toegepast, wordt dit ingesloten in het document en wordt het overal toegepast.</span><span class="sxs-lookup"><span data-stu-id="f000e-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="f000e-147">Een vertrouwelijkheidslabel biedt diverse beschermingskenmerken, zoals verplicht watermerk of versleuteling.</span><span class="sxs-lookup"><span data-stu-id="f000e-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="f000e-148">Vertrouwelijkheidslabels moeten zijn ingeschakeld voor bestanden in SharePoint en OneDrive, zodat de overeenkomende gegevens op de pagina met de gegevensclassificatie worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f000e-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="f000e-149">Zie [Vertrouwelijkheidslabels inschakelen voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f000e-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="f000e-150">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="f000e-150">Retention labels</span></span>

<span data-ttu-id="f000e-151">Met [bewaarlabel](retention.md) kunt u definiëren hoelang een gelabeld item wordt bewaard en kunt u de stappen definiëren voordat u het verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f000e-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="f000e-152">Ze kunnen handmatig of automatisch worden toegepast via beleid.</span><span class="sxs-lookup"><span data-stu-id="f000e-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="f000e-153">Ze kunnen een rol spelen bij het voldoen aan wettelijke en wettelijke vereisten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f000e-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="f000e-154">Inhoudsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="f000e-154">How to use content explorer</span></span>

1. <span data-ttu-id="f000e-155">Open **Microsoft 365-compliancecentrum**  > **Gegevensclassificatie** > **Inhoudsverkenner**.</span><span class="sxs-lookup"><span data-stu-id="f000e-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="f000e-156">Als u de naam van het label of het type gevoelige informatie weet, kunt u dit typen in het filtervak.</span><span class="sxs-lookup"><span data-stu-id="f000e-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="f000e-157">U kunt ook naar het item bladeren door het labeltype uit te breiden en het label in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f000e-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="f000e-158">Selecteer een locatie onder **Alle locaties** en zoom in op de mapstructuur van het item.</span><span class="sxs-lookup"><span data-stu-id="f000e-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="f000e-159">Dubbelklik om het item te openen in Inhoudsverkenner.</span><span class="sxs-lookup"><span data-stu-id="f000e-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="f000e-160">Exporteren</span><span class="sxs-lookup"><span data-stu-id="f000e-160">Export</span></span>
<span data-ttu-id="f000e-161">Met het besturingselement voor **exporteren** wordt een CSV-bestand met een lijst weergegeven van wat wordt weergegeven in het deelvenster **Alle locaties** openen.</span><span class="sxs-lookup"><span data-stu-id="f000e-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![exportbesturingselement voor gegevensclassificatie](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="f000e-163">Zoeken</span><span class="sxs-lookup"><span data-stu-id="f000e-163">Search</span></span>

<span data-ttu-id="f000e-164">Wanneer u inzoomt op een locatie, zoals een Exchange-map, of een SharePoint- of OneDrive-site, wordt het hulpprogramma **zoeken** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f000e-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![zoekrool voor Inhoudsverkenner](../media/data_classification_search_tool.png)


<span data-ttu-id="f000e-166">Het bereik van de zoektool is wat wordt weergegeven in het deelvenster **Alle locaties** en waar u op kunt zoeken varieert afhankelijk van de geselecteerde locatie.</span><span class="sxs-lookup"><span data-stu-id="f000e-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="f000e-167">Wanneer **Exchange** de geselecteerde locatie is, kunt u zoeken op het volledige e-mailadres van het postvak, bijvoorbeeld `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="f000e-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="f000e-168">Wanneer **SharePoint** of **OneDrive** zijn geselecteerd, wordt de zoektool weergegeven wanneer u inzoomt op sitenamen, mappen en bestanden.</span><span class="sxs-lookup"><span data-stu-id="f000e-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="f000e-169">**OneDrive** Tijdens ons preview-programma hebben we geluisterd naar uw waardevolle feedback over de integratie met OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f000e-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="f000e-170">Op basis van deze feedback blijft de OneDrive-functionaliteit in preview totdat alle problemen zijn opgelost.</span><span class="sxs-lookup"><span data-stu-id="f000e-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="f000e-171">Afhankelijk van uw tenant zien sommige klanten OneDrive mogelijk niet als locatie.</span><span class="sxs-lookup"><span data-stu-id="f000e-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="f000e-172">Wij waarderen uw ondersteuning hierbij.</span><span class="sxs-lookup"><span data-stu-id="f000e-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="f000e-173">U kunt zoeken op:</span><span class="sxs-lookup"><span data-stu-id="f000e-173">You can search on:</span></span>


|<span data-ttu-id="f000e-174">waarde</span><span class="sxs-lookup"><span data-stu-id="f000e-174">value</span></span>|<span data-ttu-id="f000e-175">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="f000e-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="f000e-176">volledige sitenaam</span><span class="sxs-lookup"><span data-stu-id="f000e-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="f000e-177">naam van hoofdmap - alle submappen worden opgeslagen</span><span class="sxs-lookup"><span data-stu-id="f000e-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="f000e-178">Bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="f000e-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="f000e-179">tekst aan het begin van bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="f000e-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="f000e-180">Tekst na een onderstrepingsteken (_) in bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="f000e-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="f000e-181">`Resume` of `1234`</span><span class="sxs-lookup"><span data-stu-id="f000e-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="f000e-182">bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="f000e-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="f000e-183">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f000e-183">See also</span></span>

- [<span data-ttu-id="f000e-184">Meer informatie over vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="f000e-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="f000e-185">Meer informatie over bewaarbeleid en retentielabels</span><span class="sxs-lookup"><span data-stu-id="f000e-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="f000e-186">Definities van entiteiten van het type vertrouwelijke gegevens.md</span><span class="sxs-lookup"><span data-stu-id="f000e-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="f000e-187">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="f000e-187">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)