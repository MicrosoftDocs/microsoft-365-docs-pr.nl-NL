---
title: Gegevensprivacyrisico's beoordelen en gevoelige items identificeren met Microsoft 365
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
ms.custom: ''
description: Bepaal de regelgeving voor gegevensprivacy, de relevante scenario's, uw gereedheid en de gevoelige informatietypen die zich in uw Microsoft 365-omgeving bevinden.
ms.openlocfilehash: ba47a43c7af8d97af852e0a3ef417cdc1dbab46a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521371"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Gegevensprivacyrisico's beoordelen en gevoelige items identificeren met Microsoft 365

Het beoordelen van de regelgeving en risico's voor gegevensprivacy waaraan uw organisatie is onderworpen, is een belangrijke eerste stap voordat u gerelateerde verbeteringsacties uitvoert, waaronder die welke haalbaar zijn met Microsoft 365-functies en -services. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Mogelijk toepasbare regelgeving voor gegevensprivacy

Zie voor een goede referentie over het bredere regelgevingskader voor regelgeving inzake gegevensprivacy de [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) en de reeks artikelen over de Algemene Verordening [Gegevensbescherming (AVG) en](../compliance/gdpr.md)andere materialen over de regelgeving waaraan u mogelijk in uw branche of regio worden onderworpen.

### <a name="gdpr"></a>AVG

De AVG, de meest bekende en aangehaalde gegevensprivacywetgeving, regelt het verzamelen, opslaan, verwerken en delen van persoonsgegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon die woonachtig is in de Europese Unie (EU). 

Volgens GDPR artikel 4: 

