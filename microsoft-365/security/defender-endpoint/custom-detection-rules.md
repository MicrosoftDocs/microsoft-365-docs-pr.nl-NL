---
title: Aangepaste detectieregels maken in Microsoft Defender ATP
ms.reviewer: ''
description: Meer informatie over het maken van aangepaste detectieregels op basis van geavanceerde zoekquery's
keywords: aangepaste detecties, maken, beheren, waarschuwingen, bewerken, uitvoeren op aanvraag, frequentie, interval, detectieregels, geavanceerd zoeken, jagen, query, antwoordacties, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500499"
---
# <a name="create-custom-detection-rules"></a>Aangepaste detectieregels maken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Met aangepaste detectieregels die zijn gebaseerd op geavanceerde zoekquery's, kunt u proactief verschillende gebeurtenissen en systeemstaten controleren, waaronder vermoedelijke inbreukactiviteit en verkeerd geconfigureerde apparaten. [](advanced-hunting-overview.md) U kunt instellen dat ze regelmatig worden uitgevoerd, waarschuwingen genereren en antwoordacties uitvoeren wanneer er overeenkomsten zijn.

Lees dit artikel voor meer informatie over het maken van nieuwe aangepaste detectieregels. Of [bekijk bestaande regels weergeven en beheren.](custom-detections-manage.md)

> [!NOTE]
> Als u aangepaste detecties wilt maken of beheren, [moet uw](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) rol de machtiging **beveiligingsinstellingen** beheren hebben.

## <a name="1-prepare-the-query"></a>1. De query voorbereiden.

Ga in het Microsoft Defender-beveiligingscentrum naar **Geavanceerd zoeken** en selecteer een bestaande query of maak een nieuwe query. Wanneer u een nieuwe query gebruikt, moet u de query uitvoeren om fouten te identificeren en mogelijke resultaten te begrijpen.

>[!IMPORTANT]
>Als u wilt voorkomen dat de service te veel waarschuwingen retourneert, is elke regel beperkt tot het genereren van slechts 100 waarschuwingen wanneer deze wordt uitgevoerd. Voordat u een regel maakt, kunt u de query aanpassen om te voorkomen dat u een waarschuwing voor normale, dagelijkse activiteiten uitvoert.

### <a name="required-columns-in-the-query-results"></a>Vereiste kolommen in de queryresultaten

Als u een query wilt gebruiken voor een aangepaste detectieregel, moet de query de volgende kolommen retourneren:

- `Timestamp`
- `DeviceId`
- `ReportId`

Eenvoudige query's, zoals query's die de operator of operator niet gebruiken om resultaten aan te passen of te aggregeren, retourneert meestal `project` `summarize` deze algemene kolommen.

Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren. Als u bijvoorbeeld de voorkeur geeft aan aggregeren en tellen op , kunt u ze nog steeds retourneren en deze verkrijgen van de meest recente gebeurtenis waarbij elk `DeviceId` `Timestamp` apparaat is `ReportId` betrokken.

De voorbeeldquery hieronder telt het aantal unieke apparaten () met antivirusdetecties en gebruikt deze om alleen die apparaten met meer dan `DeviceId` vijf detecties te vinden. Als u de meest recente `Timestamp` en de bijbehorende `ReportId` functie wilt retourneren, wordt de `summarize` operator met de functie `arg_max` gebruikt.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Voor betere queryprestaties stelt u een tijdfilter in dat overeenkomt met de geplande runfrequentie voor de regel. Aangezien de minst voorkomende run elke 24 uur is, worden alle nieuwe gegevens bestrijken door te filteren op de afgelopen dag.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. Maak een nieuwe regel en geef waarschuwingsdetails op.

Met de query in de queryeditor selecteert u **Detectieregel maken** en geeft u de volgende waarschuwingsdetails op:

