---
title: Informatiebescherming implementeren voor regelgeving voor gegevensprivacy met Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: Configureer de beveiligings- en service-infrastructuur om uw gegevens te beschermen en zich te houden aan de privacyvoorschriften van gegevens.
ms.openlocfilehash: 640ce075515c687c037cb0e4ab3e03e3beda81dc
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522287"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Informatiebescherming implementeren voor regelgeving voor gegevensprivacy met Microsoft 365

Uw organisatie kan onderworpen zijn aan regionale regelgeving inzake gegevensprivacy die vereist dat u rechten en controle over persoonlijke gegevens die in uw IT-infrastructuur zijn opgeslagen, zowel on-premises als in de cloud, moet beschermen, beheren en beheren. Het beste voorbeeld van een verordening inzake gegevensprivacy is de Algemene Verordening Gegevensbescherming (AVG) van de Europese Unie. Het niet naleven van de privacyregels kan leiden tot aanzienlijke boetes.

Voorbeelden van de typen gegevens in Microsoft 365 zijn chatsessies in Microsoft Teams, e-mails in Exchange en bestanden in SharePoint en OneDrive. Deze oplossing biedt richtlijnen voor het identificeren, lokaliseren, beveiligen, beheren en reageren op privacyincidenten voor persoonlijke gegevens die zijn opgeslagen in Microsoft 365-services waarvoor privacyvoorschriften gelden.

![Informatiebescherming implementeren voor gegevensprivacyregels](../media/information-protection-deploy/information-protection-deploy-big-picture.png)

Aanvullende informatie wordt ook verstrekt over het gebruik van Microsoft 365-identiteits-, apparaat- en beschermingsbeveiligingscontroles voor uw gegevensprivacybehoeften. 

Gebruik deze Microsoft 365-mogelijkheden en functies om te voldoen aan de criteria voor de bescherming van informatie voor naleving van de voorschriften inzake gegevensprivacy.

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Compliancebeheer | Beheer van wettelijk voorgeschreven complianceactiviteiten met betrekking tot de cloudservices van Microsoft met dit hulpprogramma voor risicoanalyse op basis van werkstromen in het Service Trust Portal van Microsoft. | Microsoft 365 E3 en E5 |
| Compliancescore (preview) | Bekijk een totaalscore van uw huidige complianceconfiguratie en aanbevelingen voor het verbeteren hiervan in het Microsoft 365 Compliance Center. | Microsoft 365 E3 en E5 |
| Atp (Office Advanced Threat Protection) | Beveilig uw Microsoft 365-apps en -gegevens tegen een aanval, zoals e-mailberichten, Office-documenten en hulpmiddelen voor samenwerking. | Microsoft 365 E3 en E5 | 
| Vertrouwelijkheidslabels | Classificeer en bescherm de gegevens van uw organisatie zonder de productiviteit van gebruikers en hun vermogen om samen te werken te belemmeren door het labelen van e-mail, bestanden of websites met diverse beschermingsniveaus. | Microsoft 365 E3 en E5 |
| Preventie van gegevensverlies (DLP) | Detecteer, waarschuw voor en blokkeer risicovol, onbedoeld of ongepast delen, zoals het delen van gegevens met persoonlijke informatie, zowel intern als extern. | Microsoft 365 E3 en E5 | 
| Labels en beleid voor gegevensretentie | Implementeer informatiebeheer-besturingselementen, zoals hoe lang gegevens bewaard blijven en vereisten voor het opslaan van persoonlijke gegevens van klanten, om te voldoen aan het beleid of de gegevensvoorschriften van uw organisatie. | Microsoft 365 E3 en E5 |
| E-mailversleuteling | Versleutelde e-mailberichten met gereguleerde gegevens, zoals persoonlijke gegevens van klanten, verzenden naar en ontvangen van personen binnen en buiten de organisatie. | Microsoft 365 E3 en E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organisatie van de begeleiding in deze oplossing

Om u inzicht te geven in de Microsoft 365-hulpprogramma's die beschikbaar zijn voor het identificeren, beheren, beheren en controleren van persoonsgegevens die onderworpen zijn aan een of meer privacygerelateerde voorschriften, is deze richtlijnen ingedeeld in secties.
 
![Informatiebescherming implementeren voor gegevensprivacyregels](../media/information-protection-deploy/information-protection-deploy-grid.png)

Elk van deze secties komt overeen met een apart artikel in deze oplossing.

>[!Note]
>Als u al bekend bent met uw privacyverplichtingen en uitvoert tegen een bestaand abonnement, u zich richten op de richtlijnen Voor voorkomen, beschermen, behouden en onderzoeken.

>[!Important]
>Als u deze richtlijnen volgen, voldoet u niet noodzakelijkerwijs aan de regelgeving voor gegevensprivacy, vooral gezien het aantal vereiste stappen dat buiten de context van de functies valt. U bent verantwoordelijk voor het waarborgen van uw compliance en het raadplegen van uw juridische en compliance teams of om advies en advies in te winnen bij derden die gespecialiseerd zijn in compliance.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan: De privacyrisico's van gegevens beoordelen en gevoelige items identificeren 

