---
title: De incidentenwachtrij weergeven en organiseren
ms.reviewer: ''
description: Bekijk de lijst met incidenten en leer hoe u filters kunt toepassen om de lijst te beperken en een meer gerichte weergave te krijgen.
keywords: weergeven, organiseren, incidenten, aggregatie, onderzoeken, wachtrij, ttp
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499939"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>De wachtrij Microsoft Defender voor eindpuntincidenten weergeven en organiseren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

De **wachtrij Incidenten** toont een verzameling incidenten die zijn gemarkeerd vanaf apparaten in uw netwerk. Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken.

Standaard worden in de wachtrij incidenten weergegeven die de afgelopen 30 dagen zijn gezien, waarbij het meest recente incident boven aan de lijst wordt weergegeven, zodat u de meest recente incidenten als eerste kunt zien.

Er zijn verschillende opties waar u uit kunt kiezen om de wachtrijweergave Incidenten aan te passen. 

Op de bovenste navigatie kunt u:
- Kolommen aanpassen om kolommen toe te voegen of te verwijderen 
- Het aantal items wijzigen dat per pagina moet worden weergegeven
- De items selecteren die per pagina moeten worden weergegeven
- Batch-select the incidents to assign 
- Navigeren tussen pagina's
- Filters toepassen

![Afbeelding van incidentenwachtrij](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>De wachtrij voor incidenten sorteren en filteren
U kunt de volgende filters toepassen om de lijst met incidenten te beperken en een meer gerichte weergave te krijgen.

### <a name="severity"></a>Ernst

Ernst van incident | Omschrijving
:---|:---
Hoog </br>(Rood) | Bedreigingen die vaak worden gekoppeld aan geavanceerde permanente bedreigingen (APT). Deze incidenten geven een hoog risico aan vanwege de ernst van de schade die ze kunnen toebrengen aan apparaten.
Gemiddeld </br>(Oranje) | Bedreigingen die zelden worden waargenomen in de organisatie, zoals afwijkende registerwijziging, uitvoering van verdachte bestanden en waargenomen gedrag dat typisch is voor aanvalsfasen.
Laag </br>(Geel) | Bedreigingen die zijn gekoppeld aan voorkomende malware en hackprogramma's die niet noodzakelijkerwijs een geavanceerde bedreiging aangeven die is gericht op de organisatie.
Informatief </br>(Grijs) | Informatie-incidenten worden mogelijk niet beschouwd als schadelijk voor het netwerk, maar kunnen wel goed zijn om bij te houden.

## <a name="assigned-to"></a>Toegewezen aan
U kunt ervoor kiezen om de lijst te filteren door toegewezen aan iedereen of degenen te selecteren die aan u zijn toegewezen.

### <a name="category"></a>Categorie
Incidenten worden gecategoriseerd op basis van de beschrijving van het stadium waarin de cyberbeveiligingsketen zich in de keten voor cyberbeveiligingsbeveiliging beveiligt. Deze weergave helpt de bedreigingsanalist om prioriteit, urgentie en bijbehorende antwoordstrategie te bepalen die moet worden geïmplementeerd op basis van context.

### <a name="status"></a>Status
U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.

### <a name="data-sensitivity"></a>Gegevensgevoeligheid
Gebruik dit filter om incidenten weer te geven die gevoeligheidslabels bevatten.

## <a name="incident-naming"></a>Naamgeving voor incidenten

Als u het bereik van het incident in één oogopslag wilt begrijpen, worden incidentnamen automatisch gegenereerd op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.

Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*

> [!NOTE]
> Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, behouden hun naam.


## <a name="see-also"></a>Zie ook
- [Incidentenwachtrij](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Incidenten beheren](manage-incidents.md)
- [Incidenten onderzoeken](investigate-incidents.md)

