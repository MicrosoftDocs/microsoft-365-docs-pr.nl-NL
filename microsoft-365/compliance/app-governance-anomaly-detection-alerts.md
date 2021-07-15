---
title: Waarschuwingen voor anomaliedetectie onderzoeken
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Waarschuwingen voor anomaliedetectie onderzoeken.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420242"
---
# <a name="investigate-anomaly-detection-alerts"></a>Waarschuwingen voor anomaliedetectie onderzoeken

 Microsoft App-governance biedt beveiligingsdetecties en -waarschuwingen voor schadelijke activiteiten. Het doel van deze handleiding is om u algemene en praktische informatie te bieden over elke waarschuwing, om u te helpen bij uw onderzoeks- en hersteltaken. Deze handleiding bevat algemene informatie over de voorwaarden voor het activeren van waarschuwingen. Omdat anomaliedetecties van nature niet-deterministisch zijn, worden ze alleen geactiveerd wanneer er gedrag plaatsvindt dat afwijkt van de norm. Ten slotte kunnen sommige waarschuwingen in preview zijn, dus bekijk regelmatig de officiële documentatie voor de bijgewerkte waarschuwingsstatus.

## <a name="mitre-attck"></a>MITRE ATT&CK

Om het gemakkelijker te maken om de relatie tussen waarschuwingen voor Microsoft-app-governance en de bekende MITRE ATT&CK Matrix in kaart te brengen, hebben we de waarschuwingen gecategoriseerd op basis van hun overeenkomstige MITRE ATT&CK-tactiek. Deze aanvullende verwijzing maakt het gemakkelijker om de vermoedelijke aanvalstechniek te begrijpen die mogelijk wordt gebruikt wanneer de Microsoft Application Security en Governance-waarschuwing wordt geactiveerd.

Deze handleiding bevat informatie over het onderzoeken en oplossen van waarschuwingen voor Microsoft-app-governance in de volgende categorieën.

- Initiële toegang
- Uitvoering
- Persistentie
- Escalatie van bevoegdheden
- Ontwijking van verdediging
- Toegang tot referenties
- Verzameling
- Exfiltratie
- Impact

## <a name="security-alert-classifications"></a>Classificaties van beveiligingswaarschuwingen

Na goed onderzoek kunnen alle waarschuwingen voor Microsoft-app-governance worden geclassificeerd als een van de volgende activiteitstypen:

- Terecht-positief (TP): een waarschuwing over een bevestigde schadelijke activiteit.
- Goedaardig terecht-positief (B-TP): een waarschuwing over verdachte maar niet schadelijke activiteiten, zoals een penetratietest of andere geautoriseerde verdachte actie.
- Fout-positief (FP): een waarschuwing voor een niet-schadelijke activiteit.

## <a name="general-investigation-steps"></a>Algemene onderzoeksstappen

Gebruik de volgende algemene richtlijnen bij het onderzoeken van een type waarschuwing om een duidelijker beeld te krijgen van de mogelijke bedreiging voordat u de aanbevolen actie toepast.

- Controleer het ernstniveau van de app en vergelijk deze met de rest van de apps in uw Tenant. Met deze beoordeling kunt u bepalen welke apps in uw Tenant een groter risico vormen.
- Als u een TP identificeert, bekijk dan alle app-activiteiten om inzicht te krijgen in de impact. Bekijk bijvoorbeeld de volgende app-informatie:

  - Bereiken waarvoor toegang is verleend
  - Ongebruikelijk gedrag  
  - IP-adres en locatie

## <a name="initial-access-alerts"></a>Waarschuwingen voor initiële toegang

In deze sectie worden waarschuwingen beschreven die aangeven dat een schadelijke app probeert voet aan de grond te houden in uw organisatie.  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>Gecodeerde app-naam met verdachte toestemmingsbereiken

**Ernst**: gemiddeld

**Beschrijving**: met deze detectie worden OAuth-apps geïdentificeerd met tekens, zoals Unicode- of gecodeerde tekens, die zijn aangevraagd voor verdachte toestemmingsbereiken en die toegang hebben verkregen tot e-mailmappen van gebruikers via de Graph API. Deze waarschuwing kan duiden op een poging om een schadelijke app te camoufleren als een bekende en vertrouwde app, zodat kwaadwillenden de gebruikers kunnen misleiden om toestemming te geven voor de schadelijke app.