Het beoordelen van de privacyvoorschriften en -risico's waaraan uw organisatie is onderworpen, is een belangrijke eerste stap voordat u begint met het implementeren van verbeteringen, waaronder die welke mogelijk zijn via de Microsoft 365-configuratie. Dit kan een algemene beoordeling van de gereedheid of identificatie van bepaalde gevoelige informatietypen zijn die onderworpen zijn aan wettelijke controles waaraan uw organisatie moet voldoen, evenals het optreden ervan in uw Microsoft 365-omgeving.

Zie De [privacyrisico's van gegevens beoordelen en gevoelige items identificeren](information-protection-deploy-assess.md)voor meer informatie.

## <a name="track-use-compliance-score-and-compliance-manager"></a>Track: Compliance Score en Compliance Manager gebruiken 

Compliance Score en Compliance Manager bieden een geïntegreerde set tools die beschikbaar zijn in het Microsoft 365 Compliance-beheercentrum en servicesvertrouwensportal. Samen bieden deze tools u een ingebouwde mogelijkheid om verbeteringsacties in het algemeen bij te houden en te beheren, evenals die met betrekking tot de regelgeving inzake meerdere gegevensprivacy waaraan u wordt onderworpen.

Met de tools u ook gebruikmaken van ingebouwde beoordelingssjablonen die specifiek zijn voor elke verordening, waarbij u actiepunten voor elke geselecteerde beoordelingssjabloon bijhouden en specifieke regelgevingscontroles bekijken en deze relateren aan specifieke acties.

Zie [Compliance Score en Compliance Manager gebruiken om verbeteracties te beheren voor](information-protection-deploy-compliance.md)meer informatie.

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Voorkomen: identiteits-, apparaat- en bedreigingsbescherming gebruiken voor regelgeving voor gegevensprivacy

Microsoft 365 biedt een aantal mogelijkheden voor identiteits-, apparaat- en bedreigingsbescherming die u gebruiken om te voldoen aan de naleving van de naleving van de privacy van gegevens. 

Zie [Identiteits-, apparaat- en bedreigingsbescherming gebruiken voor de regelgeving op het spel](information-protection-deploy-identity-device-threat.md).

In dit artikel wordt kort beschreven waar de regelgeving voor gegevensprivacy in deze gebieden over het algemeen om vraagt en wordt een lijst gegeven van gerelateerde Microsoft 365-oplossingen, met links naar meer informatie om u te helpen eventuele implementatievereisten aan te pakken. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Informatie beschermen die onderworpen is aan de privacywetgeving van gegevens

De regelgeving inzake gegevensprivacy dicteert een aantal controles op de bescherming van persoonsgegevens die in uw omgeving kunnen worden gebruikt, waaronder meer dan veertig beschermingsinformatiecontroles voor alleen de vier voorschriften inzake gegevensprivacy in onze voorbeeldset van GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (Us Health Care Privacy Act) en de Brazil Data Protection Act (LGPD).

Zie [Informatie beveiligen onder voorbehoud van de privacyregelgeving van gegevens in uw organisatie voor](information-protection-deploy-protect-information.md)meer informatie.

In dit artikel worden de belangrijkste controleschema's uiteengezet die kunnen worden gebruikt voor het aanpakken van informatiebeschermingsbehoeften voor gegevensprivacy in uw organisatie.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Behouden: Informatie regelen die onderworpen is aan de privacywetgeving

De regelgeving inzake gegevensprivacy vraagt om controles op het beheer van persoonlijke gegevens die in uw omgeving kunnen worden gebruikt, waaronder meer dan vierentwintig controles in de vier regelgeving inzake gegevensprivacy in onze voorbeeldset van GDPR, CCPA, HIPAA-HITECH en LGPD.

Zie [Informatie beheren die onderworpen is aan de privacyregelgeving van gegevens in uw organisatie](information-protection-deploy-govern.md).

Hoewel de regelgeving inzake gegevensprivacy vaag kan zijn met betrekking tot &mdash; informatiebeheer, zoals doelgerichte bewaring, het verwijderen en archiveren van &mdash; dit artikel, worden de primaire controleschema's vastgelegd die u gebruiken om adresbeheerbehoeften voor gegevensprivacy in uw organisatie te gebruiken.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>Onderzoek: Monitor en reageer onder voorbehoud van de privacywetgeving

Er zijn Microsoft 365-functies beschikbaar om u te helpen bij het monitoren, onderzoeken en reageren op privacyincidenten in uw organisatie terwijl u gerelateerde mogelijkheden operationaliseert. 

Het hebben van processen, procedures en andere documentatie voor elk van deze kan belangrijk zijn om aan te tonen dat regelgevende instanties aan de regels voldoen.

Zie [Gegevensprivacy-incidenten in uw organisatie controleren en reageren op gegevensprivacy](information-protection-deploy-monitor-respond.md)voor meer informatie.
