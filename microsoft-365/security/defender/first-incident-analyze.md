---
title: Stap 1. Triage en analyseer uw eerste incident
description: Hoe triage en begin de analyse van uw eerste incident in Microsoft 365 Defender.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365, incidentrespons, cyberaanvallen
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
ms.openlocfilehash: 8eb36ca630a9748de07c5cbe84f0e43ef23a47cf
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841076"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Stap 1. Triage en analyseer uw eerste incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Terwijl u enige tijd besteedt aan het opstellen, implementeren en onderhouden van beveiligingsmaatregelen volgens de standaarden van de organisatie, kunt u beveiligingsoplossingen instellen waarmee u snel beveiligingsrisico's en bedreigingen kunt identificeren. Microsoft 365 Met Defender kunt u incidenten opsporen, triagen en onderzoeken via de ervaring met één deelvenster-van-glas, waar u de informatie kunt vinden die u nodig hebt om tijdig beslissingen te nemen. 

Wanneer een beveiligingsincident is gedetecteerd, Microsoft 365 Defender details die u nodig hebt om een incident of incidenten te triageeren of prioriteit te geven boven anderen. Nadat de prioriteit is bepaald, kunnen analisten hun energie vervolgens richten op het onderzoeken van zaken die aan hen zijn toegewezen.

## <a name="detection-by-microsoft-365-defender"></a>Detectie door Microsoft 365 Defender

Microsoft 365 Defender ontvangt waarschuwingen en gebeurtenissen van meerdere Microsoft-beveiligingsplatforms als detectiebronnen om een holistisch beeld en context van schadelijke activiteiten te maken. Dit zijn de mogelijke detectiebronnen:

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) is een eindpuntdetectie en -respons-oplossing (EDR) die gebruikmaakt van Microsoft Defender-antivirussoftware en geavanceerde bedreigingsbeveiliging in de cloud met Microsoft Security Graph. Defender for Endpoint is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. Het beschermt eindpunten tegen cyberaanvallen, detecteert geavanceerde aanvallen en datalekken, automatiseert beveiligingsincidenten en verbetert de beveiliging. 
- [Microsoft Defender voor](/defender-for-identity/what-is) identiteit is een cloudgebaseerde beveiligingsoplossing die uw on-premises Ad DS-signalen (Active Directory Domain Services) gebruikt om geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. 
- [Microsoft Cloud App Security](/cloud-app-security/) fungeert als poortwachter voor realtime toegang tussen uw zakelijke gebruikers en de cloudbronnen die ze gebruiken, waar uw gebruikers zich ook bevinden en ongeacht het apparaat dat ze gebruiken. 
- [Microsoft Defender voor Office 365](../office-365-security/overview.md) beschermt uw organisatie tegen schadelijke bedreigingen in e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen. 
- [Azure Security Center](/azure/security-center/security-center-introduction) is een geïntegreerd beveiligingsbeheersysteem voor infrastructuur dat de beveiliging van uw datacenters verbetert en geavanceerde bedreigingsbeveiliging biedt voor uw hybride werkbelastingen in de cloud en on-premises. 

In Microsoft 365 Defender worden [incidenten](incidents-overview.md) geïdentificeerd door waarschuwingen van deze verschillende detectiebronnen te correeren. In plaats van resources aan elkaar te rijgen of meerdere waarschuwingen te onderscheiden in hun respectieve incidenten, kunt u meteen beginnen met de wachtrij voor incidenten in Microsoft 365 Defender. Op deze manier kunt u incidenten op een efficiënte manier over eindpunten, identiteiten, e-mail en toepassingen triagen en de schade door een aanval beperken.

## <a name="triage-your-incidents"></a>Uw incidenten triage

Incidentrespons in Microsoft 365 Defender wordt gestart nadat u de lijst met incidenten hebt ge triaged met de aanbevolen methode van prioriteit van uw organisatie. Triage betekent dat u een niveau van urgentie of urgentie toewijst aan incidenten, dat vervolgens bepaalt in welke volgorde ze worden onderzocht. 

Een handige voorbeeldhandleiding om te bepalen welk incident prioriteit moet krijgen in Microsoft 365 Defender kan worden samengevat met de formule: *Ernst + Impact = Prioriteit.* 

