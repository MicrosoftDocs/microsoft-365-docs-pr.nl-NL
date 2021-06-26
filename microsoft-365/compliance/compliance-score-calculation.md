---
title: Berekening van nalevingsscore
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over hoe Microsoft Compliance Manager een persoonlijke score berekent op basis van acties die zijn ondernomen om risico's aan te pakken en uw compliance-houding te verbeteren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e1e3f4b90b0a5e83a1e068cd30f76b3a8c7bb22
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149164"
---
# <a name="compliance-score-calculation"></a>Berekening van nalevingsscore

**In dit artikel:** Lees hoe Compliance Manager een compliancescore voor uw organisatie berekent. In dit artikel wordt uitgelegd hoe  u uw **score** interpreteert, wat de beoordeling van de basislijn voor gegevensbescherming **omvat,** continue monitoring en hoe verschillende soorten acties worden beheerd **en beoordeeld.**

> [!IMPORTANT]
> Aanbevelingen van Compliancebeheer mogen niet worden geïnterpreteerd als een garantie voor naleving. Het is aan u om de effectiviteit van klantbesturingselementen per regelgevingsomgeving te evalueren en te valideren. Deze services zijn onderworpen aan de voorwaarden in de [Voorwaarden voor onlineservices.](https://go.microsoft.com/fwlink/?linkid=2108910) Zie ook [Microsoft 365 licentie-richtlijnen voor beveiliging en naleving](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>Uw compliancescore lezen

Het compliancebeheerdashboard geeft uw algehele nalevingsscore weer. Deze score meet uw voortgang bij het voltooien van aanbevolen verbeteracties binnen besturingselementen. Uw score kan u helpen uw huidige nalevingshouding te begrijpen. Het kan u ook helpen om prioriteit te geven aan acties op basis van hun potentieel om risico's te beperken.

Er wordt een scorewaarde toegewezen op drie niveaus:

1. **Actiescore voor verbetering:** elke actie heeft een andere invloed op uw score, afhankelijk van het mogelijke risico

2. **Control score:** deze score is de som van de punten die zijn verdiend door het uitvoeren van verbeteracties binnen het besturingselement. Deze som wordt in zijn geheel toegepast op uw algemene nalevingsscore wanneer het besturingselement aan beide van de volgende voorwaarden voldoet:
    - **Implementatiestatus** is gelijk **aan Geïmplementeerd of** Alternatieve **implementatie** en
    - **Testresultaat** is gelijk aan **Geslaagd**.

3. **Beoordelingsscore:** deze score is de som van uw controlescores. Deze wordt berekend aan de hand van actiescores. Elke Actie van Microsoft en elke verbeteringsactie die door uw organisatie wordt beheerd, wordt eenmaal geteld, ongeacht hoe vaak in een besturingselement wordt verwezen.

De algemene nalevingsscore wordt berekend met actiescores, waarbij elke Actie van Microsoft eenmaal wordt geteld, elke technische actie die u beheert één keer wordt geteld en elke niet-technische actie die u beheert, eenmaal per groep wordt geteld. Deze logica is ontworpen om de meest nauwkeurige boekhouding te bieden van de manier waarop acties worden geïmplementeerd en getest in uw organisatie. U merkt mogelijk dat hierdoor uw algemene nalevingsscore kan afwijken van het gemiddelde van uw beoordelingsscores. Lees hieronder meer over [hoe acties worden gescoord.](#action-types-and-points)

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Eerste score op basis Microsoft 365 basislijn gegevensbescherming
  
Compliance Manager geeft u een eerste score op basis van de Microsoft 365 basislijn voor gegevensbescherming. Deze basislijn is een set besturingselementen met belangrijke voorschriften en standaarden voor gegevensbescherming en algemeen gegevensbeheer. Deze basislijn haalt hoofdzakelijk elementen uit NIST CSF (National Institute of Standards and Technology Cyberbeveiligingskader) en ISO (International Organization for Standardization), evenals uit FedRAMP (Federal Risk and Authorization Management Program) en GDPR (General Data Protection Regulation of the European Union).

De eerste score wordt berekend op basis van de standaardbeoordeling basislijn gegevensbescherming die aan alle organisaties is verstrekt. Bij uw eerste bezoek verzamelt Compliance Manager al signalen van uw Microsoft 365 oplossingen. U ziet in één oogopslag hoe uw organisatie presteert ten opzichte van belangrijke standaarden en voorschriften voor gegevensbescherming en ziet voorgestelde verbeteracties.

Omdat elke organisatie specifieke behoeften heeft, vertrouwt Compliance Manager op u om beoordelingen in te stellen en te beheren om risico's zo veel mogelijk te minimaliseren en te beperken.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Hoe Compliance Manager besturingselementen continu beoordeelt

Compliance Manager scant automatisch uw Microsoft 365 omgeving en detecteert uw systeeminstellingen, continu en automatisch uw technische actiestatus bijwerken. Microsoft Secure Score is de onderliggende engine die de monitoring uitvoert.

Uw actiestatus wordt elke 24 uur bijgewerkt op uw dashboard. Wanneer u een aanbeveling volgt om een besturingselement te implementeren, ziet u meestal de status van het besturingselement dat de volgende dag wordt bijgewerkt.

Als u bijvoorbeeld meervoudige verificatie (MFA) inschakelen in de Azure AD-portal, wordt de instelling gedetecteerd en wordt deze weergegeven in de details van de oplossing voor besturingselementtoegang. Als u MFA echter niet hebt in- of uit- gezet, markeert Compliance Manager dit als een aanbevolen actie die u moet ondernemen.

Meer informatie over [Secure Score en hoe deze werkt.](../security/defender/microsoft-secure-score.md)
  
## <a name="action-types-and-points"></a>Actietypen en punten

Compliance manager houdt twee soorten acties bij:

1. **Uw verbeteracties:** acties die uw organisatie beheert.
2. **Microsoft-acties:** acties die door Microsoft worden beheert.

Beide typen acties hebben punten die meetellen voor de totale score wanneer ze zijn voltooid.

### <a name="technical-and-non-technical-actions"></a>Technische en niet-technische acties

Acties worden gegroepeerd op technische of niet-technische aard. Het scoreeffect van elke actie verschilt per type.

- **Technische acties** worden geïmplementeerd door te werken met de technologie van een oplossing (bijvoorbeeld door een configuratie te wijzigen). De punten voor technische acties worden eenmaal per actie toegekend, ongeacht het aantal groepen.

- **Niet-technische acties** worden beheerd door uw organisatie en geïmplementeerd op andere manieren dan het werken met de technologie van een oplossing. Er zijn twee soorten niet-technische acties: **documentatie** en **operationeel.** De punten voor deze acties worden toegepast op de nalevingsscore op groepsniveau. Dit betekent dat als een actie in meerdere groepen bestaat, u de puntwaarde van de actie ontvangt telkens wanneer u deze in een groep implementeert.

**Voorbeeld van de manier waarop technische en niet-technische acties worden gescored:**

Stel dat u een technische actie hebt met een waarde van 3 punten die bestaat uit 5 groepen en dat u een niet-technische actie hebt met een waarde van 3 punten die bestaat uit dezelfde 5 groepen.

Als u de technische actie hebt geïmplementeerd, is het totale aantal punten dat u ontvangt 3. Dit komt omdat u de actie slechts één keer hoeft te implementeren voor uw tenant. De implementatie- en teststatus voor de technische actie wordt in alle gevallen van die actie hetzelfde weergeven, in elke groep waar deze deel van uitmaken.

Als u de niet-technische actie in elk van de 5 groepen hebt geïmplementeerd, is het totale aantal punten dat u ontvangt 15. Dit komt omdat u de actie in elke groep moet implementeren. De implementatie- en teststatus voor de niet-technische actie verschilt per groep, omdat de actie afzonderlijk binnen elk van de groepen wordt geïmplementeerd.

Deze scorelogica is ontworpen om de meest nauwkeurige boekhouding te bieden van de manier waarop acties worden geïmplementeerd en getest in uw organisatie.

### <a name="how-score-values-are-determined"></a>De manier waarop scorewaarden worden bepaald
 
Acties krijgen een scorewaarde toegewezen op basis van of ze verplicht of discretionair zijn, en of ze preventief, foutief of corrigerend zijn.

### <a name="mandatory-and-discretionary-actions"></a>Verplichte en discretionaire acties

 - **Verplichte acties** kunnen niet opzettelijk of per ongeluk worden overgeslagen. Een voorbeeld van een verplichte actie is een centraal beheerd wachtwoordbeleid dat vereisten stelt voor wachtwoordlengte, complexiteit en verloop. Gebruikers moeten deze vereisten volgen om toegang te krijgen tot het systeem.
  
 - **Discretionaire acties zijn** afhankelijk van gebruikers om een beleid te begrijpen en na te leven. Een beleid waarbij gebruikers bijvoorbeeld worden verplicht hun computer te vergrendelen wanneer ze de computer verlaten, is een discretionaire actie omdat deze afhankelijk is van de gebruiker.
  
### <a name="preventative-detective-and-corrective-actions"></a>Preventieve, recherche- en corrigerende acties
  
 - **Preventieve acties richten** zich op specifieke risico's. Het beveiligen van gegevens in rust met behulp van versleuteling is bijvoorbeeld een preventief middel tegen aanvallen en inbreuken. Scheiding van rechten is een preventief optreden om belangenverstrengeling te beheren en fraude te beschermen.
  
 - **Met detectieacties** worden systemen actief gecontroleerd om onregelmatige omstandigheden of gedragingen te identificeren die risico's vertegenwoordigen, of die kunnen worden gebruikt om inbraken of inbreuken op te sporen. Voorbeelden hiervan zijn systeemtoegangscontrole en bevoorrechte beheeracties. Nalevingsaudits voor regelgeving zijn een soort actie van de recherche die wordt gebruikt om procesproblemen op te lossen.
  
- **Corrigerende acties** proberen de negatieve effecten van een beveiligingsincident tot een minimum te beperken, corrigerende actie te ondernemen om het onmiddellijke effect te beperken en de schade zo mogelijk terug te draaien. Reactie op privacy-incidenten is een corrigerende actie om schade te beperken en systemen te herstellen naar een operationele status na een inbreuk.
  
Elke actie heeft een toegewezen waarde in Compliance Manager op basis van het risico dat deze vertegenwoordigt:

|**Type**|**Toegewezen score**|
|:-----|:-----|
| Preventief verplicht | 27 |
| Preventief discretionair | 9 |
| Detective verplicht | 3 |
| Discretionaire bevoegdheid van de recherche | 1 |
| Corrigerend verplicht | 3 |
| Correctieve discretionaire bevoegdheid | 1 |
  
![Actiepuntwaarden compliancebeheer](../media/compliance-score-action-scoring.png "Actiepuntwaarden compliancebeheer")