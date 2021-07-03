---
title: Gegevensbescherming implementeren voor privacyregels voor gegevens met Microsoft 365
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
description: Gegevensbescherming configureren in Microsoft 365 voor privacyregels voor gegevens, zoals avg en de California Consumer Privacy Act (CTPA), waaronder Microsoft Teams, SharePoint en e-mail.
ms.openlocfilehash: c0ffe7cf850ec6e7ae8c974f983ce43668bf6f30
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287709"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Gegevensbescherming implementeren voor privacyregels voor gegevens met Microsoft 365

Uw organisatie is mogelijk onderworpen aan regionale privacyregels voor gegevens, waarvoor u rechten en controle moet bieden over persoonlijke gegevens die zijn opgeslagen in uw IT-infrastructuur, zowel on-premises als in de cloud. Het beste voorbeeld van een privacyregel voor gegevens is de Algemene verordening gegevensbescherming (AVG) van de Europese Unie. Als u zich niet aan de privacyregels voor gegevens houdt, kan dit leiden tot aanzienlijke boetes.

Voorbeelden van de typen gegevens in Microsoft 365 zijn chatsessies in Microsoft Teams, e-mailberichten in Exchange en bestanden in SharePoint en OneDrive. Deze oplossing biedt richtlijnen voor het beoordelen van risico's en het nemen van passende maatregelen om persoonlijke gegevens in Microsoft 365. Dit omvat het identificeren van persoonlijke gegevens, zodat u incidenten met gegevensbescherming kunt beschermen, regelen en hierop kunt reageren.

