---
title: Prioriteit geven aan incidenten in Microsoft 365 Defender
description: Informatie over het filteren van incidenten in de wachtrij voor incidenten in Microsoft 365 Defender
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten, analyseren, antwoord
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636264"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioriteit geven aan incidenten in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Microsoft 365 Defender past correlatieanalyse toe en aggregeert gerelateerde waarschuwingen en geautomatiseerde onderzoeken van verschillende producten in een incident. Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gezien de end-to-end zichtbaarheid die Microsoft 365 Defender heeft in de hele suite met producten. In deze weergave krijgen uw beveiligingsanalisten het bredere verhaal over aanvallen, waarmee ze complexe bedreigingen in uw organisatie beter kunnen begrijpen en kunnen omgaan.

In **de wachtrij Incident** ziet u een verzameling incidenten die zijn gemaakt op verschillende apparaten, gebruikers en postvakken. Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken. 

U komt bij de incidentenwachtrij van **Incidenten & waarschuwingen > Incidenten** op de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com) Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

In **de sectie Meest recente incidenten en waarschuwingen** ziet u een grafiek van het aantal ontvangen waarschuwingen en incidenten die in de afgelopen 24 uur zijn gemaakt.

Standaard worden in de wachtrij voor incidenten in het Microsoft 365 beveiligingscentrum incidenten weergegeven die de afgelopen zes maanden zijn gezien. Het meest recente incident staat bovenaan de lijst, zodat u het eerst kunt zien.

De incidentwachtrij heeft aanpasbare kolommen (selecteer Kolommen **kiezen)** die u inzicht geven in de verschillende kenmerken van het incident of de beïnvloede entiteiten. Op deze manier kunt u een weloverwogen beslissing nemen over de prioriteit van incidenten voor analyse.

Voor extra zichtbaarheid in één oogopslag worden met automatische naamgeving voor incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal eindpunten dat is beïnvloed, de betreffende gebruikers, detectiebronnen of categorieën. Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.

Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*

> [!NOTE]
> Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, worden niet gewijzigd.

In de wachtrij voor incidenten worden ook meerdere filteropties beschikbaar, waarmee u, wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opsnuiven of kunt besluiten zich te concentreren op een specifiek scenario of bedreiging. Door filters toe te passen op de incidentwachtrij, kan worden bepaald welk incident direct aandacht nodig heeft. 

## <a name="available-filters"></a>Beschikbare filters

In de standaardwachtrij voor incidenten kunt u **Filters** selecteren om een deelvenster Filters weer te geven, waaruit u een gefilterde reeks incidenten kunt bekijken. Hier volgt een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Voorbeeld van het filtervenster voor de incidentwachtrij":::

In deze tabel worden de filternamen vermeld die beschikbaar zijn.

| Filternaam | Beschrijving |
|:-------|:-----|
| Toegewezen aan | U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of waarschuwingen die door automatisering worden verwerkt. |
| Categorieën | Kies categorieën om zich te richten op specifieke tactieken, technieken of aanvalsonderdelen. |
| Classificatie | Filter incidenten op basis van de setclassificaties van de gerelateerde waarschuwingen. De waarden omvatten waar waarschuwingen, onwaar waarschuwingen of niet ingesteld. |
| Gegevensgevoeligheid | Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren. Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, kunt u snel bepalen of gevoelige informatie mogelijk is gehackt en kunt u prioriteit geven aan het oplossen van deze incidenten. <br><br> Alleen van toepassing als Microsoft Information Protection is ingeschakeld.|
| Apparaatgroep | Filteren op gedefinieerde apparaatgroepen. |
| Onderzoekstoestand | Filter incidenten op basis van de status van automatisch onderzoek.  |
| Meerdere categorieën | U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden op meerdere categorieën en zo mogelijk meer schade kunnen veroorzaken. |
| Meerdere servicebronnen  | Filter om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender voor Eindpunt, Microsoft Cloud App Security, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365). |
| BESTURINGSSYSTEEM-platform | Beperk de weergave van de incidentwachtrij per besturingssysteem. |
| Servicebronnen | Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing uit die gekozen bron bevatten. |
| Ernst | De ernst van een incident is een indicatie van de invloed die het kan hebben op uw activa. Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht. |
| Status | U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn. |
|||

## <a name="next-steps"></a>Volgende stappen

Nadat u hebt bepaald welk incident de hoogste prioriteit vereist, selecteert u het en:

- [Beheer](manage-incidents.md) de eigenschappen van het incident voor tags, toewijzing, onmiddellijke oplossing voor fout-positieve incidenten en opmerkingen.
- Begin uw [onderzoeken.](investigate-incidents.md)

## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten beheren](manage-incidents.md)
- [Incidenten onderzoeken](investigate-incidents.md)
