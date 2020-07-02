---
title: 'Stap 2: classificatie voor uw omgeving configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie over en configuratie van verschillende manieren om gegevens in uw organisatie te classificeren.
ms.openlocfilehash: 57d4c692630826f371ea825d86fc64b959b71df2
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005808"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Stap 2: classificatie voor uw omgeving configureren

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 6: Gegevensbeveiliging](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

In deze stap werkt u met uw juridische en nalevingsteams om een classificatieschema te definiëren voor de gegevens van uw organisatie.

## <a name="microsoft-365-classification-types"></a>Classificatietypen van Microsoft 365

Microsoft 365 bevat vier classificatietypen:

- Gevoelige informatietypen
- Retentielabels
- Gevoeligheidslabels
- Labels en bescherming van Azure Information Protection

### <a name="sensitive-information-types"></a>Gevoelige informatietypen

Met gevoelige informatietypen voor Microsoft 365 definieert u hoe geautomatiseerd processen herkent, zoals het zoeken naar specifieke gegevenstypen. Dit zijn onder andere gevoelige gegevens van werknemers of klanten, zoals burgerservicenummers en creditcardnummers. U gebruikt de gevoelige informatietypen voor het zoeken naar gevoelige gegevens en u past DLP-regels en -beleid (preventie van gegevensverlies) toe om deze gegevens te beveiligen. Zie [wat DLP-beleid omvat](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains) voor meer informatie. 

Gevoelige informatietypen zijn met name handig om te voldoen aan naleving en vereisten van regelgeving, zoals voor de Algemene Verordening Gegevensbescherming (AVG).

### <a name="retention-labels"></a>Retentielabels

Een deel van het definiëren van een strategie van gegevensbeheer bestaat uit het bepalen hoe lang bepaalde typen documenten of documenten met specifieke inhoud moeten worden bewaard in overeenstemming met het organisatiebeleid en regionale regelgeving. Zo moeten sommige typen documenten gedurende een bepaalde periode worden bewaard en vervolgens verwijderd, en moeten andere voor onbepaalde tijd bewaard blijven.

Voor documenten die zijn opgeslagen in Microsoft 365, definieert u en past u retentielabels toe op documenten en gegevens die zijn opgeslagen in Exchange-e-mail, SharePoint Online, OneDrive voor Bedrijven en chat- en kanaalberichten van Microsoft Teams. 

Als u retentielabels gebruikt, moet u een label configureren voor elke categorie met bestanden waarop een bewaarbeleid moet worden toegepast. Met het retentielabel kunt u het volgende opgeven:

- Een verzameling beschrijvingen voor de bestanden (bijvoorbeeld op bedrijfsafdeling, bestandscategorie of voorschrift).
- De retentie-instellingen voor de bestanden waaraan het retentielabel is gekoppeld, zoals de bewaartijden en gedragingen nadat de bewaartijd is bereikt.

U kunt een retentielabel ook automatisch op bestanden toepassen door een SharePoint Online-site zodanig te configureren dat een standaardretentielabel wordt toegepast op alle nieuwe documenten op de site. 

Zie het [overzicht met retentielabels](https://docs.microsoft.com/office365/securitycompliance/labels) voor meer informatie.

### <a name="sensitivity-labels"></a>Gevoeligheidslabels

Bij het beschermen en implementeren van beveiliging voor specifieke soorten documenten of documenten met specifieke inhoud worden deze onder meer gemarkeerd met een label zodat de extra beveiliging kan worden toegepast. Met gevoeligheidslabels in Microsoft 365 kunt u het volgende doen:

- Beveiligingsinstellingen afdwingen, zoals versleuteling, machtigingen of het toevoegen van een watermerk.
- Endpoint Protection van Windows-gegevensbescherming gebruiken om te voorkomen dat inhoud wordt gekopieerd naar een app van derden, zoals Twitter of Gmail, of wordt gekopieerd naar verwisselbare opslag, zoals een USB-station.
- Microsoft Cloud App Security (CAS) gebruiken om inhoud in apps en services van derden te beveiligen. 
- Inhoud classificeren zonder beveiligingsinstellingen.

Als u gevoeligheidslabels gebruikt, moet u een label configureren voor elk beveiligings- en informatiebeschermingsniveau. Maak bijvoorbeeld drie gevoeligheidslabels voor:

- Basislijn
- Gevoelig
- Sterk gereglementeerd

Als u bestanden met sterk gereglementeerde gegevens opslaat op een SharePoint Online-site en u wilt dat deze bestanden dezelfde machtigingen hebben als de site indien de bestanden de site verlaten, moet u een extra gevoeligheidslabel maken met dezelfde machtigingen als voor de site.

Zie dit [overzicht met gevoeligheidslabels ](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels) voor meer informatie.

### <a name="azure-information-protection-labels-and-protection"></a>Labels en bescherming van Azure Information Protection

U kunt Azure Information Protection-labels gebruiken om de documenten en e-mailberichten in uw organisatie te classificeren. Deze labels kunnen worden toegepast op documenten die zijn opgeslagen buiten Microsoft 365. Deze labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers, of door een combinatie waarin gebruikers aanbevelingen hebben gekregen.

Ga als volgt te werk om Azure Information Protection-labels en -beveiliging te plannen en te implementeren:

1. Bekijk de [vereisten voor Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Volg het [implementatieschema voor classificatie, labels en bescherming](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Zie de [bibliotheek met documentatie van Azure Information Protection](https://docs.microsoft.com/information-protection/) voor meer informatie.

Bestaande Azure Information Protection-labels werken naadloos samen met gevoeligheidslabels. U kunt bijvoorbeeld uw bestaande labels voor Azure Information Protection-labels en de labels die worden toegepast op documenten en e-mail behouden.

Als u zowel gevoeligheidslabels als Azure Information Protection-labels hebt, moet u de [Azure Information Protection-labels naar de gevoeligheidslabels migreren](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).

## <a name="example-classification-for-gdpr"></a>Voorbeeld: classificatie voor AVG

Zie [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data) (Een classificatieschema voor persoonlijke gegevens ontwikkelen) voor een voorbeeld van een classificatieschema dat persoonlijke gegevens voor AVG bevat.

## <a name="take-it-for-a-test-drive"></a>Doe de test

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Handleiding voor het testlab: gegevensclassificatie](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) voor deze stap als tussentijds controlepunt.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)|[Verbeterde beveiliging voor Office 365 configureren](infoprotect-configure-increased-security-office-365.md)|

