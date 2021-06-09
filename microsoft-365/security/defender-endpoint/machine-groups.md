---
title: Apparaatgroepen maken en beheren in Microsoft Defender voor Eindpunt
description: Maak apparaatgroepen en stel geautomatiseerde herstelniveaus in door de regels te bevestigen die van toepassing zijn op de groep
keywords: apparaatgroepen, groepen, herstel, niveau, regels, aadgroep, rol, toewijzen, rang
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d4f62acde4e7d790c7a7c8635f51c99f0823687d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842768"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="a3e87-104">Apparaatgroepen maken en beheren</span><span class="sxs-lookup"><span data-stu-id="a3e87-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a3e87-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a3e87-105">**Applies to:**</span></span>
- <span data-ttu-id="a3e87-106">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a3e87-106">Azure Active Directory</span></span>
- <span data-ttu-id="a3e87-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="a3e87-107">Office 365</span></span>

> <span data-ttu-id="a3e87-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a3e87-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a3e87-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a3e87-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a3e87-110">In een ondernemingsscenario krijgen beveiligingsbewerkingsteams meestal een set apparaten toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="a3e87-111">Deze apparaten worden gegroepeerd op basis van een set kenmerken, zoals hun domeinen, computernamen of aangewezen tags.</span><span class="sxs-lookup"><span data-stu-id="a3e87-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="a3e87-112">In Microsoft Defender voor Eindpunt kunt u apparaatgroepen maken en deze gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="a3e87-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="a3e87-113">Toegang tot gerelateerde waarschuwingen en gegevens beperken tot specifieke Azure AD-gebruikersgroepen [met toegewezen RBAC-rollen](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="a3e87-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="a3e87-114">Verschillende instellingen voor automatisch herstel configureren voor verschillende sets apparaten</span><span class="sxs-lookup"><span data-stu-id="a3e87-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="a3e87-115">Specifieke herstelniveaus toewijzen die moeten worden toegepast tijdens geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a3e87-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="a3e87-116">Filter in een onderzoek de lijst **Apparaten** op specifieke apparaatgroepen met behulp van het **filter** Groeperen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-116">In an investigation, filter the **Devices list** to specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="a3e87-117">U kunt apparaatgroepen maken in de context van op rollen gebaseerde toegang (RBAC) om te bepalen wie specifieke actie kan ondernemen of informatie kan bekijken door de apparaatgroep(s) toe te wijzen aan een gebruikersgroep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="a3e87-118">Zie Portaltoegang beheren met behulp van op rollen [gebaseerd toegangsbeheer voor meer informatie.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="a3e87-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="a3e87-119">Lees voor een uitgebreid overzicht van de toepassing RBAC: [Is uw SOC plat met RBAC.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="a3e87-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="a3e87-120">Als onderdeel van het proces voor het maken van een apparaatgroep, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="a3e87-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="a3e87-121">Stel het geautomatiseerde herstelniveau voor die groep in.</span><span class="sxs-lookup"><span data-stu-id="a3e87-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="a3e87-122">Zie Geautomatiseerde onderzoeken gebruiken om bedreigingen te onderzoeken en te corrigeren voor meer informatie over [herstelniveaus.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="a3e87-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="a3e87-123">Geef de overeenkomende regel op waarmee wordt bepaald welke apparaatgroep tot de groep behoort op basis van de apparaatnaam, het domein, de tags en het besturingssysteemplatform.</span><span class="sxs-lookup"><span data-stu-id="a3e87-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="a3e87-124">Als een apparaat ook is afgestemd op andere groepen, wordt het alleen toegevoegd aan de hoogst gerangschikte apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-124">If a device is also matched to other groups, it's added only to the highest ranked device group.</span></span>
- <span data-ttu-id="a3e87-125">Selecteer de Azure AD-gebruikersgroep die toegang moet hebben tot de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="a3e87-126">Rangschik de apparaatgroep ten opzichte van andere groepen nadat deze is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a3e87-126">Rank the device group relative to other groups after it's created.</span></span>

>[!NOTE]
><span data-ttu-id="a3e87-127">Een apparaatgroep is toegankelijk voor alle gebruikers als u er geen Azure AD-groepen aan toewijst.</span><span class="sxs-lookup"><span data-stu-id="a3e87-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="a3e87-128">Een apparaatgroep maken</span><span class="sxs-lookup"><span data-stu-id="a3e87-128">Create a device group</span></span>

1. <span data-ttu-id="a3e87-129">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Apparaatgroepen.**</span><span class="sxs-lookup"><span data-stu-id="a3e87-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="a3e87-130">Klik **op Apparaatgroep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a3e87-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="a3e87-131">Voer de groepsnaam- en automatiseringsinstellingen in en geef de overeenkomende regel op die bepaalt welke apparaten tot de groep behoren.</span><span class="sxs-lookup"><span data-stu-id="a3e87-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="a3e87-132">Zie [Hoe het geautomatiseerde onderzoek wordt gestart.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="a3e87-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="a3e87-133">Als u apparaten per organisatie-eenheid wilt groeperen, kunt u de registersleutel configureren voor de groep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="a3e87-134">Zie Apparaatlabels maken en beheren voor meer informatie over [apparaatlabels.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="a3e87-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="a3e87-135">Bekijk een voorbeeld van verschillende apparaten die door deze regel worden gematcht.</span><span class="sxs-lookup"><span data-stu-id="a3e87-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="a3e87-136">Als u tevreden bent over de regel, klikt u op **het tabblad Gebruikerstoegang.**</span><span class="sxs-lookup"><span data-stu-id="a3e87-136">If you're satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="a3e87-137">Wijs de gebruikersgroepen toe die toegang hebben tot de apparaatgroep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a3e87-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a3e87-138">U kunt alleen toegang verlenen tot Azure AD-gebruikersgroepen die zijn toegewezen aan RBAC-rollen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="a3e87-139">Klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a3e87-139">Click **Close**.</span></span> <span data-ttu-id="a3e87-140">De configuratiewijzigingen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="a3e87-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="a3e87-141">Apparaatgroepen beheren</span><span class="sxs-lookup"><span data-stu-id="a3e87-141">Manage device groups</span></span>

<span data-ttu-id="a3e87-142">U kunt de rang van een apparaatgroep promoten of verlagen, zodat deze hogere of lagere prioriteit krijgt tijdens het koppelen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-142">You can promote or demote the rank of a device group so that it's given higher or lower priority during matching.</span></span> <span data-ttu-id="a3e87-143">Wanneer een apparaat is afgestemd op meer dan één groep, wordt het alleen toegevoegd aan de hoogst gerangschikte groep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-143">When a device is matched to more than one group, it's added only to the highest ranked group.</span></span> <span data-ttu-id="a3e87-144">U kunt ook groepen bewerken en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-144">You can also edit and delete groups.</span></span>



>[!WARNING]
><span data-ttu-id="a3e87-145">Het verwijderen van een apparaatgroep kan van invloed zijn op regels voor e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="a3e87-146">Als een apparaatgroep is geconfigureerd onder een meldingsregel voor e-mail, wordt deze uit die regel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3e87-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="a3e87-147">Als de apparaatgroep de enige groep is die is geconfigureerd voor een e-mailmelding, wordt deze regel voor e-mailmeldingen samen met de apparaatgroep verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3e87-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="a3e87-148">Apparaatgroepen zijn standaard toegankelijk voor alle gebruikers met portaltoegang.</span><span class="sxs-lookup"><span data-stu-id="a3e87-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="a3e87-149">U kunt het standaardgedrag wijzigen door Azure AD-gebruikersgroepen toe te wijzen aan de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="a3e87-150">Apparaten die niet zijn afgestemd op groepen, worden toegevoegd aan groep Niet-gegroepeerde apparaten (standaard).</span><span class="sxs-lookup"><span data-stu-id="a3e87-150">Devices that aren't matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="a3e87-151">U kunt de rang van deze groep niet wijzigen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="a3e87-152">U kunt echter het herstelniveau van deze groep wijzigen en de Azure AD-gebruikersgroepen definiëren die toegang hebben tot deze groep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="a3e87-153">Het kan enkele minuten duren voordat wijzigingen worden toegepast op de configuratie van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-153">Applying changes to device group configuration may take up to several minutes.</span></span>


### <a name="add-device-group-definitions"></a><span data-ttu-id="a3e87-154">Apparaatgroepsdefinities toevoegen</span><span class="sxs-lookup"><span data-stu-id="a3e87-154">Add device group definitions</span></span>
<span data-ttu-id="a3e87-155">Apparaatgroepdefinities kunnen ook meerdere waarden voor elke voorwaarde bevatten.</span><span class="sxs-lookup"><span data-stu-id="a3e87-155">Device group definitions can also include multiple values for each condition.</span></span> <span data-ttu-id="a3e87-156">U kunt meerdere tags, apparaatnamen en domeinen instellen op de definitie van één apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="a3e87-156">You can set multiple tags, device names, and domains to the definition of a single device group.</span></span>

1. <span data-ttu-id="a3e87-157">Maak een nieuwe apparaatgroep en selecteer vervolgens **het tabblad** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="a3e87-157">Create a new device group, then select **Devices** tab.</span></span>
2. <span data-ttu-id="a3e87-158">Voeg de eerste waarde toe voor een van de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="a3e87-158">Add the first value for one of the conditions.</span></span>
3. <span data-ttu-id="a3e87-159">Selecteer `+` om meer rijen van hetzelfde eigenschapstype toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="a3e87-159">Select `+` to add more rows of the same property type.</span></span>

>[!TIP]
> <span data-ttu-id="a3e87-160">Gebruik de operator 'OF' tussen rijen van hetzelfde voorwaardetype, waarmee meerdere waarden per eigenschap kunnen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a3e87-160">Use the 'OR' operator between rows of the same condition type, which allows multiple values per property.</span></span>
> <span data-ttu-id="a3e87-161">U kunt maximaal 10 rijen (waarden) toevoegen voor elk eigenschapstype- tag, apparaatnaam, domein.</span><span class="sxs-lookup"><span data-stu-id="a3e87-161">You can add up to 10 rows (values) for each property type - tag, device name, domain.</span></span>

<span data-ttu-id="a3e87-162">Zie Apparaatgroepen - Microsoft 365 beveiliging voor meer informatie over het koppelen [aan definities van apparaatgroepen.](https://sip.security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="a3e87-162">For more information on linking to device groups definitions, see [Device groups - Microsoft 365 security](https://sip.security.microsoft.com/homepage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3e87-163">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a3e87-163">Related topics</span></span>

- [<span data-ttu-id="a3e87-164">Portaltoegang beheren met behulp van op rollen gebaseerd toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="a3e87-164">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="a3e87-165">Apparaattags maken en beheren</span><span class="sxs-lookup"><span data-stu-id="a3e87-165">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="a3e87-166">Lijst met tenantapparaatgroepen met behulp van Graph API</span><span class="sxs-lookup"><span data-stu-id="a3e87-166">Get list of tenant device groups using Graph API</span></span>](/graph/api/device-list-memberof)