**TP of FP?**

- **TP-**: als u kunt bevestigen dat de OAuth-app de weergavenaam heeft gecodeerd met verdachte bereiken die afkomstig zijn van een onbekende bron, wordt een terecht-positief aangegeven.  

  **Aanbevolen actie**: controleer het machtigingsniveau dat door deze app is aangevraagd en welke gebruikers toegang hebben verleend. Op basis van uw onderzoek kunt u ervoor kiezen om de toegang tot deze app te blokkeren.

  Als u de toegang tot de app wilt blokkeren, selecteert u op de pagina OAuth-apps, in de rij met de app die u wilt blokkeren, het blokkeringspictogram. U kunt kiezen of u gebruikers wilt laten weten dat de app die ze hebben geïnstalleerd en geautoriseerd, is geblokkeerd. De melding laat gebruikers weten dat de app wordt uitgeschakeld en dat ze niet langer toegang hebben tot de verbonden app. Als u niet wilt dat ze het te weten komen, deselecteert u Gebruikers informeren die toegang hebben verleend tot deze verboden app in het dialoogvenster. We raden u aan app-gebruikers te laten weten dat hun app binnenkort wordt geblokkeerd voor gebruik.

- **FP**: als u wilt bevestigen dat de app een gecodeerde naam heeft, maar een legitiem zakelijk gebruik in de organisatie heeft.

  **Aanbevolen actie**: sluit de waarschuwing.

#### <a name="understand-the-scope-of-the-breach"></a>Inzicht in het bereik van de schending

Volg de zelfstudie over het [onderzoeken van riskante OAuth-apps](/cloud-app-security/investigate-risky-oauth).

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a>OAuth-app met leesbereiken heeft verdachte antwoord-URL

**Ernst**: gemiddeld

**Beschrijving**: deze detectie identificeert een OAuth-app met alleen leesbereiken zoals User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared omleiden naar verdachte antwoord-URL via Graph API. Met deze activiteit wordt geprobeerd aan te geven dat schadelijke apps met minder machtigingen (zoals leesbereiken) kunnen worden misbruikt om gebruikersaccountverkenningen uit te voeren.

**TP of FP?**

- **TP-**: als u kunt bevestigen dat de OAuth-app met leesbereik wordt geleverd vanuit een onbekende bron en wordt omgeleid naar een verdachte URL, wordt een terecht-positief aangegeven.

  **Aanbevolen actie**: controleer de antwoord-URL en bereiken die door de app zijn aangevraagd. Op basis van uw onderzoek kunt u ervoor kiezen om de toegang tot deze app te blokkeren. Controleer het machtigingsniveau dat door deze app is aangevraagd en welke gebruikers toegang hebben verleend.

  Als u de toegang tot de app wilt blokkeren, selecteert u op de pagina OAuth-apps, in de rij met de app die u wilt blokkeren, het blokkeringspictogram. U kunt kiezen of u gebruikers wilt laten weten dat de app die ze hebben geïnstalleerd en geautoriseerd, is geblokkeerd. De melding laat gebruikers weten dat de app wordt uitgeschakeld en dat ze niet langer toegang hebben tot de verbonden app. Als u niet wilt dat ze het te weten komen, deselecteert u Gebruikers informeren die toegang hebben verleend tot deze verboden app in het dialoogvenster. We raden u aan app-gebruikers te laten weten dat hun app binnenkort wordt geblokkeerd voor gebruik.

- **B-TP-**: als u na onderzoek kunt bevestigen dat de app een legitiem zakelijk gebruik heeft in de organisatie.

  **Aanbevolen actie**: sluit de waarschuwing.

#### <a name="understand-the-scope-of-the-breach"></a>Inzicht in het bereik van de schending 

1. Bekijk alle activiteiten die door de app zijn uitgevoerd.
1. Als u vermoedt dat een app verdacht is, raden we u aan de naam en antwoord-URL van de app te onderzoeken in verschillende app-stores. Wanneer u app-stores controleert, richt u zich op de volgende typen apps:
   - Apps die onlangs zijn gemaakt.
   - Apps met een verdachte antwoord-URL
   - Apps die niet recent zijn bijgewerkt. Als er geen updates zijn, wordt de app mogelijk niet meer ondersteund.
