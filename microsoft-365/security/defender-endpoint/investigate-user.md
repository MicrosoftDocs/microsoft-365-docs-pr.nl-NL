---
title: Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt
description: Onderzoek een gebruikersaccount naar mogelijke gecompromitteerde referenties of draaipunt op het bijbehorende gebruikersaccount tijdens een onderzoek.
keywords: onderzoeken, account, gebruiker, gebruikersentiteit, waarschuwing, Microsoft Defender voor Eindpunt
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935063"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="08a6c-104">Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="08a6c-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08a6c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="08a6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="08a6c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="08a6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="08a6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08a6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="08a6c-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="08a6c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="08a6c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="08a6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="08a6c-110">Entiteiten van gebruikersaccounts onderzoeken</span><span class="sxs-lookup"><span data-stu-id="08a6c-110">Investigate user account entities</span></span>

<span data-ttu-id="08a6c-111">Identificeer gebruikersaccounts met de meest actieve waarschuwingen (weergegeven op het dashboard als 'Gebruikers met risico') en onderzoek gevallen van mogelijke gecompromitteerde referenties, of draai in het bijbehorende gebruikersaccount bij het onderzoeken van een waarschuwing of apparaat om mogelijke zijbewegingen tussen apparaten met dat gebruikersaccount te identificeren.</span><span class="sxs-lookup"><span data-stu-id="08a6c-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="08a6c-112">U kunt gebruikersaccountgegevens vinden in de volgende weergaven:</span><span class="sxs-lookup"><span data-stu-id="08a6c-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="08a6c-113">Dashboard</span><span class="sxs-lookup"><span data-stu-id="08a6c-113">Dashboard</span></span>
- <span data-ttu-id="08a6c-114">Waarschuwingswachtrij</span><span class="sxs-lookup"><span data-stu-id="08a6c-114">Alert queue</span></span>
- <span data-ttu-id="08a6c-115">Pagina Apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="08a6c-115">Device details page</span></span>

<span data-ttu-id="08a6c-116">Er is een klikbare koppeling voor gebruikersaccounts beschikbaar in deze weergaven, die u naar de pagina met gebruikersaccountgegevens gaat waar meer informatie over het gebruikersaccount wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="08a6c-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="08a6c-117">Wanneer u een entiteit van een gebruikersaccount onderzoekt, ziet u:</span><span class="sxs-lookup"><span data-stu-id="08a6c-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="08a6c-118">Gebruikersaccountgegevens, Microsoft Defender voor identiteitswaarschuwingen en aangemeld op apparaten, rol, aanmeldingstype en andere details</span><span class="sxs-lookup"><span data-stu-id="08a6c-118">User account details, Microsoft Defender for Identity alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="08a6c-119">Overzicht van de incidenten en apparaten van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="08a6c-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="08a6c-120">Waarschuwingen met betrekking tot deze gebruiker</span><span class="sxs-lookup"><span data-stu-id="08a6c-120">Alerts related to this user</span></span>
- <span data-ttu-id="08a6c-121">Waargenomen in organisatie (apparaten die zijn aangemeld bij)</span><span class="sxs-lookup"><span data-stu-id="08a6c-121">Observed in organization (devices logged on to)</span></span>

