---
title: Uitzonderingen maken en weergeven voor beveiligingsaanbevelingen - bedreigings- en kwetsbaarheidsbeheer
description: Maak en controleer uitzonderingen voor beveiligingsaanbevelingen in bedreigings- en kwetsbaarheidsbeheer.
keywords: Microsoft Defender for Endpoint tvm remediation, Microsoft Defender for Endpoint tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1af8e5ec9d3aef560c739de5212e8118cf89cd7a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933743"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="cedf7-104">Uitzonderingen maken en weergeven voor beveiligingsaanbevelingen - bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="cedf7-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cedf7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cedf7-105">**Applies to:**</span></span>

- [<span data-ttu-id="cedf7-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="cedf7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cedf7-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="cedf7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cedf7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cedf7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cedf7-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="cedf7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cedf7-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="cedf7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="cedf7-111">Als alternatief voor een herstelaanvraag wanneer een aanbeveling op dit moment niet relevant is, kunt u uitzonderingen maken voor aanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="cedf7-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="cedf7-112">Als uw organisatie apparaatgroepen heeft, kunt u de uitzondering op specifieke apparaatgroepen bereiken.</span><span class="sxs-lookup"><span data-stu-id="cedf7-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="cedf7-113">Uitzonderingen kunnen worden gemaakt voor geselecteerde apparaatgroepen, of voor alle apparaatgroepen van vroeger en nu.</span><span class="sxs-lookup"><span data-stu-id="cedf7-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="cedf7-114">Wanneer een uitzondering wordt gemaakt voor een aanbeveling, is de aanbeveling pas actief na het einde van de duur van de uitzondering.</span><span class="sxs-lookup"><span data-stu-id="cedf7-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="cedf7-115">De aanbevelingstoestand wordt gewijzigd in **Volledige uitzondering** of **Gedeeltelijke uitzondering** (per apparaatgroep).</span><span class="sxs-lookup"><span data-stu-id="cedf7-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="cedf7-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="cedf7-116">Permissions</span></span>

<span data-ttu-id="cedf7-117">Alleen gebruikers met machtigingen voor het verwerken van uitzonderingen kunnen uitzonderingen beheren (waaronder het maken of annuleren).</span><span class="sxs-lookup"><span data-stu-id="cedf7-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="cedf7-118">[Meer informatie over RBAC-rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cedf7-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Weergave van machtigingen voor het afhandelen van uitzonderingen.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="cedf7-120">Een uitzondering maken</span><span class="sxs-lookup"><span data-stu-id="cedf7-120">Create an exception</span></span>

<span data-ttu-id="cedf7-121">Selecteer een beveiligingsaanbeveling voor wie u een uitzondering wilt maken en selecteer vervolgens **Opties** voor uitzondering en vul het formulier in.</span><span class="sxs-lookup"><span data-stu-id="cedf7-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Hier wordt weergegeven waar de knop voor 'uitzonderingsopties' zich bevindt in een flyout voor beveiligingsaanbeveling.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="cedf7-123">Uitzondering per apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="cedf7-123">Exception by device group</span></span>

<span data-ttu-id="cedf7-124">Pas de uitzondering toe op alle huidige apparaatgroepen of kies specifieke apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="cedf7-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="cedf7-125">Toekomstige apparaatgroepen worden niet opgenomen in de uitzondering.</span><span class="sxs-lookup"><span data-stu-id="cedf7-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="cedf7-126">Apparaatgroepen die al een uitzondering hebben, worden niet weergegeven in de lijst.</span><span class="sxs-lookup"><span data-stu-id="cedf7-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="cedf7-127">Als u alleen bepaalde apparaatgroepen selecteert, verandert de aanbevelingstoestand van 'actief' in 'gedeeltelijke uitzondering'.</span><span class="sxs-lookup"><span data-stu-id="cedf7-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="cedf7-128">De status wordt gewijzigd in 'volledige uitzondering' als u alle apparaatgroepen selecteert.</span><span class="sxs-lookup"><span data-stu-id="cedf7-128">The state will change to “full exception” if you select all the device groups.</span></span>

![De vervolgkeuzekeuze van de apparaatgroep weergeven.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="cedf7-130">Gefilterde weergaven</span><span class="sxs-lookup"><span data-stu-id="cedf7-130">Filtered views</span></span>

<span data-ttu-id="cedf7-131">Als u op een van de pagina's voor bedreigings- en kwetsbaarheidsbeheer op apparaatgroep hebt gefilterd, worden alleen de gefilterde apparaatgroepen weergegeven als opties.</span><span class="sxs-lookup"><span data-stu-id="cedf7-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="cedf7-132">Dit is de knop om te filteren op apparaatgroep op een van de pagina's voor bedreigings- en kwetsbaarheidsbeheer:</span><span class="sxs-lookup"><span data-stu-id="cedf7-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Filter geselecteerde apparaatgroepen weergeven.](images/tvm-selected-device-groups.png)

<span data-ttu-id="cedf7-134">Uitzonderingsweergave met gefilterde apparaatgroepen:</span><span class="sxs-lookup"><span data-stu-id="cedf7-134">Exception view with filtered device groups:</span></span>

![De vervolgkeuzekeuze van de gefilterde apparaatgroep weergeven.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="cedf7-136">Groot aantal apparaatgroepen</span><span class="sxs-lookup"><span data-stu-id="cedf7-136">Large number of device groups</span></span>

<span data-ttu-id="cedf7-137">Als uw organisatie meer dan 20 apparaatgroepen heeft, **selecteert** u Bewerken naast de optie gefilterde apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="cedf7-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Hier wordt weergegeven hoe u grote aantallen groepen bewerkt.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="cedf7-139">Er wordt een flyout weergegeven waarin u apparaatgroepen kunt zoeken en kiezen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cedf7-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="cedf7-140">Selecteer het vinkje onder Zoeken om alles te controleren/uit te checken.</span><span class="sxs-lookup"><span data-stu-id="cedf7-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Flyout voor grote apparatengroep weergeven.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="cedf7-142">Globale uitzonderingen</span><span class="sxs-lookup"><span data-stu-id="cedf7-142">Global exceptions</span></span>

<span data-ttu-id="cedf7-143">Als u globale beheerdersmachtigingen hebt, kunt u een globale uitzondering maken en annuleren.</span><span class="sxs-lookup"><span data-stu-id="cedf7-143">If you have global administrator permissions, you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="cedf7-144">Dit is van **invloed op** alle huidige en toekomstige apparaatgroepen in uw organisatie, en alleen een gebruiker met vergelijkbare machtigingen kan deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cedf7-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="cedf7-145">De aanbevelingstoestand verandert van 'actief' in 'volledige uitzondering'.</span><span class="sxs-lookup"><span data-stu-id="cedf7-145">The recommendation state will change from “active” to “full exception.”</span></span>

![De optie Globale uitzondering weergeven.](images/tvm-exception-global.png)

<span data-ttu-id="cedf7-147">Enkele dingen waar u rekening mee moet houden:</span><span class="sxs-lookup"><span data-stu-id="cedf7-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="cedf7-148">Als een aanbeveling een globale uitzondering is, worden nieuwe uitzonderingen voor apparaatgroepen opgeschort totdat de algemene uitzondering is verlopen of geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="cedf7-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="cedf7-149">Daarna worden de uitzonderingen voor de nieuwe apparaatgroep van kracht totdat ze verlopen.</span><span class="sxs-lookup"><span data-stu-id="cedf7-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="cedf7-150">Als een aanbeveling al uitzonderingen voor specifieke apparaatgroepen heeft en er een algemene uitzondering wordt gemaakt, wordt de uitzondering voor de apparaatgroep opgeschort totdat deze verloopt of wordt de globale uitzondering geannuleerd voordat deze verloopt.</span><span class="sxs-lookup"><span data-stu-id="cedf7-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="cedf7-151">Uitvulling</span><span class="sxs-lookup"><span data-stu-id="cedf7-151">Justification</span></span>

<span data-ttu-id="cedf7-152">Selecteer uw rechtvaardiging voor de uitzondering die u moet indienen in plaats van de beveiligingsaanbeveling in kwestie te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="cedf7-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="cedf7-153">Vul de uitvullingscontext in en stel de duur van de uitzondering in.</span><span class="sxs-lookup"><span data-stu-id="cedf7-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="cedf7-154">In de volgende lijst worden de argumenten achter de uitzonderingsopties begegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="cedf7-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="cedf7-155">**Controle door derden** - Een product of software van derden heeft al een adres voor deze aanbeveling- Als u dit type uitvulling kiest, wordt uw blootstellingsscore lager en verhoogt u uw veilige score omdat uw risico is beperkt</span><span class="sxs-lookup"><span data-stu-id="cedf7-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="cedf7-156">**Alternatieve mitigatie** - Een intern hulpmiddel heeft al een oplossing voor deze aanbeveling: als u dit type rechtvaardiging kiest, wordt uw blootstellingsscore lager en verhoogt u de veilige score omdat uw risico is beperkt</span><span class="sxs-lookup"><span data-stu-id="cedf7-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="cedf7-157">**Risico geaccepteerd:** een laag risico en/of het implementeren van de aanbeveling is te duur</span><span class="sxs-lookup"><span data-stu-id="cedf7-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="cedf7-158">**Geplande herstel (respijt)** - Al gepland, maar wacht op uitvoering of autorisatie</span><span class="sxs-lookup"><span data-stu-id="cedf7-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="cedf7-159">Alle uitzonderingen weergeven</span><span class="sxs-lookup"><span data-stu-id="cedf7-159">View all exceptions</span></span>

<span data-ttu-id="cedf7-160">Ga naar het **tabblad Uitzonderingen** op **de pagina** Herstel.</span><span class="sxs-lookup"><span data-stu-id="cedf7-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="cedf7-161">U kunt filteren op uitvulling, type en status.</span><span class="sxs-lookup"><span data-stu-id="cedf7-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="cedf7-162">Selecteer een uitzondering om een flyout te openen met meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cedf7-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="cedf7-163">Uitzonderingen per apparatengroep hebben een lijst met elke apparaatgroep die de uitzonderingsdekking heeft, die u kunt exporteren.</span><span class="sxs-lookup"><span data-stu-id="cedf7-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="cedf7-164">U kunt ook de gerelateerde aanbeveling bekijken of de uitzondering annuleren.</span><span class="sxs-lookup"><span data-stu-id="cedf7-164">You can also view the related recommendation or cancel the exception.</span></span>

![Het tabblad Uitzonderingen weergeven op de pagina Herstel.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="cedf7-166">Een uitzondering annuleren</span><span class="sxs-lookup"><span data-stu-id="cedf7-166">How to cancel an exception</span></span>

<span data-ttu-id="cedf7-167">Als u een uitzondering wilt annuleren, gaat u naar het tabblad **Uitzonderingen** op de **pagina** Herstel.</span><span class="sxs-lookup"><span data-stu-id="cedf7-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="cedf7-168">Selecteer de uitzondering.</span><span class="sxs-lookup"><span data-stu-id="cedf7-168">Select the exception.</span></span>

<span data-ttu-id="cedf7-169">Als u de uitzondering voor alle apparaatgroepen of voor een algemene uitzondering wilt annuleren, selecteert u de knop Uitzondering **annuleren voor alle apparaatgroepen.**</span><span class="sxs-lookup"><span data-stu-id="cedf7-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="cedf7-170">U kunt alleen uitzonderingen annuleren voor apparaatgroepen waar u machtigingen voor hebt.</span><span class="sxs-lookup"><span data-stu-id="cedf7-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![De knop Annuleren.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="cedf7-172">De uitzondering voor een specifieke apparaatgroep annuleren</span><span class="sxs-lookup"><span data-stu-id="cedf7-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="cedf7-173">Selecteer de specifieke apparaatgroep om de uitzondering te annuleren.</span><span class="sxs-lookup"><span data-stu-id="cedf7-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="cedf7-174">Er wordt een flyout weergegeven voor de apparaatgroep en u kunt **Uitzondering annuleren selecteren.**</span><span class="sxs-lookup"><span data-stu-id="cedf7-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Hier wordt weergegeven hoe u een specifieke apparaatgroep selecteert.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="cedf7-176">Impact weergeven nadat uitzonderingen zijn toegepast</span><span class="sxs-lookup"><span data-stu-id="cedf7-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="cedf7-177">Selecteer op de pagina  Beveiligingsaanbevelingen de optie Kolommen aanpassen en schakel de selectievakjes Voor Blootgestelde apparaten **(na uitzonderingen)** en **Impact (na uitzonderingen) in.**</span><span class="sxs-lookup"><span data-stu-id="cedf7-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Opties voor kolommen aanpassen weergeven.](images/tvm-after-exceptions.png)

<span data-ttu-id="cedf7-179">In de kolom Blootgestelde apparaten (na uitzonderingen) worden de overige apparaten getoond die nog steeds aan beveiligingsproblemen worden blootgesteld nadat uitzonderingen zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="cedf7-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="cedf7-180">Uitzonderingsgronden die van invloed zijn op de blootstelling, zijn onder meer 'third party control' en 'alternate mitigation'.</span><span class="sxs-lookup"><span data-stu-id="cedf7-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="cedf7-181">Andere redenen beperken de blootstelling van een apparaat niet en worden nog steeds als blootgesteld beschouwd.</span><span class="sxs-lookup"><span data-stu-id="cedf7-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="cedf7-182">Het effect (na uitzonderingen) toont de resterende invloed op de blootstellingsscore of de veilige score nadat uitzonderingen zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="cedf7-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="cedf7-183">Uitzonderingsuitvullingen die van invloed zijn op de scores zijn 'third party control' en 'alternate mitigation'.</span><span class="sxs-lookup"><span data-stu-id="cedf7-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="cedf7-184">Andere rechtvaardigingen beperken de blootstelling van een apparaat niet, zodat de belichtingsscore en de veilige score niet veranderen.</span><span class="sxs-lookup"><span data-stu-id="cedf7-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![De kolommen in de tabel weergeven.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="cedf7-186">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="cedf7-186">Related topics</span></span>

- [<span data-ttu-id="cedf7-187">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="cedf7-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cedf7-188">Beveiligingsproblemen verhelpen</span><span class="sxs-lookup"><span data-stu-id="cedf7-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="cedf7-189">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="cedf7-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="cedf7-190">Blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="cedf7-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="cedf7-191">Microsoft Secure Score voor apparaten</span><span class="sxs-lookup"><span data-stu-id="cedf7-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
