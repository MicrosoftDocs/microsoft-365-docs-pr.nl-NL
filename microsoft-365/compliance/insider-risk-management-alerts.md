---
title: Waarschuwingen voor insiderrisicobeheer
description: Meer informatie over waarschuwingen voor insiderrisicobeheer in Microsoft 365
keywords: Microsoft 365, insider risk, risk management, compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0ee3fdf19552ee80737f6758e655d297228c469e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226549"
---
# <a name="insider-risk-management-alerts"></a>Waarschuwingen voor insiderrisicobeheer

Waarschuwingen voor insiderrisicobeheer worden automatisch gegenereerd door risicoindicatoren die zijn gedefinieerd in beleidsregels voor insiderrisicobeheer. Deze waarschuwingen geven compliance-analisten en -onderzoekers een overzicht van de huidige risicostatus en stellen uw organisatie in staat om te triagen en acties te ondernemen voor ontdekte risico's. Standaard genereren beleidsregels een bepaalde hoeveelheid waarschuwingen met een lage, [](insider-risk-management-settings.md#alert-volume) gemiddelde en hoge ernst, maar u kunt het waarschuwingsvolume naar uw wensen verhogen of verlagen. Bovendien kunt u de waarschuwingsdrempel [voor beleidsindicatoren](insider-risk-management-settings.md#indicator-level-settings-preview) configureren bij het maken van een nieuw beleid met de beleidswizard.