![Afbeelding van de pagina met de details van de gebruikersaccount-entiteit](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="08a6c-123">Gebruikersgegevens</span><span class="sxs-lookup"><span data-stu-id="08a6c-123">User details</span></span>

<span data-ttu-id="08a6c-124">Het  deelvenster Gebruikersdetails aan de linkerkant bevat informatie over de gebruiker, zoals gerelateerde geopende incidenten, actieve waarschuwingen, SAM-naam, SID, Microsoft Defender voor identiteitswaarschuwingen, het aantal apparaten waarop de gebruiker is aangemeld, wanneer de gebruiker voor het eerst en het laatst is gezien, rol en aanmeldingstypen.</span><span class="sxs-lookup"><span data-stu-id="08a6c-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Microsoft Defender for Identity alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="08a6c-125">Afhankelijk van de integratiefuncties die u hebt ingeschakeld, ziet u andere details.</span><span class="sxs-lookup"><span data-stu-id="08a6c-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="08a6c-126">Als u bijvoorbeeld de Skype voor zakelijke integratie inschakelen, kunt u vanuit de portal contact opnemen met de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="08a6c-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="08a6c-127">De **sectie Azure ATP-waarschuwingen** bevat een koppeling die u naar de pagina Microsoft Defender voor identiteit gaat, als u de functie Microsoft Defender voor identiteit hebt ingeschakeld en er waarschuwingen zijn met betrekking tot de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="08a6c-127">The **Azure ATP alerts** section contains a link that will take you to the Microsoft Defender for Identity page, if you have enabled the Microsoft Defender for Identity feature, and there are alerts related to the user.</span></span> <span data-ttu-id="08a6c-128">Op de pagina Microsoft Defender voor identiteit vindt u meer informatie over de waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="08a6c-128">The Microsoft Defender for Identity page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="08a6c-129">U moet de integratie inschakelen op zowel Microsoft Defender voor identiteit als Defender voor Eindpunt om deze functie te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08a6c-129">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="08a6c-130">In Defender voor Eindpunt kunt u deze functie inschakelen in geavanceerde functies.</span><span class="sxs-lookup"><span data-stu-id="08a6c-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="08a6c-131">Zie Geavanceerde functies inschakelen voor meer informatie over het inschakelen van [geavanceerde functies.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="08a6c-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="08a6c-132">Het overzicht, waarschuwingen en waargenomen in organisatie zijn verschillende tabbladen die verschillende kenmerken over het gebruikersaccount weergeven.</span><span class="sxs-lookup"><span data-stu-id="08a6c-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="08a6c-133">Overzicht</span><span class="sxs-lookup"><span data-stu-id="08a6c-133">Overview</span></span>

<span data-ttu-id="08a6c-134">Op **het** tabblad Overzicht ziet u de details van incidenten en een lijst met de apparaten waar de gebruiker zich bij heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="08a6c-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="08a6c-135">U kunt deze uitv vouwen om de details van de logboekgebeurtenissen voor elk apparaat te bekijken.</span><span class="sxs-lookup"><span data-stu-id="08a6c-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="08a6c-136">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="08a6c-136">Alerts</span></span>

<span data-ttu-id="08a6c-137">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn gekoppeld aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="08a6c-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="08a6c-138">Deze lijst is een gefilterde weergave van de waarschuwingswachtrij en toont waarschuwingen waarin de context van de gebruiker het geselecteerde gebruikersaccount is, de datum waarop de laatste activiteit is gedetecteerd, een korte beschrijving van de waarschuwing, het apparaat dat aan de waarschuwing is gekoppeld, de ernst van de waarschuwing, de status van de waarschuwing in de wachtrij en wie de waarschuwing heeft toegewezen. [](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="08a6c-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="08a6c-139">Waargenomen in organisatie</span><span class="sxs-lookup"><span data-stu-id="08a6c-139">Observed in organization</span></span>

<span data-ttu-id="08a6c-140">Op het tabblad Waargenomen **in** organisatie kunt u een datumbereik opgeven om een lijst weer te geven met apparaten waarop deze gebruiker is aangemeld, het meest voorkomende en minst vaak aangemelde gebruikersaccount voor elk van deze apparaten en het totaal aantal waargenomen gebruikers op elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="08a6c-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="08a6c-141">Als u een item selecteert in de tabel Waargenomen in organisatie, wordt het item uitgebreid, met meer informatie over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="08a6c-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="08a6c-142">Als u rechtstreeks een koppeling in een item selecteert, wordt u naar de bijbehorende pagina doorsturen.</span><span class="sxs-lookup"><span data-stu-id="08a6c-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="08a6c-143">Specifieke gebruikersaccounts zoeken</span><span class="sxs-lookup"><span data-stu-id="08a6c-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="08a6c-144">Selecteer **Gebruiker** in de **vervolgkeuzelijst** Zoekbalk.</span><span class="sxs-lookup"><span data-stu-id="08a6c-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="08a6c-145">Voer het gebruikersaccount in het **veld Zoeken** in.</span><span class="sxs-lookup"><span data-stu-id="08a6c-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="08a6c-146">Klik op het zoekpictogram of druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="08a6c-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="08a6c-147">Er wordt een lijst met gebruikers weergegeven die overeenkomen met de querytekst.</span><span class="sxs-lookup"><span data-stu-id="08a6c-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="08a6c-148">U ziet het domein en de naam van het gebruikersaccount, wanneer het gebruikersaccount voor het laatst is gezien, en het totale aantal apparaten waarop het is geregistreerd in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="08a6c-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="08a6c-149">U kunt de resultaten filteren op de volgende tijdsperioden:</span><span class="sxs-lookup"><span data-stu-id="08a6c-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="08a6c-150">1 dag</span><span class="sxs-lookup"><span data-stu-id="08a6c-150">1 day</span></span>
- <span data-ttu-id="08a6c-151">3 dagen</span><span class="sxs-lookup"><span data-stu-id="08a6c-151">3 days</span></span>
- <span data-ttu-id="08a6c-152">7 dagen</span><span class="sxs-lookup"><span data-stu-id="08a6c-152">7 days</span></span>
- <span data-ttu-id="08a6c-153">30 dagen</span><span class="sxs-lookup"><span data-stu-id="08a6c-153">30 days</span></span>
- <span data-ttu-id="08a6c-154">6 maanden</span><span class="sxs-lookup"><span data-stu-id="08a6c-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="08a6c-155">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="08a6c-155">Related topics</span></span>

- [<span data-ttu-id="08a6c-156">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="08a6c-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="08a6c-157">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="08a6c-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="08a6c-158">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="08a6c-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="08a6c-159">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="08a6c-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="08a6c-160">Apparaten onderzoeken in de lijst Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="08a6c-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="08a6c-161">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="08a6c-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="08a6c-162">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="08a6c-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