1. Als u nog steeds vermoedt dat een app verdacht is, kunt u de naam van de app, de naam van de uitgever en de antwoord-URL online onderzoeken  

## <a name="persistence-alerts"></a>Persistentiewaarschuwingen

In deze sectie worden waarschuwingen beschreven die aangeven dat een kwaadwillende actor probeert voet aan de grond te houden in uw organisatie.

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a>App met verdacht OAuth-bereik maakt Postvak IN-regel  

**Ernst**: gemiddeld

**MITRE-id's**: T1137.005, T1114  

Deze detectie identificeert een OAuth-app die toestemming heeft verleend voor verdachte bereiken, een verdachte regel voor Postvak IN heeft gemaakt en vervolgens de e-mailmappen en berichten van gebruikers heeft geopend via de Graph API. Regels voor Postvak IN, zoals het doorsturen van alle of specifieke e-mailberichten naar een ander e-mailaccount en Graph-aanroepen voor toegang tot e-mailberichten en het verzenden naar een ander e-mailaccount, kunnen een poging zijn om gegevens van uw organisatie te exfiltreren.  

**TP of FP?**

- **TP**: als u kunt bevestigen dat de regel voor postvak IN is gemaakt door een OAuth-app van derden met verdachte bereiken die afkomstig zijn van een onbekende bron, wordt een terecht-positief aangegeven.

  **Aanbevolen actie**: de app uitschakelen en verwijderen, het wachtwoord opnieuw instellen en de regel postvak IN verwijderen.

  Volg de zelfstudie over het opnieuw instellen van een wachtwoord met Azure Active Directory en volg de zelfstudie over het verwijderen van regels voor Postvak IN.

- **FP**: als u kunt bevestigen dat de app om legitieme redenen een regel voor postvak IN heeft gemaakt voor een nieuw of persoonlijk extern e-mailaccount.

  **Aanbevolen actie**: sluit de waarschuwing.

#### <a name="understand-the-scope-of-the-breach"></a>Inzicht in het bereik van de schending

1. Bekijk alle activiteiten die door de app zijn uitgevoerd.
1. Controleer de bereiken die door de app zijn verleend.
1. Controleer de regelactie en voorwaarde voor postvak IN die door de app zijn gemaakt.

## <a name="collection-alerts"></a>Verzamelingswaarschuwingen

In deze sectie worden waarschuwingen beschreven die aangeven dat een kwaadwillende actor mogelijk gegevens probeert te verzamelen die van belang zijn voor het doel van uw organisatie.

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>App heeft afwijkende Graph-aanroepen gedaan om e-mail te lezen

**Ernst**: gemiddeld

**MITRE-ID**: T1114

Deze detectie identificeert wanneer de Line of Business (LOB) OAuth-app toegang krijgt tot een ongebruikelijk en groot aantal e-mailmappen en berichten van gebruikers via de Graph API, wat kan wijzen op een poging tot inbreuk op uw organisatie.

**TP of FP?**

- **TP**: als u kunt bevestigen dat de ongebruikelijke Graph-activiteit is uitgevoerd door de Line of Business (LOB) OAuth-app, wordt een terecht-positief aangegeven.

  **Acties aanbevelen**: schakel de app tijdelijk uit, stel het wachtwoord opnieuw in en schakel de app opnieuw in.

  Volg de zelfstudie over het Opnieuw instellen van een wachtwoord met behulp van Azure Active Directory.

- **FP**: als u kunt bevestigen dat de app is bedoeld om ongebruikelijk grote hoeveelheden Graph-aanroepen uit te voeren.

  **Aanbevolen actie**: sluit de waarschuwing.

#### <a name="understand-the-scope-of-the-breach"></a>Inzicht in het bereik van de schending

1. Controleer het activiteitenlogboek op gebeurtenissen die door deze app worden uitgevoerd om meer inzicht te krijgen in andere Graph-activiteiten om e-mailberichten te lezen en gevoelige e-mailgegevens van gebruikers te verzamelen.
1. Controleer op onverwachte referenties die worden toegevoegd aan de app.
