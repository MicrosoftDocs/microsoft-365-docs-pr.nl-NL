---
title: BCC- en uitgebreide geadresseerden van distributiegroep behouden voor eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place beleid voor bewaring, bewaring van rechtszaken en Microsoft 365 kunt u postvakinhoud behouden om te voldoen aan de vereisten voor naleving van regelgeving en eDiscovery.
ms.openlocfilehash: f00ed951fb68778b9c62ae874c2cca964bd6cb5c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162180"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>BCC- en uitgebreide geadresseerden van distributiegroep behouden voor eDiscovery
  
In-Place bewaarbeleid voor bewaring, bewaring van rechtszaken en [Microsoft 365](./retention.md) (gemaakt in het beveiligings- & compliancecentrum) kunt u postvakinhoud behouden om te voldoen aan de vereisten voor naleving van regelgeving en eDiscovery. Informatie over geadresseerden die rechtstreeks zijn geadresseerd in de velden Aan en CC van een bericht, is standaard opgenomen in alle berichten. Het is echter mogelijk dat uw organisatie de mogelijkheid nodig heeft om details over alle geadresseerden van een bericht te zoeken en te reproduceren. Dit zijn:
  
- **Geadresseerden met het veld BCC van een bericht:** BCC-geadresseerden worden opgeslagen in het bericht in het postvak van de afzender, maar niet opgenomen in kopteksten van het bericht dat bij geadresseerden wordt bezorgd. 
    
- **Geadresseerden van uitgebreide distributiegroep:** Geadresseerden die het bericht ontvangen omdat ze lid zijn van een distributiegroep waaraan het bericht is geadresseerd, in de velden Aan, CC of BCC. 
    
Exchange Online en Exchange Server 2013 (cumulatieve update 7 en nieuwere versies) bewaren informatie over BCC- en uitgebreide geadresseerden van distributiegroepen. U kunt naar deze informatie zoeken met behulp van een In-Place eDiscovery-zoekopdracht in het Exchange-beheercentrum (EAC) of een inhoudszoekactie in het beveiligings- & Compliancecentrum. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Hoe BCC-geadresseerden en uitgebreide geadresseerden van distributiegroepen behouden blijven

Zoals eerder vermeld, wordt informatie over BCC'ed-geadresseerden opgeslagen met het bericht in het postvak van de afzender. Deze informatie wordt geïndexeerd en beschikbaar voor eDiscovery-zoekopdrachten en -in- en uit-standen. 
  
Informatie over geadresseerden van uitgebreide distributiegroep wordt opgeslagen met het bericht nadat u een postvak hebt In-Place in de wacht- of procesopslag. In Office 365 wordt deze informatie ook opgeslagen wanneer een Microsoft 365 bewaarbeleid wordt toegepast op een postvak. Het lidmaatschap van de distributiegroep wordt bepaald op het moment dat het bericht wordt verzonden. De uitgebreide lijst met geadresseerden die is opgeslagen met het bericht, wordt niet beïnvloed door wijzigingen in het lidmaatschap van de groep nadat het bericht is verzonden. 
  
| Informatie over... | Wordt opgeslagen in... | Wordt standaard opgeslagen? | Is toegankelijk voor... |
|:-----|:-----|:-----|:-----|
|Aan- en CC-geadresseerden  <br/> |Berichteigenschappen in de postvakken van de afzender en geadresseerden.  <br/> |Ja  <br/> |Afzender, geadresseerden en compliancemedewerkers  <br/> |
|BCC-geadresseerden  <br/> |De eigenschap Bericht in het postvak van de afzender.  <br/> |Ja  <br/> |Afzender- en compliancemedewerkers  <br/> |
|Geadresseerden van uitgebreide distributiegroep  <br/> |Berichteigenschappen in het postvak van de afzender.  <br/> |Nee. Uitgebreide gegevens van geadresseerden van distributiegroep worden opgeslagen nadat een postvak is geplaatst In-Place bewaring of bewaring van rechtszaken of is toegewezen aan een Microsoft 365 bewaarbeleid.  <br/> |Compliance officers  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Zoeken naar berichten die zijn verzonden naar BCC- en uitgebreide geadresseerden van distributiegroep

Wanneer u zoekt naar berichten die naar een geadresseerde zijn verzonden, bevatten eDiscovery-zoekresultaten nu berichten die zijn verzonden naar een distributiegroep waar de geadresseerde lid van is. In de volgende tabel ziet u de scenario's waarin berichten die worden verzonden naar BCC en geadresseerden van uit uitgebreide distributiegroep, worden geretourneerd in eDiscovery-zoekopdrachten.
  
Scenario 1: Jan is lid van de US-Sales distributiegroep. In deze tabel worden eDiscovery-zoekresultaten weergegeven wanneer Bob een bericht rechtstreeks of indirect via een distributiegroep naar Jan verzendt.
  
| Wanneer u in het postvak van Bob zoekt naar verzonden berichten... | En het bericht wordt verzonden met... | Resultaten bevatten bericht? |
|:-----|:-----|:-----|
|Naar:Jan  <br/> |John op TO  <br/> |Ja  <br/> |
|Naar:Jan  <br/> |US-Sales op TO  <br/> |Ja  <br/> |
|To:US-Sales  <br/> |US-Sales op TO  <br/> |Ja  <br/> |
|CC:Jan  <br/> |Jan op CC  <br/> |Ja  <br/> |
|CC:Jan  <br/> |US-Sales op CC  <br/> |Ja  <br/> |
|CC:US-Sales  <br/> |US-Sales op CC  <br/> |Ja  <br/> |
   