![Wat is informatiebeveiliging voor privacyregels voor gegevens](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

Er wordt ook aanvullende informatie verstrekt over het gebruik van Microsoft 365 identiteits-, apparaat- en bedreigingsbeveiligingsbesturingselementen voor uw privacybehoeften voor gegevens.

Bekijk deze video voor een overzicht van het implementatieproces.
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

Met Microsoft 365 functies en functies voldoet u aan de criteria voor het beveiligen van informatie.

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Compliancebeheer | Beheer nalevingsactiviteiten voor regelgeving, krijg een algemene score van uw huidige nalevingsconfiguratie en zoek aanbevelingen voor verbetering. Dit is een op werkstroom gebaseerd hulpprogramma voor risicoanalyse in de Microsoft 365-compliancecentrum. | Microsoft 365 E3 en E5 |
| Microsoft Defender voor Office 365 | Beveilig uw Microsoft 365-apps en -gegevens tegen een aanval, zoals e-mailberichten, Office-documenten en hulpmiddelen voor samenwerking. | Microsoft 365 E3 en E5 |
| Vertrouwelijkheidslabels | Classificeer en bescherm de gegevens van uw organisatie zonder de productiviteit van gebruikers en de mogelijkheid om samen te werken te belemmeren. Plaats etiketten met verschillende beveiligingsniveaus op e-mail, bestanden of sites. | Microsoft 365 E3 en E5 |
| Preventie van gegevensverlies (DLP) | Detecteer, waarschuw en blokkeer risicovolle, onbedoelde of ongepaste delen van gegevens met persoonlijke gegevens, zowel intern als extern. | Microsoft 365 E3 en E5 |
| Labels en beleid voor gegevensretentie | Besturingselementen voor informatiebeheer implementeren. Dit kan bijvoorbeeld bepalen hoe lang gegevens (zoals persoonlijke gegevens met betrekking tot klanten) moeten worden behouden om te voldoen aan het beleid of de gegevensvoorschriften van uw organisatie. | Microsoft 365 E3 en E5 |
| E-mailversleuteling | Bescherm persoonlijke gegevens door versleutelde e-mailberichten te verzenden en te ontvangen tussen personen binnen en buiten uw organisatie. | Microsoft 365 E3 en E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organisatie van de richtlijnen in deze oplossing

Deze richtlijnen zijn ingedeeld in secties Microsoft 365 om u te helpen voldoen aan een of meer privacygerelateerde voorschriften.

![Stappen voor het implementeren van gegevensbescherming voor privacyregels voor gegevens](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Elk van deze secties komt overeen met een afzonderlijk artikel in deze oplossing.

> [!NOTE]
> Als u al bekend bent met uw verplichtingen op het gebied van gegevensbescherming en een bestaand plan wilt uitvoeren, kunt u zich richten op de richtlijnen Voorkomen, Beschermen, Behouden en Onderzoeken.

> [!IMPORTANT]
> Als u deze richtlijnen volgt, voldoet u niet per se aan de privacyregel voor gegevens, met name gezien het aantal vereiste stappen buiten de context van de functies. U bent verantwoordelijk voor het waarborgen van uw naleving en het raadplegen van uw juridische en complianceteams of om advies en advies in te winnen bij derden die gespecialiseerd zijn in naleving.

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan: Privacyrisico's voor gegevens beoordelen en gevoelige items identificeren

Het beoordelen van privacyregels en risico's voor uw organisatie is een belangrijke eerste stap voordat u verbeteringen gaat implementeren, waaronder het configureren van mogelijkheden in Microsoft 365. Dit werk kan een algehele gereedheidsbeoordeling of identificatie omvatten van bepaalde gevoelige informatietypen die onderworpen zijn aan wettelijke controles die uw organisatie moet naleven.

Zie Privacyrisico's voor gegevens beoordelen en gevoelige items [identificeren voor meer informatie.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Bijhouden: Voer risicoanalyses uit en controleer de nalevingsscore

Compliance Manager, beschikbaar in de Microsoft 365-compliancecentrum, biedt u een ingebouwde mogelijkheid om verbeteringsacties in het algemeen bij te houden en te beheren, evenals acties met betrekking tot meerdere privacyregels voor gegevens die op u van toepassing zijn.

U kunt ingebouwde beoordelingssjablonen gebruiken die specifiek zijn voor elke verordening, waar u actie-items voor elke geselecteerde beoordelingssjabloon kunt bijhouden en specifieke regelgevingsbesturingselementen kunt bekijken en deze kunt relateren aan specifieke acties.

Zie Compliancebeheer gebruiken om verbeteracties [te beheren voor meer informatie.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>Voorkomen: Persoonlijke gegevens beveiligen

Microsoft 365 biedt mogelijkheden voor identiteits-, apparaat- en bedreigingsbeveiliging die u kunt gebruiken om te voldoen aan de naleving van de regelgeving voor gegevensbescherming.

Zie Identiteits-, apparaat- en bedreigingsbeveiliging gebruiken voor privacyregels voor gegevens voor [meer informatie.](information-protection-deploy-identity-device-threat.md)

In dit artikel wordt kort beschreven wat de privacyregels voor gegevens in het algemeen op deze gebieden vragen en bevat een overzicht van gerelateerde Microsoft 365-oplossingen, met koppelingen naar meer informatie om u te helpen bij het voldoen aan implementatievereisten.

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Gegevens beveiligen die onderworpen zijn aan privacyregels voor gegevens

Privacyregels voor gegevens dicteren een aantal besturingselementen voor persoonlijke gegevensbescherming die in uw omgeving kunnen worden gebruikt, waaronder meer dan 40 besturingselementen voor het beschermen van informatie in slechts de vier privacyregels voor gegevens in onze voorbeeldset avg, California Consumer Protection Act (CCPA), HIPAA-HITECH (Privacy act voor de Amerikaanse gezondheidszorg) en de Brazil Data Protection Act (LGPD).

Zie Informatie beveiligen onder de privacyregel [voor gegevens in uw organisatie voor meer informatie.](information-protection-deploy-protect-information.md)

In dit artikel worden de belangrijkste beheerschema's beschreven die kunnen worden gebruikt om tegemoet te komen aan de gegevensbeschermingsbehoeften voor gegevensbescherming in uw organisatie.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Behouden: Informatie onder de privacyregel voor gegevens bepalen

Privacyregels voor gegevens vragen om beheerbesturingselementen voor persoonlijke gegevens die kunnen worden gebruikt in uw omgeving, waaronder meer dan 24 besturingselementen in de vier privacyregels voor gegevens in onze voorbeeldset van AVG, CTPA, HIPAA-HITECH en LGPD.

Zie Voor meer informatie Informatie [regelen die onderhevig is aan privacyregel voor gegevens in uw organisatie.](information-protection-deploy-govern.md)

Hoewel de privacyregels voor gegevens vaag kunnen zijn met betrekking tot informatiebeheer, zoals doelbewust bewaren, worden in dit artikel de primaire beheerschema's beschreven die u kunt gebruiken voor informatiebeheerbehoeften voor gegevensbescherming in uw &mdash; &mdash; organisatie.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Onderzoeken: Incidenten met gegevensbescherming bewaken, onderzoeken en beantwoorden

Er zijn Microsoft 365 functies beschikbaar om u te helpen bij het bewaken, onderzoeken en reageren op incidenten met gegevensbescherming in uw organisatie terwijl u gerelateerde mogelijkheden operationeel kunt maken.

Het hebben van processen, procedures en andere documentatie voor het gebruik van deze functies kan belangrijk zijn om naleving aan regelgevende instanties aan te tonen.

Zie Incidenten met gegevensbescherming in uw organisatie bewaken en beantwoorden [voor meer informatie.](information-protection-deploy-monitor-respond.md)

## <a name="training-for-administrators"></a>Training voor beheerders

Met deze trainingsmodules van Microsoft Learn kunt u meer informatie krijgen over de mogelijkheden die belangrijk zijn voor informatiebeveiliging.


#### <a name="information-protection"></a>Gegevensbescherming

|Training:|Bedrijfsgegevens beveiligen met Microsoft 365|
|:---|:---|
|![Teams infobeveiligingstrainingspictogram](../media/protect-enterprise-information-microsoft-365.svg)|Het beveiligen en beveiligen van de gegevens van uw organisatie is lastiger dan ooit. In het leerpad Ondernemingsgegevens beveiligen met Microsoft 365 wordt besproken hoe u uw gevoelige informatie kunt beschermen tegen onbedoelde oversharing of misbruik, hoe u gegevens kunt ontdekken en classificeren, hoe u deze met gevoeligheidslabels kunt beschermen en hoe u uw gevoelige gegevens kunt bewaken en analyseren om te beschermen tegen verlies. Dit leerpad kan u helpen bij het voorbereiden van de Microsoft 365 Certified: Security Administrator Associate en Microsoft 365 Certified: Enterprise Administration Expert certifications..<br><br>1 uur - Learning Pad - 5 modules|

> [!div class="nextstepaction"]
> [Start >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identiteit en toegang

|Training:|Identiteit en toegang beveiligen met Azure Active Directory|
|:---|:---|
|![Pictogram Voor training voor identiteit en toegang](../media/protect-identity-and-access-with-microsoft-365.svg)|Het leerpad Identiteit en Access omvat de nieuwste identiteits- en toegangstechnologieën, hulpmiddelen voor het versterken van verificatie en richtlijnen voor identiteitsbeveiliging binnen uw organisatie. Met microsoft-toegangs- en identiteitstechnologieën kunt u de identiteit van uw organisatie beveiligen, ongeacht of deze on-premises of in de cloud is, en uw gebruikers in staat stellen veilig te werken vanaf elke locatie. Met dit leerpad kunt u zich voorbereiden op de Microsoft 365 Certified: Beveiligingsbeheerder associate en Microsoft 365 Certified: Enterprise Administration Expert-certificeringen.<br><br>2 uur 52 min - Learning Pad - 6 modules|

> [!div class="nextstepaction"]
> [Start >](/learn/modules/m365-identity-overview/introduction/)