Bekijk de [Video Triage-ervaring](https://www.youtube.com/watch?v=KgmpxBLJLPI) met waarschuwingen voor insiderrisicobeheer voor een overzicht van hoe waarschuwingen details, context en gerelateerde inhoud bieden voor risicovolle activiteiten en hoe u uw onderzoeksproces effectiever kunt maken.

## <a name="alert-dashboard"></a>Waarschuwingsdashboard

Met het dashboard Insider Risk **Alert** kunt u waarschuwingen die worden gegenereerd door beleidsregels voor insiderrisico's bekijken en erop reageren. Elke rapportwidget bevat gegevens van de afgelopen 30 dagen.

- **Totaal aantal waarschuwingen dat moet** worden beoordeeld: Het totale aantal waarschuwingen dat moet worden beoordeeld en drie keer moet worden beoordeeld, inclusief een uitsplitsing op ernst van de waarschuwing.
- **Waarschuwingen openen in de afgelopen 30** dagen: het totale aantal waarschuwingen dat is gemaakt door beleid komt overeen met de afgelopen 30 dagen, gesorteerd op hoge, gemiddelde en lage ernst van waarschuwingen.
- **Gemiddelde tijd om waarschuwingen op te lossen:** een overzicht van nuttige waarschuwingsstatistieken:
  - Gemiddelde tijd om waarschuwingen met hoge ernst op te lossen, weergegeven in uren, dagen of maanden.
  - Gemiddelde tijd om waarschuwingen met gemiddelde ernst op te lossen, weergegeven in uren, dagen of maanden.
  - Gemiddelde tijd om waarschuwingen met een lage ernst op te lossen, weergegeven in uren, dagen of maanden.

![Waarschuwingsdashboard voor insiderrisicobeheer](../media/insider-risk-alerts-dashboard.png)

> [!NOTE]
> Insider-risicobeheer gebruikt ingebouwde waarschuwingsbeperking om uw risicoonderzoek te beschermen en te optimaliseren en de ervaring te controleren. Deze beperking beschermt tegen problemen die kunnen leiden tot een overbelasting van beleidswaarschuwingen, zoals verkeerd geconfigureerde gegevensconnectoren of DLP-beleid. Hierdoor kan het weergeven van nieuwe waarschuwingen voor een gebruiker vertraging oplopen.

## <a name="alert-status-and-severity"></a>Status en ernst van waarschuwing

U kunt waarschuwingen naar een van de volgende statussen triage:

- **Bevestigd:** een waarschuwing die is bevestigd en toegewezen aan een nieuwe of bestaande zaak.
- **Afgewezen:** een waarschuwing die is afgewezen als goedaardig in het triageproces.
- **Behoeften controleren:** een nieuwe waarschuwing waarbij triageacties nog niet zijn ondernomen.
- **Opgelost:** een waarschuwing die deel uitmaakt van een gesloten en opgeloste zaak.

Waarschuwingsrisicoscores worden automatisch berekend op basis van verschillende indicatoren voor risicoactiviteit. Deze indicatoren omvatten het type risicoactiviteit, het aantal en de frequentie van het optreden van de activiteit, de geschiedenis van gebruikersrisicoactiviteit en de toevoeging van activiteitenrisico's die de ernst van de activiteit kunnen verhogen. Met de waarschuwingsrisicoscore wordt de programmatische toewijzing van een ernst van het risico voor elke waarschuwing aan de gebruiker gegeven en kan deze niet worden aangepast. Als waarschuwingen niet worden afgerekend en de risicoactiviteiten nog steeds toenemen tot de waarschuwing, kan de ernst van het risico toenemen. Risicoanalisten en -onderzoekers kunnen de ernst van het waarschuwingsrisico gebruiken om waarschuwingen te triageeren in overeenstemming met het risicobeleid en de standaarden van uw organisatie.

Ernst van het waarschuwingsrisico is:

- **Hoge ernst:** De activiteiten en indicatoren voor de waarschuwing vormen een aanzienlijk risico. De bijbehorende risicoactiviteiten zijn ernstig, herhalend en sterk afhankelijk van andere significante risicofactoren.
- **Gemiddelde ernst:** De activiteiten en indicatoren voor de waarschuwing vormen een matig risico. De bijbehorende risicoactiviteiten zijn gemiddeld, frequent en hebben een correlatie met andere risicofactoren.
- **Lage ernst:** De activiteiten en indicatoren voor de waarschuwing vormen een gering risico. De bijbehorende risicoactiviteiten zijn secundair, komen minder vaak voor en vormen geen basis voor andere significante risicofactoren.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Waarschuwingen filteren op het waarschuwingsdashboard

Afhankelijk van het aantal en het type actief beleid voor insiderrisicobeheer in uw organisatie, kan het controleren van een grote wachtrij met waarschuwingen lastig zijn. Met behulp van waarschuwingsfilters kunnen analisten en onderzoekers waarschuwingen op verschillende kenmerken sorteren. Als u waarschuwingen wilt filteren op het **dashboard Waarschuwingen,** selecteert u het **besturingselement** Filter. U kunt waarschuwingen filteren op een of meer kenmerken:

- **Status:** Selecteer een of meer statuswaarden om de lijst met waarschuwingen te filteren. De opties *zijn Bevestigd*, *Afgewezen*, *Behoeften controleren* en *Opgelost*.
- **Ernst:** Selecteer een of meer ernstsniveaus voor waarschuwingsrisico's om de lijst met waarschuwingen te filteren. De opties zijn *Hoog,* *Gemiddeld* en *Laag.*
- **Tijd gedetecteerd:** Selecteer de begin- en einddatums voor wanneer de waarschuwing is gemaakt.
- **Beleid:** Selecteer een of meer beleidsregels om de waarschuwingen te filteren die worden gegenereerd door het geselecteerde beleid.

## <a name="search-alerts-on-the-alert-dashboard"></a>Zoekwaarschuwingen op het dashboard Waarschuwing

Als u in de naam van de waarschuwing naar een bepaald woord wilt zoeken, selecteert u **het** besturingselement Zoeken en typt u het woord dat u wilt zoeken. In de zoekresultaten wordt een beleidswaarschuwing weergegeven die het woord bevat dat is gedefinieerd in de zoekopdracht.

## <a name="triage-alerts"></a>Triagewaarschuwingen

Als u een insiderrisicowaarschuwing wilt triageren, volgt u de volgende stappen:

1. Ga in [Microsoft 365-compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Waarschuwingen.**
2. Selecteer in **het dashboard Waarschuwingen** de waarschuwing die u wilt triagen.
3. In het **detailvenster Waarschuwingen** kunt u de volgende tabbladen bekijken en de waarschuwing triageeren:
    - **Overzicht:** Dit tabblad bevat algemene informatie over de waarschuwing en stelt u in staat om de waarschuwing te bevestigen en een nieuw geval te maken of u kunt de waarschuwing afwijzen. Het bevat de huidige status voor de waarschuwing en het ernstniveau van het *waarschuwingsrisico,* vermeld als *Hoog,* *Gemiddeld* of Laag. Het ernstniveau kan in de tijd toenemen of afnemen als de waarschuwing niet triaged is.
        - **Wat is er gebeurd (voorbeeld)**: geeft de drie belangrijkste risicoactiviteiten en beleidswedstrijden weer tijdens de evaluatieperiode van de activiteit, inclusief het type schending dat is gekoppeld aan de activiteit en het aantal exemplaren.
        - **Gebruikersgegevens:** geeft algemene informatie weer over de gebruiker die aan de waarschuwing is toegewezen. Als anonimiseren is ingeschakeld, worden de gebruikersnaam, het e-mailadres, de alias en de organisatievelden geanonimiseerd.
        - **Waarschuwingsdetails:** Dit omvat de tijdsduur sinds de waarschuwing is gegenereerd, het beleid dat de waarschuwing heeft gegenereerd en de case die wordt gegenereerd op basis van de waarschuwing, wordt weergegeven. Voor nieuwe waarschuwingen wordt in **het veld Zaak** Geen weergegeven.
        - **Gedetecteerde inhoud (voorbeeld)**: bevat inhoud die is gekoppeld aan de risicoactiviteiten voor de waarschuwing en een overzicht van activiteitengebeurtenissen per belangrijke gebieden. Als u een activiteitskoppeling selecteert, wordt de Activiteitsverkenner geopend en worden aanvullende details over de activiteit weergegeven.
    - **Gebruikersactiviteit:** op dit tabblad wordt de activiteitengeschiedenis weergegeven voor de gebruiker die aan de waarschuwing is gekoppeld. Deze geschiedenis bevat andere waarschuwingen en activiteiten met betrekking tot risico-indicatoren die zijn gedefinieerd in de sjabloon die is toegewezen aan het beleid voor deze waarschuwing. In deze geschiedenis kunnen risicoanalisten en -onderzoekers in het verleden risicogedrag van de werknemer als onderdeel van het triageproces in rekening brengen.
    - **Acties:** De volgende acties zijn beschikbaar voor elke waarschuwing:
        - **Uit uitgebreide weergave openen:** hiermee opent u het **dashboard activiteitsverkenner.**
        - **Bevestig en maak een case:** Gebruik deze actie om een nieuw geval te bevestigen en te maken voor alle waarschuwingen die aan een gebruiker zijn gekoppeld. Met deze actie wordt de status van de waarschuwing automatisch *gewijzigd in Bevestigd.*
        - **Waarschuwing afwijzen:** gebruik deze actie om de waarschuwing te afwijzen. Met deze actie wordt de status van de waarschuwing *gewijzigd in Opgelost.*

## <a name="activity-explorer-preview"></a>Activiteitsverkenner (voorbeeld)

> [!NOTE]
> Activiteitsverkenner is beschikbaar in het waarschuwingsbeheergebied voor gebruikers met triggeringgebeurtenissen nadat deze functie beschikbaar is in uw organisatie.

De Activiteitsverkenner biedt risicoonderzoekers en -analisten een uitgebreid analytisch hulpmiddel dat gedetailleerde informatie over waarschuwingen biedt. Met de Activiteitsverkenner kunnen revisoren snel een tijdlijn bekijken van gedetecteerde riskante activiteiten en alle risicoactiviteiten identificeren en filteren die aan waarschuwingen zijn gekoppeld. Als u waarschuwingen wilt filteren in de Activiteitsverkenner, selecteert u het besturingselement Filter. U kunt waarschuwingen filteren op een of meer kenmerken die worden vermeld in het detailvenster voor de waarschuwing. Activiteitsverkenner ondersteunt ook aanpasbare kolommen om onderzoekers en analisten te helpen het dashboard te richten op de informatie die voor hen het belangrijkst is.

![Overzicht van insiderrisicobeheeractiviteitsverkenner](../media/insider-risk-activity-explorer.png)

Als u de **Activiteitsverkenner wilt** gebruiken, gaat u als volgt te werk:

1. Ga in Microsoft 365-compliancecentrum naar **Insider-risicobeheer** en selecteer het **tabblad Waarschuwingen.**
2. Selecteer in **het dashboard Waarschuwingen** de waarschuwing die u wilt triagen.
3. Selecteer in **het detailvenster Waarschuwingen** de optie **Uit uitgebreide weergave openen.**
4. Selecteer op de pagina voor de geselecteerde waarschuwing het tabblad **Activiteitsverkenner.**

Wanneer u activiteiten in de Activiteitenverkenner bekijkt, kunnen onderzoekers en analisten een specifieke activiteit selecteren en het deelvenster activiteitsdetails openen. In het deelvenster wordt gedetailleerde informatie weergegeven over de activiteit die onderzoekers en analisten kunnen gebruiken tijdens het triageproces voor waarschuwingen. De gedetailleerde informatie kan context bieden voor de waarschuwing en helpen bij het identificeren van het volledige bereik van de risicoactiviteit die de waarschuwing heeft geactiveerd.

![Details van insiderrisicobeheeractiviteit explorer](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Een case maken voor een waarschuwing

Wanneer een waarschuwing wordt gecontroleerd en triaged, kunt u een nieuwe zaak maken om de risicoactiviteit verder te onderzoeken. Als u een melding wilt maken, gaat u als volgt te werk:

1. Ga in [Microsoft 365-compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Waarschuwingen.**
2. Selecteer in **het dashboard Waarschuwingen** de waarschuwing die u wilt bevestigen en maak een nieuwe zaak voor.
3. Selecteer in **het deelvenster Waarschuwingendetails** de optie **Acties** controleren  >  **& maken.**
4. Voer in het dialoogvenster Waarschuwing bevestigen en **insiderrisicocase** maken een naam voor de zaak in, selecteer gebruikers die u wilt toevoegen als inzenders en voeg opmerkingen toe indien van toepassing. Opmerkingen worden automatisch als een notitie aan de zaak toegevoegd.
5. Selecteer **Zaak maken** om een nieuwe zaak te maken of selecteer **Annuleren** om het dialoogvenster te sluiten zonder een zaak te maken.

Nadat de zaak is gemaakt, kunnen onderzoekers en analisten de zaak beheren en handelen. Zie het [artikel Insider-case voor risicobeheer](insider-risk-management-cases.md) voor meer informatie.
