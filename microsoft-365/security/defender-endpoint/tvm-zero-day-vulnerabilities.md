---
title: Zero-day-beveiligingslekken beperken - bedreigings- en kwetsbaarheidsbeheer
description: Meer informatie over het vinden en beperken van zero-day-beveiligingslekken in uw omgeving via bedreigings- en kwetsbaarheidsbeheer.
keywords: mdatp tvm zero day vulnerabilities, tvm, threat & vulnerability management, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b2092f24e4ee3e35918fbdc54b68570ef29fd08e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060466"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="8c3b8-104">Zero-day-beveiligingslekken beperken - bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c3b8-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c3b8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8c3b8-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c3b8-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="8c3b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8c3b8-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c3b8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8c3b8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c3b8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8c3b8-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8c3b8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c3b8-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="8c3b8-111">Een zero-day-kwetsbaarheid is een openbaar openbaar gemaakt beveiligingsprobleem waarvoor geen officiële patches of beveiligingsupdates zijn uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="8c3b8-112">Zero-day-beveiligingslekken hebben vaak hoge ernstniveaus en worden actief benut.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="8c3b8-113">Bedreigings- en kwetsbaarheidsbeheer geeft alleen zero-day-beveiligingslekken weer waar het informatie over heeft.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="8c3b8-114">Informatie over zero-day-beveiligingslekken zoeken</span><span class="sxs-lookup"><span data-stu-id="8c3b8-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="8c3b8-115">Wanneer er een zero-day-kwetsbaarheid is gevonden, wordt informatie over het probleem overgebracht via de volgende ervaringen in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="8c3b8-116">Dashboard Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c3b8-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="8c3b8-117">Zoek naar aanbevelingen met een zero-day tag in de kaart 'Top security recommendations'.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Topaanbevelingen met een zero-day-tag.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="8c3b8-119">Zoek de beste software met de zero-day tag in de kaart 'Top vulnerable software'.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Top kwetsbaar software met een zero-day tag.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="8c3b8-121">Pagina Zwakke punten</span><span class="sxs-lookup"><span data-stu-id="8c3b8-121">Weaknesses page</span></span>

<span data-ttu-id="8c3b8-122">Zoek naar het benoemde zero-day-beveiligingsprobleem, samen met een beschrijving en details.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="8c3b8-123">Als aan dit beveiligingsprobleem een CVE-ID is toegewezen, ziet u het zero-day label naast de CVE-naam.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="8c3b8-124">Als aan dit beveiligingsprobleem geen CVE-ID is toegewezen, vindt u deze onder een interne, tijdelijke naam die eruitziet als 'TVM-XXXX-XXXX'.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="8c3b8-125">De naam wordt bijgewerkt zodra een officiële CVE-ID is toegewezen, maar de vorige interne naam kan nog steeds worden doorzocht en in het zijpaneel worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Zero day example for CVE-2020-17087 in weaknesses page.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="8c3b8-127">Pagina Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="8c3b8-127">Software inventory page</span></span>

<span data-ttu-id="8c3b8-128">Zoek naar software met de zero-day tag.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="8c3b8-129">Filter op de tag 'zero day' om alleen software te zien met zero-day-beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 in the software inventory page.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="8c3b8-131">Softwarepagina</span><span class="sxs-lookup"><span data-stu-id="8c3b8-131">Software page</span></span>

<span data-ttu-id="8c3b8-132">Zoek naar een zero-day-tag voor elke software die is beïnvloed door het zero-day-beveiligingsprobleem.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Voorbeeld van nul dagen voor de softwarepagina van Windows Server 2016.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="8c3b8-134">Pagina Met beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="8c3b8-134">Security recommendations page</span></span>

<span data-ttu-id="8c3b8-135">Bekijk duidelijke suggesties over herstel- en mitigatieopties, inclusief tijdelijke oplossingen als deze bestaan.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="8c3b8-136">Filter op de tag 'zero day' om alleen beveiligingsaanbevelingen te zien voor het oplossen van zero-day-beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="8c3b8-137">Als er software is met een zero-day-kwetsbaarheid en extra beveiligingslekken, krijgt u één aanbeveling over alle beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 in the security recommendations page.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="8c3b8-139">Zero-day-beveiligingslekken oplossen</span><span class="sxs-lookup"><span data-stu-id="8c3b8-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="8c3b8-140">Ga naar de pagina met beveiligingsaanbevelingen en selecteer een aanbeveling met een nuldag.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="8c3b8-141">Er wordt een flyout geopend met informatie over de zero-day en andere beveiligingslekken voor die software.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="8c3b8-142">Er wordt een koppeling gemaakt naar opties voor beperking en tijdelijke oplossingen als deze beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="8c3b8-143">Tijdelijke oplossingen kunnen het risico van dit zero-day-beveiligingsprobleem beperken totdat een patch of beveiligingsupdate kan worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="8c3b8-144">Open herstelopties en kies het type aandacht.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="8c3b8-145">Een 'aandacht vereist' hersteloptie wordt aanbevolen voor de zero-day-beveiligingslekken, omdat er nog geen update is uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="8c3b8-146">U kunt geen einddatum selecteren, omdat er geen specifieke actie moet worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="8c3b8-147">Als er oudere beveiligingsproblemen zijn voor deze software die u wilt herstellen, kunt u de hersteloptie 'aandacht vereist' overschrijven en 'bijwerken' kiezen.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Zero day flyout example of Windows Server 2016 in the security recommendations page.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="8c3b8-149">Herstelactiviteiten van nul dagen bijhouden</span><span class="sxs-lookup"><span data-stu-id="8c3b8-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="8c3b8-150">Ga naar de pagina Herstel van bedreigings- en [kwetsbaarheidsbeheer](tvm-remediation.md) om het item herstelactiviteit weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="8c3b8-151">Als u de optie 'aandacht vereist' kiest, is er geen voortgangsbalk, ticketstatus of einddatum omdat er geen werkelijke actie is die we kunnen controleren.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="8c3b8-152">U kunt filteren op hersteltype, zoals 'software-update' of 'aandacht vereist', om alle activiteitenitems in dezelfde categorie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="8c3b8-153">Beveiligingslekken van nul dagen verhelpen</span><span class="sxs-lookup"><span data-stu-id="8c3b8-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="8c3b8-154">Wanneer er een patch wordt uitgebracht voor de zero-day, wordt de aanbeveling gewijzigd in 'Update' en een blauw label er naast met de naam 'Nieuwe beveiligingsupdate voor nuldag'.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="8c3b8-155">Het wordt niet langer gezien als een zero-day-tag, de zero-day tag wordt van alle pagina's verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8c3b8-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Aanbeveling voor 'Microsoft Windows 10 bijwerken' met een nieuw patchlabel.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="8c3b8-157">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="8c3b8-157">Related articles</span></span>

- [<span data-ttu-id="8c3b8-158">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c3b8-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8c3b8-159">Dashboard</span><span class="sxs-lookup"><span data-stu-id="8c3b8-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="8c3b8-160">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="8c3b8-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="8c3b8-161">Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="8c3b8-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="8c3b8-162">Beveiligingslekken in mijn organisatie</span><span class="sxs-lookup"><span data-stu-id="8c3b8-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
