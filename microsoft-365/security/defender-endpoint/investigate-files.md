---
title: Microsoft Defender onderzoeken voor endpoint-bestanden
description: Gebruik de onderzoeksopties om informatie te krijgen over bestanden die zijn gekoppeld aan waarschuwingen, gedragingen of gebeurtenissen.
keywords: onderzoeken, onderzoeken, bestand, schadelijke activiteit, aanvalsmotivatie, diepgaande analyse, diep analyserapport
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
ms.openlocfilehash: b509ab6d0c3e5183b99173e950198bad0ccd8ee0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186063"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="8bd39-104">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8bd39-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bd39-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8bd39-105">**Applies to:**</span></span>
- [<span data-ttu-id="8bd39-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="8bd39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8bd39-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bd39-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8bd39-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8bd39-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8bd39-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8bd39-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="8bd39-110">Onderzoek de details van een bestand dat is gekoppeld aan een specifieke waarschuwing, gedrag of gebeurtenis om te bepalen of het bestand schadelijke activiteiten vertoont, de motivatie van de aanval te identificeren en het mogelijke bereik van de inbreuk te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="8bd39-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="8bd39-111">Er zijn veel manieren om toegang te krijgen tot de gedetailleerde profielpagina van een specifiek bestand.</span><span class="sxs-lookup"><span data-stu-id="8bd39-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="8bd39-112">U kunt bijvoorbeeld de zoekfunctie gebruiken, op een koppeling klikken vanuit de processtructuur **Waarschuwing,** **Incidentgrafiek,** **Artefacttijdlijn** of een gebeurtenis selecteren die wordt weergegeven in de **apparaattijdlijn.**</span><span class="sxs-lookup"><span data-stu-id="8bd39-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="8bd39-113">Eenmaal op de gedetailleerde profielpagina kunt u schakelen tussen de nieuwe en oude pagina-indelingen door de nieuwe pagina **Bestand te wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="8bd39-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="8bd39-114">In de rest van dit artikel wordt de nieuwere pagina-indeling beschreven.</span><span class="sxs-lookup"><span data-stu-id="8bd39-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="8bd39-115">U kunt informatie krijgen uit de volgende secties in de bestandsweergave:</span><span class="sxs-lookup"><span data-stu-id="8bd39-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="8bd39-116">Bestandsdetails, malwaredetectie, bestandsprepresenties</span><span class="sxs-lookup"><span data-stu-id="8bd39-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="8bd39-117">Uitgebreide analyse</span><span class="sxs-lookup"><span data-stu-id="8bd39-117">Deep analysis</span></span>
- <span data-ttu-id="8bd39-118">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8bd39-118">Alerts</span></span>
- <span data-ttu-id="8bd39-119">Waargenomen in organisatie</span><span class="sxs-lookup"><span data-stu-id="8bd39-119">Observed in organization</span></span>
- <span data-ttu-id="8bd39-120">Uitgebreide analyse</span><span class="sxs-lookup"><span data-stu-id="8bd39-120">Deep analysis</span></span>
- <span data-ttu-id="8bd39-121">Bestandsnamen</span><span class="sxs-lookup"><span data-stu-id="8bd39-121">File names</span></span>

<span data-ttu-id="8bd39-122">U kunt ook actie ondernemen op een bestand vanaf deze pagina.</span><span class="sxs-lookup"><span data-stu-id="8bd39-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="8bd39-123">Bestandsacties</span><span class="sxs-lookup"><span data-stu-id="8bd39-123">File actions</span></span>

<span data-ttu-id="8bd39-124">Boven aan de profielpagina, boven de bestandsgegevenskaarten.</span><span class="sxs-lookup"><span data-stu-id="8bd39-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="8bd39-125">Acties die u hier kunt uitvoeren zijn:</span><span class="sxs-lookup"><span data-stu-id="8bd39-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="8bd39-126">Stoppen en in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="8bd39-126">Stop and quarantine</span></span>
- <span data-ttu-id="8bd39-127">Indicator Toevoegen/bewerken</span><span class="sxs-lookup"><span data-stu-id="8bd39-127">Add/edit indicator</span></span>
- <span data-ttu-id="8bd39-128">Downloadbestand</span><span class="sxs-lookup"><span data-stu-id="8bd39-128">Download file</span></span>
- <span data-ttu-id="8bd39-129">Een bedreigingsexpert raadplegen</span><span class="sxs-lookup"><span data-stu-id="8bd39-129">Consult a threat expert</span></span>
- <span data-ttu-id="8bd39-130">Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="8bd39-130">Action center</span></span>

<span data-ttu-id="8bd39-131">Zie Actie ondernemen voor een bestand voor meer [informatie over deze acties.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8bd39-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="8bd39-132">Bestandsdetails, malwaredetectie en bestandsprevalentie</span><span class="sxs-lookup"><span data-stu-id="8bd39-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="8bd39-133">In de bestandsdetails, incidenten, malwaredetectie en bestandsprecierkaarten worden verschillende kenmerken van het bestand weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8bd39-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="8bd39-134">U ziet details zoals de MD5 van het bestand, de detectieverhouding virustotaal en AV-detectie van Microsoft Defender indien beschikbaar, en de prevalentie van het bestand.</span><span class="sxs-lookup"><span data-stu-id="8bd39-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="8bd39-135">Op de kaart bestandsprevalentie ziet u waar het bestand is gezien op apparaten in de organisatie en wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="8bd39-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8bd39-136">Verschillende gebruikers zien mogelijk ongelijksoortige waarden in de apparaten *in de sectie* organisatie van de bestandsprevalentiekaart.</span><span class="sxs-lookup"><span data-stu-id="8bd39-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="8bd39-137">Dit komt omdat op de kaart gegevens worden weergegeven op basis van het RBAC-bereik dat een gebruiker heeft.</span><span class="sxs-lookup"><span data-stu-id="8bd39-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="8bd39-138">Dit betekent dat als een gebruiker zichtbaarheid heeft gekregen op een bepaalde set apparaten, hij of zij alleen de invloed van de organisatie van het bestand op deze apparaten ziet.</span><span class="sxs-lookup"><span data-stu-id="8bd39-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Afbeelding van bestandsgegevens](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="8bd39-140">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8bd39-140">Alerts</span></span>

<span data-ttu-id="8bd39-141">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die aan het bestand zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="8bd39-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="8bd39-142">Deze lijst bevat veel van dezelfde informatie als de wachtrij Waarschuwingen, met uitzondering van de apparaatgroep, indien van het betreffende apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bd39-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="8bd39-143">U kunt kiezen welk soort informatie wordt weergegeven door kolommen **aanpassen te selecteren** op de werkbalk boven de kolomkoppen.</span><span class="sxs-lookup"><span data-stu-id="8bd39-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Afbeelding van waarschuwingen met betrekking tot de bestandssectie](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="8bd39-145">Waargenomen in organisatie</span><span class="sxs-lookup"><span data-stu-id="8bd39-145">Observed in organization</span></span>

<span data-ttu-id="8bd39-146">Op **het tabblad Waargenomen in organisatie** kunt u een datumbereik opgeven om te zien welke apparaten met het bestand zijn waargenomen.</span><span class="sxs-lookup"><span data-stu-id="8bd39-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="8bd39-147">Op dit tabblad wordt een maximum aantal van 100 apparaten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8bd39-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="8bd39-148">Als u _alle apparaten_ met het bestand wilt zien,  exporteert u het tabblad naar een CSV-bestand door Exporteren te selecteren in het actiemenu boven de kolomkoppen van het tabblad.</span><span class="sxs-lookup"><span data-stu-id="8bd39-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Afbeelding van het meest recente waargenomen apparaat met het bestand](images/atp-observed-machines.png)

<span data-ttu-id="8bd39-150">Gebruik de schuifregelaar of de bereik selector om snel een periode op te geven die u wilt controleren op gebeurtenissen met het bestand.</span><span class="sxs-lookup"><span data-stu-id="8bd39-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="8bd39-151">U kunt een tijdvenster zo klein opgeven als één dag.</span><span class="sxs-lookup"><span data-stu-id="8bd39-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="8bd39-152">Hierdoor kunt u alleen bestanden zien die op dat moment met dat IP-adres zijn gecommuniceerd, waardoor onnodig schuiven en zoeken drastisch wordt verkleind.</span><span class="sxs-lookup"><span data-stu-id="8bd39-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="8bd39-153">Uitgebreide analyse</span><span class="sxs-lookup"><span data-stu-id="8bd39-153">Deep analysis</span></span>

<span data-ttu-id="8bd39-154">Op **het tabblad** Diepe analyse kunt u het bestand indienen voor uitgebreide analyse, om meer details over het gedrag van het bestand te ontdekken, evenals het effect dat het heeft binnen uw organisaties. [](respond-file-alerts.md#deep-analysis)</span><span class="sxs-lookup"><span data-stu-id="8bd39-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="8bd39-155">Nadat u het bestand hebt verzenden, wordt het uitgebreide analyserapport weergegeven op dit tabblad zodra de resultaten beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="8bd39-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="8bd39-156">Als er niets is gevonden in een uitgebreide analyse, is het rapport leeg en blijft de resultatenruimte leeg.</span><span class="sxs-lookup"><span data-stu-id="8bd39-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Afbeelding van het tabblad Diepe analyse](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="8bd39-158">Bestandsnamen</span><span class="sxs-lookup"><span data-stu-id="8bd39-158">File names</span></span>

<span data-ttu-id="8bd39-159">Het **tabblad Bestandsnamen** bevat alle namen die het bestand heeft waargenomen om te gebruiken, binnen uw organisaties.</span><span class="sxs-lookup"><span data-stu-id="8bd39-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Afbeelding van het tabblad Bestandsnamen](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="8bd39-161">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8bd39-161">Related topics</span></span>

- [<span data-ttu-id="8bd39-162">De wachtrij microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="8bd39-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8bd39-163">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="8bd39-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="8bd39-164">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8bd39-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="8bd39-165">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="8bd39-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8bd39-166">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8bd39-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="8bd39-167">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8bd39-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="8bd39-168">Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8bd39-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="8bd39-169">Antwoordacties uitvoeren op een bestand</span><span class="sxs-lookup"><span data-stu-id="8bd39-169">Take response actions on a file</span></span>](respond-file-alerts.md)
