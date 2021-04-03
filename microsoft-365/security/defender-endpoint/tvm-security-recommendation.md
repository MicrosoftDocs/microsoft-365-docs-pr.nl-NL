---
title: Beveiligingsaanbevelingen door bedreigings- en kwetsbaarheidsbeheer
description: Krijg actiebare beveiligingsaanbevelingen die prioriteit krijgen op basis van bedreiging, waarschijnlijkheid dat deze wordt geschonden en waarde in bedreigings- en kwetsbaarheidsbeheer.
keywords: threat and vulnerability management, mdatp tvm security recommendation, cyberbeveiligingsaanbeveling, actievolle beveiligingsaanbeveling
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 97d496271c1ef7185419f7d39956da0429f070aa
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500480"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a>Beveiligingsaanbevelingen - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Zwakke punten in de cyberbeveiliging die in uw organisatie zijn geïdentificeerd, worden in kaart gebracht aan actiebare beveiligingsaanbevelingen en worden geprioriteerd op basis van hun impact. Met prioriteitsaanbevelingen kunt u de tijd verkorten om beveiligingsproblemen te beperken of te verhelpen en naleving te verbeteren.

Elke beveiligingsaanbeveling bevat actiestappen voor herstel. Voor hulp bij taakbeheer kan de aanbeveling ook worden verzonden met Microsoft Intune en Microsoft Endpoint Configuration Manager. Wanneer het bedreigingslandschap verandert, wordt de aanbeveling ook gewijzigd terwijl er continu gegevens uit uw omgeving worden verzameld.

>[!TIP]
>Zie E-mailmeldingen voor kwetsbaarheid configureren in Microsoft Defender voor Eindpunt voor e-mailberichten over [nieuwe beveiligingsprobleemgebeurtenissen](configure-vulnerability-email-notifications.md)

## <a name="how-it-works"></a>Hoe het werkt

Elk apparaat in de organisatie wordt gescored op basis van drie belangrijke factoren om klanten te helpen zich op het juiste moment op de juiste dingen te concentreren.

- **Bedreiging:** kenmerken van de beveiligingslekken en exploits in de apparaten en inbreukgeschiedenis van uw organisatie. Op basis van deze factoren worden in de beveiligingsaanbevelingen de bijbehorende koppelingen naar actieve waarschuwingen, lopende bedreigingscampagnes en bijbehorende analyserapporten voor bedreigingen weergeven.

- **Kans op inbreuk** : de beveiligingsstatus en tolerantie van uw organisatie tegen bedreigingen

- **Bedrijfswaarde:** de activa, kritieke processen en intellectuele eigenschappen van uw organisatie

## <a name="navigate-to-the-security-recommendations-page"></a>Naar de pagina Beveiligingsaanbevelingen gaan

Toegang tot de pagina Beveiligingsaanbevelingen op verschillende manieren:

- Navigatiemenu bedreigings- en kwetsbaarheidsbeheer in [het Microsoft Defender-beveiligingscentrum](portal-overview.md)
- Belangrijkste beveiligingsaanbevelingen in het [dashboard bedreigings- en kwetsbaarheidsbeheer](tvm-dashboard-insights.md)

Verwante beveiligingsaanbevelingen weergeven op de volgende plaatsen:

- Softwarepagina
- Apparaatpagina

### <a name="navigation-menu"></a>Navigatiemenu

Ga naar het navigatiemenu voor bedreigings- en kwetsbaarheidsbeheer en selecteer **Beveiligingsaanbevelingen.** De pagina bevat een lijst met beveiligingsaanbevelingen voor de bedreigingen en beveiligingsproblemen in uw organisatie.

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a>Belangrijkste beveiligingsaanbevelingen in het dashboard bedreigings- en kwetsbaarheidsbeheer

Op een bepaalde dag als beveiligingsbeheerder kunt u het [dashboard](tvm-dashboard-insights.md) bedreigings- [](tvm-exposure-score.md) en kwetsbaarheidsbeheer bekijken om uw blootstellingsscore naast uw Microsoft Secure Score voor apparaten [te zien.](tvm-microsoft-secure-score-devices.md) Het doel is **om** de blootstelling van uw  organisatie aan beveiligingsproblemen te verlagen en de apparaatbeveiliging van uw organisatie te verhogen om beter bestand te zijn tegen cyberbeveiligingsaanvallen. De lijst met beste beveiligingsaanbevelingen kan u helpen dat doel te bereiken.

