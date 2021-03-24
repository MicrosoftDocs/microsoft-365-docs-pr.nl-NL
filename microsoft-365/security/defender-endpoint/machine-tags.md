---
title: Apparaatlabels maken en beheren
description: Apparaatlabels gebruiken om apparaten te groepen om context vast te leggen en het maken van dynamische lijst in te stellen als onderdeel van een incident
keywords: tags, apparaatlabels, apparaatgroepen, groepen, herstel, niveau, regels, aadgroep, rol, toewijzen, rang
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
ms.openlocfilehash: 4a64d3242a34ec8bf6d5646513170aa35dd3a94c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060706"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="a192c-104">Apparaatlabels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="a192c-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a192c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a192c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a192c-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="a192c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a192c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a192c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a192c-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a192c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a192c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a192c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a192c-110">Voeg tags toe aan apparaten om een logische groep te maken.</span><span class="sxs-lookup"><span data-stu-id="a192c-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="a192c-111">Apparaatlabels ondersteunen de juiste toewijzing van het netwerk, zodat u verschillende tags kunt koppelen om context vast te leggen en dynamische lijstcreatie als onderdeel van een incident kunt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a192c-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="a192c-112">Tags kunnen worden gebruikt als filter in de lijstweergave **Apparaten** of om apparaten te groeperen.</span><span class="sxs-lookup"><span data-stu-id="a192c-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="a192c-113">Zie Apparaatgroepen maken en beheren voor meer informatie over [apparaatgroepering.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="a192c-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="a192c-114">U kunt op de volgende manieren tags toevoegen op apparaten:</span><span class="sxs-lookup"><span data-stu-id="a192c-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="a192c-115">De portal gebruiken</span><span class="sxs-lookup"><span data-stu-id="a192c-115">Using the portal</span></span>
- <span data-ttu-id="a192c-116">Een registersleutelwaarde instellen</span><span class="sxs-lookup"><span data-stu-id="a192c-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="a192c-117">Er kan enige latentie zijn tussen het moment dat een tag wordt toegevoegd aan een apparaat en de beschikbaarheid ervan in de lijst met apparaten en de pagina met apparaten.</span><span class="sxs-lookup"><span data-stu-id="a192c-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="a192c-118">Zie Api voor apparaatlabels toevoegen of verwijderen als u apparaatlabels wilt toevoegen met [API.](add-or-remove-machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="a192c-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="a192c-119">Apparaatlabels toevoegen en beheren met de portal</span><span class="sxs-lookup"><span data-stu-id="a192c-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="a192c-120">Selecteer het apparaat waar u tags op wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="a192c-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="a192c-121">U kunt een apparaat selecteren of zoeken in een van de volgende weergaven:</span><span class="sxs-lookup"><span data-stu-id="a192c-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="a192c-122">**Dashboard Beveiligingsbewerkingen:** selecteer de naam van het apparaat in de sectie Topapparaten met actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="a192c-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="a192c-123">**Waarschuwingenwachtrij:** selecteer de naam van het apparaat naast het apparaatpictogram in de waarschuwingenwachtrij.</span><span class="sxs-lookup"><span data-stu-id="a192c-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="a192c-124">**Lijst met** apparaten: selecteer de naam van het apparaat in de lijst met apparaten.</span><span class="sxs-lookup"><span data-stu-id="a192c-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="a192c-125">**Zoekvak:** selecteer Apparaat in de vervolgkeuzelijst en voer de naam van het apparaat in.</span><span class="sxs-lookup"><span data-stu-id="a192c-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="a192c-126">U kunt ook naar de waarschuwingspagina gaan via de bestands- en IP-weergaven.</span><span class="sxs-lookup"><span data-stu-id="a192c-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="a192c-127">Selecteer **Tags beheren** in de rij met antwoordacties.</span><span class="sxs-lookup"><span data-stu-id="a192c-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Afbeelding van de knop Tags beheren](images/manage-tags.png)

3. <span data-ttu-id="a192c-129">Typen om tags te zoeken of te maken</span><span class="sxs-lookup"><span data-stu-id="a192c-129">Type to find or create tags</span></span>

    ![Afbeelding van het toevoegen van tags op een apparaat1](images/new-tags.png)

<span data-ttu-id="a192c-131">Tags worden toegevoegd aan de apparaatweergave en worden ook weergegeven in de **lijstweergave** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="a192c-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="a192c-132">Vervolgens kunt u het filter **Tags gebruiken** om de relevante lijst met apparaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="a192c-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="a192c-133">Filteren werkt mogelijk niet op tagnamen die haakjes bevatten.</span><span class="sxs-lookup"><span data-stu-id="a192c-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="a192c-134">Wanneer u een nieuwe tag maakt, wordt een lijst met bestaande tags weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a192c-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="a192c-135">In de lijst worden alleen tags weergegeven die zijn gemaakt via de portal.</span><span class="sxs-lookup"><span data-stu-id="a192c-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="a192c-136">Bestaande tags die zijn gemaakt op clientapparaten, worden niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a192c-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="a192c-137">U kunt ook tags uit deze weergave verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a192c-137">You can also delete tags from this view.</span></span>

![Afbeelding van het toevoegen van tags op een apparaat2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="a192c-139">Apparaatlabels toevoegen door een registersleutelwaarde in te stellen</span><span class="sxs-lookup"><span data-stu-id="a192c-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="a192c-140">Alleen van toepassing op de volgende apparaten:</span><span class="sxs-lookup"><span data-stu-id="a192c-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="a192c-141">Windows 10, versie 1709 of hoger</span><span class="sxs-lookup"><span data-stu-id="a192c-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="a192c-142">Windows Server, versie 1803 of hoger</span><span class="sxs-lookup"><span data-stu-id="a192c-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="a192c-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a192c-143">Windows Server 2016</span></span>
>- <span data-ttu-id="a192c-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a192c-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="a192c-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="a192c-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="a192c-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a192c-146">Windows 8.1</span></span>
>- <span data-ttu-id="a192c-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="a192c-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="a192c-148">Het maximum aantal tekens dat in een tag kan worden ingesteld, is 200.</span><span class="sxs-lookup"><span data-stu-id="a192c-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="a192c-149">Apparaten met vergelijkbare tags kunnen handig zijn wanneer u contextuele actie moet toepassen op een specifieke lijst met apparaten.</span><span class="sxs-lookup"><span data-stu-id="a192c-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="a192c-150">Gebruik de volgende registersleutelinvoer om een tag toe te voegen op een apparaat:</span><span class="sxs-lookup"><span data-stu-id="a192c-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="a192c-151">Registersleutel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="a192c-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="a192c-152">Registersleutelwaarde (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="a192c-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="a192c-153">Registersleutelgegevens: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="a192c-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="a192c-154">De apparaattag maakt deel uit van het apparaatinformatierapport dat eenmaal per dag wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="a192c-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="a192c-155">Als alternatief kunt u ervoor kiezen om het eindpunt opnieuw op te starten dat een nieuw apparaatinformatierapport zou overbrengen.</span><span class="sxs-lookup"><span data-stu-id="a192c-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="a192c-156">Als u een tag wilt verwijderen die is toegevoegd met de bovenstaande registersleutel, verwijdert u de inhoud van de registersleutelgegevens in plaats van de 'Groep'-toets te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a192c-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
