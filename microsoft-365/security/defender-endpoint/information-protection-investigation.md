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
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Gevoeligheidslabels gebruiken om prioriteit te geven aan de respons op incidenten  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Een standaardlevenscyclus voor permanente bedreigingen bestaat uit gegevens exfiltratie. Bij een beveiligingsincident is het belangrijk om prioriteit te kunnen geven aan onderzoeken waarbij gevoelige bestanden mogelijk gevaar lopen, zodat bedrijfsgegevens en -informatie worden beveiligd.

Met Defender voor Eindpunt kunt u de prioriteit van beveiligingsincidenten veel eenvoudiger maken met het gebruik van gevoeligheidslabels. Gevoeligheidslabels identificeren snel incidenten waarbij apparaten met gevoelige informatie betrokken kunnen zijn, zoals vertrouwelijke informatie. 

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Incidenten met gevoelige gegevens onderzoeken
Meer informatie over het gebruik van gegevensgevoeligheidslabels om prioriteit te geven aan onderzoek naar incidenten.

>[!NOTE]
>Labels worden gedetecteerd voor Windows 10, versie 1809 of hoger.

1. Selecteer Microsoft Defender-beveiligingscentrum **incidenten**. 

2. Schuif naar rechts om de kolom **Gegevensgevoeligheid te** zien. Deze kolom geeft gevoeligheidslabels weer die zijn waargenomen op apparaten die betrekking hebben op de incidenten, zodat wordt aangegeven of gevoelige bestanden mogelijk worden beïnvloed door het incident.

    ![Afbeelding van de kolom gegevensgevoeligheid](images/data-sensitivity-column.png)

    U kunt ook filteren op basis van **gegevensgevoeligheid** 

    ![Afbeelding van gegevensgevoeligheidsfilter](images/data-sensitivity-filter.png)

3. Open de pagina met incidenten om verder te onderzoeken.

    ![Afbeelding van details van incidentpagina](images/incident-page.png)

4. Selecteer het **tabblad Apparaten** om apparaten te identificeren die bestanden met gevoeligheidslabels opslaan.

    ![Afbeelding van het tabblad Apparaat](images/investigate-devices-tab.png)
   

5. Selecteer de apparaten waarmee gevoelige gegevens worden opgeslagen en zoek door de tijdlijn om te bepalen welke bestanden mogelijk worden beïnvloed en onderneemt de juiste actie om ervoor te zorgen dat gegevens worden beveiligd. 

   U kunt de gebeurtenissen in de tijdlijn van het apparaat beperken door te zoeken naar labels voor gegevensgevoeligheid. Als u dit doet, worden alleen gebeurtenissen vermeld die zijn gekoppeld aan bestanden met de naam van het label.

    ![Afbeelding van apparaattijdlijn met vernauwde zoekresultaten op basis van label](images/machine-timeline-labels.png)


>[!TIP]
>Deze gegevenspunten worden ook zichtbaar via de 'DeviceFileEvents' in geavanceerde zoekopdrachten, zodat geavanceerde query's en planningsdetectie rekening kunnen houden met gevoeligheidslabels en bestandsbeveiligingsstatus. 