- **Ernst is** het niveau dat is aangewezen door Microsoft 365 Defender en de geïntegreerde beveiligingsonderdelen. 
- **De** impact wordt bepaald door de organisatie en omvat in het algemeen een drempelwaarde voor beïnvloede gebruikers, apparaten, services (of een combinatie daarvan) en zelfs het type waarschuwing. 

Analisten starten vervolgens onderzoeken op basis van **de** prioriteitscriteria die door de organisatie zijn ingesteld.

Incidentprioriteit kan variëren, afhankelijk van de organisatie. NIST raadt ook aan rekening te houden met de functionele en informatie-impact van het incident en de herstelbaarheid.  

Het volgende is slechts één benadering van triage: 

1. Ga naar de [pagina incidenten](incidents-overview.md) om triage te starten. Hier ziet u een lijst met incidenten die van invloed zijn op uw organisatie. Standaard worden ze gerangschikt van het meest recente naar het oudste incident. Hier ziet u ook verschillende kolommen voor elk incident met onder andere de ernst, categorie, het aantal actieve waarschuwingen en beïnvloede entiteiten. U kunt de set kolommen aanpassen en de incidentwachtrij sorteren op een aantal van deze kolommen door de kolomnaam te selecteren. U kunt de wachtrij voor incidenten ook filteren op basis van uw behoeften. Zie Prioriteit geven aan incidenten voor een volledige lijst met beschikbare [filters.](incident-queue.md#available-filters)
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Voorbeeld van de incidentwachtrij"::: 

    Een voorbeeld van hoe u triage voor deze reeks incidenten kunt uitvoeren, is het prioriteit geven aan incidenten die van invloed zijn op meer gebruikers en apparaten. In dit voorbeeld kunt u prioriteit geven aan incident-id 6769 omdat dit van invloed was op het grootste aantal entiteiten: 7 apparaten, 6 gebruikers en 2 postvakken. Bovendien lijkt het incident waarschuwingen van Microsoft Defender voor identiteit te bevatten die een melding op basis van identiteit en mogelijke diefstal van referenties aangeven.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Voorbeeld van een incident met een hoge impact":::
 
2. Selecteer de cirkel naast de naam van het incident om de details te bekijken. Aan de rechterkant wordt een zijdeelvenster weergegeven, dat aanvullende informatie bevat die uw triage verder kan helpen. 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Voorbeeld van een zijvenster voor incidenten"::: 

   Als u bijvoorbeeld kijkt welke [MITRE ATT&CK-tactieken](https://attack.mitre.org/) de aanvaller heeft gebruikt op basis van de categorieën van het incident, kunt u dit incident prioriteit geven omdat de aanvaller gestolen referenties heeft gebruikt, opdracht en controle heeft ingesteld, zijbewegingen heeft uitgevoerd en bepaalde gegevens heeft geëfiltreerd. Dit suggereert dat de aanvaller al diep in het netwerk is gegaan en mogelijk vertrouwelijke informatie heeft gestolen.

   Als uw organisatie het Zero Trust-framework heeft geïmplementeerd, zou u referentiestoegang bovendien beschouwen als een belangrijke beveiligingsovertreding die de moeite waard is om prioriteit te geven.
 
   Als u omlaag schuift in het zijvenster, ziet u de specifieke beïnvloede entiteiten, zoals gebruikers, apparaten en postvakken. U kunt het blootstellingsniveau van elk apparaat en de eigenaren van de betreffende postvakken controleren.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Voorbeeld van details van een zijvenster met incidenten"::: 
 
3. Verderop in het zijvenster vindt u de bijbehorende waarschuwingen. Microsoft 365 Defender heeft de correlatie van deze waarschuwingen al uitgevoerd in één incident, waardoor u tijd en resources bespaart die beter zijn besteed aan het herstellen van de aanval. Waarschuwingen zijn verdachte en dus mogelijk schadelijke systeemgebeurtenissen die de aanwezigheid van een aanvaller in een netwerk suggereren. 

   In dit voorbeeld is vastgesteld dat 87 afzonderlijke waarschuwingen deel uitmaken van één beveiligingsincident. U kunt alle waarschuwingen bekijken om snel te zien hoe de aanval is uitgevoerd.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Voorbeeld van waarschuwingen in een zijvenster voor incidenten"::: 
 
## <a name="analyze-your-first-incident"></a>Uw eerste incident analyseren

Het is even belangrijk om de context rond waarschuwingen te begrijpen. Vaak is een waarschuwing geen afzonderlijke gebeurtenis. Er is een keten van processen die zijn gemaakt, opdrachten en acties die mogelijk niet tegelijkertijd zijn opgetreden. Daarom moet een analist zoeken naar de eerste en laatste activiteiten van de verdachte entiteit in apparaattijdlijns om de context van de waarschuwingen te begrijpen.

Er zijn meerdere manieren om gegevens te lezen en te analyseren met Microsoft 365 Defender, maar het doel voor analisten is om zo snel mogelijk op incidenten te reageren. Hoewel Microsoft 365 Defender de mean [time to Remediate (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) aanzienlijk [](m365d-autoir.md) kan verminderen via de toonaangevende functie voor geautomatiseerd onderzoek en antwoord, zijn er altijd gevallen waarvoor handmatige analyse nodig is. 

Hier volgt een voorbeeld:

1. Wanneer triageprioriteit is bepaald, begint een analist met een grondige analyse door de naam van het incident te selecteren. Op deze pagina wordt het **overzicht van incidenten weergegeven** waarin gegevens worden weergegeven op tabbladen om te helpen bij de analyse. Onder het **tabblad** Waarschuwingen wordt het type waarschuwingen weergegeven. Analisten kunnen op elke waarschuwing klikken om in te zoomen op de betreffende detectiebron. 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Voorbeeld van het tabblad Overzicht van een incident"::: 
 
    Voor een beknopte handleiding over welk domein elke detectiebron wordt beschreven, bekijkt u de [sectie](#detection-by-microsoft-365-defender) Detecteren van dit artikel.

2.  Op het **tabblad Waarschuwingen** kan een analist naar de detectiebron draaien om een uitgebreider onderzoek en analyse uit te voeren. Selecteer bijvoorbeeld Malwaredetectie met Microsoft Cloud App Security als de detectiebron de analist naar de bijbehorende waarschuwingspagina brengt.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Voorbeeld van het selecteren van een waarschuwing van een incident"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Voorbeeld van een bijbehorende pagina in Microsoft Cloud App Security"::: 
  
3.  Als u ons voorbeeld verder wilt onderzoeken, schuift u naar de onderkant van de pagina om de getroffen **gebruikers weer te geven.** Als u de activiteit en context rond de detectie van malware wilt zien, selecteert u de gebruikerspagina van Annette Hill. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Voorbeeld van een gebruikerspagina":::
  
4.  Op de gebruikerspagina staat een chronologische lijst met gebeurtenissen die beginnen met een risicovolle aanmelding vanuit een IP-adresmelding van het *TOR-netwerk.* Hoewel de achterdochtigheid van een activiteit afhankelijk is van de aard van de manier waarop een organisatie haar bedrijfsactiviteiten doet, wordt in de meeste gevallen het gebruik van The Onion Router (TOR), een netwerk waarmee gebruikers anoniem kunnen surfen op het web, in een bedrijfsomgeving mogelijk zeer onwaarschijnlijk en overbodig geacht voor normale onlinebewerkingen.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Voorbeeld van de chronologische lijst met gebeurtenissen voor een gebruiker":::
  
5.  Elke waarschuwing kan worden geselecteerd om meer informatie over de activiteit te verkrijgen. Als u bijvoorbeeld Activiteit **selecteert in een IP-adresmelding voor tor,** gaat u naar de eigen pagina van die waarschuwing. Annette is een beheerder van Office 365, wat betekent dat ze verhoogde bevoegdheden heeft en dat het bronincident mogelijk heeft geleid tot toegang tot vertrouwelijke informatie. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Voorbeeld van waarschuwingendetails voor Microsoft Cloud App Security"::: 
 
6.  Door andere waarschuwingen te selecteren, kan een analist een volledig beeld van de aanval krijgen.

## <a name="next-step"></a>Volgende stap

[![Stap 2: Informatie over het verhelpen van incidenten](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Lees hoe u [incidenten kunt verhelpen.](first-incident-remediate.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
