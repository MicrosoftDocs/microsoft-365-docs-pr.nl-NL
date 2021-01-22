---
title: Privacyrisico's van gegevens beoordelen en gevoelige items identificeren met Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Bepaal de regelgeving voor de privacy van gegevens, de relevante scenario's, uw gereedheid en de typen gevoelige informatie in uw Microsoft 365-omgeving.
ms.openlocfilehash: c5a1662f5e82c8b8b9439439df0ee369d45e7616
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931900"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Privacyrisico's van gegevens beoordelen en gevoelige items identificeren met Microsoft 365

Het beoordelen van de regelgeving en risico's voor de privacy van gegevens in uw organisatie is een belangrijke eerste stap voordat u verwante verbeteringsacties implementeert, waaronder acties die mogelijk zijn met Microsoft 365-functies en -services. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Mogelijk van toepassing zijnde privacyregels voor gegevens

Zie de [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) en de reeks artikelen over de Algemene Verordening Gegevensbescherming [(AVG)](../compliance/gdpr.md)en andere informatie over de regelgeving die mogelijk in uw branche of regio van toepassing is, voor een goede verwijzing naar het bredere regelgevingskader voor regelgeving met betrekking tot gegevens-privacy.

### <a name="gdpr"></a>AVG

De AVG, de meest bekende en geciteerde persoon uit de privacyregelregel voor gegevens, reguleert het verzamelen, opslaan, verwerken en delen van persoonlijke gegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon die in de Europese Unie (EU) woont. 

Volgens avg artikel 4: 

- 'persoonlijke gegevens': alle gegevens met betrekking tot een geïdentificeerde of identificeerbare natuurlijke persoon ('betrokkene'); een identificeerbare natuurlijke persoon is iemand die direct of indirect kan worden geïdentificeerd, met name door te verwijzen naar een id, zoals een naam, een identificatienummer, locatiegegevens, een online-id of aan een of meer factoren die specifiek zijn voor de fysieke, natuurlijke, genetisch, mentale, economische, culturele of sociale identiteit van die natuurlijke persoon.

### <a name="iso-27001"></a>ISO 27001

Het voldoen aan andere standaarden, zoals ISO 27001, is ook herkend door verschillende Europese leidinggevenden als een geldige proxy of intent voor de personen, het proces en de technologie in het spectrum. De standaarden die worden gespecificeerd, overlappen en voldoen aan iso-27001-gebaseerde beveiligingsmechanismen, kunnen in bepaalde omstandigheden worden beschouwd als een proxy die voldoet aan bepaalde privacyverplichtingen.

### <a name="other-data-privacy-regulations"></a>Overige privacyregels voor gegevens

In andere belangrijke privacyvoorschriften voor gegevens worden ook vereisten voor de verwerking van persoonsgegevens vermeld.

In de Verenigde Staten zijn dit de California Consumer Protection Act[(HIPA),](../compliance/ccpa-faq.md)HIPAA-HITECH (United States health care privacy act) en De Graham Leach Wordtley Act (WORDTA). Aanvullende state-specific regulations zijn ook in-place of in ontwikkeling. 

Wereldwijd zijn er andere voorbeelden van de National GDPR Implementation Act (BDSG) van Duitsland, de Brazil Data Protection Act (LGPD) en nog veel meer.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Toewijzing van regelgeving aan categorieën voor technische controle van Microsoft 365

Veel van de regelgeving met betrekking tot gegevens privacy hebben overlappende vereisten, dus u moet weten van welke regelgeving deze voorschriften afhankelijk zijn voordat u een technisch controleschema ontwikkelt. 

Voor latere naslaginformatie in de artikelen van deze algemene oplossing bevat deze tabel tekstfragmenten uit een steekproef van de privacyvoorschriften voor gegevens. 