Scenario 2: Bob stuurt een e-mail naar Jan (To/CC) en Jack (BCC rechtstreeks of indirect via een distributiegroep). In de onderstaande tabel ziet u de zoekresultaten van eDiscovery.
  
| Wanneer u zoekt... | Voor verzonden berichten... | Resultaten bevatten bericht? | Opmerkingen |
|:-----|:-----|:-----|:-----|
|Postvak van Bob  <br/> |To/cc:John  <br/> |Ja  <br/> |Geeft een indicatie dat Jack BCC'ed was.  <br/> |
|Postvak van Bob  <br/> |BCC:Jack  <br/> |Ja  <br/> |Geeft een indicatie dat Jack BCC'ed was.  <br/> |
|Postvak van Bob  <br/> |BCC:Jack (via distributiegroep)  <br/> |Ja  <br/> |De lijst met leden van de BCC'ed-distributiegroep, die is uitgebreid wanneer het bericht is verzonden, is zichtbaar in eDiscovery-zoekvoorbeeld, export en logboeken.  <br/> |
|Postvak van Jan  <br/> |To/cc:John  <br/> |Ja  <br/> |Geen indicatie van BCC-geadresseerden.  <br/> |
|Postvak van Jan  <br/> |BCC:Jack (rechtstreeks of via distributiegroep)  <br/> |Nee  <br/> |BCC-gegevens worden niet opgeslagen in het bericht dat wordt bezorgd bij geadresseerden. U moet zoeken in het postvak van de afzender.  <br/> |
|Postvak van Jack  <br/> |To/CC:John (rechtstreeks of via distributiegroep)  <br/> |Ja  <br/> |To/CC-informatie wordt opgenomen in het bericht dat wordt bezorgd bij alle geadresseerden.  <br/> |
|Postvak van Jack  <br/> |BCC:Jack (rechtstreeks of via distributiegroep)  <br/> |Nee  <br/> |BCC-gegevens worden niet opgeslagen in het bericht dat wordt bezorgd bij geadresseerden. U moet zoeken in het postvak van de afzender.  <br/> |
   
## <a name="frequently-asked-questions"></a>Veelgestelde vragen

 **V. Wanneer en waar worden gegevens van BCC-geadresseerden opgeslagen?**
  
A. BCC-geadresseerdegegevens blijven standaard behouden in het oorspronkelijke bericht in het postvak van de afzender. Als de BCC-geadresseerde een distributiegroep is, wordt het lidmaatschap van de distributiegroep alleen uitgebreid als het postvak van de afzender in bewaring staat of is toegewezen aan een Microsoft 365 bewaarbeleid.
  
 **V. Wanneer en waar wordt de lijst met geadresseerden van uitgebreide distributiegroep opgeslagen?**
  
A. Het groepslidmaatschap wordt uitgebreid op het moment dat het bericht wordt verzonden. De lijst met uitgebreide leden van de distributiegroep wordt opgeslagen in het oorspronkelijke bericht in het postvak van de afzender. Het postvak van de afzender moet zijn In-Place Bewaring, Procesophoud of toegewezen aan een Microsoft 365 bewaarbeleid.
  
 **V. Kunnen de to/cc-geadresseerden zien welke geadresseerden BCC'ed zijn?**
  
A. Nee. Deze informatie is niet opgenomen in berichtkoppen en is niet zichtbaar voor geadresseerden van To/CC. De afzender kan het veld BCC zien dat is opgeslagen in het oorspronkelijke bericht dat in zijn postvak is opgeslagen. Compliance officers kunnen deze informatie zien bij het doorzoeken van het postvak van de afzender.
  
 **V. Hoe kan ik ervoor zorgen dat geadresseerden van uitgebreide distributiegroepen altijd behouden blijven?**
  
A. Als u ervoor wilt zorgen dat uitgebreide leden van de distributiegroep altijd behouden blijven met een [bericht,](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) zet u alle postvakken in bewaring of maakt u een organisatiebrede Microsoft 365 bewaarbeleid. 
  
 **V. Welke typen groepen worden ondersteund?**
  
A. Distributiegroepen, beveiligingsgroepen met e-mail en dynamische distributiegroepen worden ondersteund. 
  
 **V. Is er een limiet voor het aantal geadresseerden van distributiegroepen dat in het bericht wordt uitgebreid en opgeslagen?**
  
A. Maximaal 10.000 leden van een distributiegroep blijven behouden.
  
 **V. Worden geneste distributiegroepen ondersteund?**
  
A. Ja, 25 niveaus van geneste distributiegroepen worden uitgebreid.
  
 **V. Waar zijn de BCC- en uitgebreide geadresseerdegegevens van de distributiegroep zichtbaar?**
  
A. BCC- en uitgebreide informatie over geadresseerden van distributiegroepen is zichtbaar voor compliancemedewerkers bij het uitvoeren van een eDiscovery-zoekopdracht. Geadresseerden van BCC en uitgebreide distributiegroep worden opgenomen in zoekresultaten die naar een Discovery-postvak worden gekopieerd of geëxporteerd naar een PST-bestand en in het eDiscovery-logboek dat is opgenomen in de zoekresultaten. BCC-geadresseerdegegevens zijn ook beschikbaar in het zoekvoorbeeld.
  
 **V. Wat gebeurt er als een lid van een distributiegroep is verborgen in de algemene adreslijst (GAL) van de organisatie?**
  
A. Er is geen effect. Als geadresseerden verborgen zijn voor de gal, worden ze nog steeds opgenomen in de lijst met geadresseerden voor de uitgebreide distributiegroep.