---
title: Gegevens beveiligen die onderworpen zijn aan privacyregels voor gegevens
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
description: Implementeer Microsoft 365 beveiligings- en compliancefuncties en bescherm uw persoonlijke gegevens.
ms.openlocfilehash: 479774069844964e2e603dee5efbc7b8ef867918
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229261"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Gegevens beveiligen die onderworpen zijn aan privacyregels voor gegevens

In uw abonnement kunnen een aantal besturingselementen voor gegevensbescherming worden gebruikt om te voldoen aan de nalevingsvereisten en -voorschriften voor gegevensbescherming. Deze omvatten Algemene verordening gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse privacywet voor gezondheidszorg), de California Consumer Protection Act (CCPA) en de Brazil Data Protection Act (LGPD).

Deze besturingselementen zijn binnen de volgende oplossingsgebieden:

- Vertrouwelijkheidslabels
- Preventie van gegevensverlies (DLP)
- Office-berichtversleuteling (OME)
- Teams en toegangsbesturingselementen voor sites

![Belangrijke services voor het beschermen van persoonlijke gegevens die onderworpen zijn aan privacyregels voor gegevens](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

> [!NOTE]
> In deze oplossing worden beveiligings- en compliancefuncties beschreven om informatie te beveiligen die onderhevig is aan privacyregels voor gegevens. Voor een volledige lijst met beveiligingsfuncties in Microsoft 365, Microsoft 365 [beveiligingsdocumentatie.](../security/index.yml) Zie voor een volledige lijst met compliancefuncties in Microsoft 365 documentatie [Microsoft 365 compliance.](../compliance/index.yml)

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Privacyregels voor gegevens die van invloed zijn op besturingselementen voor informatiebeveiliging

Hier is een voorbeeldlijst met privacyregels voor gegevens die betrekking kunnen hebben op besturingselementen voor informatiebeveiliging:

- AVG Artikel 5, lid 1, onder f))
- AVG-artikel (32)(1)(a)
- LGPD-artikel 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Zie de [privacyrisico's voor gegevens beoordelen en het artikel gevoelige items identificeren](information-protection-deploy-assess.md) voor meer informatie over elk van de bovenstaande items.

Regels voor gegevensbescherming voor gegevensbescherming raden het volgende aan:

- Bescherming tegen verlies of onbevoegde toegang, gebruik en/of overdracht.
- Toepassing op basis van risico's van beveiligingsmechanismen.
- Gebruik van versleuteling waar van toepassing.

Uw organisatie wil mogelijk ook Microsoft 365 inhoud voor andere doeleinden, zoals andere compliancebehoeften of om zakelijke redenen. Het opstellen van uw gegevensbeschermingsschema voor gegevensbescherming moet worden uitgevoerd als onderdeel van de algemene planning, implementatie en beheer van gegevensbescherming.

Om u te helpen aan de slag te gaan met een informatiebeveiligingsschema in Microsoft 365, bevat de volgende sectie een korte lijst met gerelateerde mogelijkheden en verbeteracties voor Microsoft 365. De lijst bevat mogelijkheden en verbeteracties die van toepassing zijn op privacyregels voor gegevens. De lijst bevat echter geen oudere technologieën als er een nieuwere mogelijkheid is die de oudere grotendeels overtrof. IRM (Information Rights Management) voor SharePoint en OneDrive is bijvoorbeeld niet opgenomen in de lijst, maar gevoeligheidslabels zijn opgenomen.

## <a name="managing-information-protection-in-microsoft-365"></a>Informatiebeveiliging beheren in Microsoft 365

[Microsoft-oplossingen voor informatiebeveiliging](../compliance/information-protection.md) omvatten een aantal geïntegreerde mogelijkheden in Microsoft 365, Microsoft Azure en Microsoft Windows. In Microsoft 365 oplossingen voor informatiebeveiliging:

- [Serviceversleuteling met klantsleutel](../compliance/customer-key-overview.md)
- [Gevoelige informatietypen](../compliance/sensitive-information-type-entity-definitions.md) (beschreven in het [artikel Privacyrisico's voor gegevens](information-protection-deploy-assess.md)beoordelen en gevoelige items identificeren)
- [Gevoeligheidslabels](../compliance/sensitivity-labels.md)
  - Service/containerniveau
  - Client-side/content-level
  - Geautomatiseerd voor gegevens-at-rest in SharePoint en OneDrive
- Preventie van gegevensverlies (DLP, Data Loss Prevention)
- [Microsoft 365 Preventie van gegevensverlies in eindpunten](../compliance/endpoint-dlp-learn-about.md)
- [Office 365-berichtversleuteling nieuwe mogelijkheden (OME)](../compliance/ome.md) en OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)

Daarnaast zijn beveiliging op site- en bibliotheekniveau belangrijke mechanismen die u in een beveiligingsschema kunt opnemen.

Zie voor informatie over andere mogelijkheden voor informatiebeveiliging buiten Microsoft 365 informatie:

- [Microsoft Cloud Application Security (MCAS)](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows-gegevensbescherming](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Met gevoeligheidslabels uit het Microsoft Information Protection framework kunt u de gegevens van uw organisatie classificeren en beveiligen zonder de productiviteit van gebruikers en de mogelijkheid om samen te werken te belemmeren.

> [!div class="mx-imgBorder"]
> ![Gevoeligheidslabels in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Vereisten voor gevoeligheidslabels

Voltooi deze activiteiten voordat u een van de mogelijkheden op basis van gevoeligheidslabels implementeert die hieronder worden gemarkeerd:

1. U begrijpt het volgende:
   - **Zakelijke vereisten.** Stel de zakelijke redenen vast voor het toepassen van gevoeligheidslabels in uw onderneming. Bijvoorbeeld uw privacyvereisten voor gegevens voor informatiebeveiliging.
   - **Mogelijkheden voor gevoeligheidslabels.** Gevoeligheidslabels kunnen complex worden, dus zorg ervoor dat u de documentatie over gevoeligheidslabels [leest](../compliance/sensitivity-labels.md) voordat u aan de slag gaat.
   - **Belangrijke dingen om te onthouden** Gevoeligheidslabels worden beheerd in het Microsoft Compliance-beheercentrum, maar de opties voor targeting en toepassing variëren aanzienlijk.
      - Er zijn gevoeligheidslabels voor sites, groepen en Teams op containerniveau (de instellingen zijn niet van toepassing op inhoud in de container). Deze worden gepubliceerd voor gebruikers en groepen die deze toepassen wanneer een site, groep of Team is ingericht.
      - Er zijn gevoeligheidslabels voor actieve inhoud. Deze worden ook gepubliceerd voor gebruikers of groepen, die ze handmatig toepassen of ze worden automatisch toegepast wanneer:
        - Het bestand wordt geopend/bewerkt/opgeslagen, op het bureaublad van de gebruiker of op SharePoint site.
        - Een e-mailbericht wordt opgesteld en verzonden.
      - Er zijn gevoeligheidslabels voor automatische toepassing op bestanden in SharePoint en OneDrive naast e-mailberichten die worden verzonden via Exchange. Deze zijn bedoeld voor alle sites of specifieke sites en zijn automatisch van toepassing op de bestanden in rust in deze omgevingen.

2. Huidige gevoeligheidslabels rationaliseren met eerdere of alternatieve methoden

   - Azure Information Protection

      Het huidige gevoeligheidslabelsysteem moet mogelijk worden afgestemd op een bestaande implementatie van [Azure Information Protection-etiketten.](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)
   - OME

      Als u van plan bent moderne gevoeligheidslabels te gebruiken voor e-mailbeveiliging en bestaande methoden voor e-mailversleuteling, zoals OME, kunnen ze naast elkaar bestaan, maar u moet de scenario's begrijpen waarin een van beide moet worden toegepast. Zie [Office 365-berichtversleuteling nieuwe mogelijkheden (OME),](#office-365-message-encryption-ome-new-capabilities)waaronder een tabel waarin moderne gevoeligheidslabelbeveiliging wordt vergeleken met op OME gebaseerde beveiliging.

3. Integratie plannen in een bredere informatiebeveiligingsregeling. Naast coëxistentie met OME kunnen gevoeligheidslabels naast elkaar worden gebruikt, zoals Microsoft 365 preventie van gegevensverlies (DLP) en Microsoft Cloud App Security. Zie [Microsoft Information Protection in Microsoft 365](../compliance/information-protection.md) om uw doelstellingen voor gegevensbescherming op het gebied van gegevensbescherming te bereiken.

4. Ontwikkel een gevoeligheidslabelclassificatie en -besturingselementschema. Zie [Taxonomie voor gegevensclassificatie en gevoeligheidslabel.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Algemene richtlijnen

1. **Schemadefinitie.** Voordat u technische mogelijkheden gebruikt om etiketten en beveiliging toe te passen, werkt u in uw hele organisatie om een classificatieschema te definiëren. Mogelijk hebt u al een classificatieschema, waardoor u gemakkelijker persoonlijke gegevens kunt toevoegen.
2. **Aan de slag.** Begin met het bepalen van het aantal en de namen van etiketten die moeten worden geïmplementeerd. Doe deze activiteit zonder u zorgen te maken over welke technologie u moet gebruiken en hoe etiketten worden toegepast. Pas dit schema universeel toe in uw organisatie, inclusief gegevens die on-premises en in andere cloudservices aanwezig zijn.
3. **Aanvullende aanbevelingen** Wanneer u beleid, etiketten en voorwaarden ontwerpt en implementeert, kunt u de volgende aanbevelingen volgen:

   - **Gebruik een bestaand classificatieschema (indien van toepassing).** Veel organisaties gebruiken al gegevensclassificatie in een of andere vorm. Evalueer zorgvuldig het bestaande labelschema en gebruik het zo mogelijk zoals het is. Als u vertrouwde etiketten gebruikt die herkenbaar zijn voor uw eindgebruikers, wordt acceptatie mogelijk gemaakt.
   - **Begin klein.** Er is vrijwel geen limiet voor het aantal labels dat u kunt maken. Grote aantallen etiketten en sublabels kunnen echter de acceptatie vertragen.
   - **Gebruik scenario's en gebruiksscenario's.** Identificeer veelgebruikte gevallen binnen uw organisatie en gebruik scenario's die zijn afgeleid van de privacyregels voor gegevens waarop u van toepassing bent. Controleer of de voorgestelde label- en classificatieconfiguratie in de praktijk werkt.
   - **Vraag elke aanvraag voor een nieuw label.** Heeft elk scenario of use case echt een nieuw label nodig of kunt u gebruiken wat u al hebt? Door het aantal etiketten tot een minimum te beperken, wordt de acceptatie verbeterd.
   - **Gebruik sublabels voor belangrijke afdelingen.** Sommige afdelingen hebben specifieke behoeften waarvoor specifieke etiketten nodig zijn. Definieer deze labels als sublabels voor een bestaand label en overweeg een bereikbeleid te gebruiken dat is toegewezen aan gebruikersgroepen in plaats van globaal.
   - **Houd rekening met beleid met een bereik.** Beleid dat is gericht op subsets van gebruikers voorkomt overbelasting van etiketten. Met een beleid met een bereik kunt u specifieke rollen- of afdelingslabels of sublabels toewijzen aan alleen werknemers die voor die specifieke afdeling werken.
   - **Gebruik duidelijke labelnamen.** Gebruik geen jargon, standaarden of acroniems als labelnamen. Probeer namen te gebruiken die resoneren met de eindgebruiker om de acceptatie te verbeteren. In plaats van labels zoals PII, PCI, HIPAA, LBI, MBI en HBI te gebruiken, moet u rekening houden met namen als Niet-Zakelijk, Openbaar, Algemeen, Vertrouwelijk en Zeer Vertrouwelijk.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Gevoeligheidslabels maken en implementeren voor sites, groepen en teams

Wanneer u [gevoeligheidslabels](../compliance/sensitivity-labels-teams-groups-sites.md) maakt in de Microsoft 365-compliancecentrum, kunt u deze nu toepassen op deze containers:

- Microsoft Teams sites
- Microsoft 365 groepen (voorheen Office 365 groepen)
- SharePoint sites

Gebruik de volgende labelinstellingen om de inhoud in die containers te beveiligen:

- Privacy (openbaar of privé) van Microsoft 365 met een groep verbonden Teams sites
- Externe gebruikerstoegang
- Toegang vanaf niet-beheerde apparaten

Als u voor gegevensbescherming wilt voorkomen dat containers extern worden gedeeld die worden gebruikt voor het opslaan van inhoud met gevoelige persoonlijke gegevens, markeert u de bestanden met de gegevens als privé en hebt u beheerde apparaten nodig.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Gevoeligheidslabels voor inhoud maken en implementeren

Met gevoeligheidslabels die zijn toegepast op bestanden, kunt u de inhoud ervan versleutelen, de inhoud watermerk geven en andere besturingselementen definiëren voor Office-toepassingen, waaronder Outlook en webversie van Office.

Wanneer u klaar bent om de gegevens van uw organisatie te gaan beveiligen met gevoeligheidslabels:

1. **Maak de labels.** Maak en benoem uw gevoeligheidslabels volgens de classificatie-taxonomie van uw organisatie voor verschillende gevoeligheidsniveaus voor inhoud. Zie het white paper Data Classification and [Sensitivity Label Taxonomie voor](https://aka.ms/dataclassificationwhitepaper)meer informatie over het ontwikkelen van een classificatie taxonomie.
2. **Bepalen wat elk label kan doen.** Configureer de beveiligingsinstellingen die u aan elk label wilt koppelen. U wilt bijvoorbeeld dat inhoud met een lagere gevoeligheid (zoals een label Algemeen) alleen een kop- of voettekst heeft toegepast, terwijl inhoud met een hogere gevoeligheid (zoals een label vertrouwelijk) een watermerk moet hebben en versleuteling moet zijn ingeschakeld.
3. **De labels publiceren.** Wanneer uw gevoeligheidslabels zijn geconfigureerd, kunt u deze publiceren met een labelbeleid. Bepaal welke gebruikers en groepen de labels moeten hebben en welke beleidsinstellingen u wilt gebruiken. Eén label is herbruikbaar. U definieert het eenmaal en vervolgens kunt u het opnemen in verschillende labelbeleidsregels die aan verschillende gebruikers zijn toegewezen.

Wanneer u gevoeligheidslabels publiceert vanaf de Microsoft 365-compliancecentrum, worden ze weergegeven in Office [apps](../compliance/sensitivity-labels-office-apps.md) voor gebruikers om inhoud te classificeren en te beveiligen terwijl deze wordt gemaakt of bewerkt.

![Implementatiestroom voor gevoeligheidslabels in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Voor gegevensbescherming kunt u handmatig een gevoeligheidslabel met versleuteling en andere regels toepassen op e-mail of inhoud die gevoelige persoonlijke gegevens bevat.

> [!NOTE]
> Gevoeligheidslabels waarin versleuteling is ingeschakeld die is toegepast op e-mail, hebben enkele overlappende functionaliteit met OME. Zie [Vergelijking van veilige e-mailscenario's met OME- en gevoeligheidslabels.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Autolabeling aan clientzijde wanneer gebruikers documenten bewerken of e-mailberichten opstellen

Wanneer u een gevoeligheidslabel maakt, kunt u dat [label](../compliance/apply-sensitivity-label-automatically.md) automatisch toewijzen aan inhoud, inclusief e-mail, wanneer deze overeenkomt met de voorwaarden die u opgeeft.

De mogelijkheid om automatisch gevoeligheidslabels toe te passen op inhoud is belangrijk omdat:

- Het is niet nodig om uw gebruikers te trainen wanneer ze een van uw classificaties moeten gebruiken.
- U hoeft niet te vertrouwen op gebruikers om alle inhoud op de juiste manier te classificeren.
- Gebruikers hoeven niet meer op de hoogte te zijn van uw beleid, maar kunnen zich op hun werk richten.

Autolabeling ondersteunt het aanbevelen van een label aan gebruikers en het automatisch toepassen van een label. Maar in beide gevallen besluit de gebruiker of het label wordt geaccepteerd of geweigerd, om ervoor te zorgen dat inhoud beter wordt gelabeld.

Dit labelen aan clientzijde heeft een minimale vertraging voor documenten tot gevolg, omdat het label kan worden aangebracht voordat het document wordt opgeslagen. Niet alle client-apps ondersteunen echter automatisch labelen. Deze mogelijkheid wordt ondersteund door de geïntegreerde labelingclient van Azure Information Protection en sommige versies van Office [apps.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Zie Autolabeling configureren [voor Office voor configuratie-instructies.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Voor gegevensbescherming kunt u gevoeligheidslabels automatisch toepassen op inhoud die gevoelige persoonlijke gegevens bevat.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Autolabels aan servicezijde wanneer inhoud al is opgeslagen

Deze methode wordt autoclassificatie met gevoeligheidslabels genoemd. U hoort het ook wel autolabeling voor gegevens in rust (voor documenten in SharePoint en OneDrive) en gegevens die onderweg zijn (voor e-mail die wordt verzonden of ontvangen door Exchange). Voor Exchange bevat het geen e-mailberichten in postvakken die in rust staan.

Omdat deze labeling wordt toegepast door de service zelf in plaats van door de gebruikerstoepassing, hoeft u zich geen zorgen te maken over welke apps gebruikers hebben en welke versie. Hierdoor is deze functionaliteit direct beschikbaar binnen uw gehele organisatie en geschikt om op schaal te labelen. Beleid voor automatisch labelen ondersteunt geen aanbevolen labels, omdat de gebruiker geen interactie heeft met het labelproces. In plaats daarvan voert de beheerder het beleid in de simulatiemodus uit, om ervoor te zorgen dat de inhoud juist wordt gelabeld voordat het label werkelijk wordt toegepast.

Zie Beleidsregels voor automatisch labelen [configureren voor SharePoint, OneDrive en Exchange voor configuratie-instructies.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

Voor gegevens privacy binnen sites van belang, push sensitivity labels for automatic encryption of content containing sensitive personal information.

## <a name="data-loss-prevention"></a>Preventie van gegevensverlies

U kunt preventie van gegevensverlies [(DLP)](../compliance/dlp-learn-about-dlp.md) in Microsoft 365 gebruiken om risicovolle, onbedoelde of ongepaste delen te detecteren, te waarschuwen en te blokkeren, zoals het delen van gegevens met persoonlijke gegevens, zowel intern als extern.

Met DLP kunt u het volgende doen:

- Identificeer en controleer risicovolle activiteiten voor delen.
- Gebruikers informeren met in-context-richtlijnen om de juiste beslissingen te nemen.
- Beleidsregels voor gegevensgebruik afdwingen op inhoud zonder de productiviteit te belemmeren.
- Integreer met classificatie en labeling om gegevens te detecteren en te beveiligen wanneer deze worden gedeeld.

### <a name="supported-workloads-for-dlp"></a>Ondersteunde werkbelastingen voor DLP

Met een DLP-beleid in de Microsoft 365-compliancecentrum kunt u gevoelige items op verschillende locaties in Microsoft 365 identificeren, controleren en automatisch beveiligen, zoals Exchange Online, SharePoint, OneDrive en Microsoft Teams.

U kunt bijvoorbeeld elk document met een creditcardnummer identificeren dat is opgeslagen op een OneDrive-site of u kunt alleen de OneDrive sites van specifieke personen controleren.

U kunt ook gevoelige items bewaken en beveiligen in de lokaal geïnstalleerde versies van Excel, PowerPoint en Word, waaronder de mogelijkheid om gevoelige items te identificeren en DLP-beleid toe te passen. DLP biedt continue monitoring wanneer personen inhoud van deze Office delen.

> [!div class="mx-imgBorder"]
> ![Ondersteunde werkbelastingen voor DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

In deze afbeelding ziet u een voorbeeld van DLP-beveiliging van persoonlijke gegevens.

> [!div class="mx-imgBorder"]
> ![Voorbeeld van het beveiligen van persoonlijke gegevens met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP wordt gebruikt om een document of e-mailbericht met een statusrecord te identificeren en blokkeert vervolgens automatisch de toegang tot dat document of blokkeert de e-mail die wordt verzonden. DLP geeft de geadresseerde vervolgens een beleidstip en stuurt een waarschuwing naar de eindgebruiker en beheerder.

### <a name="planning-for-dlp"></a>Planning voor DLP

Plan uw DLP-beleid voor:

- Uw zakelijke vereisten.

- Een risicoanalyse van de organisatie zoals beschreven in het artikel [Privacyrisico's](information-protection-deploy-assess.md)voor gegevens beoordelen en gevoelige items identificeren .

- Andere informatiebeschermings- en beheermechanismen in de plaats of in de planning voor gegevensbescherming.

- De gevoelige informatietypen die u hebt geïdentificeerd voor persoonlijke gegevens op basis van uw beoordelingswerk, zoals beschreven in het artikel Privacyrisico's voor gegevens beoordelen en gevoelige [items identificeren.](information-protection-deploy-assess.md) DLP-beleidsvoorwaarden kunnen zijn gebaseerd op zowel gevoelige informatietypen als bewaarlabels.

- De bewaarlabels die u nodig hebt om DLP-voorwaarden op te geven. Zie de [informatie die onderworpen is aan de privacyregel voor gegevens in uw organisatie](information-protection-deploy-govern.md) voor meer informatie.

- Doorlopend DLP-beleidsbeleid, waarbij iemand in de organisatie beleidsregels moet beheren en afstemmen op wijzigingen in gevoelige informatietypen, bewaarlabels, regelgeving en compliancebeleid.

Hoewel gevoeligheidslabels niet kunnen worden gebruikt in DLP-beleidsvoorwaarden, kunnen bepaalde beveiligingsscenario's om toegang te voorkomen mogelijk worden bereikt met alleen gevoeligheidslabels die automatisch kunnen worden toegepast op basis van gevoelige informatietypen. Als er een krachtige gevoeligheidslabel is, moet u overwegen of DLP moet worden gebruikt om de beveiliging te vergroten, omdat:

  - DLP kan voorkomen dat bestanden worden gedeeld. Gevoeligheidslabels kunnen alleen toegang verhinderen.

  - DLP heeft meer gedetailleerde controleniveaus op het gebied van regels, voorwaarden en acties.

  - DLP-beleid kan worden toegepast op Teams chat- en kanaalberichten. Gevoeligheidslabels kunnen alleen worden toegepast op documenten en e-mail.


### <a name="dlp-policies"></a>DLP-beleid

DLP-beleidsregels worden geconfigureerd in het Microsoft Compliance-beheercentrum en geven het beveiligingsniveau op, het gevoelige informatietype dat het beleid zoekt en de doelbelastingen. De basisonderdelen bestaan uit het identificeren van de beveiliging en de typen gegevens.

> [!div class="mx-imgBorder"]
> ![DLP-beleidsconfiguratie in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Hier is een voorbeeld van het DLP-beleid voor de bewustmaking van de AVG.

![Voorbeeld van DLP-beleid voor de bewustmaking van de AVG](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Zie [dit artikel voor](../compliance/create-test-tune-dlp-policy.md) meer informatie over het maken en toepassen van DLP-beleid.

### <a name="protection-levels-for-data-privacy"></a>Beveiligingsniveaus voor gegevensbescherming

In de volgende tabel vindt u drie configuraties voor het vergroten van de beveiliging met behulp van DLP.

![Beschermingsniveaus voor gegevensbescherming met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

De eerste configuratie, Awareness, kan worden gebruikt als uitgangspunt en een minimumniveau van beveiliging om te voldoen aan de nalevingsvereisten voor privacyregels voor gegevens.

> [!NOTE]
> Naarmate de beveiligingsniveaus toenemen, wordt de mogelijkheid van gebruikers om gegevens te delen en te openen in sommige gevallen kleiner en kan dit van invloed zijn op hun productiviteit of het vermogen om dagelijkse taken uit te voeren.

Als u uw werknemers wilt helpen productiever te blijven in een veiligere omgeving bij het verhogen van het beveiligingsniveau, neemt u de tijd om hen te trainen en op te leiden over nieuwe beveiligingsbeleidsregels en -procedures.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Voorbeeld van het gebruik van gevoeligheidslabels met DLP

Gevoeligheidslabels kunnen samenwerken met DLP om gegevensbescherming te bieden in een sterk gereguleerde omgeving. Hier volgen de belangrijkste stappen van de geïntegreerde implementatie:

1. Wettelijke en anderszins zakelijke vereisten voor gegevensbescherming worden gedocumenteerd.
2. Doelgegevensbronnen, typen en eigendom worden gekenmerkt ten opzichte van privacyproblemen met gegevens.
3. Er is een algemene strategie voor het aanpakken van vereisten en het beschermen en bepalen van hotspots voor gegevens privacy.
4. Er wordt een gefaseerd actieplan opgesteld om de strategie voor gegevensbeschermingsbeheer aan te pakken.

Wanneer deze elementen zijn bepaald, kunt u gevoelige informatietypen, uw gevoeligheidslabels taxonomie en DLP-beleid samen gebruiken. In deze afbeelding ziet u een voorbeeld.

> [!div class="mx-imgBorder"]
> ![Voorbeeld van gevoeligheidslabels die werken met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Hier zijn enkele scenario's voor gegevensbescherming met behulp van DLP- en gevoeligheidslabels samen, zoals wordt weergegeven in de afbeelding.

| Scenario | Proces |
|:-------|:-----|
| A | <ol><li>Gevoeligheidslabels voor inhoud worden door een beheerder gepubliceerd voor gebruikers en groepen voor handmatige of automatische toepassing op inhoud en e-mail. </li><li>Gebruiker A past de etiketten handmatig of automatisch toe bij interactie met inhoud, met versleuteling of andere instellingen. </li><li>Gebruiker A verzendt een beveiligd e-mailbericht of bestand naar gebruiker B, een gastgebruiker. </li></ol> |
| B | DLP-beleid dat door een beheerder naar gebruiker A is gepubliceerd, blokkeert gebruiker A om het e-mailbericht en/of bestand naar gebruiker B te verzenden. |
| C |  Gevoeligheidslabel met de instelling 'eigenaar kan geen gasten uitnodigen' wordt gepubliceerd aan gebruiker A, die een team of site Teams of SharePoint heeft. Een andere gebruiker van de site probeert selectief een bestand te delen met gebruiker B, maar DLP blokkeert het bestand. |
| D | Gevoeligheidslabel voor automatische toepassing op site-inhoud wordt gepubliceerd op een of meer sites, waardoor een andere beveiligingslaag wordt gebruikt, wat resulteert in een beveiligde site. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365-berichtversleuteling (OME) nieuwe mogelijkheden

Personen gebruiken vaak e-mail om gevoelige items uit te wisselen, zoals gezondheidsgegevens van patiënten of klant- en werknemersgegevens. Versleuteling van e-mailberichten helpt ervoor te zorgen dat alleen beoogde geadresseerden berichtinhoud kunnen bekijken.

Met [OME](../compliance/ome.md)kunt u versleutelde berichten verzenden en ontvangen tussen personen binnen en buiten uw organisatie. OME werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. OME helpt ervoor te zorgen dat alleen beoogde geadresseerden berichtinhoud kunnen bekijken.

Voor gegevensbescherming gebruikt u OME om interne berichten met gevoelige items te beveiligen. Office 365-berichtversleuteling is een onlineservice die is gebaseerd op Microsoft Azure Rights Management (Azure RMS) die deel uitmaakt van Azure Information Protection. Dit omvat versleutelings-, identiteits- en autorisatiebeleid om uw e-mail te beveiligen. U kunt berichten versleutelen met behulp van sjablonen voor rechtenbeheer, de optie Niet doorsturen en de optie alleen-versleutelen.

U kunt ook regels voor e-mailstroom definiëren om deze beveiliging toe te passen. U kunt bijvoorbeeld een regel maken die de versleuteling vereist van alle berichten die zijn geadresseerd aan een specifieke geadresseerde of die specifieke trefwoordenwoorden in de onderwerpregel bevatten, en ook opgeven dat geadresseerden de inhoud van het bericht niet kunnen kopiëren of afdrukken.

Bovendien helpt OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) u om te voldoen aan nalevingsvereisten die flexibelere controles vereisen voor externe geadresseerden en hun toegang tot versleutelde e-mailberichten. Met OME Advanced Message Encryption in Microsoft 365 kunt u gevoelige e-mailberichten die buiten de organisatie worden gedeeld, besturen met automatisch beleid dat gevoelige informatietypen detecteert.

Als u voor gegevensbescherming e-mail wilt delen met een externe partij, kunt u een vervaldatum opgeven en berichten intrekken. U kunt alleen een vervaldatum intrekken en instellen voor berichten die naar externe geadresseerden worden verzonden.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Vergelijking van veilige e-mailscenario's met OME- en gevoeligheidslabels

OME- en gevoeligheidslabels die zijn toegepast op e-mail met versleuteling, hebben enige overlap, dus het is belangrijk om te begrijpen op welke scenario's deze van toepassing kunnen zijn, zoals wordt weergegeven in deze tabel.

| Scenario | Gevoeligheidslabels | OME |
|:-------|:-----|:-------|
| Interne + partners <br> Veilig communiceren en samenwerken tussen interne gebruikers en vertrouwde partners | Aanraden: labels met volledig aangepaste classificatie en beveiliging | Ja: alleen versleutelen of beveiliging niet doorsturen zonder classificatie |
| Externe partijen <br> Veilig communiceren en samenwerken met externe/consumentengebruikers | Ja: vooraf gedefinieerde geadresseerden in label | Aanbevolen: just-in-time beveiliging op basis van geadresseerden |
| Interne + partners, met verloopdatum/intrekking <br> Toegang van e-mail en inhoud met interne gebruikers en vertrouwde partners met verloop en intrekking bepalen | Aanbevolen: volledig aangepaste beveiliging met toegangsduur, gebruiker kan bestanden handmatig bijhouden en intrekken | Nee: geen intrekking of vervaldatum voor interne e-mail |
| Externe partijen met vervaldatum/intrekking <br> Toegang van e-mail en inhoud met externe/consumentengebruikers met verloop en intrekking bepalen | Ja: de gebruiker kan bestanden handmatig bijhouden | Aanbevelen (E5) : de beheerder kan e-mail intrekken & Beveiligingscentrum |
| Autolabeling <br> Organisatie wil e-mail/bijlagen automatisch beveiligen met specifieke gevoelige inhoud en/of specifieke geadresseerden | Aanbevelen (E5) - Autolabeling in Exchange en Outlook clients, verhoogt de regels voor e-mailstroom en DLP-beleid | Ja- regels voor e-mailstroom en DLP-beleid met alleen versleutelen of Beveiliging niet doorsturen |
||||

Er zullen ook verschillen zijn in ervaringen van eindgebruikers en beheerders tussen deze twee methoden.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams met beveiliging voor zeer gevoelige gegevens

Zie Een [team](secure-teams-security-isolation.md)configureren met beveiligingsisolatie voor organisaties die van plan zijn om persoonlijke gegevens op te slaan die onderworpen zijn aan privacyregels voor gegevens in Teams. Dit biedt gedetailleerde richtlijnen en configuratiestappen voor:

- Identiteit en apparaattoegang
- Een privéteam maken
- Vergrendeling van onderliggende teamsitemachtigingen
- Een groepsgevoeligheidslabel met versleuteling