| Regelgeving | Artikel/sectie | Fragment | Toepasselijke categorieën voor technisch beheer |
|:-------|:-----|:-------|:-------|
| AVG | Artikel 5(1)(f) | Persoonlijke gegevens worden op een manier verwerkt die de juiste beveiliging van de persoonsgegevens garandeert, met inbegrip van beveiliging tegen ongeautoriseerde of onrechtmatige verwerking en tegen onbedoelde verlies, beschadiging of beschadiging, met behulp van passende technische of organisatorische maatregelen ('integriteit en vertrouwelijkheid'.  |  (Alles) <br> Identiteit <br> Apparaat <br> Bedreigingsbeveiliging <br> Gegevens beveiligen <br> Gegevens regelen <br> Ontdekken en reageren |
|  | Artikel (32)(1)(a) | Rekening houdend met de status en de kosten van de implementatie en de aard, omvang, context en doeleinden van verwerking, en met het risico van verschillende waarschijnlijkheid en ernst voor de rechten en vrijheidsgraden van natuurlijke personen, moeten de controller en de processor passende technische en organisatorische maatregelen implementeren om te zorgen voor een beveiligingsniveau dat geschikt is voor het risico , met inbegrip van inter-ins van toepassing: (a) het gepsdonimiseerde en versleutelen van persoonlijke gegevens. | Gegevens beveiligen |
|  | Artikel (13)(2)(a) | "... op het moment dat persoonsgegevens worden verkregen, dient de controller de volgende verdere informatie te verstrekken die nodig is om een redelijke en transparante verwerking te garanderen: (a) de periode waarin de persoonsgegevens worden opgeslagen, of, indien dat niet mogelijk is, de criteria die worden gebruikt om die periode te bepalen. | Gegevens regelen |
|  | Artikel (15)(1)(e) | De onderwerpen hebben het recht om via de controllerbevestiging te bevestigen of persoonlijke gegevens met betrekking tot hem of haar al dan niet worden verwerkt, en in dat geval, toegang tot de persoonsgegevens en de volgende informatie: (e) het bestaan van het recht om een verzoek in te dienen bij de recodering van de controller of het wissen van persoonlijke gegevens of het beperken van de verwerking van persoonsgegevens met betrekking tot de betreffende persoon of het object tot een dergelijke verwerking | Ontdekken en reageren |
| LGPD | Artikel 46 | Verwerkingsagenten nemen beveiliging, technische en administratieve maatregelen over die persoonsgegevens kunnen beschermen tegen onbevoegde toegang en onbedoelde of onwettige situaties van gebruik, verlies, wijziging, communicatie of enig type onrechtmatige verwerking. | Gegevens beveiligen <br> Gegevens regelen <br> Ontdekken en reageren|
|  | Artikel 48 | De controller dient de nationale instantie en de betrokken gegevens te communiceren over het voorkomen van een beveiligingsincident die voor de betrokken onderwerpen risico's of relevante schade kan veroorzaken. | Ontdekken en reageren |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Implementeert technische beveiligingsmaatregelen om te beschermen tegen ongeautoriseerde toegang tot elektronisch beveiligde gezondheidsgegevens die worden verzonden via een elektronisch communicatienetwerk. | Gegevens beveiligen |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementeert een mechanisme om elektronisch beveiligde statusinformatie te versleutelen wanneer dit van toepassing wordt geacht. | Gegevens beveiligen |
|  | 45 CFR 164.312(c)(2) | Implementeert elektronische mechanismen om elektronisch beveiligde gezondheidsinformatie te bevestigen en niet op onbevoegde wijze te wijzigen of te vernietigen. | Gegevens regelen |
|  | 45 CFR 164.316(b)(1)(i) | Als een actie, activiteit of evaluatie door dit subdeel moet worden gedocumenteerd, behoudt u een geschreven (mogelijk elektronische) record van de actie, activiteit of evaluatie | Gegevens regelen |
|  | 45 CFR 164.316(b)(1)(ii) | Behoudt de documentatie die is vereist in de paragrafen (b)(1) van dit gedeelte 6 jaar vanaf de datum van aanmaak of vanaf de datum waarop deze laatste van kracht was, als dat later is. | Gegevens regelen |
|  | 45 C.F.R. 164,308(a)(1)(ii)(D) | Procedures implementeren om regelmatig records te controleren van activiteiten in het informatiesysteem, zoals auditlogboeken, toegangsrapporten en rapporten over het bijhouden van beveiligingsincidenden | Ontdekken en reageren |
|  | 45 C.F.R. 164,308(a)(6)(ii) | Verdachte of bekende beveiligingsincidenten identificeren en hierop reageren; verkleint, voor zover deze zich voordoen, schadelijke effecten van beveiligingsincidenten die bekend zijn bij de gedekte entiteit of het bedrijfsmedewerker; en beveiligingsincidenten en hun resultaten documenteren. | Ontdekken en reageren |
|  | 45 C.F.R. 164,312(b) | Implementeert hardware-, software- en proceduremechanismen waarmee activiteiten in informatiesystemen die elektronische beveiligde statusgegevens bevatten of gebruiken, worden registreren en onderzocht. | Ontdekken en reageren |
| A | 1798.105(c) | Een bedrijf dat een controleerbaar verzoek van een consument ontvangt om de persoonlijke gegevens van de consument uit de onderverdeling (a) van deze sectie te verwijderen, verwijdert de persoonlijke gegevens van de gebruiker uit zijn administratie en leidt alle serviceproviders aan om de persoonlijke gegevens van de consument uit zijn administratie te verwijderen. | Ontdekken en reageren |
|  | 1798.105(d) | (uitzonderingen op 1798.105(c) <br> Het is niet vereist dat een bedrijf of een serviceprovider voldoet aan een verzoek van een consument om de persoonlijke gegevens van de consument te verwijderen indien het noodzakelijk is dat de zakelijke of serviceprovider de persoonlijke gegevens van de consument onderhoudt met het oog op: (zie de huidige regelgeving voor aanvullende informatie). | Ontdekken en reageren |
|||||

>[!Important]
>Dit is niet bedoeld als een volledige lijst. Raadpleeg [Compliancebeheer](../compliance/compliance-manager.md) of uw juridische of nalevingsadviseur voor meer informatie over de geschiktheid van de geciteerde secties voor de weergegeven categorieën voor technische controle.
>

## <a name="knowing-your-data"></a>Uw gegevens kennen

Ongeacht de regelgeving waarop u van toepassing bent, zijn de verschillende gebruikersgegevenstypen binnen en buiten uw organisatie belangrijk die van invloed kunnen zijn op uw algemene strategie voor persoonsgegevens, afhankelijk van de branche- en overheidsvoorschriften die van toepassing zijn op uw organisatie. Dit omvat waar persoonlijke gegevens worden opgeslagen, welk type gegevens het is en hoeveel ervan en in welke omstandigheden deze zijn verzameld.
 
![Weten wat uw gegevens zijn: welk type gegevens het is en hoeveel gegevens er zijn, en in welke omstandigheden deze zijn verzameld](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Overdraagbaarheid van gegevens 

Gegevens worden ook in de tijd verplaatst terwijl deze worden verwerkt, verfijnd en er andere versies van worden afgeleid. Een eerste momentopname is nooit voldoende. Er moet een continu proces zijn voor het kennen van uw gegevens. Dit vertegenwoordigt een van de grootste uitdagingen voor grote organisaties die grote hoeveelheden persoonlijke gegevens verwerken. Organisaties die het probleem 'Weet uw gegevens' niet oplossen, kunnen uiteindelijk met een zeer hoog risico en mogelijke boetes van overheidsinstanties eindigen.

![De levenscyclus van gegevens](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Waar de persoonlijke gegevens zich

Om tegemoet te komen aan de privacyregels voor gegevens, kunt u niet vertrouwen op algemene ideeën over waar u denkt dat persoonlijke gegevens kunnen bestaan, nu of in de toekomst. Uit de privacyregels voor gegevens blijkt dat organisaties voortdurend weten waar persoonlijke gegevens zich ver van voordeed. Dit maakt het belangrijk om een eerste momentopname te maken van al uw gegevensbronnen voor mogelijke opslag van persoonlijke gegevens, waaronder uw Microsoft 365-omgeving, en mechanismen in te stellen voor continue controle en detectie.

Als uw algehele gereedheid en risico met betrekking tot regelgeving met betrekking tot gegevens-privacy nog niet is geëvalueerd, gebruikt u de volgende driestapskader om aan de slag te gaan. 

![Stappen voor het beoordelen van uw algehele gereedheid en risico met betrekking tot privacyregels voor gegevens](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Dit artikel en de inhoud ervan zijn niet bedoeld voor juridische adviesservices. U krijgt alleen enkele basishulpmiddelen en koppelingen naar hulpmiddelen die mogelijk in de eerste fasen van uw beoordeling van pas kunnen komen.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Stap 1: Een basiskennis ontwikkelen van de scenario's voor persoonlijke gegevens van uw organisatie 

U moet de blootstelling aan privacyrisico's voor gegevens meten op basis van het type persoonlijke gegevens dat momenteel wordt beheerd, waar deze worden opgeslagen, welke controles er worden geplaatst, hoe de levenscyclus van de gegevens wordt beheerd en wie er toegang toe heeft. 

Als uitgangspunt is het belangrijk om te inventariseren welke typen persoonlijke gegevens er bestaan in uw Microsoft 365-omgeving. Gebruik deze categorieën:

- Werknemersgegevens die nodig zijn voor het uitvoeren van dagelijkse bedrijfsfuncties
- Gegevens die de organisatie heeft over zakelijke klanten, partners en andere relaties in het scenario business-to-business (B2B)
- Gegevens die de organisatie heeft over consumenten die informatie verstrekken aan onlineservices die de organisatie beheert in het scenario business-to-customer (B2C)

Hier volgen een voorbeeld van de verschillende typen gegevens voor veel voorkomende afdelingen van een organisatie.

![Typen persoonlijke gegevens](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Veel van de persoonlijke gegevens die onderhevig zijn aan privacyregels voor gegevens worden meestal verzameld en opgeslagen buiten Microsoft 365. Persoonlijke gegevens van web- of mobiele toepassingen die door consumenten worden gebruikt, moeten van dergelijke toepassingen naar Microsoft 365 zijn geëxporteerd om te kunnen worden onderzocht door Microsoft 365, zodat de privacy van gegevens kan worden onderzocht. 

Uw blootstelling aan gegevens privacy in Microsoft 365 is mogelijk beperkter ten opzichte van uw webtoepassingen en CRM-systemen, waarop deze oplossing niet van toepassing is.

Het is ook belangrijk na te denken over de volgende veelvoorkomende problemen met de naleving van gegevens privacy bij het evalueren van uw risicoprofiel:

 - **Verdeling van persoonlijke gegevens.** Hoe spreidingsinformatie over een bepaald onderwerp? Is het bekend dat het zo goed is om overheidsinstanties te overtuigen dat er juiste controle is? Kan het indien nodig worden onderzocht en opgelost?
- **Beveiligen tegen exfiltration.** Hoe bebeveiligen u persoonlijke gegevens van een bepaald type of bron tegen gegevens die worden gehackt en hoe te reageren als dat zo was?
- **Bescherming en risico.** Welke mechanismen voor gegevensbescherming zijn geschikt ten opzichte van het risico en hoe de bedrijfscontinuïteit en productiviteit behouden kunnen worden en de invloed van eindgebruikers minimaliseren als tussenkomst van eindgebruikers vereist is? Moet u bijvoorbeeld handmatige classificatie of versleuteling gebruiken?
- **Bewaren van persoonlijke gegevens.** Hoe lang moeten gegevens met persoonlijke gegevens om geldige zakelijke redenen worden bewaard en hoe u een bewaarbeleid voor altijd kunt vermijden, in balans met bewaarbehoeften voor bedrijfscontinuïteit?
- **Verzoeken van gegevensonderwerpen verwerken.** Welke mechanismen zijn nodig om verzoeken van gegevensonderwerpen (DSR's) en eventuele herstelacties, zoals anoniem maken, corrigeren en verwijderen te verwerken?
- **Continue controle en rapportage.** Welke dagelijkse controle-, gebruiks- en rapportagetechnieken zijn beschikbaar voor de verschillende gegevenstypen en bronnen?
- **Beperkingen voor de gegevensverwerking.** Gelden er beperkingen voor het gebruik van gegevens voor gegevens die via deze methoden worden verzameld of opgeslagen, zodat de organisatie rekening moet houden met privacycontroles? Bijvoorbeeld: toezeggingen dat persoonsgegevens niet door verkopers worden gebruikt, kunnen vereisen dat uw organisatie mechanismen op zetten om overdracht of opslag van deze gegevens te voorkomen in systemen die zijn gekoppeld aan de verkooporganisatie.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Werknemersgegevens die nodig zijn voor het uitvoeren van dagelijkse bedrijfsfuncties

Van nature moeten organisaties gegevens over werknemers verzamelen voor elektronische identiteits- en HR-doeleinden, afhankelijk van waar ze het in hun werknemersovereenkomsten mee eens zijn. Zolang een persoon voor een bedrijf werkt, is dit meestal geen probleem. De organisatie wil mogelijk mechanismen maken om te voorkomen dat kwaadwillende actors persoonlijke gegevens van werknemers exfilteren of lekken. 

Als een persoon een bedrijf verlaat, hebben organisaties meestal schema's voor processen, procedures en bewaar- en verwijderingsschema's voor het verwijderen van gebruikersaccounts, het buiten bedrijf stellen van postvakken en persoonlijke stations en het wijzigen van de werknemerstatus in zaken zoals personeelszakensystemen. In situaties waarin een juridische procedure is betrokken, kan een werknemer of een andere partij bij een juridisch onderzoek geldige redenen hebben voor het verkrijgen van informatie over persoonlijke gegevens die zijn opgeslagen in de systemen van de organisatie. In sommige gevallen kan die partij vragen om dergelijke gegevens te verwijderen of anoniem te maken. 

Om aan dergelijke behoeften te voldoen, moeten er processen en procedures zijn om dergelijke aanvragen te vergemakkelijken, zodat preventie, herstel en herstel noodzakelijk zijn om dergelijke aanvragen mogelijk te maken, omdat bepaalde informatie over een werknemer redelijkerwijs essentieel kan worden beschouwd voor bedrijfscontinuïteit. Dit zijn bijvoorbeeld gegevens die een persoon heeft gebruikt om een bestand te maken of een functie te hebben uitgevoerd. 

>[!Note]
>Zie het artikel Monitor [and Respond](information-protection-deploy-monitor-respond.md)voor technieken voor het beschermen van persoonlijke gegevens in Microsoft 365. Mogelijk wilt u ook geautomatiseerde classificatie- en beveiligingsschema's gebruiken om ervoor te zorgen dat persoonlijke gegevens binnen de organisatie worden beheerd en om te voorkomen dat ze de organisatie verlaten in schadelijke situaties. Zie het [artikel Informatie beveiligen](information-protection-deploy-protect-information.md) voor meer informatie.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Gegevens die de organisatie over haar zakelijke klanten heeft in het B2B-scenario

Het verzamelen van B2B-gegevens is ook een uitdaging omdat uw organisatie mogelijk gegevens van klantnamen en transacties in de verschillende systemen moet bewaren voor bedrijfscontinuïteit, maar die gegevens toch beschermen tegen onbedoelde of schadelijke exfiltration. Net als werknemersgegevens moeten er beleidsregels, procedures en technische besturingselementen zijn om dergelijke gegevens te beschermen en deze conform gedefinieerde bewaar- en verwijderingsschema's te verouderen. 

Contracten met externe klanten, partners en de andere entiteiten waarmee de organisatie zaken doet, hebben meestal een taal waarin de verwerking van dergelijke gegevens wordt aangepakt, zoals bescherming, bewaar en verwijdering, zowel tijdens als nadat de entiteit een relatie met de organisatie heeft. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Gegevens die de organisatie heeft over consumenten die informatie verstrekken aan onlineservices die de organisatie beheert in het B2C-scenario

Deze categorie is de categorie waar de meeste mensen naar denken vanwege de privacy van gegevens, omdat er veel openbare exemplaren zijn van het uitleken van klantgegevens. Dit kan opzettelijk zijn, zoals een derde partij onder contract bij de provider, of onbedoeld, zoals het exfiltration door een kwaadwillende actor. Bescherming van consumentengegevens is een van de belangrijkste redenen waarom de EU en anderen deze voorschriften hebben vastgesteld. Voor regelgeving met de privacy van gegevens, zoals AVG en AE.A, moet u plannen voor:

- [Controlelijsten voor actieplannen](../compliance/gdpr-action-plan.md) [en gereedheid voor verantwoordelijkheid](../compliance/gdpr-arc-office365.md)
- [Beoordelingen van de invloed op gegevensbescherming](../compliance/gdpr-data-protection-impact-assessments.md)
- [Meldingen over inbreuk](../compliance/gdpr-breach-office365.md)
- [Verzoeken van betrokkenen](../compliance/gdpr-dsr-office365.md)

Als in uw organisatie niet veel rechtstreeks gegevens van consumenten worden verzameld, is deze categorie mogelijk minder belangrijk. Het is echter mogelijk dat u nog steeds de processen moet doortrekken die in deze artikelen worden beschreven om naleving te realiseren.

### <a name="step-1-summary"></a>Overzicht van stap 1

Het inzicht in uw blootstelling aan risico' s en privacyregels voor gegevens is een belangrijke eerste stap die is gebaseerd op een basiskennis van de scenario's voor persoonlijke gegevens van uw organisatie.

Als u geen persoonlijke gegevens hebt van consumenten in uw Microsoft 365-omgeving of als u naar bepaalde delen van de omgeving wilt gaan en de behoefte aan technische controle wordt gebaseerd op het gebruik van gegevens van het type consumenten, dan hoeft die technische controle alleen in delen met hoog risico in de omgeving te worden gebruikt, niet overal.

Hoewel een externe organisatie of een aanbeveling voor standaardbeheersets, zoals uit Compliance Manager in Microsoft 365, u kan helpen uw controlestrategie te informeren, moet uw keuze voor implementatie worden gestuurd op basis van informatieinventaris om uw blootstelling aan het echte risico te kwantificeren.

De meeste organisaties worden blootgesteld aan een van de bovenstaande scenario's. Het maken van een benadering van de evaluatie is belangrijk.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Stap 2: Uw gereedheid voor het voldoen aan de privacyregels voor gegevens beoordelen

Hoewel deze specifiek zijn voor de AVG, bieden de vragen die in het gratis hulpprogramma voor het beoordelen van de AVG van [Microsoft](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) worden gesteld een goed begin om inzicht te krijgen in uw algehele gereedheid voor privacy van gegevens. 

Organisaties die onderhevig zijn aan andere privacyregels voor gegevens, zoals THEOE.A in de Verenigde Staten of de LGPD in Brazilië, kunnen ook baat hebben bij de inventaris van dit hulpprogramma vanwege overlappende bepalingen in de AVG.

AVG-beoordeling bestaat uit deze secties:

| Sectie | Beschrijving |
|:-------|:-----|
| Beheermodel | <ol><li>Wordt in uw privacybeleid expliciet vermeld welke gegevens worden verwerkt? </li><li>Geeft u regelmatig beoordelingen van privacy-impact (PIA's)? </li><li> Gebruikt u een hulpprogramma voor het beheren van persoonlijke gegevens (PI)? </li><li> Bent u wettelijk bevoegd om zaken te doen met PI-gegevens voor een bepaalde persoon? Houdt u toestemming voor gegevens bij? </li><li> Houdt u controlecontroles bij, implementeert en beheert u? Controleert u op gegevenslekken? </li></ol>|
| Verwijdering en melding | <ol><li>Geeft u expliciete instructies over hoe de gegevens van gebruikers kunnen worden gebruikt? </li><li> Hebt u gedocumenteerde processen voor het afhandelen van toestemming voor het aftrekken van toestemming? </li><li> Is er een proces voor automatisch verwijderen voor gegevens? </li><li>   Hebt u een proces voor het valideren van identiteiten bij het contact met een klant? </li></ol>|
| Risicobeperking en informatiebeveiliging | <ol><li>Gebruikt u hulpmiddelen om ongestructureerde gegevens te scannen? </li><li>Zijn alle servers up-to-date en gebruikt u firewalls om ze te beschermen? </li><li>Gebruikt u regelmatig back-ups van uw servers? </li><li>Controleert u actief op gegevenslekken? </li><li>Versleutelt u uw gegevens in rust en in verzending? </li></ol>|
| Beleidsbeheer | <ol><li>Hoe beheert u uw bindende bedrijfsregels (BCR's)? </li><li>Houdt u toestemming voor gegevens bij? </li><li> Op een schaal van 1 tot 5, 5 die volledig wordt gedekt, omvatten uw contracten gegevensclassificaties en verwerkingsvereisten? </li><li>Hebt u een incidentresponsplan en test u dit regelmatig? </li><li>Welk beleid gebruikt u voor het beheren van de toegang? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Stap 3: Identificeer typen gevoelige informatie die voorkomen in uw Microsoft 365-omgeving. 

Deze stap omvat de identificatie van specifieke typen gevoelige informatie die onderhevig zijn aan specifieke wettelijke controles, en het voorkomen ervan in uw Microsoft 365-omgeving. 

Het vinden van inhoud in uw omgeving met persoonlijke inhoud kan een enorme taak zijn, die voorheen een combinatie was van het gebruik van Compliancezoekactie, eDiscovery, Advanced eDiscovery, DLP en controle. 

Met de nieuwe oplossing **Gegevensclassificatie** in het Microsoft Compliance-beheercentrum is dit veel eenvoudiger geworden met de Mogelijkheid voor Inhoudsverkenner, die werkt met ingebouwde of aangepaste typen gevoelige informatie, waaronder de typen met betrekking tot persoonlijke gegevens. [](../compliance/data-classification-content-explorer.md)
 
### <a name="sensitive-information-types"></a>Typen gevoelige informatie

Het Microsoft Compliance-beheercentrum is vooraf geladen met meer dan 100 typen gevoelige informatie, die met elkaar te maken hebben met het identificeren en vinden van persoonlijke gegevens. Deze ingebouwde typen gevoelige informatie kunnen helpen bij het identificeren en beveiligen van creditcardnummers, bankrekeningnummers, paspoortnummers en meer, op basis van patronen die zijn gedefinieerd door een reguliere expressie (regex) of een functie. Zie waar de typen gevoelige [informatie naar zoeken voor meer informatie.](../compliance/what-the-sensitive-information-types-look-for.md)

Als u gevoelige items van een organisatie- of regiotype wilt identificeren en beveiligen, zoals een aangepaste notatie voor werknemer-ids of andere persoonlijke gegevens die nog niet worden gedekt door een ingebouwd type gevoelige informatie, kunt u met de volgende methoden een aangepast type gevoelige informatie maken: 

- PowerShell
- Aangepaste regels met exacte gegevensmatch (EDM)
- Via de gebruikersinterface van het compliancecentrum, zoals is gemarkeerd in het artikel [Score voor nalevingsscore en compliancebeheer](information-protection-deploy-compliance.md)

U kunt ook een bestaand, ingebouwd type gevoelige informatie aanpassen.

Zie de volgende artikelen voor meer informatie:

- [Een ingebouwd type gevoelige informatie aanpassen](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Meer informatie over typen gevoelige informatie](../compliance/sensitive-information-type-learn-about.md)
- [Een aangepast type gevoelige informatie maken in het beveiligings- & compliancecentrum](../compliance/create-a-custom-sensitive-information-type.md)
- [Een aangepast type gevoelige informatie maken in & Compliancecentrum PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Aangepaste typen gevoelige informatie maken met classificatie op basis van exacte gegevensmatch](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Inhoudsverkenner

De nieuwe Inhoudsverkenner in het Microsoft 365-compliancebeheerderscentrum is een belangrijk hulpmiddel om te bepalen of vertrouwelijke items in uw omgeving voorkomen. [](../compliance/data-classification-content-explorer.md) Het is een geautomatiseerd hulpprogramma voor het initiële en doorlopende scannen van uw volledige Microsoft 365-abonnement op het voorkomen van typen gevoelige informatie en de weergave van de resultaten.
 
Met het nieuwe hulpmiddel Inhoudsverkenner kunt u snel de locaties van gevoelige items in uw omgeving identificeren met behulp van ingebouwde typen gevoelige informatie of aangepaste typen. Hiervoor kan het nodig zijn om een proces in te stellen en een verantwoordelijkheid in te stellen voor het regelmatig onderzoeken van de aanwezigheid en locatie van gevoelige items.

Samen met de andere stappen die in dit artikel worden beschreven, vormt dit een beginpunt voor het identificeren van uw algehele blootstelling aan risico' s, gereedheid en locatie van gevoelige items die u moet beschermen via geplande microsoft 365-configuratie en -controle. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andere methoden voor het identificeren van persoonlijke gegevens in uw omgeving

Naast Inhoudsverkenner hebben organisaties toegang tot de functie Inhoud zoeken om aangepaste zoekopdrachten te maken om persoonlijke gegevens in hun omgeving te vinden, met behulp van geavanceerde zoekcriteria en aangepaste filters.

In dit artikel wordt gedetailleerde informatie gegeven over het gebruik van Inhoud zoeken voor het ontdekken van [persoonlijke gegevens.](../compliance/search-for-and-find-personal-data.md) Inhoud zoeken en andere detectietechnieken worden ook verkend in [DSR's voor de AVG en THEE.A.](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)

In het artikel over het controleren en reageren van persoonlijke gegevens in Microsoft 365 krijgt u meer inzicht in de technieken voor het ontwikkelen [en herstellen van persoonlijke gegevens.](information-protection-deploy-monitor-respond.md)
