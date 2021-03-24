---
title: Incidenten in Microsoft Defender ATP onderzoeken
description: Zie bijbehorende waarschuwingen, beheer het incident en zie metagegevens voor waarschuwingen om een incident te onderzoeken
keywords: onderzoeken, incident, waarschuwingen, metagegevens, risico, detectiebron, beïnvloede apparaten, patronen, correlatie
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
ms.openlocfilehash: 6f8986b3cb6b6fd846febefe8a64ab4099348f5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058421"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Incidenten in Microsoft Defender voor Eindpunt onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Onderzoeken van incidenten die van invloed zijn op uw netwerk, begrijpen wat ze betekenen en bewijs verzamelen om deze op te lossen. 

Wanneer u een incident onderzoekt, ziet u:
- Details van incidenten
- Opmerkingen en acties bij incidenten
- Tabbladen (waarschuwingen, apparaten, onderzoeken, bewijs, grafiek)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a>Details van incidenten analyseren 
Klik op een incident om het **deelvenster Incident te bekijken.** Selecteer **De pagina Incident openen** om de incidentdetails en gerelateerde informatie (waarschuwingen, apparaten, onderzoeken, bewijs, grafiek) te bekijken. 

![Afbeelding van incidentdetails1](images/atp-incident-details.png)

### <a name="alerts"></a>Waarschuwingen
U kunt de waarschuwingen onderzoeken en zien hoe ze zijn gekoppeld in een incident. Waarschuwingen worden gegroepeerd in incidenten op basis van de volgende redenen:
- Geautomatiseerd onderzoek: het geautomatiseerde onderzoek heeft de gekoppelde waarschuwing geactiveerd tijdens het onderzoeken van de oorspronkelijke waarschuwing 
- Bestandskenmerken: de bestanden die aan de waarschuwing zijn gekoppeld, hebben vergelijkbare kenmerken
- Handmatig koppelen : een gebruiker heeft de waarschuwingen handmatig gekoppeld
- Tijd proximate - De waarschuwingen zijn binnen een bepaalde periode op hetzelfde apparaat geactiveerd
- Hetzelfde bestand: de bestanden die aan de waarschuwing zijn gekoppeld, zijn exact hetzelfde
- Dezelfde URL: de URL die de waarschuwing heeft geactiveerd, is exact hetzelfde

![Afbeelding van het tabblad Waarschuwingen met de pagina incidentdetails met de redenen waarom de waarschuwingen in dat incident aan elkaar zijn gekoppeld](images/atp-incidents-alerts-reason.png)

U kunt ook een waarschuwing beheren en metagegevens voor waarschuwingen bekijken, samen met andere informatie. Zie Waarschuwingen [onderzoeken voor meer informatie.](investigate-alerts.md) 

### <a name="devices"></a>Apparaten
U kunt ook de apparaten onderzoeken die deel uitmaken van of gerelateerd zijn aan een bepaald incident. Zie Apparaten [onderzoeken voor meer informatie.](investigate-machines.md)

![Afbeelding van het tabblad Apparaten op pagina met details van incidenten](images/atp-incident-device-tab.png)

### <a name="investigations"></a>Onderzoeken
Selecteer **Onderzoeken om** alle automatische onderzoeken te bekijken die door het systeem zijn gestart in reactie op de incidentenwaarschuwingen.

![Afbeelding van het tabblad Onderzoeken in de pagina incidentdetails](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>Door het bewijs heen gaan
Microsoft Defender voor Eindpunt onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch kunt reageren en informatie krijgt over de belangrijke bestanden, processen, services en meer. 

Elk van de geanalyseerde entiteiten wordt gemarkeerd als geïnfecteerd, gesaneerd of verdacht. 

![Afbeelding van het tabblad Bewijs in de pagina incidentdetails](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>Bijbehorende cyberbeveiligingsdreigingen visualiseren 
Met Microsoft Defender voor Eindpunt worden de bedreigingsgegevens samengevoegd tot een incident, zodat u de patronen en correlaties kunt zien die afkomstig zijn van verschillende gegevenspunten. U kunt een dergelijke correlatie bekijken via de incidentgrafiek.

### <a name="incident-graph"></a>Incidentgrafiek
The **Graph** vertelt het verhaal van de cyberbeveiligingsaanval. U ziet bijvoorbeeld wat het invoerpunt was, welke indicator voor compromissen of activiteit is waargenomen op welk apparaat. etc.

![Afbeelding van de incidentgrafiek](images/atp-incident-graph-tab.png)

U kunt op de cirkels in de incidentgrafiek klikken om de details van de schadelijke bestanden, bijbehorende bestandsdetecties, hoeveel exemplaren er wereldwijd zijn geweest, of deze zijn waargenomen in uw organisatie, zo ja, hoeveel exemplaren.

![Afbeelding van incidentdetails](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>Verwante onderwerpen
- [Wachtrij incidenten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Incidenten in Microsoft Defender voor Eindpunt onderzoeken](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Microsoft Defender voor eindpuntincidenten beheren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
