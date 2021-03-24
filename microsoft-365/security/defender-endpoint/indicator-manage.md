---
title: Indicatoren beheren
ms.reviewer: ''
description: Indicatoren beheren voor een bestandshash, IP-adres, URL's of domeinen die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060114"
---
# <a name="manage-indicators"></a><span data-ttu-id="61f88-104">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="61f88-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="61f88-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="61f88-105">**Applies to:**</span></span>
- [<span data-ttu-id="61f88-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="61f88-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="61f88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61f88-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="61f88-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="61f88-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61f88-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="61f88-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="61f88-110">Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="61f88-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="61f88-111">Selecteer het tabblad van het entiteitstype dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="61f88-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="61f88-112">Werk de details van de indicator bij en klik op **Opslaan** of klik op de knop **Verwijderen** als u de entiteit uit de lijst wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="61f88-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="61f88-113">Een lijst met IocCs importeren</span><span class="sxs-lookup"><span data-stu-id="61f88-113">Import a list of IoCs</span></span>

<span data-ttu-id="61f88-114">U kunt er ook voor kiezen om een CSV-bestand te uploaden dat de kenmerken van indicatoren, de actie die moet worden ondernomen en andere details definieert.</span><span class="sxs-lookup"><span data-stu-id="61f88-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="61f88-115">Download de voorbeeld-CSV om de ondersteunde kolomkenmerken te kennen.</span><span class="sxs-lookup"><span data-stu-id="61f88-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="61f88-116">Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="61f88-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="61f88-117">Selecteer het tabblad van het entiteitstype waar u indicatoren voor wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="61f88-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="61f88-118">Selecteer **Bestand importeren**  >  **kiezen.**</span><span class="sxs-lookup"><span data-stu-id="61f88-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="61f88-119">Selecteer **Importeren.**</span><span class="sxs-lookup"><span data-stu-id="61f88-119">Select **Import**.</span></span> <span data-ttu-id="61f88-120">Doe dit voor alle bestanden die u wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="61f88-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="61f88-121">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="61f88-121">Select **Done**.</span></span>

<span data-ttu-id="61f88-122">In de volgende tabel ziet u de ondersteunde parameters.</span><span class="sxs-lookup"><span data-stu-id="61f88-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="61f88-123">Parameter</span><span class="sxs-lookup"><span data-stu-id="61f88-123">Parameter</span></span> | <span data-ttu-id="61f88-124">Type</span><span class="sxs-lookup"><span data-stu-id="61f88-124">Type</span></span>    |   <span data-ttu-id="61f88-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="61f88-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="61f88-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="61f88-126">indicatorType</span></span> | <span data-ttu-id="61f88-127">Enum</span><span class="sxs-lookup"><span data-stu-id="61f88-127">Enum</span></span> | <span data-ttu-id="61f88-128">Type indicator.</span><span class="sxs-lookup"><span data-stu-id="61f88-128">Type of the indicator.</span></span> <span data-ttu-id="61f88-129">Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url".</span><span class="sxs-lookup"><span data-stu-id="61f88-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="61f88-130">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="61f88-130">**Required**</span></span>
<span data-ttu-id="61f88-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="61f88-131">indicatorValue</span></span> | <span data-ttu-id="61f88-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-132">String</span></span> | <span data-ttu-id="61f88-133">Identiteit van de [entiteit Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="61f88-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="61f88-134">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="61f88-134">**Required**</span></span>
<span data-ttu-id="61f88-135">actie</span><span class="sxs-lookup"><span data-stu-id="61f88-135">action</span></span> | <span data-ttu-id="61f88-136">Enum</span><span class="sxs-lookup"><span data-stu-id="61f88-136">Enum</span></span> | <span data-ttu-id="61f88-137">De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="61f88-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="61f88-138">Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'.</span><span class="sxs-lookup"><span data-stu-id="61f88-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="61f88-139">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="61f88-139">**Required**</span></span>
<span data-ttu-id="61f88-140">titel</span><span class="sxs-lookup"><span data-stu-id="61f88-140">title</span></span> | <span data-ttu-id="61f88-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-141">String</span></span> | <span data-ttu-id="61f88-142">Indicatorwaarschuwingstitel.</span><span class="sxs-lookup"><span data-stu-id="61f88-142">Indicator alert title.</span></span> <span data-ttu-id="61f88-143">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="61f88-143">**Required**</span></span>
<span data-ttu-id="61f88-144">beschrijving</span><span class="sxs-lookup"><span data-stu-id="61f88-144">description</span></span> | <span data-ttu-id="61f88-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-145">String</span></span> |  <span data-ttu-id="61f88-146">Beschrijving van de indicator.</span><span class="sxs-lookup"><span data-stu-id="61f88-146">Description of the indicator.</span></span> <span data-ttu-id="61f88-147">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="61f88-147">**Required**</span></span>
<span data-ttu-id="61f88-148">verlooptijd</span><span class="sxs-lookup"><span data-stu-id="61f88-148">expirationTime</span></span> | <span data-ttu-id="61f88-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="61f88-149">DateTimeOffset</span></span> | <span data-ttu-id="61f88-150">De verlooptijd van de indicator in de volgende notatie YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="61f88-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="61f88-151">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="61f88-151">**Optional**</span></span>
<span data-ttu-id="61f88-152">ernst</span><span class="sxs-lookup"><span data-stu-id="61f88-152">severity</span></span> | <span data-ttu-id="61f88-153">Enum</span><span class="sxs-lookup"><span data-stu-id="61f88-153">Enum</span></span> | <span data-ttu-id="61f88-154">De ernst van de indicator.</span><span class="sxs-lookup"><span data-stu-id="61f88-154">The severity of the indicator.</span></span> <span data-ttu-id="61f88-155">Mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="61f88-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="61f88-156">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="61f88-156">**Optional**</span></span>
<span data-ttu-id="61f88-157">aanbevolenActie</span><span class="sxs-lookup"><span data-stu-id="61f88-157">recommendedActions</span></span> | <span data-ttu-id="61f88-158">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-158">String</span></span> | <span data-ttu-id="61f88-159">Aanbevolen acties voor ti-indicatorwaarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="61f88-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="61f88-160">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="61f88-160">**Optional**</span></span>
<span data-ttu-id="61f88-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="61f88-161">rbacGroupNames</span></span> | <span data-ttu-id="61f88-162">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-162">String</span></span> | <span data-ttu-id="61f88-163">Door komma's gescheiden lijst met RBAC-groepsnamen waar de indicator op zou worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="61f88-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="61f88-164">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="61f88-164">**Optional**</span></span>
<span data-ttu-id="61f88-165">categorie</span><span class="sxs-lookup"><span data-stu-id="61f88-165">category</span></span> | <span data-ttu-id="61f88-166">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-166">String</span></span> | <span data-ttu-id="61f88-167">Categorie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="61f88-167">Category of the alert.</span></span> <span data-ttu-id="61f88-168">Voorbeelden hiervan zijn: Uitvoering en toegang tot referenties.</span><span class="sxs-lookup"><span data-stu-id="61f88-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="61f88-169">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="61f88-169">**Optional**</span></span>
<span data-ttu-id="61f88-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="61f88-170">mitretechniques</span></span>| <span data-ttu-id="61f88-171">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="61f88-171">String</span></span> | <span data-ttu-id="61f88-172">MITRE-technieken code/id (door komma's gescheiden).</span><span class="sxs-lookup"><span data-stu-id="61f88-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="61f88-173">Zie Ondernemingstactieken [voor meer informatie.](https://attack.mitre.org/tactics/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="61f88-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="61f88-174">**Optioneel** Het wordt aanbevolen om een waarde toe te voegen aan een categorie wanneer een MITRE-techniek wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="61f88-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="61f88-175">Zie Waarschuwingscategorieën van Microsoft Defender voor eindpunten zijn nu uitgelijnd met [MITRE ATT-&CK! voor](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="61f88-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="61f88-176">Zie ook</span><span class="sxs-lookup"><span data-stu-id="61f88-176">See also</span></span>
- [<span data-ttu-id="61f88-177">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="61f88-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="61f88-178">Indicatoren voor bestanden maken</span><span class="sxs-lookup"><span data-stu-id="61f88-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="61f88-179">Indicatoren maken voor IPs en URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="61f88-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="61f88-180">Indicatoren maken op basis van certificaten</span><span class="sxs-lookup"><span data-stu-id="61f88-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
