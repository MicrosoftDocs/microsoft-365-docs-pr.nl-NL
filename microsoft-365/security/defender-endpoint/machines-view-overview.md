---
title: De lijst met Microsoft Defender voor eindpuntapparaten weergeven en organiseren
description: Meer informatie over de beschikbare functies die u kunt gebruiken in de lijst Apparaten, zoals het sorteren, filteren en exporteren van de lijst om de onderzoeken te verbeteren.
keywords: sorteren, filteren, exporteren, csv, apparaatnaam, domein, laatst gezien, intern IP, status, actieve waarschuwingen, actieve malwaredetecties, bedreigingscategorie, waarschuwingen controleren, netwerk, verbinding, malware, type, wachtwoord stealer, ransomware, exploit, bedreiging, algemene malware, ongewenste software
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
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861573"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>De lijst Met Microsoft Defender voor eindpuntapparaten weergeven en organiseren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


In **de lijst Apparaten** ziet u een lijst met de apparaten in uw netwerk waar waarschuwingen zijn gegenereerd. Standaard worden in de wachtrij apparaten weergegeven die de afgelopen 30 dagen zijn weergegeven.  

In één oogopslag ziet u informatie zoals domein, risiconiveau, besturingssysteemplatform en andere details voor eenvoudige identificatie van apparaten die het meest risico lopen.

Er zijn verschillende opties waar u uit kunt kiezen om de lijstweergave voor apparaten aan te passen. Op de bovenste navigatie kunt u:

- Kolommen toevoegen of verwijderen
- De hele lijst exporteren in CSV-indeling
- Het aantal items selecteren dat per pagina moet worden weergegeven
- Filters toepassen

Tijdens het onboardingproces wordt de lijst **Apparaten** geleidelijk gevuld met apparaten terwijl ze sensorgegevens beginnen te rapporteren. Gebruik deze weergave om uw ingebouwde eindpunten bij te houden wanneer ze online komen, of download de volledige lijst met eindpunten als een CSV-bestand voor offlineanalyse.

>[!NOTE]
> Als u de lijst met apparaten exporteert, bevat deze elk apparaat in uw organisatie. Het kan een aanzienlijke hoeveelheid tijd duren om te downloaden, afhankelijk van hoe groot uw organisatie is. Als u de lijst exporteert in CSV-indeling, worden de gegevens op een ongefilterde manier weergegeven. Het CSV-bestand bevat alle apparaten in de organisatie, ongeacht de filters die in de weergave zelf worden toegepast.

![Afbeelding van apparatenlijst met lijst met apparaten](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>De lijst met apparaten sorteren en filteren

U kunt de volgende filters toepassen om de lijst met waarschuwingen te beperken en een meer gerichte weergave te krijgen.

### <a name="risk-level"></a>Risiconiveau

Het risiconiveau weerspiegelt de algemene risicobeoordeling van het apparaat op basis van een combinatie van factoren, waaronder het type en de ernst van actieve waarschuwingen op het apparaat. Door actieve waarschuwingen op te lossen, herstelactiviteiten goed te keuren en volgende waarschuwingen te onderdrukken, kan het risiconiveau worden verlaagd.

### <a name="exposure-level"></a>Blootstellingsniveau

Het blootstellingsniveau weerspiegelt de huidige blootstelling van het apparaat op basis van de cumulatieve impact van de beveiligingsaanbevelingen in behandeling. De mogelijke niveaus zijn laag, gemiddeld en hoog. Lage blootstelling betekent dat uw apparaten minder kwetsbaar zijn voor gebruik.

Als op het blootstellingsniveau 'Geen gegevens beschikbaar' staat, zijn er een paar redenen waarom dit het geval kan zijn:

- De rapportage van het apparaat is langer dan 30 dagen gestopt, in dat geval wordt het als inactief beschouwd en wordt de blootstelling niet berekend
- Apparaat os niet ondersteund - zie [minimumvereisten voor Microsoft Defender voor Eindpunt](minimum-requirements.md)
- Apparaat met verouderde agent (zeer onwaarschijnlijk)

### <a name="os-platform"></a>Besturingssysteemplatform

Selecteer alleen de besturingssysteemplatforms die u wilt onderzoeken.

### <a name="health-state"></a>Status

Filteren op de volgende statussen van apparaten:

- **Actief:** apparaten die sensorgegevens actief aan de service rapporteren.
- **Inactief:** apparaten die al meer dan 7 dagen geen signalen meer verzenden.
- **Verkeerd geconfigureerd: apparaten** die communicatie met de service hebben beschadigd of die geen sensorgegevens kunnen verzenden. Verkeerd geconfigureerde apparaten kunnen verder worden geclassificeerd als:
  - Geen sensorgegevens
  - Communicatie met verminderde werking

  Zie Ongezonde sensoren oplossen voor meer informatie over het oplossen van problemen op verkeerd [geconfigureerde apparaten.](fix-unhealthy-sensors.md)

### <a name="antivirus-status"></a>Antivirusstatus

Apparaten filteren op antivirusstatus. Is alleen van toepassing op actieve Windows 10-apparaten.

- **Uitgeschakeld-** Virusbeveiliging & is uitgeschakeld.
- **Niet rapporteren:** virusbeveiliging & geen rapportage.
- **Niet bijgewerkt-** Virusbeveiliging & is niet up-to-date.

Zie Het dashboard [Threat & Vulnerability Management weergeven voor meer informatie.](tvm-dashboard-insights.md)

### <a name="threat-mitigation-status"></a>Status van bedreigingsbeperking

Als u apparaten wilt weergeven die mogelijk worden beïnvloed door een bepaalde bedreiging, selecteert u de bedreiging in de vervolgkeuzelijst en selecteert u vervolgens welk beveiligingsaspect moet worden beperkt.

Zie Bedreigingsanalyse voor meer [informatie over bepaalde bedreigingen.](threat-analytics.md) Zie Threat [& Vulnerability Management voor](next-gen-threat-and-vuln-mgt.md)informatie over risicobeperking.

### <a name="windows-10-version"></a>Windows 10-versie

Selecteer alleen de Windows 10-versies die u wilt onderzoeken.

### <a name="tags--groups"></a>Tags & Groepen

Filter de lijst op basis van de groepering en labeling die u aan afzonderlijke apparaten hebt toegevoegd. Zie [Apparaatlabels maken en beheren](machine-tags.md) en [Apparaatgroepen maken en beheren.](machine-groups.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten](investigate-machines.md)