![Voorbeeld van De beste beveiligingsaanbevelingskaart, met vier beveiligingsaanbevelingen.](images/top-security-recommendations350.png)

In de belangrijkste beveiligingsaanbevelingen worden de verbeterkansen vermeld die zijn geprioriteerd op basis van de belangrijke factoren die in de vorige sectie worden genoemd: bedreiging, kans op inbreuk en waarde. Als u een aanbeveling selecteert, gaat u naar de pagina met beveiligingsaanbevelingen met meer informatie.

## <a name="security-recommendations-overview"></a>Overzicht van beveiligingsaanbevelingen

Bekijk aanbevelingen, het aantal gevonden zwakke punten, gerelateerde onderdelen, bedreigingsinzichten, aantal blootgestelde apparaten, status, hersteltype, herstelactiviteiten, invloed op uw blootstellingsscore en Microsoft Secure Score voor apparaten en bijbehorende tags.

De kleur van de **grafiek Exposed-apparaten** wordt gewijzigd naarmate de trend verandert. Als het aantal blootgestelde apparaten toe neemt, verandert de kleur in rood. Als het aantal blootgestelde apparaten afneemt, verandert de kleur van de grafiek in groen.

>[!NOTE]
>Bedreigings- en kwetsbaarheidsbeheer toont apparaten die tot **30** dagen geleden werden gebruikt. Dit is anders dan de rest van Microsoft Defender voor Eindpunt, waarbij een apparaat dat langer dan 7 dagen niet in gebruik is, een inactieve status heeft.

![Voorbeeld van de landingspagina voor beveiligingsaanbevelingen.](images/tvmsecrec-updated.png)

### <a name="icons"></a>Pictogrammen

Met handige pictogrammen kunt u ook snel de aandacht vestigen op:
- ![pijl die een doel raakt](images/tvm_alert_icon.png) mogelijke actieve waarschuwingen
- ![rode bug](images/tvm_bug_icon.png) bijbehorende openbare exploits
- ![gloeilamp](images/tvm_insight_icon.png) aanbevelingen

### <a name="explore-security-recommendation-options"></a>Opties voor beveiligingsaanbeveling verkennen

Selecteer de beveiligingsaanbeveling die u wilt onderzoeken of verwerken.

![Voorbeeld van een flyoutpagina met beveiligingsaanbevelingen.](images/secrec-flyouteolsw.png)

In het flyout kunt u een van de volgende opties kiezen:

- **Open de softwarepagina:** open de softwarepagina om meer context te krijgen over de software en hoe deze wordt gedistribueerd. De informatie kan bedreigingscontext, bijbehorende aanbevelingen, gevonden zwakke punten, het aantal blootgestelde apparaten, gevonden beveiligingslekken, namen en gedetailleerde apparaten met de geïnstalleerde software en de distributie van versies omvatten.

- [**Herstelopties:**](tvm-remediation.md) verzend een herstelaanvraag om een ticket te openen in Microsoft Intune, waar uw IT-beheerder deze kan ophalen en adresseren. Houd de herstelactiviteit bij op de pagina Herstel.

- [**Uitzonderingsopties:**](tvm-exception.md) verzend een uitzondering, geef rechtvaardiging en stel de duur van de uitzondering in als u het probleem nog niet kunt verhelpen.

>[!NOTE]
>Wanneer een softwarewijziging wordt aangebracht op een apparaat, duurt het meestal 2 uur voordat de gegevens worden weergegeven in de beveiligingsportal. Het kan echter soms langer duren. Configuratiewijzigingen kunnen 4 tot 24 uur duren.

### <a name="investigate-changes-in-device-exposure-or-impact"></a>Wijzigingen in apparaatblootstelling of -impact onderzoeken

Als er een grote sprong is gemaakt in het aantal blootgestelde apparaten of als het effect op de blootstellingsscore van uw organisatie en Microsoft Secure Score voor apparaten sterk is toegenomen, is deze beveiligingsaanbeveling het onderzoeken waard.

