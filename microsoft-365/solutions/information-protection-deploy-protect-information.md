---
title: Gegevens beschermen onder de privacyregel voor gegevens
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
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
description: Microsoft 365-functies voor beveiliging en naleving implementeren en uw persoonlijke gegevens beschermen.
ms.openlocfilehash: a5bba79f8ab382707b6fd5e448003a0271d690c6
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597236"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Gegevens beschermen onder de privacyregel voor gegevens

In uw abonnement kunnen een aantal besturingselementen voor gegevensbescherming worden gebruikt om te voldoen aan de nalevingsbehoeften en voorschriften voor gegevensbescherming. Deze omvatten de Algemene Verordening Gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse wet voor de privacy van de zorg), California Consumer Protection Act (ACT) en de Brazil Data Protection Act (LGPD).

Deze besturingselementen zijn binnen de volgende oplossingsgebieden:

- Vertrouwelijkheidslabels
- Preventie van gegevensverlies (DLP)
- Office-berichtversleuteling (OME)
- Toegangsbesturingselementen voor Teams en sites

![Belangrijke services ter bescherming van persoonlijke gegevens die onderhevig zijn aan de privacyregel voor gegevens](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Deze oplossing beschrijft de functies voor beveiliging en naleving om informatie te beschermen die onderhevig is aan privacyregels voor gegevens. Zie de microsoft 365-beveiligingsdocumentatie voor een volledige lijst met beveiligingsfuncties in [Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/) Zie de microsoft 365-compliancedocumentatie voor een volledige lijst met nalevingsfuncties in [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/)
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Privacyregels voor gegevens die van invloed zijn op besturingselementen voor gegevensbescherming

Hier is een voorbeeldlijst met regelgeving met betrekking tot gegevensbescherming die betrekking kan hebben op besturingselementen voor gegevensbescherming:

- AVG Artikel 5(1)(f))
- AVG-artikel (32)(1)(a)
- LGPD Artikel 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Zie het [artikel over het beoordelen van de privacyrisico's](information-protection-deploy-assess.md) van gegevens en het vaststellen van gevoelige items voor meer informatie over elk van de bovenstaande onderwerpen.

De privacyregels voor gegevens voor gegevensbescherming raden het volgende aan:

- Bescherming tegen verlies of onbevoegde toegang, gebruik en/of overdracht.
- Op risico gebaseerde toepassing van beschermingsmechanismen.
- Gebruik van versleuteling wanneer dat van toepassing is.

Uw organisatie wil mogelijk ook Microsoft 365-inhoud beveiligen voor andere doeleinden, zoals andere nalevingsbehoeften of om zakelijke redenen. Het opzetten van het schema voor gegevensbescherming voor gegevens privacy moet worden uitgevoerd als onderdeel van de algehele planning, implementatie en beheer van gegevensbescherming.

Om u op weg te helpen met een gegevensbeschermingsschema in Microsoft 365, bevat de volgende sectie een korte lijst met gerelateerde mogelijkheden en acties ter verbetering van Microsoft 365. De lijst bevat mogelijkheden en acties ter verbetering die van toepassing zijn op de privacyregels voor gegevens. De lijst bevat echter geen oudere technologieën als er een nieuwere mogelijkheid is die grotendeels de oudere versie overtrof. IRM (Information Rights Management) voor SharePoint en OneDrive is bijvoorbeeld niet opgenomen in de lijst, maar gevoeligheidslabels zijn wel opgenomen.

## <a name="managing-information-protection-in-microsoft-365"></a>Gegevensbescherming beheren in Microsoft 365

Microsoft [Information Protection-oplossingen](../compliance/information-protection.md) omvatten een aantal geïntegreerde mogelijkheden in Microsoft 365, Microsoft Azure en Microsoft Windows. In Microsoft 365 zijn de volgende oplossingen beschikbaar voor het beschermen van gegevens:

- [Serviceversleuteling met klantsleutel](../compliance/customer-key-overview.md)
- [Typen gevoelige informatie (beschreven](../compliance/what-the-sensitive-information-types-look-for.md) in het [artikel Over privacyrisico's](information-protection-deploy-assess.md)van gegevens beoordelen en artikel over gevoelige items identificeren)
- [Gevoeligheidslabels](../compliance/sensitivity-labels.md) 
  - Service-/containerniveau
  - Client-side/content-level
  - Geautomatiseerd voor gegevens-in-rest in SharePoint en OneDrive
- Preventie van gegevensverlies (DLP, Data Loss Prevention)
- [Preventie van gegevensverlies voor Microsoft 365-eindpunt](../compliance/endpoint-dlp-learn-about.md)
- Nieuwe mogelijkheden voor [Office 365-berichtversleuteling (OME)](../compliance/ome.md) en OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)

Daarnaast zijn beveiliging op site- en bibliotheekniveau belangrijke mechanismen die u in elk beveiligingsschema kunt opnemen.

Zie voor meer informatie over andere mogelijkheden voor gegevensbeveiliging buiten Microsoft 365:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows-gegevensbescherming](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

Met gevoeligheidslabels van het Microsoft Information Protection Framework kunt u de gegevens van uw organisatie classificeren en beschermen zonder de productiviteit van gebruikers en hun mogelijkheid om samen te werken te hinderen.

![Gevoeligheidslabels in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Vereisten voor gevoeligheidslabels

Voltooi deze activiteiten voordat u een van de hieronder beschreven mogelijkheden op basis van gevoeligheidslabels implementeert:

1. Begrijp het volgende:
   - **Zakelijke vereisten.** Stel de zakelijke redenen vast voor het toepassen van gevoeligheidslabels in uw onderneming. Bijvoorbeeld uw vereisten voor gegevensbescherming.
   - **Mogelijkheden voor gevoeligheidslabels.** Gevoeligheidslabels kunnen complex worden, dus zorg ervoor dat u de documentatie [voor gevoeligheidslabels leest voordat](../compliance/sensitivity-labels.md) u begint.
   - **Belangrijke dingen om te onthouden** Gevoeligheidslabels worden beheerd in het Microsoft Compliance-beheercentrum, maar de opties voor doelgroepen en toepassingen variëren aanzienlijk.
      - Er zijn gevoeligheidslabels voor sites, groepen en Teams op containerniveau (de instellingen zijn niet van toepassing op inhoud in de container). Deze worden gepubliceerd naar gebruikers en groepen die deze toepassen wanneer een site, groep of team wordt ingericht.
      - Er zijn gevoeligheidslabels voor actieve inhoud. Deze worden ook gepubliceerd naar gebruikers of groepen die ze handmatig toepassen of ze worden automatisch toegepast in de volgende wanneer:
        - Het bestand wordt geopend/bewerkt/opgeslagen op het bureaublad van de gebruiker of op een SharePoint-site.
        - Een e-mailbericht wordt opgesteld en verzonden.
      - Er zijn gevoeligheidslabels voor automatische toepassing op bestanden in rust in SharePoint en OneDrive, naast e-mailberichten die worden verzonden via Exchange. Deze zijn gericht op alle sites of specifieke sites en zijn automatisch van toepassing op de bestanden in rustomgevingen.

2. Huidige gevoeligheidslabels rationaliseren met eerdere of alternatieve methoden

   - Azure Information Protection

      Mogelijk moet het huidige schema voor gevoeligheidslabels worden afgestemd met elke bestaande implementatie van Labels voor [Azure Information Protection.](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)
   - OME

      Als u van plan bent om moderne gevoeligheidslabels te gebruiken voor e-mailbeveiliging en bestaande methoden voor e-mailversleuteling, zoals OME, zijn er co-bestaande methoden, maar u moet de scenario's begrijpen waarin een van beide moet worden toegepast. Zie de nieuwe mogelijkheden van [Office 365-berichtversleuteling (OME),](#office-365-message-encryption-ome-new-capabilities)die een tabel bevat waarin moderne gevoeligheidslabeltypebeveiliging wordt vergeleken met OME-beveiliging.

3. Integratie plannen in een breder gegevensbeschermingsschema. Naast co-existie met OME kunnen huidige gevoeligheidslabels worden gebruikt aan de zijkant van voorzieningen zoals Microsoft 365 voor preventie van gegevensverlies (DLP) en Microsoft Cloud App Security. Zie [Gevoeligheidslabels en Microsoft Cloud App Security om](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) uw doelen te bereiken op het gebied van gegevensbescherming op het gebied van gegevensbescherming.

4. Ontwikkel een classificatie van gevoeligheidslabels en een besturingselementschema. Zie [Taxonomie voor gegevensclassificatie en gevoeligheidslabel.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Algemene richtlijnen

1. **Schemadefinitie.** Voordat u de technische mogelijkheden gebruikt om labels en beveiliging toe te passen, moet u binnen uw organisatie een classificatieschema definiëren. Mogelijk hebt u al een classificatieschema, waardoor het gemakkelijker wordt om persoonlijke gegevens toe te voegen. 
2. **Aan de slag.** Begin met het bepalen van het aantal en de namen van de labels die moeten worden geïmplementeerd. Doe deze activiteit zonder u bezig te houden met welke technologie moet worden gebruikt en hoe labels worden toegepast. Dit schema universeel toepassen in uw organisatie, inclusief gegevens die zich on-premises en in andere cloudservices bevinden.
3. **Aanvullende aanbevelingen** Als u beleid, labels en voorwaarden ontwerpt en implementeert, kunt u de volgende aanbevelingen volgen:

   - **Gebruik een bestaand classificatieschema (indien van toepassing).** Veel organisaties gebruiken al gegevensclassificatie in een bepaalde vorm. Evalueer het bestaande etiketschema zorgvuldig en gebruik het zo mogelijk. Het gebruik van bekende labels die herkenbaar zijn voor uw eindgebruikers, zal acceptatie aan stimuleren.
   - **Begin klein.** Er is bijna geen limiet voor het aantal etiketten dat u kunt maken. Grote aantallen labels en sublabels kunnen echter de acceptatie vertragen.
   - **Scenario's en use cases gebruiken.** Identificeer veelvoorkomende use cases in uw organisatie en gebruik scenario's die zijn afgeleid van de privacyregels voor gegevens waarover u van toepassing bent. Controleer of de indeling van het label en de classificatie in de praktijk werkt.
   - **Vraag elke aanvraag voor een nieuw etiket.** Heeft elk scenario of elke use case echt een nieuw label nodig of kunt u gebruiken wat u al hebt? Als u het aantal etiketten zo klein mogelijk houdt, wordt de acceptatie verbeterd.
   - **Gebruik sublabels voor de belangrijkste afdelingen.** Sommige afdelingen hebben specifieke behoeften waarvoor specifieke labels zijn vereist. Definieer deze labels als sublabels voor een bestaand etiket en overweeg om beleid binnen een bereik te gebruiken dat is toegewezen aan gebruikersgroepen in plaats van globaal.
   - **Overweeg beleid binnen bereik.** Beleid dat is gericht op subsets van gebruikers voorkomt een overvloed aan labels. Met een bereikbeleid kunnen rollen of afdelingsspecifieke labels of sublabels worden toegewezen aan alleen werknemers die voor die specifieke afdeling werken. 
   - **Gebruik duidelijke labelnamen.** Gebruik geen vakjargon, standaarden of acroniemen als labelnamen. Probeer namen te gebruiken die resoneren met de eindgebruiker om de acceptatie te verbeteren. In plaats van labels zoals PII, PCI, HIPAA, LBI, MBI en HBI te gebruiken, kunt u ook rekening houden met namen als Niet-Zakelijk, Openbaar, Algemeen, Vertrouwelijk en Zeer vertrouwelijk.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Gevoeligheidslabels maken en implementeren voor sites, groepen en teams

Wanneer u [gevoeligheidslabels maakt](../compliance/sensitivity-labels-teams-groups-sites.md) in het Microsoft 365-compliancecentrum, kunt u ze nu toepassen op deze containers:

- Microsoft Teams-sites
- Microsoft 365-groepen (voorheen Office 365-groepen)
- SharePoint-sites

Gebruik de volgende labelinstellingen om de inhoud in deze containers te beveiligen:

- Privacy (openbaar of privé) van Teams-sites met Microsoft 365-groepen
- Externe gebruikerstoegang
- Toegang vanaf niet-beheerde apparaten

Als u extern delen wilt voorkomen voor containers die worden gebruikt voor het opslaan van inhoud met gevoelige persoonlijke gegevens, moet u de bestanden met de gegevens markeren als privé en moeten de apparaten worden beheerd.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Gevoeligheidslabels voor inhoud maken en implementeren

Met gevoeligheidslabels die op bestanden zijn toegepast, kunt u hun inhoud versleutelen, de inhoud watermerken en andere besturingselementen definiëren voor inhoud in Office-toepassingen, waaronder Outlook en de webversie van Office.

Wanneer u klaar bent om de gegevens van uw organisatie te gaan beschermen met gevoeligheidslabels:

1. **Maak de etiketten.** Maak en noem uw gevoeligheidslabels op basis van de classificatie taxonomie van uw organisatie voor verschillende gevoeligheidsniveaus van inhoud. Zie het white paper Data Classification and [Sensitivity Label Taxonomy (Taxonomie](https://aka.ms/dataclassificationwhitepaper)voor gevoeligheidslabels) voor meer informatie over het ontwikkelen van een classificatie taxonomie.
2. **Definieer wat elk etiket kan doen.** Configureer de beveiligingsinstellingen die aan elk etiket moeten worden gekoppeld. U wilt bijvoorbeeld dat bij inhoud met een lagere vertrouwelijkheid (zoals het label Algemeen) alleen een kop- of voettekst wordt toegepast, terwijl voor inhoud met een hogere vertrouwelijkheid (zoals het label Vertrouwelijk) een watermerk moet zijn en versleuteling moet zijn ingeschakeld.
3. **Publiceer de labels.** Nadat uw gevoeligheidslabels zijn geconfigureerd, publiceert u ze met behulp van een labelbeleid. Bepaal welke gebruikers en groepen de labels moeten hebben en welke beleidsinstellingen moeten worden gebruikt. Eén etiket is herbruikbaar. U definieert het één keer en vervolgens kunt u het opnemen in verschillende labelbeleidsregels die zijn toegewezen aan verschillende gebruikers.

Wanneer u gevoeligheidslabels publiceert vanuit het Microsoft 365-compliancecentrum, worden ze weergegeven in [Office-apps](../compliance/sensitivity-labels-office-apps.md) zodat gebruikers inhoud kunnen classificeren en beveiligen terwijl deze wordt gemaakt of bewerkt.

![Implementatiestroom voor gevoeligheidslabels in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Voor gegevens privacy pas u handmatig een gevoeligheidslabel met versleuteling en andere regels toe op e-mail of inhoud die gevoelige persoonlijke gegevens bevat.

>[!Note]
>Gevoeligheidslabels waarin versleuteling is ingeschakeld voor e-mail, hebben enkele overlappende functionaliteit met OME. Zie [Secure email scenarios comparison with OME and sensitivity labels.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Automatische labeling aan de clientzijde wanneer gebruikers documenten bewerken of e-mailberichten opstellen

Wanneer u een gevoeligheidslabel maakt, kunt u dat [label](../compliance/apply-sensitivity-label-automatically.md) automatisch toewijzen aan inhoud, inclusief e-mail, wanneer dit overeenkomt met voorwaarden die u opgeeft.

De mogelijkheid om gevoeligheidslabels automatisch toe te passen op inhoud is belangrijk omdat:

- U hoeft uw gebruikers niet te trainen wanneer ze elk van uw classificaties kunnen gebruiken.
- U hoeft er niet van afhankelijk te zijn dat gebruikers alle inhoud correct classificeren.
- Gebruikers hoeven niet langer op de slag te gaan met uw beleid, maar kunnen zich concentreren op hun werk.

Automatische labeling ondersteunt het aanbevelen van een label aan gebruikers en het automatisch toepassen van een label. In beide gevallen bepaalt de gebruiker echter of het label moet worden geaccepteerd of afgewezen om ervoor te zorgen dat de juiste labeling van de inhoud wordt gegarandeerd.

Deze labeling aan de clientzijde heeft minimale vertraging voor documenten omdat het label zelfs kan worden toegepast voordat het document wordt opgeslagen. Niet alle client-apps ondersteunen echter automatische labeling. Deze mogelijkheid wordt ondersteund door de geïntegreerde labelclient van Azure Information Protection en sommige [versies van Office-apps.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Zie Hoe u automatische [labeling configureert voor Office-apps voor configuratie-instructies.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Voor gegevens privacy, moet u gevoeligheidslabels automatisch toepassen op inhoud die gevoelige persoonlijke gegevens bevat.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Automatische labeling aan de servicezijde wanneer inhoud al is opgeslagen

Deze methode wordt ook wel automatische classificatie met gevoeligheidslabels genoemd. U kunt dit ook wel automatische labeling horen voor gegevens in rust (voor documenten in SharePoint en OneDrive) en gegevens die worden verzonden (voor e-mail die door Exchange wordt verzonden of ontvangen). Voor Exchange worden er geen e-mailberichten in postvakken in de rest van de e-mail vermeld.
 
Omdat deze labeling door de service zelf wordt toegepast in plaats van door de gebruikerstoepassing, hoeft u zich geen zorgen te maken over welke apps gebruikers hebben en welke versie. Hierdoor is deze functie onmiddellijk beschikbaar in uw organisatie en geschikt voor labelen op schaal. Beleid voor automatische labeling biedt geen ondersteuning voor aanbevolen labeling omdat de gebruiker niet communiceert met het labelproces. In plaats daarvan voert de beheerder het beleid uit in de modus voor de autorulatie om ervoor te zorgen dat inhoud op de juiste manier wordt gelabeld voordat het label daadwerkelijk wordt toegepast.

Zie Beleid voor automatische [labeling configureren voor SharePoint, OneDrive en Exchange voor configuratie-instructies.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

Voor gegevens privacy binnen sites van probleem, push gevoeligheidslabels voor automatische versleuteling van inhoud met gevoelige persoonlijke informatie.

## <a name="data-loss-prevention"></a>Preventie van gegevensverlies 

U kunt preventie van gegevensverlies [(Data Loss Prevention, DLP)](../compliance/data-loss-prevention-policies.md) in Microsoft 365 gebruiken om risicovolle, onbedoelde of ongepaste delen te detecteren, te waarschuwen en te blokkeren, zoals het delen van gegevens met persoonlijke gegevens, zowel intern als extern.

Met DLP kunt u:

- Identificeer risicovolle activiteiten met delen en houd deze in de gaten.
- Leer gebruikers met in-context richtlijnen om de juiste beslissingen te nemen.
- Dwing beleid voor gegevensgebruik af op inhoud zonder dat dit de productiviteit belemmert.
- Integreer met classificatie en labeling om gegevens te detecteren en te beschermen wanneer deze worden gedeeld.

### <a name="supported-workloads-for-dlp"></a>Ondersteunde werkbelastingen voor DLP

Met een DLP-beleid in het Microsoft 365-compliancecentrum kunt u gevoelige items op veel locaties in Microsoft 365 identificeren, controleren en automatisch beschermen, zoals Exchange Online, SharePoint, OneDrive en Microsoft Teams.

U kunt bijvoorbeeld elk document identificeren dat een creditcardnummer bevat dat is opgeslagen op een OneDrive-site of u kunt alleen de OneDrive-sites van bepaalde personen controleren.

U kunt ook gevoelige items in de lokaal geïnstalleerde versies van Excel, PowerPoint en Word controleren en beveiligen, waaronder de mogelijkheid om gevoelige items te identificeren en DLP-beleidsregels toe te passen. DLP biedt doorlopend toezicht wanneer personen inhoud van deze Office-apps delen.

![Ondersteunde werkbelastingen voor DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

In deze afbeelding ziet u een voorbeeld van DLP-beveiliging van persoonlijke gegevens.

![Voorbeeld van het beveiligen van persoonlijke gegevens met behulp van DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP wordt gebruikt om een document of e-mailbericht met een statusrecord te identificeren en vervolgens wordt de toegang tot dat document automatisch blokkeert of wordt e-mail niet verzonden. DLP stuurt de geadresseerde vervolgens een beleidstip en stuurt een waarschuwing naar de eindgebruiker en de beheerder.

### <a name="planning-for-dlp"></a>Plannen voor DLP

Plan uw DLP-beleid voor: 

- De behoeften van uw bedrijf.

- Een risicogebaseerde evaluatie van de organisatie zoals beschreven in het artikel Over [privacyrisico's](information-protection-deploy-assess.md)voor gegevens beoordelen en gevoelige items identificeren.

- Andere mechanismen voor gegevensbescherming en beheer ter bescherming van gegevens of bij de planning van de privacy van gegevens.

- De typen gevoelige informatie die u hebt geïdentificeerd voor persoonlijke gegevens op basis van uw beoordelingswerk zoals beschreven in het artikel Over privacyrisico's voor gegevens beoordelen en het vaststellen [van gevoelige items.](information-protection-deploy-assess.md) DLP-beleidsvoorwaarden kunnen zijn gebaseerd op gevoelige informatietypen en bewaarlabels.

- De labels voor bewaren die u moet opgeven voor DLP-voorwaarden. Zie voor meer informatie de informatie die onderhevig is aan de [privacyregel](information-protection-deploy-govern.md) van uw organisatie.

- Doorlopend DLP-beleidsbeheer, waarbij iemand in de organisatie beleidsregels moet beheren en afstemmen voor wijzigingen in typen gevoelige informatie, bewaarlabels, regelgeving en nalevingsbeleid.

Hoewel gevoeligheidslabels niet kunnen worden gebruikt in DLP-beleidsvoorwaarden, kunnen bepaalde beveiligingsscenario's om toegang te voorkomen, mogelijk worden bereikt met alleen gevoeligheidslabels die automatisch kunnen worden toegepast op basis van typen gevoelige informatie. Als er een robuust gevoeligheidslabel is, moet u overwegen of U DLP moet gebruiken om de beveiliging te verhogen, omdat:

  - Met DLP kan het delen van bestanden worden voorkomen. Gevoeligheidslabels kunnen de toegang gewoon verhinderen.

  - DLP heeft een meer gedetailleerde controleniveaus wat betreft regels, voorwaarden en acties.

  - DLP-beleid kan worden toegepast op Teams-chat en kanaalberichten. Gevoeligheidslabels kunnen alleen worden toegepast op documenten en e-mailberichten.


### <a name="dlp-policies"></a>DLP-beleid

DLP-beleid wordt geconfigureerd in het Microsoft Compliance-beheercentrum en geven het beschermingsniveau op, het type gevoelige informatie dat door het beleid wordt gezocht en de doelwerkbelasting. De basisonderdelen bestaan uit het identificeren van de beveiliging en de typen gegevens.

![Configuratie van DLP-beleid in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Hier is een voorbeeld van DLP-beleid voor de bekendheid met de AVG.

![Voorbeeld van DLP-beleid voor de bekendheid met de AVG](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Zie [dit artikel voor](../compliance/create-test-tune-dlp-policy.md) meer informatie over het maken en toepassen van DLP-beleid.

### <a name="protection-levels-for-data-privacy"></a>Beveiligingsniveaus voor gegevens privacy

De volgende tabel bevat drie configuraties die de beveiliging verhogen met behulp van DLP.

![Beschermingsniveaus voor gegevens privacy met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

De eerste configuratie, Informatie over gegevens, kan worden gebruikt als uitgangspunt en een minimumniveau van bescherming om te voldoen aan de nalevingsvereisten voor regelgeving met gegevens-privacy.

>[!Note]
>Naarmate de beschermingsniveaus toenemen, zullen gebruikers in sommige gevallen minder mogelijkheden hebben om informatie te delen en te openen, wat van invloed kan zijn op hun productiviteit of de mogelijkheid om dagelijkse taken uit te voeren.
>

Om uw werknemers te helpen productief te blijven in een veiligere omgeving wanneer het beveiligingsniveau wordt verhogen, neemt u de tijd om ze te trainen en te informeren over nieuw beveiligingsbeleid en nieuwe procedures.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Voorbeeld van het gebruik van gevoeligheidslabels met DLP

Gevoeligheidslabels kunnen samen met DLP gegevens privacy bieden in een sterk reguleerde omgeving. Dit zijn de belangrijkste stappen van de geïntegreerde implementatie:

1. Wettelijke en anderszins zakelijke vereisten voor gegevens privacy worden gedocumenteerd.
2. Doelgegevensbronnen, -typen en -eigendom worden gekenmerkt ten opzichte van privacyproblemen met gegevens.
3. Er is een algemene strategie om aan vereisten te voldoen en hotspots voor gegevens privacy te beschermen en te bepalen.
4. Er wordt een gefaseerd actieplan opgesteld om de strategie voor gegevensbeschermingsbeheer op te zetten.

Zodra deze elementen zijn bepaald, kunt u typen gevoelige informatie, uw taxonomie voor gevoeligheidslabels en DLP-beleid samen gebruiken. In deze afbeelding ziet u een voorbeeld.

![Voorbeeld van gevoeligheidslabels die werken met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Hier zijn enkele scenario's voor gegevensbescherming waarin gebruik wordt gemaakt van DLP en gevoeligheidslabels, zoals wordt weergegeven in de afbeelding.

| Scenario | Proces |
|:-------|:-----|
| A | <ol><li>Gevoeligheidslabels voor inhoud worden door een beheerder gepubliceerd naar gebruikers en groepen voor handmatige of automatische toepassing op inhoud en e-mail. </li><li>Gebruiker A past de labels handmatig of automatisch toe bij interactie met inhoud, met versleuteling of andere instellingen die zijn toegepast. </li><li>Gebruiker A verzendt een beveiligd e-mailbericht of bestand naar gebruiker B, een gastgebruiker. </li></ol> |
| B | Met DLP-beleid dat door een beheerder is gepubliceerd naar Gebruiker A wordt het e-mailbericht en/of bestand niet naar gebruiker B verzonden. |
| C |  Het gevoeligheidslabel met de instelling 'eigenaar kan geen gasten uitnodigen' wordt gepubliceerd naar gebruiker A, die een Teams-team of SharePoint-site indeelt. Een andere gebruiker van de site probeert selectief een bestand te delen met gebruiker B, maar DLP blokkeert het. |
| D | Het gevoeligheidslabel voor automatische toepassing op site-inhoud wordt gepubliceerd op een of meer sites, wat een andere beveiligingslaag biedt, wat resulteert in een beveiligde site. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Nieuwe mogelijkheden voor Office 365-berichtversleuteling (OME)

Mensen gebruiken vaak e-mail om gevoelige items uit te wisselen, zoals gezondheidsinformatie van patiënten of klant- en werknemersgegevens. Versleuteling van e-mailberichten zorgt ervoor dat alleen beoogde geadresseerden de inhoud van berichten kunnen bekijken.

Met [OME](../compliance/ome.md)kunt u versleutelde berichten verzenden en ontvangen tussen personen binnen en buiten uw organisatie. OME werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. OME zorgt ervoor dat alleen beoogde geadresseerden de inhoud van berichten kunnen bekijken.

Voor gegevens privacy gebruikt u OME om interne berichten met gevoelige items te beveiligen. Office 365-berichtversleuteling is een onlineservice die is gebaseerd op Microsoft Azure Rights Management (Azure RMS), dat deel uitmaakt van Azure Information Protection. Dit geldt ook voor beleidsregels voor versleuteling, identiteit en autorisatie om uw e-mail te beveiligen. U kunt berichten versleutelen met behulp van rights management-sjablonen, de optie Niet doorsturen en de optie alleen-versleutelen.

U kunt ook regels voor de e-mailstroom definiëren om deze beveiliging toe te passen. U kunt bijvoorbeeld een regel maken waarin alle berichten moeten worden versleuteld die zijn geadresseerd aan een specifieke geadresseerde of die specifieke trefwoorden in de onderwerpregel bevatten, en ook opgeven dat geadresseerden de inhoud van het bericht niet kunnen kopiëren of afdrukken.

Bovendien helpt OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) u aan nalevingsvereisten te voldoen die flexibelere controle vereisen over externe geadresseerden en hun toegang tot versleutelde e-mailberichten. Met OME Advanced Message Encryption in Microsoft 365 kunt u gevoelige e-mailberichten die buiten de organisatie worden gedeeld, controleren met automatisch beleid voor het detecteren van typen gevoelige informatie. 

Als u voor gegevens privacy e-mail wilt delen met een externe partij, kunt u een vervaldatum opgeven en berichten intrekken. U kunt alleen een vervaldatum intrekken en instellen voor berichten die naar externe geadresseerden worden verzonden.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Vergelijking van beveiligde e-mailscenario's met OME en gevoeligheidslabels

OME en gevoeligheidslabels die met versleuteling worden toegepast op e-mail, hebben enige overlapping. Het is dus belangrijk om te weten op welke scenario's een van beide van toepassing kan zijn, zoals in deze tabel wordt weergegeven.

| Scenario | Gevoeligheidslabels | OME |
|:-------|:-----|:-------|
| Interne + partners <br> Veilig communiceren en samenwerken tussen interne gebruikers en vertrouwde partners | Aanbevelen: labels met volledig aangepaste classificatie en beveiliging | Ja: alleen versleutelen of beveiliging niet doorsturen zonder classificatie |
| Externe partijen <br> Veilig communiceren en samenwerken met externe/consumentengebruikers | Ja: vooraf gedefinieerde geadresseerden in label | Aanbevelen: just-in-time-beveiliging op basis van geadresseerden |
| Interne + partners, met verloop- en intrekkingsdatum <br> Toegang van e-mail en inhoud met verloop- en intrekkingsdatums van interne gebruikers en vertrouwde partners controleren | Aanbevelen: volledig aangepaste beveiliging met toegangsduur, gebruiker kan bestanden handmatig bijhouden en intrekken | Nee: geen intrekken of verlopen van interne e-mail |
| Externe partijen met verloop- en intrekkingsdatum <br> Toegang van e-mail en inhoud met verloop- en intrekkingsverloop door externe/consumentengebruikers controleren | Ja, de gebruiker kan bestanden handmatig bijhouden | Aanbevelen (E5) – beheerder kan e-mail intrekken uit & Compliancecentrum |
| Automatische labeling <br> Organisatie wil e-mail/bijlagen automatisch beveiligen met specifieke gevoelige inhoud en/of specifieke geadresseerden | Aanbevelen (E5), automatische labeling in Exchange- en Outlook-clients, verhoogt de regels voor de e-mailstroom en het DLP-beleid | Ja: regels voor e-mailstroom en DLP-beleid met de beveiliging Versleutelen of Niet doorsturen |
||||

Er zullen ook verschillen zijn tussen deze twee methoden voor eindgebruikers en beheerders.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams met beveiliging voor zeer gevoelige gegevens

Zie Een [team](secure-teams-security-isolation.md)configureren met beveiligingsisolatie, dat gedetailleerde richtlijnen en configuratiestappen bevat voor organisaties die van plan zijn om persoonlijke gegevens onder de privacyregel van gegevens in Teams op te slaan.

- Identiteit en apparaattoegang
- Een privéteam maken
- Vergrendeling van machtigingen voor onderliggende teamsite
- Een gevoeligheidslabel op basis van een groep met versleuteling