- **Detectienaam**:naam van de detectieregel
- **Frequentie:** interval voor het uitvoeren van de query en het uitvoeren van actie. [Zie aanvullende richtlijnen hieronder](#rule-frequency)
- **Waarschuwingstitel**: titel weergegeven met waarschuwingen die door de regel worden geactiveerd
- **Ernst : potentieel** risico van het onderdeel of de activiteit die door de regel is geïdentificeerd. [Lees meer over ernst van waarschuwingen](alerts-queue.md#severity)
- **Categorie**(type bedreigingsonderdeel of -activiteit, indien van het type). [Meer informatie over waarschuwingscategorieën](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK-technieken**: een of meer aanvalstechnieken die door de regel zijn geïdentificeerd, zoals beschreven in het MITRE ATT-&CK-framework. Deze sectie is niet beschikbaar met bepaalde waarschuwingscategorieën, zoals malware, ransomware, verdachte activiteiten en ongewenste software
- **Beschrijving**: meer informatie over het onderdeel of de activiteit die door de regel is geïdentificeerd 
- **Aanbevolen acties**: aanvullende acties die reageren op een waarschuwing

Lees meer over de waarschuwingswachtrij voor meer informatie over hoe waarschuwingsgegevens [worden weergegeven.](alerts-queue.md)

### <a name="rule-frequency"></a>Regelfrequentie

Wanneer u deze opgeslagen hebt, wordt er onmiddellijk een nieuwe aangepaste detectieregel uitgevoerd en wordt gecontroleerd op overeenkomsten uit de afgelopen 30 dagen met gegevens. De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen en duur van terugkijken op basis van de frequentie die u kiest:

- **Elke 24 uur :** wordt elke 24 uur uitgevoerd en controleert gegevens uit de afgelopen 30 dagen
- **Elke 12 uur :** wordt elke 12 uur uitgevoerd en controleert gegevens uit de afgelopen 24 uur
- **Elke 3 uur :** wordt elke 3 uur uitgevoerd en controleert gegevens uit de afgelopen 6 uur
- **Elk uur**: wordt elk uur uitgevoerd en de gegevens van de afgelopen 2 uur worden gecontroleerd

Wanneer u een regel bewerkt, worden deze uitgevoerd met de toegepaste wijzigingen in de volgende run time die is gepland op basis van de frequentie die u hebt ingesteld.


> [!TIP]
> De tijdfilters in de query overeenkomen met de duur van de terugblik. Resultaten buiten de terugblikduur worden genegeerd.

Selecteer de frequentie die overeenkomt met de manier waarop u detecties wilt controleren en houd rekening met de capaciteit van uw organisatie om op de waarschuwingen te reageren.

## <a name="3-choose-the-impacted-entities"></a>3. Kies de beïnvloede entiteiten.

Identificeer de kolommen in de queryresultaten waar u de belangrijkste beïnvloede of beïnvloede entiteit verwacht te vinden. Een query kan bijvoorbeeld zowel apparaat- als gebruikers-ID's retourneren. Door te bepalen welke van deze kolommen de belangrijkste beïnvloede entiteit vertegenwoordigt, kan de service relevante waarschuwingen, correlerende incidenten en doelreactieacties aggregeren.

U kunt slechts één kolom selecteren voor elk entiteitstype. Kolommen die niet door uw query worden geretourneerd, kunnen niet worden geselecteerd.

## <a name="4-specify-actions"></a>4. Geef acties op.

Uw aangepaste detectieregel kan automatisch acties uitvoeren op bestanden of apparaten die door de query worden geretourneerd.

### <a name="actions-on-devices"></a>Acties op apparaten

Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:

- **Isolatieapparaat:** hiermee wordt volledige netwerkisolatie toegepast, waardoor het apparaat geen verbinding kan maken met een toepassing of service, met uitzondering van de Defender for Endpoint-service. [Meer informatie over apparaatisolatie](respond-machine-alerts.md#isolate-devices-from-the-network)
- **Verzamel onderzoekspakket:** verzamelt apparaatgegevens in een ZIP-bestand. [Meer informatie over het onderzoekspakket](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **Antivirusscan uitvoeren**: voert een volledige Microsoft Defender Antivirus-scan uit op het apparaat
- **Onderzoek starten**: start een [geautomatiseerd onderzoek](automated-investigations.md) op het apparaat
- **De uitvoering van apps** beperken: stelt beperkingen in op het apparaat om alleen bestanden toe te staan die zijn ondertekend met een door Microsoft uitgegeven certificaat. [Meer informatie over het beperken van het uitvoeren van apps](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>Acties op bestanden

Deze acties worden toegepast op bestanden in de `SHA1` of de kolom van de `InitiatingProcessSHA1` queryresultaten:

- **Toestaan/blokkeren:** hiermee wordt het bestand automatisch toegevoegd aan de lijst met aangepaste [indicators,](manage-indicators.md) zodat het bestand altijd kan worden uitgevoerd of geblokkeerd. U kunt het bereik van deze actie zo instellen dat deze alleen wordt genomen voor geselecteerde apparaatgroepen. Dit bereik is onafhankelijk van het bereik van de regel.
- **Quarantainebestand**: verwijdert het bestand van de huidige locatie en plaatst een kopie in quarantaine

### <a name="actions-on-users"></a>Acties voor gebruikers

- **Als gebruiker markeren als gecompromitteerd:** hiermee wordt het risiconiveau van de gebruiker in Azure Active Directory op 'hoog' gebracht, wat het bijbehorende [identiteitsbeveiligingsbeleid activeert.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. Stel het regelbereik in.

Stel het bereik in om op te geven welke apparaten onder de regel vallen:

- Alle apparaten
- Specifieke apparaatgroepen

Alleen gegevens van apparaten in bereik worden opgevraagd. Acties worden ook alleen op die apparaten ondernomen.

## <a name="6-review-and-turn-on-the-rule"></a>6. Controleer de regel en schakel deze in.

Nadat u de regel heeft beoordeeld, **selecteert u Maken om** deze op te slaan. De aangepaste detectieregel wordt onmiddellijk uitgevoerd. Deze wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en antwoordacties uit te voeren.

U kunt [aangepaste detectieregels weergeven en beheren,](custom-detections-manage.md)de vorige runs controleren en de waarschuwingen controleren die ze hebben geactiveerd. U kunt ook een regel op aanvraag uitvoeren en deze wijzigen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Aangepaste detectieregels weergeven en beheren](custom-detections-manage.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De geavanceerde zoekquerytaal leren](advanced-hunting-query-language.md)
- [Waarschuwingen weergeven en ordenen](alerts-queue.md)
