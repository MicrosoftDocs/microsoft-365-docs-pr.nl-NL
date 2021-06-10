---
title: Gevoeligheidslabels gebruiken om prioriteit te geven aan de respons op incidenten
description: Informatie over het gebruik van gevoeligheidslabels om prioriteit te geven aan incidenten en incidenten te onderzoeken
keywords: informatie, beveiliging, gegevens, verlies, preventie,etiketten, dlp, incident, onderzoek, onderzoek
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186123"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="40f98-104">Gevoeligheidslabels gebruiken om prioriteit te geven aan de respons op incidenten</span><span class="sxs-lookup"><span data-stu-id="40f98-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40f98-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="40f98-105">**Applies to:**</span></span>
- [<span data-ttu-id="40f98-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="40f98-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40f98-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40f98-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="40f98-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="40f98-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="40f98-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="40f98-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="40f98-110">Een standaardlevenscyclus voor permanente bedreigingen bestaat uit gegevens exfiltratie.</span><span class="sxs-lookup"><span data-stu-id="40f98-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="40f98-111">Bij een beveiligingsincident is het belangrijk om prioriteit te kunnen geven aan onderzoeken waarbij gevoelige bestanden mogelijk gevaar lopen, zodat bedrijfsgegevens en -informatie worden beveiligd.</span><span class="sxs-lookup"><span data-stu-id="40f98-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="40f98-112">Met Defender voor Eindpunt kunt u de prioriteit van beveiligingsincidenten veel eenvoudiger maken met het gebruik van gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="40f98-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="40f98-113">Gevoeligheidslabels identificeren snel incidenten waarbij apparaten met gevoelige informatie betrokken kunnen zijn, zoals vertrouwelijke informatie.</span><span class="sxs-lookup"><span data-stu-id="40f98-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="40f98-114">Incidenten met gevoelige gegevens onderzoeken</span><span class="sxs-lookup"><span data-stu-id="40f98-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="40f98-115">Meer informatie over het gebruik van gegevensgevoeligheidslabels om prioriteit te geven aan onderzoek naar incidenten.</span><span class="sxs-lookup"><span data-stu-id="40f98-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="40f98-116">Labels worden gedetecteerd voor Windows 10, versie 1809 of hoger.</span><span class="sxs-lookup"><span data-stu-id="40f98-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="40f98-117">Selecteer Microsoft Defender-beveiligingscentrum **incidenten**.</span><span class="sxs-lookup"><span data-stu-id="40f98-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="40f98-118">Schuif naar rechts om de kolom **Gegevensgevoeligheid te** zien.</span><span class="sxs-lookup"><span data-stu-id="40f98-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="40f98-119">Deze kolom geeft gevoeligheidslabels weer die zijn waargenomen op apparaten die betrekking hebben op de incidenten, zodat wordt aangegeven of gevoelige bestanden mogelijk worden beïnvloed door het incident.</span><span class="sxs-lookup"><span data-stu-id="40f98-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Afbeelding van de kolom gegevensgevoeligheid](images/data-sensitivity-column.png)

    <span data-ttu-id="40f98-121">U kunt ook filteren op basis van **gegevensgevoeligheid**</span><span class="sxs-lookup"><span data-stu-id="40f98-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Afbeelding van gegevensgevoeligheidsfilter](images/data-sensitivity-filter.png)

3. <span data-ttu-id="40f98-123">Open de pagina met incidenten om verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="40f98-123">Open the incident page to further investigate.</span></span>

    ![Afbeelding van details van incidentpagina](images/incident-page.png)

4. <span data-ttu-id="40f98-125">Selecteer het **tabblad Apparaten** om apparaten te identificeren die bestanden met gevoeligheidslabels opslaan.</span><span class="sxs-lookup"><span data-stu-id="40f98-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Afbeelding van het tabblad Apparaat](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="40f98-127">Selecteer de apparaten waarmee gevoelige gegevens worden opgeslagen en zoek door de tijdlijn om te bepalen welke bestanden mogelijk worden beïnvloed en onderneemt de juiste actie om ervoor te zorgen dat gegevens worden beveiligd.</span><span class="sxs-lookup"><span data-stu-id="40f98-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="40f98-128">U kunt de gebeurtenissen in de tijdlijn van het apparaat beperken door te zoeken naar labels voor gegevensgevoeligheid.</span><span class="sxs-lookup"><span data-stu-id="40f98-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="40f98-129">Als u dit doet, worden alleen gebeurtenissen vermeld die zijn gekoppeld aan bestanden met de naam van het label.</span><span class="sxs-lookup"><span data-stu-id="40f98-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Afbeelding van apparaattijdlijn met vernauwde zoekresultaten op basis van label](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="40f98-131">Deze gegevenspunten worden ook zichtbaar via de 'DeviceFileEvents' in geavanceerde zoekopdrachten, zodat geavanceerde query's en planningsdetectie rekening kunnen houden met gevoeligheidslabels en bestandsbeveiligingsstatus.</span><span class="sxs-lookup"><span data-stu-id="40f98-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
