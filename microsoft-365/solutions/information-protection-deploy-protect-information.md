---
title: Informatie beschermen onder de regelgeving van de privacy van data
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
description: Implementeer Microsoft 365 beveiligings-en nalevings functies en beveilig uw persoonlijke gegevens.
ms.openlocfilehash: 97c34ca236ea4be98b9412518788630732259d5a
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377149"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Informatie beschermen onder de regelgeving van de privacy van data

U kunt in uw abonnement een aantal informatie beschermings bescherming voor de naleving van de vereisten en voorschriften voor de privacy van gegevens. Dit omvat de algemene verordening voor de gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse gezondheidszorg van de overheid), Californië consumentenbescherming Act (CCPA) en de wet Data Protection Act (LGPD).

Dit besturingselement bevindt zich in de volgende oplossings gebieden:

- Vertrouwelijkheidslabels
- Preventie van gegevensverlies (DLP)
- Office-berichtversleuteling (OME)
- Toegangsbeheer voor teams en sites

![Belangrijkste services voor het beschermen van persoonlijke gegevens met betrekking tot data privacy verordening](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Deze oplossing beschrijft beveiligings-en compliance-functies om informatie te beschermen, onder voorschriften van de privacy van gegevens. Zie [Beveiligingsdocumentatie voor Microsoft 365](https://docs.microsoft.com/microsoft-365/security/)voor een volledige lijst van beveiligingsfuncties in microsoft 365. Zie [documentatie voor naleving van Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/)voor een volledige lijst met compliance-functies in microsoft 365.
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Voorschriften voor de privacy van gegevens die van invloed zijn op informatiebescherming

Hier ziet u een voorbeeld van een lijst met voorschriften voor de privacy van gegevens die kunnen optreden in verband met informatie beschermingsfuncties:

- AVG artikel 5 (1) (f))
- AVG artikel (32) (1) (a)
- LGPD artikel 46
- HIPAA-HITECH (45 CFR 164.312 (e) (1))
- HIPAA-HITECH (45 C.F.R. 164.312 (e) (2) (II))

Zie het [artikel privacyinstellingen voor gegevens en Identificeer gevoelige items](information-protection-deploy-assess.md) voor meer informatie.

Voorschriften voor de privacy van gegevensbescherming is het raadzaam:

- Beveiliging tegen verlies of ongeoorloofde toegang, gebruik en/of overdracht.
- Risico gerichte toepassing van beveiligingsmechanismen.
- Gebruik van versleuteling, indien van toepassing.

Uw organisatie wil mogelijk ook Microsoft 365-inhoud beschermen voor andere doeleinden, zoals andere nalevings behoeften of voor zakelijke redenen. Het opzetten van een gegevensbeschermings schema voor de privacy van gegevens moet worden uitgevoerd als onderdeel van de algemene planning, implementatie en beheer van de gegevensbescherming.

Om u te helpen aan de slag te gaan met een informatie beschermings schema in Microsoft 365, bevat de volgende sectie een korte lijst met verwante mogelijkheden en verbeterings acties voor Microsoft 365. De lijst bevat mogelijkheden en verbeterings acties die van toepassing zijn op het Reglement voor de privacy van gegevens. De lijst bevat echter geen oudere technologieën, indien er een nieuwere functie is die de oudere mogelijkheid grotendeels vervangt. De IRM (Information Rights Management) voor SharePoint en OneDrive is bijvoorbeeld niet opgenomen in de lijst, maar er zijn vertrouwelijkheids labels opgenomen.

## <a name="managing-information-protection-in-microsoft-365"></a>Information Protection beheren in Microsoft 365

Oplossingen voor Microsoft- [informatiebescherming](../compliance/protect-information.md) bestaan uit verschillende functies, waaronder microsoft 365, Microsoft Azure en Microsoft Windows. In Microsoft 365 kunt u oplossingen voor informatiebeveiliging onder meer:

- [Service versleuteling met klant sleutel](../compliance/customer-key-overview.md)
- De [typen gevoelige informatie](../compliance/what-the-sensitive-information-types-look-for.md) (beschreven in het [artikel vertrouwelijkheid van gegevens en identificeren van gevoelige artikelen](information-protection-deploy-assess.md))
- [Vertrouwelijkheidslabels](../compliance/sensitivity-labels.md) 
  - Service/container niveau
  - Client zijde/inhouds niveau
  - Geautomatiseerd voor gegevens in SharePoint en OneDrive
- Preventie van gegevensverlies (DLP, Data Loss Prevention)
- [Microsoft 365-endpoint preventie van gegevensverlies (preview)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Office 365-bericht versleutelings mogelijkheden voor nieuwe mogelijkheden (OME)](../compliance/ome.md) en OME [geavanceerde bericht versleuteling](../compliance/ome-advanced-message-encryption.md)

Daarnaast zijn de bescherming van site-en bibliotheekniveau belangrijke mechanismen die in elk beveiligingsschema dienen te worden opgenomen.

Zie voor informatie over andere mogelijkheden voor informatiebescherming buiten Microsoft 365:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows-gegevensbescherming](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Met beschikbare palletlabels van Microsoft Information Protection Framework kunt u de gegevens van uw organisatie classificeren en beschermen zonder de productiviteit van gebruikers en de mogelijkheid om samen te werken.

![Vertrouwelijkheids labels in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Vereisten voor gevoeligheids labels

Voer deze activiteiten uit voordat u een van de hieronder gemarkeerde functies voor de vertrouwelijkheid op basis van labels implementeert:

1. Meer informatie over het volgende:
   - **Bedrijfsvereisten.** De zakelijke redenen treffen voor het toepassen van palletlabels in uw onderneming. U kunt bijvoorbeeld uw vereisten voor gegevensbeveiliging voor informatiebescherming.
   - **Mogelijkheden voor vertrouwelijkheids label.** U kunt ook ingewikkelde labels maken, dus zorg ervoor dat u de [documentatie voor de vertrouwelijkheids labels](../compliance/sensitivity-labels.md) leest voordat u aan de slag gaat.
   - **Belangrijke dingen die u moet onthouden** Coderings-labels worden beheerd in het Microsoft compliance-Beheercentrum, maar de opties voor het instellen en toepassen variëren.
      - Er zijn vertrouwelijkheids labels voor sites, groepen en teams op container niveau (de instellingen zijn niet van toepassing op inhoud in de container). Deze worden gepubliceerd voor gebruikers en groepen die ze toepassen wanneer ze een site, groep of team inrichten.
      - Er zijn tekstlabels voor actieve inhoud. Deze worden ook gepubliceerd voor gebruikers of groepen die ze handmatig toepassen, of ze worden automatisch toegepast wanneer:
        - Het bestand wordt geopend/bewerkt en opgeslagen op het bureaublad van de gebruiker of op een SharePoint-site.
        - Een e-mailbericht is geconceptd en verzonden.
      - Er zijn tekstlabels voor de automatische toepassing van de bestanden op de rest van SharePoint en OneDrive, naast e-mailberichten in transit via Exchange. Deze zijn bedoeld voor alle sites of specifieke, en worden automatisch toegepast op de bestanden op de rest van deze omgevingen.

2. De huidige vertrouwelijkheids label rationaliseren met oude of alternatieve methoden

   - Azure Information Protection

      Het huidige vertrouwelijkheids schema moet mogelijk worden afgestemd op basis van een bestaande implementatie van [Azure Information Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) .
   - OME

      Als u op zoek bent naar een modern gevoeligheid voor e-mail beveiliging en bestaande e-mail versleutelingsmethoden zoals OME, kunnen ze samenwerken, maar u moet de scenario's begrijpen waarin ze moeten worden toegepast. Zie [Office 365-bericht versleuteling (OME) voor Office](#office-365-message-encryption-ome-new-capabilities), waaronder een tabel die een tabel omvat met de basisbescherming van het type bescherming met de OME.

3. Integratie van een uitgebreid informatie schema voor informatiebescherming plannen. Met OME kunt u op de hoogte blijven van de meest voorkomende functies, zoals Microsoft 365 preventie van gegevensverlies en beveiliging van de Cloud app. Bekijk de beschikbaarheid van de [palletlabels en de Microsoft Cloud-app](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) voor informatie over het bereiken van gegevensbescherming met betrekking tot de privacy.

4. Het ontwikkelen van een milieukeur classificatie en besturingsschema. Zie de [taxonomiegegevens classificatie en vertrouwelijkheids label](https://aka.ms/dataclassificationwhitepaper).

### <a name="general-guidance"></a>Algemene richtlijnen

1. **Schema definitie.** Voordat u de technische mogelijkheden voor het toepassen van labels en beveiliging toepast, kunt u het beste in uw organisatie werken om een classificatieschema te definiëren. Misschien hebt u al een classificatieschema, zodat u eenvoudiger persoonlijke gegevens kunt toevoegen. 
2. **Aan de slag.** Onderzoek eerst op het aantal en de namen van de etiketten die u wilt implementeren. Voer deze activiteiten uit zonder u zorgen te maken over de technologieën en de manier waarop labels worden toegepast. Dit schema universeel toepassen in uw organisatie, inclusief gegevens die zich lokaal bevinden en in andere cloudservices.
3. **Aanvullende aanbevelingen** Wanneer u beleidsregels, etiketten en voorwaarden ontwerpt en implementeert, kunt u het volgende doen:

   - **Gebruik bestaand classificatieschema (indien aanwezig).** Veel organisaties gebruiken al gegevensclassificatie in bepaalde vormen. Evalueer zorgvuldig het bestaande label schema en gebruik het als dit mogelijk is. Door gebruik te maken van vertrouwde labels die herkenbaar zijn voor uw eindgebruikers, dient u de acceptatie van de schijf te gebruiken.
   - **Begin klein.** Er is bijna geen limiet voor het aantal etiketten dat u kunt maken. Grote nummers van labels en sublabels kunnen echter langzaam worden vastgesteld.
   - **Scenario's en gebruiks kwesties gebruiken.** Identificeer veelgebruikte use-cases binnen uw organisatie en gebruik scenario's die voortvloeien uit de regelgeving voor gegevensbescherming waarvan u deel uitmaakt. Controleer of de configuratie van het etiket en de classificatie voor de afdeling in de praktijk werkt.
   - **Vraag elke aanvraag voor een nieuw etiket.** Heeft elk scenario of een use case echt behoefte aan een nieuw etiket of kunt u dit gebruiken? Als u het aantal etiketten tot een minimum beperkt, verbetert de acceptatie.
   - **Gebruik labels voor belangrijkste afdelingen.** Voor sommige afdelingen geldt een specifieke behoeften waarbij bepaalde etiketten zijn vereist. U kunt deze labels definiëren als sublabels aan een bestaand etiket en het beleid voor het bereik dat is toegewezen aan gebruikersgroepen, in plaats van globaal te gebruiken.
   - **Overweeg om beleid te bereiken.** Beleidsregels die zijn gericht aan subsets van gebruikers, verhinderen overbelasting. Met een bereik beleid kunt u specifieke labels of sublabels voor rollen of afdelingen toewijzen aan alleen de werknemers die voor die specifieke afdeling werken. 
   - **Betekenisvolle etiket namen gebruiken.** Probeer geen jargon, standaarden of acroniemen te gebruiken als etiket namen. Gebruik de namen die Resonate bij de eindgebruiker worden gebruikt om de acceptatie te verbeteren. In plaats van labels te gebruiken, zoals PII, PCI, HIPAA, LBI, MBI en HBI, beschouwt u namen als niet-zakelijk, openbaar, algemeen, vertrouwelijk en zeer vertrouwelijk.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Tekstlabels voor sites, groepen en teams maken en implementeren

Wanneer u [Tekstlabels](../compliance/sensitivity-labels-teams-groups-sites.md) wilt maken in het nalevings centrum voor microsoft 365, kunt u deze nu op de volgende containers toepassen:

- Microsoft teams-sites
- Microsoft 365-groepen (voorheen Office 365-groepen)
- SharePoint-sites

Gebruik de volgende label instellingen om de inhoud van deze containers te beschermen:

- Privacy (openbaar of privé) van Microsoft 365 met groep verbonden teams-sites
- Externe gebruikers toegang
- Toegang vanaf niet-beheerde apparaten

Voor de privacy van gegevens kunt u het voorkomen dat u extern delen gebruikt voor containers die worden gebruikt voor het opslaan van inhoud met gevoelige persoonlijke gegevens, de bestanden die de gegevens bevatten als privé markeren en beheerde apparaten vereisen.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Tekstlabels voor inhoud maken en implementeren

Met behulp van coderings labels die zijn toegepast op bestanden, kunt u de inhoud ervan versleutelen, de inhoud van het watermerk en andere besturingselementen definiëren voor inhoud van Office-toepassingen, zoals Outlook en Office op het web.

Wanneer u klaar bent om de gegevens van uw organisatie met behulp van een gevoeligheid te beschermen:

1. **Maak de etiketten.** Maak en noem uw gevoeligheids etiketten op basis van de classificatie taxonomie voor verschillende niveaus van de inhoud van de organisatie. Zie voor meer informatie over het ontwikkelen van een classificatie taxonomie de [taxonomiegegevens classificatie en vertrouwelijkheids label](https://aka.ms/dataclassificationwhitepaper).
2. **Definiëren wat elk etiket kan doen.** Configureer de instellingen voor beveiliging die u wilt koppelen aan elk etiket. Als u bijvoorbeeld de inhoud van een laag of voettekst wilt laten toepassen, moet u een watermerk hebben met een watermerk en moet de optie versleuteling zijn ingeschakeld, omdat er geen koptekst of voettekst is toegepast.
3. **Publiceer de etiketten.** Nadat de milieukeur labels zijn geconfigureerd, kunt u ze publiceren met behulp van een etiket beleid. Bepalen welke gebruikers en groepen de labels en welke beleidsinstellingen moeten gebruiken. Eén etiket is herbruikbaar. U kunt dit eenmaal definiëren en u kunt dit opnemen in diverse label beleidsregels die aan verschillende gebruikers zijn toegewezen.

Wanneer u de vertrouwelijkheids etiketten van het Microsoft 365 compliance Center publiceert, wordt deze weergegeven in [Office-apps](../compliance/sensitivity-labels-office-apps.md) voor gebruikers om inhoud te classificeren en te beschermen terwijl deze wordt gemaakt of bewerkt.

![Implementatie stroom voor vertrouwelijkheids label in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Voor de privacy van gegevens kunt u handmatig een gevoeligheids label met versleuteling en andere regels toepassen op e-mail of inhoud met gevoelige persoonlijke gegevens.

>[!Note]
>Tekstlabelings labels met versleuteling ingeschakeld voor e-mail hebben enkele overlappende functies met OME. Zie [vergelijking van beveiligings scenario's met OME en](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)coderings labels.

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Automatische labels aan de client zijde wanneer gebruikers documenten bewerken of e-mailberichten opstellen

Als u een gevoeligheids label maakt, kunt u [Dit label automatisch toewijzen](../compliance/apply-sensitivity-label-automatically.md) aan inhoud, waaronder e-mail, wanneer deze overeenkomen met de voorwaarden die u opgeeft.

De mogelijkheid om op basis van de volgende berekeningsopties voor de inhoud van labels toe te passen:

- U hoeft uw gebruikers niet te trainen wanneer ze elk van uw classificaties gebruiken.
- U hoeft niet te vertrouwen op gebruikers om de inhoud juist te classificeren.
- Gebruikers hoeven niet langer op de hoogte te zijn van uw beleidsregels, ze kunnen zich in plaats daarvan op hun werk richten.

Automatische labeling biedt ondersteuning voor het aanbevelen van een label aan gebruikers en ook automatisch een etiket. In beide gevallen besluit de gebruiker of u het label wilt accepteren of weigeren, zodat u zeker weet dat de inhoud van de juiste labels moet worden gebruikt.

Deze labels op de client hebben een minimale vertraging voor documenten omdat het label kan worden toegepast, zelfs voordat het document wordt opgeslagen. U kunt echter niet alle client-apps ondersteuning bieden voor automatische labeling. Deze functie wordt ondersteund door de client voor Azure Information Protection (Unified labels) en [bepaalde versies van Office-apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Zie voor meer informatie [over het configureren van automatische labeling voor Office-apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Voor de privacy van gegevens kunt u tekstgevoelige labels automatisch toepassen voor inhoud met gevoelige persoonlijke gegevens.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Automatische labeling op service zijde wanneer inhoud al is opgeslagen

Deze methode heet automatisch classificeren met gevoeligheids labels. U kunt ook de naam automatisch label geven voor gegevens op het rest gebied (voor documenten in SharePoint en OneDrive) en gegevens in transit (voor e-mailberichten die zijn verzonden of ontvangen via Exchange). Voor Exchange bevat het postvak geen e-mailberichten in postvakken op rest.
 
Aangezien dit label wordt toegepast door de service zelf in plaats van door de gebruikerstoepassing, hoeft u zich geen zorgen te maken over de apps van gebruikers en welke versie. Daarom is deze functie direct beschikbaar in de hele organisatie en geschikt voor etikettering op schaal. Beleid voor automatisch labelen biedt geen ondersteuning voor aanbevolen labels omdat de gebruiker niet werkt met het label proces. In plaats daarvan wordt de beleidsbeheerder uitgevoerd de beleidsregels uit te voeren en te zorgen voor een juiste etiketering van de inhoud voordat u het label daadwerkelijk toepast.

Zie voor meer informatie [over het instellen van een automatisch labelbeleid voor SharePoint, OneDrive en Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

Voor de privacy van de site gelden de namen van push gevoelige labels voor automatische versleuteling van inhoud met gevoelige persoonlijke gegevens.

## <a name="data-loss-prevention"></a>Preventie van gegevensverlies 

Met de functie [preventie van gegevensverlies](../compliance/data-loss-prevention-policies.md) in microsoft 365 kunt u risicoieve, onbedoelde of ongepast delen detecteren, waarschuwen en blokkeren, zoals het delen van gegevens met persoonlijke gegevens, zowel intern als extern.

Met DLP kunt u het volgende doen:

- Identificeren en controleren van riskante activiteiten.
- Vertel gebruikers met informatie over de context van de juiste beslissingen.
- Beleidsregels voor datagebruik toepassen op inhoud zonder dat de productiviteit wordt belemmerd.
- U kunt integreren met classificatie en labels toepassen om gegevens te detecteren en te beschermen wanneer deze worden gedeeld.

### <a name="supported-workloads-for-dlp"></a>Ondersteunde werkbelasting voor DLP

Met een DLP-beleid in het nalevings centrum van Microsoft 365 kunt u gevoelige items op veel locaties identificeren, controleren en automatisch beschermen in Microsoft 365, zoals Exchange Online, SharePoint, OneDrive en Microsoft teams.

U kunt bijvoorbeeld een document identificeren dat een creditcardnummer bevat dat is opgeslagen op een willekeurige OneDrive-site, of u kunt alleen de OneDrive-sites van bepaalde personen controleren.

U kunt ook gevoelige items controleren en beschermen in de lokale versies van Excel, PowerPoint en Word, waaronder de mogelijkheid om gevoelige items te identificeren en DLP-beleidsregels toe te passen. DLP biedt voortdurend toezicht wanneer gebruikers inhoud van deze Office-apps delen.

![Ondersteunde werkbelasting voor DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

In deze afbeelding ziet u een voorbeeld van DLP beveiliging van persoonlijke gegevens.

![Voorbeeld van de bescherming van persoonlijke gegevens met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP wordt gebruikt om een document of e-mailbericht te identificeren met een status record, en de toegang tot dat document automatisch te blokkeren of het e-mailbericht wordt verzonden. DLP waarschuwt de geadresseerde vervolgens met een beleidstip en stuurt een melding naar de eindgebruiker en de beheerder.

### <a name="planning-for-dlp"></a>Plannen voor DLP

Plan uw DLP-beleid voor: 

- Uw zakelijke vereisten.

- Een beoordeling op basis van risico van de organisatie, zoals beschreven in het [artikel vertrouwelijkheid van gegevens en het identificeren van gevoelige artikelen](information-protection-deploy-assess.md).

- Andere mechanismen voor informatiebescherming en beheerfuncties ter plaatse of voor het plannen van gegevens privacy.

- De typen gevoelige informatie die u hebt vastgesteld voor persoonlijke gegevens op basis van uw beoordelingen, zoals wordt beschreven in het [artikel de beoordeelings Risico's en gevoelige artikel identificeren](information-protection-deploy-assess.md). DLP-beleidsvoorwaarden kunnen gebaseerd zijn op zowel gevoelige informatie typen als Bewaar labels.

- Voor de Bewaar etiketten moet u DLP-voorwaarden opgeven. Zie het artikel over de [beheerste informatie in het artikel over de privacy van de gegevens in uw organisatie](information-protection-deploy-govern.md) voor meer informatie.

- Voortdurende DLP-beleidsbeheer, zodat iemand in de organisatie beleidsregels kan gebruiken voor wijzigingen in gevoelige informatie typen, Bewaar etiketten, voorschriften en compliance-beleidsregels.

Hoewel gevoelige labels niet kunnen worden gebruikt in DLP-beleidsvoorwaarden, zijn bepaalde beveiligings scenario's om toegang te voorkomen, mogelijk met alleen gevoelige gevoelige labels die automatisch kunnen worden toegepast op basis van gevoelige informatie typen. Als er krachtige milieu aanduiding is ter plaatse, moet u overwegen of DLP moet worden gebruikt om de beveiliging te bevorderen omdat:

  - DLP kan delen van bestanden voorkomen. Met beschikbaarheid van vertrouwelijkheids labels kunt u eenvoudig toegang voorkomen

  - DLP biedt meer granulaire niveaus van zeggenschap over regels, voorwaarden en acties.

  - DLP-beleid kan worden toegepast op teams-chat-en kanaalberichten. Palletlabels kunnen alleen worden toegepast op documenten en e-mailberichten.


### <a name="dlp-policies"></a>DLP-beleid

DLP-beleid wordt geconfigureerd in het Microsoft compliance-Beheercentrum en het beschermingsniveau opgeven, het type gevoelige informatie dat het beleid zoekt en de Doelbelasting. De basisonderdelen bestaan uit het identificeren van de bescherming en de gegevenstypen.

![Configuratie van DLP-beleid in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Hier ziet u een voorbeeld van het DLP-beleid voor de bewustmaking van AVG.

![Voorbeeld van DLP-beleid voor bewustmaking van AVG](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Zie [dit artikel](../compliance/create-test-tune-dlp-policy.md) voor meer informatie over het maken en toepassen van DLP-beleidsregels.

### <a name="protection-levels-for-data-privacy"></a>Beveiligingsniveaus voor privacy

De volgende tabel bevat drie configuraties voor een betere beveiliging op basis van DLP.

![Beveiligingsniveaus van gegevens privacy met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

De eerste configuratie, bewustmaking, kan worden gebruikt als uitgangspunt en minimale bescherming tegen de naleving van de vereisten voor informatie privacy.

>[!Note]
>Naarmate de mate van bescherming hoger is, kan de mogelijkheid van gebruikers om informatie te delen en toegang te krijgen tot gegevens in sommige gevallen te verkorten en de dagelijkse taken mogelijk te voltooien.
>

Neem de tijd om uw medewerkers te helpen binnen een veiligere omgeving productief te zijn bij het verhogen van de beveiligingsniveaus, zodat u ze gemakkelijker kunt betrekken en leren hoe u zich kunt richten op nieuwe beveiligingsmaatregelen en-procedures.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Voorbeeld van het gebruik van tekstlabels met DLP

U kunt met DLP labels aan de hand van DLP-labels schrijven voor een zeer gereglementeerde omgeving. Dit zijn de belangrijkste stappen van de geïntegreerde implementatie:

1. Voor de veiligheid van de gegevens zijn reglementaire en andere zakelijke vereisten voor gegevens privacy gedocumenteerd.
2. Gegevensbronnen, typen en eigendom bereiken zijn gekarakteriseerd ten opzichte van de vertrouwelijkheid van gegevens.
3. Een algemene strategie voor de vereisten en beveiliging van hotspots voor gegevensbescherming en beveiliging van de privacy-hotspots.
4. Een gefaseerd actieplan met de beknopte strategie voor het opslaan van gegevens.

Wanneer deze elementen worden vastgesteld, kunt u gebruikmaken van gevoelige informatie typen, uw gevoeligheid voor de taxonomie en het DLP-beleid samen. In deze afbeelding wordt een voorbeeld weergegeven.

![Voorbeeld van palletlabels met DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Hier volgen enkele scenario's voor gegevensbescherming met behulp van DLP-en vertrouwelijkheids etiketten, zoals weergegeven in de afbeelding.

| Voorbeeld | Bewerkt |
|:-------|:-----|
| Een | <ol><li>Vertrouwelijkheids label voor inhoud wordt gepubliceerd door een beheerder aan gebruikers en groepen voor een handmatige of automatische toepassing voor inhoud en e-mail. </li><li>Gebruiker A past de labels handmatig of automatisch toe als u met inhoud communiceert, met versleutelings-of andere instellingen. </li><li>Gebruiker A stuurt een beveiligde e-mail of een beveiligd bestand naar gebruiker B, een gastgebruiker. </li></ol> |
| BB | DLP-beleid dat door een beheerder is gepubliceerd voor gebruiker A blokkeert een gebruiker, zodat de e-mail en/of het bestand niet naar gebruiker B wordt verzonden. |
| Wisselstroom |  Het vertrouwelijkheids label waarbij de instelling ' eigenaar kan geen gasten uitnodigen ' is gepubliceerd naar gebruiker A, die een teams-team of SharePoint-site bewaart. Een andere gebruiker van de site selectief probeert een bestand te delen met gebruiker B, maar DLP blokkeert. |
| 2D | Het vertrouwelijkheids label voor de automatische toepassing van site-inhoud wordt gepubliceerd op een of meer sites, die een extra beveiligingslaag bieden, wat resulteert in een beveiligde site. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Nieuwe mogelijkheden van Office 365-bericht versleuteling (OME)

Gebruikers gebruiken vaak e-mail om gevoelige items te uitwisselen, zoals informatie over de gezondheid van patiënten of informatie van klanten en werknemers. Met behulp van e-mailbericht versleuteling zorgt u ervoor dat alleen de beoogde geadresseerden de inhoud van een bericht kunnen zien

Met [OME](../compliance/ome.md)kunt u versleutelde berichten verzenden en ontvangen tussenpersonen binnen en buiten uw organisatie. OME werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. Met OME kunt u ervoor zorgen dat alleen bedoelde geadresseerden de inhoud van een bericht kunnen bekijken.

Voor de privacy van gegevens kunt u OME gebruiken om interne berichten met gevoelige items te beschermen. Office 365-bericht versleuteling is een online dienst die is gebaseerd op Microsoft Azure Rights Management (Azure RMS) dat deel uitmaakt van Azure Information Protection. Dit omvat ook versleuteling, identiteit en autorisatiebeleid om uw e-mail te beveiligen. U kunt berichten versleutelen met behulp van sjablonen voor rac's, de optie niet doorverbinden en de optie alleen versleutelen.

U kunt ook de e-mail stroom regels definiëren om deze beveiliging toe te passen. U kunt bijvoorbeeld een regel maken die de versleuteling van alle berichten die naar een bepaalde geadresseerde zijn geadresseerd, of die specifieke trefwoorden bevat in de onderwerpregel, en ook opgeven dat geadresseerden de inhoud van het bericht niet kunnen kopiëren of afdrukken.

Daarnaast helpt de [versleutelings functie van OME geavanceerde bericht versleuteling](../compliance/ome-advanced-message-encryption.md) te voldoen aan de nalevings verplichtingen met meer flexibele besturingselementen van externe geadresseerden en de toegang tot gecodeerde e-mailberichten. Met OME geavanceerde bericht versleuteling in Microsoft 365 kunt u vertrouwelijke e-mailberichten beheren die buiten de organisatie worden gedeeld met automatisch beleidsregels voor het detecteren van gevoelige gegevenstypen. 

Als u e-mail met een externe partij wilt delen, kunt u een vervaldatum en berichten intrekken opgeven. U kunt alleen een vervaldatum voor berichten die naar externe geadresseerden worden verzonden, intrekken en instellen.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Vergelijking van beveiligings scenario's voor e-mail met OME en gevoeligheids labels

OME en coderings labels die zijn toegepast op e-mailberichten met versleuteling, zijn iets te voorkomen, dus het is belangrijk dat u weet in welke scenario's die van toepassing kunnen zijn, zoals in deze tabel wordt weergegeven.

| Voorbeeld | Vertrouwelijkheids labels | OME |
|:-------|:-----|:-------|
| Internal + partners <br> Veilig communiceren en samenwerken tussen interne gebruikers en vertrouwde partners | Adviseren – labels met volledig aangepaste classificatie en bescherming | Ja – alleen versleutelen of beveiliging niet doorsturen zonder classificatie |
| Externe partijen <br> Veilig communiceren en samenwerken met gebruikers van externe consumenten | Ja – geadresseerden vooraf definiëren in label | Aanbevelingen: Just-in-time bescherming op basis van geadresseerden |
| Interne + partners, met vervaldatum/intrekking <br> Toegang tot e-mail en inhoud beheren met interne gebruikers en vertrouwde partners met een vervaldatum en intrekking | Aanbevelingen-volledig aangepaste bescherming met toegangs duur, gebruiker kan bestanden handmatig bijhouden en intrekken | Nee: geen intrekking of verlooptijd voor interne e-mail |
| Externe partijen met een vervaldatum/intrekking <br> Toegang tot e-mail en inhoud beheren met externe/consumenten gebruikers met een vervaldatum en intrekking | Ja – gebruikers kunnen bestanden handmatig bijhouden | Adviseren (E5) – beheerders kunnen e-mail intrekken vanuit beveiliging & nalevings centrum |
| Automatisch labelen <br> Organisatie wil automatisch e-mailberichten/bijlagen beveiligen met bepaalde gevoelige inhoud en/of specifieke geadresseerden | Adviseren (E5)-automatische labeling in Exchange-en Outlook-clients, breidt de e-mail stroom regels en het DLP-beleid. | Ja-e-mail stroom regels en DLP-beleid met alleen versleutelen of geen beveiliging doorsturen |
||||

Er zijn ook verschillen tussen de eindgebruikers en de beheer ervaring tussen de volgende twee methoden:

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams met bescherming voor zeer gevoelige gegevens

Voor organisaties die het plannen van persoonlijke gegevens, onder voorschriften voor de privacy van gegevens in teams, vindt u hier [een team configureren met beveiligings isolatie](secure-teams-security-isolation.md), dat gedetailleerde richtlijnen en configuratiestappen biedt voor:

- Identiteit en apparaattoegang
- Maken van een privé team
- Vergrendelen van onderliggende team site machtigingen
- Een op groepen gebaseerde vertrouwelijkheids label met versleuteling