1. Selecteer de aanbevelingspagina en **de pagina Software openen**
2. Selecteer het **tabblad Tijdlijn** van gebeurtenis om alle impactvolle gebeurtenissen met betrekking tot die software weer te geven, zoals nieuwe beveiligingslekken of nieuwe openbare exploits. [Meer informatie over de tijdlijn van gebeurtenissen](threat-and-vuln-mgt-event-timeline.md)
3. Bepaal hoe u de toename of de blootstelling van uw organisatie kunt aanpakken, zoals het indienen van een herstelaanvraag

## <a name="request-remediation"></a>Herstelverzoeken

De herstelfunctie voor bedreigings- en kwetsbaarheidsbeheer overbrugt de kloof tussen beveiligings- en IT-beheerders via de werkstroom voor herstelverzoeken. Beveiligingsbeheerders zoals u kunnen de IT-beheerder vragen om een beveiligingsprobleem op te verhelpen vanaf de pagina **Beveiligingsaanbeveling** naar Intune. [Meer informatie over herstelopties](tvm-remediation.md)

### <a name="how-to-request-remediation"></a>Herstel aanvragen

Selecteer een beveiligingsaanbeveling voor wie u herstel wilt aanvragen en selecteer vervolgens **Herstelopties.** Vul het formulier in en selecteer **Aanvraag indienen.** Ga naar de [**pagina Herstel om**](tvm-remediation.md) de status van uw herstelaanvraag weer te geven. [Meer informatie over het aanvragen van herstel](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a>Bestand voor uitzondering

Als alternatief voor een herstelaanvraag wanneer een aanbeveling op dit moment niet relevant is, kunt u uitzonderingen maken voor aanbevelingen. [Meer informatie over uitzonderingen](tvm-exception.md)

Alleen gebruikers met machtigingen voor het verwerken van uitzonderingen kunnen uitzondering toevoegen. [Meer informatie over RBAC-rollen.](user-roles.md)

Wanneer er een uitzondering wordt gemaakt voor een aanbeveling, is de aanbeveling niet meer actief. De aanbevelingstoestand wordt gewijzigd in **Volledige uitzondering** of **Gedeeltelijke uitzondering** (per apparaatgroep).

### <a name="how-to-create-an-exception"></a>Een uitzondering maken

Selecteer een beveiligingsaanbeveling voor wie u een uitzondering wilt maken en selecteer vervolgens **Uitzonderingsopties.**  

![Hier wordt weergegeven waar de knop voor 'uitzonderingsopties' zich bevindt in een flyout voor beveiligingsaanbeveling.](images/tvm-exception-options.png)

Vul het formulier in en verzend het. Als u al uw uitzonderingen (huidig [](tvm-remediation.md) en verleden) wilt weergeven, gaat u naar  de pagina Herstel onder het menu Beveiligingsprobleembeheer bedreiging **&** en selecteert u het tabblad Uitzonderingen. Meer informatie over het maken van een [uitzondering](tvm-exception.md#create-an-exception)

## <a name="report-inaccuracy"></a>Onnauwkeurigheid van rapport

U kunt een onwaar positief rapport rapporteren wanneer u vage, onnauwkeurige, onvolledige of al gesaneerde beveiligingsaanbevelingsgegevens ziet.

1. Open de beveiligingsaanbeveling.

2. Selecteer de drie puntjes naast de beveiligingsaanbeveling die u wilt rapporteren en selecteer vervolgens Onnauwkeurigheid **rapporteren.**

    ![Hier wordt weergegeven waar de knop Onnauwkeurigheid melden zich in een flyout voor beveiligingsaanbevelingen.](images/report-inaccuracy500.png)

3. Selecteer in het deelvenster Flyout de onnauwkeurigheidscategorie in de vervolgkeuzelijst, vul uw e-mailadres in en details over de onnauwkeurigheid.

4. Selecteer **Verzenden**. Uw feedback wordt onmiddellijk verzonden naar de experts voor bedreigings- en kwetsbaarheidsbeheer.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Blootstellingsscore](tvm-exposure-score.md)
- [Microsoft Secure Score voor apparaten](tvm-microsoft-secure-score-devices.md)
- [Beveiligingsproblemen verhelpen](tvm-remediation.md)
- [Uitzonderingen maken en weergeven voor beveiligingsaanbevelingen](tvm-exception.md)
- [Tijdlijn van het evenement](threat-and-vuln-mgt-event-timeline.md)
