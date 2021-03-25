---
title: Microsoft Defender ATP-incidenten beheren
description: Beheer incidenten door deze toe te wijzen, de status ervan bij te werken of de classificatie in te stellen.
keywords: incidenten, beheren, toewijzen, status, classificatie, true alert, false alert
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
ms.technology: mde
ms.openlocfilehash: b8b5e806d09f08a12c090a1055f2c165f25b7ea1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185806"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Microsoft Defender voor eindpuntincidenten beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Het beheren van incidenten is een belangrijk onderdeel van elke cyberbeveiligingsactie. U kunt incidenten beheren door een incident te selecteren in **de** wachtrij Incidenten of in het **deelvenster Incidentenbeheer.** 


Als u een incident selecteert in **de wachtrij Incidenten,** wordt het **deelvenster Incidentbeheer** weergegeven, waar u de incidentpagina kunt openen voor meer informatie.


![Afbeelding van het deelvenster Incidentenbeheer](images/atp-incidents-mgt-pane-updated.png)

U kunt incidenten aan uzelf toewijzen, de status en classificatie wijzigen, de naam ervan wijzigen of opmerkingen maken om de voortgang bij te houden.

> [!TIP]
> Voor meer zichtbaarheid in één oogopslag worden incidentnamen automatisch gegenereerd op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën. Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.
>
> Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*
>
> Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, behouden hun namen.
>


![Afbeelding van de pagina incidentdetails](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Incidenten toewijzen
Als er nog geen incident is toegewezen, kunt u Toewijzen aan **mij** selecteren om het incident aan uzelf toe te wijzen. Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.

## <a name="set-status-and-classification"></a>Status en classificatie instellen
### <a name="incident-status"></a>Incidentstatus
U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door hun status te wijzigen naarmate het onderzoek vordert. Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op incidenten.

Uw soc-analist kan bijvoorbeeld de urgente **Actieve** incidenten van vandaag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.

Uw soc-analist kan het incident ook instellen als **Opgelost** als het incident is opgelost. 

### <a name="classification"></a>Classificatie
U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is. Als u dit doet, kan het team patronen zien en er van leren.

### <a name="add-comments"></a>Opmerkingen toevoegen
U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident weer te geven.

Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.

Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.



## <a name="related-topics"></a>Verwante onderwerpen
- [Wachtrij incidenten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [De wachtrij Incidenten weergeven en ordenen](view-incidents-queue.md)
- [Incidenten onderzoeken](investigate-incidents.md)
