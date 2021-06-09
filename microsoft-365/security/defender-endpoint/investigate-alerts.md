---
title: Microsoft Defender onderzoeken voor eindpuntwaarschuwingen
description: Gebruik de onderzoeksopties om details te krijgen over waarschuwingen die van invloed zijn op uw netwerk, wat ze betekenen en hoe u deze kunt oplossen.
keywords: onderzoeken, onderzoeken, apparaten, apparaat, waarschuwingenwachtrij, dashboard, IP-adres, bestand, indienen, inzendingen, diepgaande analyse, tijdlijn, zoeken, domein, URL, IP
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
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841088"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6aa44-104">Waarschuwingen onderzoeken in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6aa44-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6aa44-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6aa44-105">**Applies to:**</span></span>
- [<span data-ttu-id="6aa44-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6aa44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6aa44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6aa44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6aa44-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6aa44-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6aa44-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6aa44-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="6aa44-110">Onderzoek waarschuwingen die van invloed zijn op uw netwerk, begrijpen wat ze betekenen en hoe u deze kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="6aa44-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="6aa44-111">Selecteer een waarschuwing in de waarschuwingenwachtrij om naar de waarschuwingspagina te gaan.</span><span class="sxs-lookup"><span data-stu-id="6aa44-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="6aa44-112">Deze weergave bevat de waarschuwingstitel, de betreffende assets, het detail zijvenster en het waarschuwingsverhaal.</span><span class="sxs-lookup"><span data-stu-id="6aa44-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="6aa44-113">Start uw onderzoek op de waarschuwingspagina door de betreffende activa of een van de entiteiten te selecteren onder de weergave van de waarschuwingsverhaalstructuur.</span><span class="sxs-lookup"><span data-stu-id="6aa44-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="6aa44-114">Het detailvenster wordt automatisch gevuld met meer informatie over wat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6aa44-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="6aa44-115">Als u wilt zien wat voor soort informatie u hier kunt bekijken, leest u [Waarschuwingen controleren in Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/review-alerts)</span><span class="sxs-lookup"><span data-stu-id="6aa44-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="6aa44-116">Onderzoeken met behulp van het waarschuwingsverhaal</span><span class="sxs-lookup"><span data-stu-id="6aa44-116">Investigate using the alert story</span></span>

<span data-ttu-id="6aa44-117">Het waarschuwingsverhaal geeft aan waarom de waarschuwing is geactiveerd, gerelateerde gebeurtenissen die vóór en na zijn gebeurd, evenals andere gerelateerde entiteiten.</span><span class="sxs-lookup"><span data-stu-id="6aa44-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="6aa44-118">Entiteiten kunnen worden geklikt en elke entiteit die geen waarschuwing is, kan worden uitvuwbaar met behulp van het uitvuwpictogram aan de rechterkant van de kaart van die entiteit.</span><span class="sxs-lookup"><span data-stu-id="6aa44-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="6aa44-119">De entiteit in focus wordt aangegeven met een blauwe streep aan de linkerkant van de kaart van die entiteit, met de waarschuwing in de titel die in eerste instantie de focus heeft.</span><span class="sxs-lookup"><span data-stu-id="6aa44-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="6aa44-120">Vouw entiteiten uit om details in één oogopslag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="6aa44-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="6aa44-121">Als u een entiteit selecteert, wordt de context van het detailvenster naar deze entiteit overschakelt en kunt u meer informatie bekijken en deze entiteit beheren.</span><span class="sxs-lookup"><span data-stu-id="6aa44-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="6aa44-122">Als *u ...* aan de rechterkant van de entiteitskaart selecteert, worden alle acties die beschikbaar zijn voor die entiteit, aan het licht komen.</span><span class="sxs-lookup"><span data-stu-id="6aa44-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="6aa44-123">Dezelfde acties worden weergegeven in het detailvenster wanneer de focus van die entiteit ligt.</span><span class="sxs-lookup"><span data-stu-id="6aa44-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="6aa44-124">De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6aa44-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Een voorbeeld van een waarschuwingsverhaal met een waarschuwing in focus en enkele uitverbrede kaarten](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="6aa44-126">Actie ondernemen vanuit het detailvenster</span><span class="sxs-lookup"><span data-stu-id="6aa44-126">Take action from the details pane</span></span>

<span data-ttu-id="6aa44-127">Nadat u een entiteit van belang hebt geselecteerd, wordt het detailvenster gewijzigd om informatie weer te geven  over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en biedt u besturingselementen om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.</span><span class="sxs-lookup"><span data-stu-id="6aa44-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="6aa44-128">Nadat u klaar bent met het onderzoeken, gaat u terug naar  de waarschuwing die u  hebt gestart, markeert u de status van de waarschuwing als Opgelost en classificeert u deze als onwaarmelding of **Waar-waarschuwing.**</span><span class="sxs-lookup"><span data-stu-id="6aa44-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="6aa44-129">Als u waarschuwingen classificeert, kunt u deze mogelijkheid afstemmen om meer waargebeurde waarschuwingen en minder onwaar waarschuwingen te geven.</span><span class="sxs-lookup"><span data-stu-id="6aa44-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="6aa44-130">Als u deze als een waar waarschuwing classificeert, kunt u ook een bepaling selecteren, zoals wordt weergegeven in de onderstaande afbeelding.</span><span class="sxs-lookup"><span data-stu-id="6aa44-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Een fragment van het detailvenster met een opgeloste waarschuwing en de vervolgkeuze uitv](images/alert-details-resolved-true.png)

<span data-ttu-id="6aa44-132">Als u een foutmelding ondervindt met een line-of-business-toepassing, maakt u een onderdrukkingsregel om dit type waarschuwing in de toekomst te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="6aa44-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![acties en classificatie in het detailvenster met de onderdrukkingsregel gemarkeerd](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="6aa44-134">Als u problemen ondervindt die niet hierboven worden beschreven, gebruikt u de 🙂 knop om feedback te geven of een ondersteuningsticket te openen.</span><span class="sxs-lookup"><span data-stu-id="6aa44-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6aa44-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6aa44-135">Related topics</span></span>
- [<span data-ttu-id="6aa44-136">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="6aa44-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="6aa44-137">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="6aa44-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="6aa44-138">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="6aa44-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="6aa44-139">Apparaten onderzoeken in de lijst Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="6aa44-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="6aa44-140">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="6aa44-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="6aa44-141">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="6aa44-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="6aa44-142">Een gebruikersaccount onderzoeken in Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6aa44-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