- "persoonsgegevens": alle informatie met betrekking tot een geïdentificeerde of identificeerbare natuurlijke persoon ("betrokkene"; een identificeerbare natuurlijke persoon is een persoon die direct of indirect kan worden geïdentificeerd, met name aan de hand van een identificatienummer zoals een naam, een identificatienummer, locatiegegevens, een online-identificatienummer of een of meer factoren die specifiek zijn voor de fysieke, fysiologische, genetische, mentale, economische, culturele of sociale identiteit van die natuurlijke persoon.

### <a name="iso-27001"></a>ISO 27001

Naleving van andere normen zoals ISO 27001 is ook erkend door verschillende Europese toezichthoudende autoriteiten als een geldige proxy van opzet in het hele spectrum van mensen, processen en technologie. De normen die het specificeert overlapping en naleving van ISO-27001-gestuurde beschermingsmechanismen kunnen worden beschouwd als een proxy die voldoet aan bepaalde privacyverplichtingen in bepaalde omstandigheden.

### <a name="other-data-privacy-regulations"></a>Andere regelgeving inzake gegevensprivacy

Andere prominente regelgeving inzake gegevensprivacy specificeert ook vereisten voor de omgang met persoonsgegevens.

In de Verenigde Staten, deze omvatten de California Consumer Protection Act[(CCPA),](../compliance/ccpa-faq.md)HIPAA-HITECH (Verenigde Staten gezondheidszorg privacy act), en de Graham Leach Bliley Act (GLBA). Aanvullende staatsspecifieke voorschriften zijn ook van kracht of in ontwikkeling. 

Over de hele wereld zijn er nog andere voorbeelden van de Nationale GDPR Implementation Act (BDSG) van Duitsland, de Brazil Data Protection Act (LGPD) en vele anderen.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Regelgeving toewijzing aan Microsoft 365 technische controle categorieën

Veel van de gegevens privacy-gerelateerde regelgeving hebben overlappende eisen, dus je moet begrijpen aan welke regelgeving ze onderworpen zijn voordat ze een technisch controlesysteem ontwikkelen. 

Voor latere verwijzing in de artikelen van deze algemene oplossing, deze tabel bevat fragmenten uit een steekproef van de regelgeving voor gegevensprivacy. 

| Verordening | Artikel/afdeling | Uittreksel | Toepasselijke technische controlecategorieën |
|:-------|:-----|:-------|:-------|
| AVG | Artikel 5, lid 1, onder f) | Persoonsgegevens worden verwerkt op een wijze die een passende beveiliging van de persoonsgegevens waarst omgaat, met inbegrip van bescherming tegen ongeoorloofde of onrechtmatige verwerking en tegen onopzettelijke schade, vernietiging of schade, met behulp van passende technische of organisatorische maatregelen ('integriteit en vertrouwelijkheid'.  |  (Alle) <br> Identiteit <br> Apparaat <br> Bescherming tegen bedreigingen <br> Informatie beveiligen <br> Informatie regelen <br> Ontdekken en reageren |
|  | Artikel 32, lid 1, onder a) | Rekening houdend met de stand van de techniek, de kosten van de uitvoering en de aard, de reikwijdte, de context en de doeleinden van de verwerking, alsmede het risico van uiteenlopende waarschijnlijkheid en ernst voor de rechten en vrijheden van natuurlijke personen, voeren de voor de verwerking verantwoordelijke en de verwerker passende technische en organisatorische maatregelen uit om een beveiligingsniveau te waarborgen dat aangepast is aan het risico , met inbegrip van onder meer: a) de pseudonimisering en versleuteling van persoonsgegevens. | Informatie beveiligen |
|  | Artikel 13, lid 2, onder a) | "... de voor de verwerking verantwoordelijke verstrekt de betrokkene op het tijdstip waarop persoonsgegevens worden verkregen, de volgende aanvullende informatie die nodig is om een eerlijke en transparante verwerking te waarborgen: a) de periode waarvoor de persoonsgegevens zullen worden opgeslagen, of indien dat niet mogelijk is, de criteria die worden gebruikt om die periode te bepalen. | Informatie regelen |
|  | Artikel 15, lid 1, onder e) | De betrokkene heeft het recht van de voor de verwerking verantwoordelijke een bevestiging te verkrijgen over de vraag of persoonsgegevens betreffende hem of haar al dan niet worden verwerkt, en in voorkomend geval toegang tot de persoonsgegevens en de volgende informatie: e) het bestaan van het recht om bij de voor de verwerking verantwoordelijke te verzoeken persoonsgegevens te rectificeren of te wissen of de verwerking van persoonsgegevens betreffende de betrokkene te beperken of te beperken of om bezwaar te maken tegen een dergelijke verwerking | Ontdekken en reageren |
| LGPD | Artikel 46 | De verwerkingsagenten nemen beveiligings-, technische en administratieve maatregelen om persoonsgegevens te beschermen tegen ongeoorloofde toegangen en toevallige of onwettige situaties van vernietiging, verlies, wijziging, communicatie of enige vorm van onjuiste of onwettige verwerking. | Informatie beveiligen <br> Informatie regelen <br> Ontdekken en reageren|
|  | Artikel 48 | De voor de verwerking verantwoordelijke moet de nationale autoriteit en de betrokkene het voorval meedelen van een veiligheidsincident dat risico's of relevante schade voor de betrokkenen kan veroorzaken. | Ontdekken en reageren |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Technische beveiligingsmaatregelen implementeren om te waken voor ongeoorloofde toegang tot elektronische beschermde gezondheidsinformatie die via een elektronisch communicatienetwerk wordt verzonden. | Informatie beveiligen |
|  | 45 C.F.R. 164.312(e)(2) | Implementeer een mechanisme om elektronische beschermde gezondheidsinformatie te versleutelen wanneer dit passend wordt geacht. | Informatie beveiligen |
|  | 45 CFR 164.312(c)(2) | Implementeer elektronische mechanismen om te bevestigen dat elektronische beschermde gezondheidsinformatie niet op ongeoorloofde wijze is gewijzigd of vernietigd. | Informatie regelen |
|  | 45 CFR 164.316(b)(1)i) | Als een actie, activiteit of beoordeling vereist is dat dit subdeel wordt gedocumenteerd, houdt u een schriftelijk (dat kan elektronisch zijn) bij van de actie, activiteit of beoordeling | Informatie regelen |
|  | 45 CFR 164.316(b)(1) | Bewaar de in punt b), punt 1, van deze afdeling vereiste documentatie gedurende 6 jaar vanaf de datum van aanmaak of de datum waarop deze voor het laatst van kracht was, naar gelang van het moment. | Informatie regelen |
|  | 45 C.F.R. 164.308(a)(1) ii)(D) | Procedures implementeren om regelmatig records van informatiesysteemactiviteiten te controleren, zoals controlelogboeken, toegangsrapporten en meldingen voor het bijhouden van beveiligingsincidenten | Ontdekken en reageren |
|  | 45 C.F.R. 164.308(a)(6) | Identificeren en reageren op verdachte of bekende beveiligingsincidenten; schadelijke gevolgen van beveiligingsincidenten die bij de betrokken entiteit of zakenpartner bekend zijn, voor zover mogelijk te beperken; en documenteer beveiligingsincidenten en de resultaten daarvan. | Ontdekken en reageren |
|  | 45 C.F.R. 164.312(b) | Implementeer hardware, software en procedurele mechanismen die activiteiten registreren en onderzoeken in informatiesystemen die elektronische beschermde gezondheidsinformatie bevatten of gebruiken. | Ontdekken en reageren |
| CCPA | 1798.105(c) | Een bedrijf dat een verifieerbaar verzoek van een consument ontvangt om de persoonlijke gegevens van de consument te verwijderen overeenkomstig onder a), van deze afdeling, verwijdert de persoonlijke gegevens van de consument uit zijn administratie en geeft dienstverleners opdracht om de persoonlijke gegevens van de consument uit zijn administratie te verwijderen | Ontdekken en reageren |
|  | 1798.105(d) | (uitzonderingen op 1798.105(c) <br> Een bedrijf of een dienstverlener hoeft niet te voldoen aan het verzoek van een consument om de persoonlijke gegevens van de consument te verwijderen indien het voor het bedrijf of de dienstverlener noodzakelijk is om de persoonlijke gegevens van de consument te bewaren om: (raadpleeg de huidige verordening voor aanvullende informatie). | Ontdekken en reageren |
|||||

>[!Important]
>Dit is niet bedoeld als een uitputtende lijst. Raadpleeg [Compliance Manager](../compliance/compliance-manager-overview.md) of uw juridische of compliance adviseur voor meer informatie over de toepasbaarheid van de genoemde secties op de genoemde categorieën.
>

## <a name="knowing-your-data"></a>Uw gegevens kennen

Ongeacht de regelgeving waaraan u onderworpen bent, waarbij verschillende typen gebruikersgegevens binnen en buiten uw organisatie communiceren met uw systemen, zijn allemaal belangrijke factoren die van invloed kunnen zijn op uw algemene strategie voor de bescherming van persoonsgegevens, afhankelijk van de branche- en overheidsvoorschriften die van toepassing zijn op uw organisatie. Dit omvat waar persoonlijke gegevens worden opgeslagen, welk type het is, en hoeveel ervan er is, en onder welke omstandigheden het werd verzameld.
 
![Het kennen van uw gegevens: Welk type het is, en hoeveel ervan er is, en onder welke omstandigheden het werd verzameld](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Gegevensportabiliteit 

Gegevens worden ook in de loop van de tijd verplaatst terwijl deze worden verwerkt, verfijnd en andere versies ervan worden afgeleid. Een eerste momentopname is nooit genoeg. Er moet een doorlopend proces zijn om uw gegevens te kennen. Dit is een van de grootste uitdagingen voor grote organisaties die grote hoeveelheden persoonsgegevens verwerken. Organisaties die niet ingaan op de "know your data" probleem kan potentieel eindigen met een zeer hoog risico en mogelijke boetes van regelgevende instanties.

![De levenscyclus van gegevens](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Wanneer de persoonsgegevens

Om de privacyregels van gegevens aan te pakken, u niet vertrouwen op algemene noties van waar u denkt dat persoonlijke gegevens kunnen bestaan, nu of in de toekomst. De regelgeving inzake gegevensprivacy vereist dat organisaties aantonen dat ze voortdurend weten waar persoonsgegevens zich bevindt. Dit maakt het belangrijk om een eerste momentopname te maken van al uw gegevensbronnen voor mogelijke opslag van persoonlijke gegevens, waaronder uw Microsoft 365-omgeving, en mechanismen in te stellen voor voortdurende monitoring en detectie.

Als u uw algehele gereedheid en risico's in verband met de regelgeving voor gegevensprivacy nog niet hebt beoordeeld, gebruikt u het volgende 3-stappenkader om aan de slag te gaan. 

![Stappen om uw algehele gereedheid en risico's in verband met de regelgeving inzake gegevensprivacy te beoordelen](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Dit artikel en de inhoud ervan zijn niet bedoeld om de plaats in te nemen van juridische adviesdiensten. Het biedt slechts een aantal fundamentele richtlijnen en links naar instrumenten die kunnen worden van hulp in de vroege stadia van uw beoordeling.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Stap 1: Een fundamenteel inzicht ontwikkelen in de scenario's van uw organisatie op het vlak van de persoonsgegevens 

U moet de blootstelling aan gegevensprivacyrisico meten op basis van het type persoonlijke gegevens dat het momenteel beheert, waar deze wordt opgeslagen, welke beschermende besturingselementen erop worden geplaatst, hoe de levenscyclus ervan wordt beheerd en wie er toegang toe heeft. 

Als uitgangspunt is het belangrijk om in te inventariseren welke soorten persoonlijke gegevens er in uw Microsoft 365-omgeving bestaan. Gebruik deze categorieën:

- Werknemersgegevens die nodig zijn om dagelijkse bedrijfsfuncties uit te voeren
- Gegevens die de organisatie heeft over haar zakelijke klanten, partners en andere relaties in het B2B-scenario (business-to-business)
- Gegevens die de organisatie heeft over consumenten die informatie verstrekken aan online services die de organisatie beheert in het B2C-scenario (business-to-customer)

Hier is een voorbeeld van de verschillende soorten gegevens voor typische afdelingen van een organisatie.

![Soorten persoonsgegevens](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Veel van de persoonsgegevens die onderworpen zijn aan de privacyregelgeving van gegevens worden meestal verzameld en opgeslagen buiten Microsoft 365. Alle persoonlijke gegevens van consumentengerichte web- of mobiele toepassingen zouden van dergelijke toepassingen naar Microsoft 365 moeten zijn geëxporteerd om binnen Microsoft 365 aan gegevensprivacy te kunnen worden onderworpen. 

De blootstelling aan gegevensprivacy in Microsoft 365 kan beperkter zijn ten opzichte van uw webtoepassingen en CRM-systemen, waar deze oplossing niet op in gaat.

Het is ook belangrijk om na te denken over de volgende algemene uitdagingen op het gebied van privacy bij het evalueren van uw risicoprofiel:

 - **Distributie van persoonsgegevens.** Hoe verspreid is informatie over een bepaald onderwerp? Is het goed genoeg om regelgevende instanties ervan te overtuigen dat er goede controles zijn? Kan het worden onderzocht en gesaneerd indien nodig?
- **Beschermen tegen exfiltratie.** Hoe bescherm je persoonsgegevens van een bepaald type of bron tegen gecompromitteerde gegevens en hoe reageer je als dat zo was?
- **Bescherming versus risico.** Welke mechanismen voor informatiebescherming zijn geschikt in verhouding tot het risico en hoe de bedrijfscontinuïteit en productiviteit kunnen worden gehandhaafd en de gevolgen van de eindgebruiker kunnen worden geminimaliseerd als er tussenkomst van de eindgebruiker nodig is? Moet bijvoorbeeld handmatige classificatie of versleuteling worden gebruikt?
- **Persoonsgegevens bewaren.** Hoe lang moet informatie met persoonsgegevens worden bewaard om geldige zakelijke redenen en hoe te voorkomen dat eerdere keep-it-forever praktijken, in evenwicht met bewaarbehoeften voor bedrijfscontinuïteit?
- **Verzoeken van de betrokkene afhandelen.** Welke mechanismen zijn nodig om verzoeken van betrokkenen (DSR's) en eventuele corrigerende maatregelen, zoals anonimisering, redactie en verwijdering, te behandelen?
- **Voortdurende monitoring en rapportage.** Wat voor dagelijkse bewakings-, onderzoeks- en rapportagetechnieken zijn beschikbaar voor de verschillende gegevenstypen en -bronnen?
- **Beperkingen op de gegevensverwerking.** Zijn er beperkingen op het gebruik van gegevens voor informatie die wordt verzameld of opgeslagen via deze methoden die de organisatie moet weergeven in privacycontroles? Toezeggingen dat persoonsgegevens niet door verkooppersoneel worden gebruikt, kunnen bijvoorbeeld vereisen dat uw organisatie mechanismen in voert om overdracht of opslag van die informatie te voorkomen in systemen die zijn gekoppeld aan de verkooporganisatie.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Werknemersgegevens die nodig zijn om dagelijkse bedrijfsfuncties uit te voeren

Organisaties moeten van nature gegevens verzamelen over werknemers voor elektronische identiteits- en HR-doeleinden, afhankelijk van wat ze in hun werknemersovereenkomsten overeenkomen. Zolang een persoon werkt voor een bedrijf, dit is meestal geen probleem. De organisatie kan willen mechanismen in te voeren om te voorkomen dat kwaadwillende actoren uit exfiltratie of lekken werknemer persoonlijke gegevens. 

Als een persoon een bedrijf verlaat, hebben organisaties doorgaans processen, procedures en bewaar- en verwijderingsschema's voor het verwijderen van gebruikersaccounts, het ontmantelen van mailboxen en persoonlijke stations en het wijzigen van de status van werknemers in zaken als personeelssystemen. Voor situaties waarin geschillen betrokken zijn, kan een werknemer of een andere partij bij een juridisch onderzoek geldige redenen hebben voor het verkrijgen van informatie over persoonsgegevens die zijn opgeslagen in de systemen van de organisatie. In sommige gevallen kan deze partij verzoeken om het verwijderen of anonimisme van deze gegevens. 

Om aan dergelijke behoeften tegemoet te komen, moeten organisaties over processen en procedures beschikken die preventieve, detective- en corrigerende behoeften aanpakken om dergelijke verzoeken te vergemakkelijken, waarbij wordt vastgesteld dat bepaalde informatie over een werknemer redelijkerwijs als cruciaal kan worden beschouwd voor de bedrijfscontinuïteit. Bijvoorbeeld informatie die een persoon een bestand heeft geschreven of een functie heeft uitgevoerd. 

>[!Note]
>Zie het artikel monitor en antwoord op de [onderzoeks- en](information-protection-deploy-monitor-respond.md)saneringstechnieken voor persoonsgegevens in Microsoft 365. U ook geautomatiseerde classificatie- en beschermingsregelingen gebruiken om ervoor te zorgen dat persoonlijke gegevens worden beheerd terwijl ze binnen de organisatie zijn, en voorkomen dat deze de organisatie verlaten in kwaadaardige actorsituaties. Zie het [artikel informatie beveiligen](information-protection-deploy-protect-information.md) voor meer informatie.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Gegevens die de organisatie heeft over haar zakelijke klanten in het B2B-scenario

Het verzamelen van B2B-informatie is ook een uitdaging omdat uw organisatie mogelijk gegevens van klantnamen en transacties in haar verschillende systemen moet bijhouden voor bedrijfscontinuïteit, maar die informatie beschermt tegen onbedoelde of schadelijke exfiltratie. Net als werknemersgegevens moeten organisaties beleidsregels, procedures en technische controles hebben om dergelijke gegevens te beschermen en deze te verouderen volgens gedefinieerde bewaar- en verwijderingsschema's. 

Contracten met externe klanten, partners en de andere entiteiten waarmee de organisatie zaken doet, hebben doorgaans taal die de verwerking van dergelijke gegevens aanpakt, inclusief bescherming, retentie en verwijdering, zowel tijdens als nadat de entiteit een relatie met de organisatie heeft. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Gegevens die de organisatie heeft over consumenten die informatie verstrekken aan online services die de organisatie beheert in het B2C-scenario

Deze categorie is degene die de meeste mensen denken over voor de privacy van gegevens, als gevolg van vele openbare gevallen van lekkage van klantgegevens. Dit kan opzettelijk zijn, zoals een derde partij onder contract bij de provider, of onbedoeld, zoals exfiltratie door een kwaadwillende acteur. Consumentenbescherming is een van de belangrijkste redenen waarom de EU en anderen deze verordeningen hebben vastgesteld. Regelgeving voor gegevensprivacy zoals GDPR en CCPA vereist dat u plannen maakt voor:

- [Actieplannen](../compliance/gdpr-action-plan.md) en [verantwoordingsplicht checklists](../compliance/gdpr-arc-office365.md)
- [Effectbeoordelingen gegevensbescherming](../compliance/gdpr-data-protection-impact-assessments.md)
- [Meldingen van inbreuk](../compliance/gdpr-breach-office365.md)
- [Verzoeken van betrokkenen](../compliance/gdpr-dsr-office365.md)

Als uw organisatie niet veel rechtstreekse gegevensverzameling van consumenten doet, is deze categorie mogelijk minder een probleem. Het kan echter nodig zijn om de processen die in deze artikelen worden beschreven, te doorlopen om naleving te bereiken.

### <a name="step-1-summary"></a>Samenvatting stap 1

Inzicht in uw blootstelling aan risico- en gegevensprivacyregelgeving is een belangrijke eerste stap die is gebaseerd op een fundamenteel begrip van de scenario's voor persoonsgegevens van uw organisatie.

Als u geen persoonlijke gegevens van consumenten in uw Microsoft 365-omgeving hebt of als deze beperkt is tot bepaalde delen van het milieu en de noodzaak van een technische controle is gebaseerd op blootstelling aan gegevens van het type consument, hoeft die technische controle mogelijk alleen te worden gebruikt in delen met een hoog risico van het milieu, niet overal.

Hoewel een aanbeveling voor externe organisatie of standaardcontrole, zoals van compliancescore in Microsoft 365, kan helpen bij het informeren van uw controlestrategie, moet uw implementatiekeuze worden bepaald door het bewustzijn van gegevensvoorraad om uw werkelijke risicoblootstelling te kwantificeren.

De meeste organisaties zullen enige blootstelling aan een van de bovenstaande scenario's. Het nemen van een holistische benadering van beoordeling is belangrijk.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Stap 2: Beoordeel uw bereidheid om te voldoen aan de privacyregels van gegevens

Hoewel specifiek voor GDPR, bieden de vragen die worden gesteld in de gratis [Microsoft GDPR-beoordelingstool](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) een goede start in de richting van inzicht in uw algehele privacybereidheid van gegevens. 

Organisaties die onderworpen zijn aan andere regelgeving inzake gegevensprivacy, zoals CCPA in de Verenigde Staten of lgpd in Brazilië, kunnen ook profiteren van de inventaris van deze tool van gereedheid vanwege overlappende bepalingen met de AVG.

GDPR-beoordeling bestaat uit deze secties:

| Sectie | Beschrijving |
|:-------|:-----|
| Beheermodel | <ol><li>Vermeldt uw privacybeleid expliciet welke gegevens worden verwerkt? </li><li>Voert u regelmatig Privacy Impact Assessments (PIA's) uit? </li><li> Gebruikt u een tool om persoonlijke gegevens (PI) te beheren? </li><li> Heeft u de wettelijke bevoegdheid om zaken te doen met pi-gegevens over een bepaald individu? Houdt u toestemming voor gegevens bij? </li><li> Houdt u controlecontroles bij, implementeer en beheert u deze? Controleert u op datalekken? </li></ol>|
| Verwijdering en kennisgeving | <ol><li>Geeft u expliciete instructies over hoe de gegevens van gebruikers toegankelijk zijn? </li><li> Heeft u gedocumenteerde processen voor de behandeling van opt-out toestemming? </li><li> Heeft u een geautomatiseerd verwijderingsproces voor gegevens? </li><li>   Heeft u een proces om identiteit te valideren wanneer u contact op met een klant? </li></ol>|
| Risicobeperking en informatiebeveiliging | <ol><li>Gebruikt u tools om ongestructureerde gegevens te scannen? </li><li>Zijn alle servers up-to-date en maakt u gebruik van firewalls om ze te beschermen? </li><li>Voert u regelmatig back-ups van uw servers uit? </li><li>Houdt u actief toezicht op datalekken? </li><li>Versleutelt u uw gegevens in rust en in de verzending? </li></ol>|
| Beleidsbeheer | <ol><li>Hoe beheert u uw Binding Corporate Rules (BCRs)? </li><li>Houdt u toestemming voor gegevens bij? </li><li> Op een schaal van 1 tot 5, 5 die volledig wordt gedekt, hebben uw contracten betrekking op gegevensclassificaties en verwerkingsvereisten? </li><li>Heeft u een incidentresponsplan en test u regelmatig? </li><li>Welk beleid gebruikt u om de toegang te beheren? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Stap 3: Identificeer gevoelige informatietypen die voorkomen in uw Microsoft 365-omgeving. 

Deze stap omvat de identificatie van bepaalde gevoelige informatietypen die onderworpen zijn aan specifieke wettelijke controles, evenals het voorkomen ervan in uw Microsoft 365-omgeving. 

Het vinden van inhoud in uw omgeving met persoonlijke inhoud kan een formidabele taak zijn, voorheen met een combinatie van het gebruik van Compliance Search, eDiscovery, Advanced eDiscovery, DLP en auditing. 

Met de nieuwe **gegevensclassificatieoplossing** in het Microsoft Compliance-beheercentrum is dit veel eenvoudiger geworden met de [Content Explorer-mogelijkheid,](../compliance/data-classification-content-explorer.md) die werkt met ingebouwde of aangepaste gevoelige informatietypen, waaronder die met betrekking tot persoonlijke gegevens.
 
### <a name="sensitive-information-types"></a>Typen gevoelige informatie

Het Microsoft Compliance-beheercentrum wordt vooraf geladen met meer dan 100 gevoelige informatietypen, waarvan de meeste betrekking hebben op het identificeren en lokaliseren van persoonlijke gegevens. Deze ingebouwde gevoelige informatietypen kunnen helpen bij het identificeren en beschermen van creditcardnummers, bankrekeningnummers, paspoortnummers en meer, op basis van patronen die worden gedefinieerd door een reguliere expressie (regex) of een functie. Zie Voor meer informatie [wat de gevoelige informatietypen zoeken.](../compliance/what-the-sensitive-information-types-look-for.md)

Als u een organisatiespecifiek of regionaal type gevoelige items moet identificeren en beveiligen, zoals een aangepaste indeling voor werknemers-id's of andere persoonlijke gegevens die nog niet onder een ingebouwd gevoelige informatietype vallen, u met deze methoden een aangepast gevoelig informatietype maken: 

- Powershell
- Aangepaste regels met exacte gegevensmatch (EDM)
- Via de beheer-gebruikersinterface van het Compliance Center, zoals gemarkeerd in het [artikel Compliance Score en Compliance Manager gebruiken](information-protection-deploy-compliance.md)

U ook een bestaand, ingebouwd gevoelig informatietype aanpassen.

Zie deze artikelen voor meer informatie:

- [Een ingebouwd type gevoelige informatie aanpassen](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Aangepaste gevoelige informatietypen](../compliance/custom-sensitive-info-types.md)
- [Een aangepast gevoelig informatietype maken in het Security & Compliance Center](../compliance/create-a-custom-sensitive-information-type.md)
- [Een aangepast gevoelig informatietype maken in Security & Compliance Center PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Aangepaste gevoelige informatietypen maken met op Exact Data Match gebaseerde classificatie](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Inhoudsverkenner

Een belangrijk hulpmiddel voor het bepalen van het voorkomen van gevoelige items in uw omgeving is de nieuwe [Content Explorer](../compliance/data-classification-content-explorer.md) in het Microsoft 365 Compliance-beheercentrum. Het is een geautomatiseerd hulpmiddel voor het initiëa en doorlopend scannen van uw hele Microsoft 365-abonnement voor het optreden van gevoelige informatietypen en weergave van de resultaten.
 
Met de nieuwe tool Content Explorer u snel de locaties van gevoelige items in uw omgeving identificeren met behulp van ingebouwde gevoelige informatietypen of aangepaste. Dit kan inhouden dat een proces wordt opgezet en dat de verantwoordelijkheid wordt toegewezen om regelmatig de aanwezigheid en locatie van gevoelige items te onderzoeken.

Samen met de andere stappen die in dit artikel worden gemarkeerd, biedt dit een startpunt voor het identificeren van uw algehele blootstelling aan risico's, gereedheid en locatie van gevoelige items die moeten worden beschermd door middel van geplande Microsoft 365-configuratie en -monitoring. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andere methoden om persoonsgegevens in uw omgeving te identificeren

Naast de Content Explorer hebben organisaties toegang tot de mogelijkheid om inhoudszoekmogelijkheden te produceren om persoonlijke gegevens in hun omgeving te vinden, met behulp van geavanceerde zoekcriteria en aangepaste filters.

Gedetailleerde richtlijnen over het gebruik van Content Search voor ontdekking van persoonsgegevens vindt u in [dit artikel.](../compliance/search-for-and-find-personal-data.md) Content Search en andere detectietechnieken worden ook onderzocht in [DSRs voor de GDPR en CCPA.](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)

Aanvullende inzichten over onderzoeks- en saneringstechnieken voor persoonsgegevens in Microsoft 365 zijn te vinden in het [monitor- en antwoordartikel](information-protection-deploy-monitor-respond.md).
