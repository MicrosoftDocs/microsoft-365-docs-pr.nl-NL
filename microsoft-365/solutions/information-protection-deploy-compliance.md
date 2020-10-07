---
title: Compliance Manager gebruiken voor het beheren van kwaliteits acties
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
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
description: Meer informatie over het gebruik van de compliance Score en Compliance Manager om uw beschermingsniveau voor persoonlijke gegevens te verbeteren.
ms.openlocfilehash: 5b41fa9fc52253d415a22aaa3422a87c4f1bda7c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377097"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Compliance Manager gebruiken voor het beheren van kwaliteits acties

Microsoft Compliance Manager kan u helpen bij het beheren van verbeteringen in verband met privacyinstellingen van de Europese Unie voor de [algemene gegevensbescherming](../compliance/gdpr.md)van de Europese Unie, de wet voor de AVG van de Europese Unie, de [consumentenbescherming van Californië](../compliance/ccpa-faq.md)

Dit artikel bevat richtlijnen voor het gebruik van dit hulpprogramma voor privacys doeleinden.

>[!Note]
>Aanbevelingen van Compliancebeheer mogen niet worden geïnterpreteerd als een garantie voor naleving. U kunt hiermee de effectiviteit van klant besturingselementen evalueren en valideren per uw regelgevings omgeving. Deze services zijn onderhevig aan de voorwaarden in de [Online Services-voor](https://go.microsoft.com/fwlink/?linkid=2108910)waarden. Zie ook [Microsoft 365 Licensing Guidance voor beveiliging en compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Aan de slag met Compliance Manager

#### <a name="what-is-compliance-manager"></a>Wat is Compliance Manager

[Compliance Manager](../compliance/compliance-manager.md) is een werkstroom programma voor risicoanalyse in het microsoft 365 compliance Center voor het beheren van regelgevings activiteiten met betrekking tot Microsoft-cloudservices. Als onderdeel van uw abonnement op Microsoft 365 of Azure Active Directory (Azure AD) helpt u nalevings beheer bij het beheren van Compliance Compliance in het model voor gedeelde verantwoordelijkheden voor Microsoft-cloudservices.

**Klaar om beoordelingen te gebruiken**

Compliance Manager biedt vooraf gedefinieerde sjablonen voor het [maken van beoordelingen](../compliance/compliance-manager-assessments.md) die zijn afgestemd op de privacy-gerelateerde regelgeving van gegevens, zoals AVG en HIPAA/Hitech. De sjablonen bevatten ingebouwde beheer toewijzingen waarmee u de vereisten voor de regulering van de regelgeving kunt verbeteren. Elke beoordeling biedt informatie over de besturingselementen die elke verordening aanroept voor specifieke doelservice, uitgesplitst door besturingselementen die door Microsoft worden beheerd en beheerd. 

Met een vooraf gebouwde sjabloon kunt u snel aan de slag met risicobeoordelingen. Naarmate u meer wilt weten over het gebruik van Compliance Manager, kunt u een vooraf gedefinieerde sjabloon aanpassen door uw eigen besturingselementen en kwaliteits verbeteringen toe te voegen, of u kunt uw eigen aangepaste proefwerken maken voor de behoeften van uw organisatie.

Bekijk de [volledige lijst met beoordelings sjablonen](../compliance/compliance-manager-templates-list.md) die beschikbaar zijn in de Compliance Manager.

**Score voor naleving van realtime**

Compliance Manager biedt u ook een compliance Score waarmee de voortgang van de aanbevolen verbeterings acties binnen besturingselementen wordt voltooid. U kunt deze score gebruiken voor het bewaken van uw voortgang en de prioriteit van acties op basis van de mogelijkheid om het risico te reduceren.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>De introductiehandleiding voor Compliance Manager gebruiken

De [Snelstartgids voor Compliance Manager](../compliance/compliance-manager-quickstart.md) levert stappen en koppelingen naar belangrijke bronnen om u te helpen met nalevings beheer:

- [Eerste bezoek: vertrouwd raken met Compliance Manager](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Werken met uw dashboard van Compliance Manager
    - Informatie over uw compliance Score
    - Meer informatie over kwaliteits stappen
    - Proefwerken met beoordelingen en sjablonen
- [Opvolgen: Compliance Manager configureren voor het beheren van uw conformiteits activiteiten](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Uw eerste beoordeling maken en beheren
    - Uitvoering en testen van werkzaamheden aan verbeterings acties voor het voltooien van de besturingselementen in uw beoordelingen
    - Inzicht in de manier waarop verschillende acties invloed hebben op de compliantie Score
- [Aanpassen: Gebruik geavanceerde functionaliteit om aan uw aangepaste behoeften te voldoen](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Aangepaste beoordelingen maken voor het bijhouden van niet-Microsoft 365-producten
    - Bestaande sjablonen wijzigen om besturingselementen toe te voegen of te verwijderen
    - Automatisch testen van stappen voor verbetering instellen

## <a name="how-your-compliance-score-is-calculated"></a>Hoe uw compliancescore wordt berekend

Uw compliance score wordt berekend op basis van een combinatie van de implementaties van Microsoft en door de klant beheerde beheer. Zie [compliance-score berekening](../compliance/compliance-score-calculation.md) voor een gedetailleerde uitleg.

Aan besturingselementen wordt een score waarde toegewezen op basis van het feit of ze verplicht zijn of worden gebruikt, of ze preventie, detectie of correctie vormen. Dit vormt gezamenlijk het risico dat het niet wordt geïmplementeerd ten opzichte van andere besturingselementen.

Zoals weergegeven in het artikel over de beoordeling van de compliance van de compliance, verkrijgen preventieve besturingselementen een betere score dan detectie en vergelijkingsfuncties, en met verplichte besturingselementen krijgt u een betere score.

De GEBRUIKERSINTERFACE van de compliance score voor naleving biedt geen ondersteuning voor deze parameters, noch de mogelijkheid deze de mogelijkheid te geven te filteren. Als u echter de gekoppelde sjabloon van Compliance Manager downloadt, worden deze parameters voor de meeste regels in de geretourneerde gegevensset weergeven.

Voor technische controle wordt Compliance Manager automatisch de score voor verbetering van de actie automatisch bijgewerkt nadat de actie is geïmplementeerd en getest. Andere activiteiten van niet-technische besturing, &mdash; zoals degenen die operationeel of gerelateerd zijn aan de documentatie, &mdash; moeten handmatig worden opgenomen in de opgenomen punten, zodat ze in de Score van punten worden opgenomen.

U wordt ook aangeraden bepaalde verbeterings acties uit te voeren voor andere doeleinden, bijvoorbeeld labels voor het aanhouden van een Bewaar programma voor andere doeleinden dan de naleving van de &mdash; regelgeving voor data-regulering, &mdash; zodat u tegoed krijgt voor het gebruik van een dergelijke functie, ook als deze wordt gebruikt voor andere doeleinden, en geen aanvals actie.

Uw compliance score moet als een relatieve meetwaarde worden beschouwd om de verbeteringen op een grootschalige schaal bij te houden. U mag geen perfecte score nastreven.

## <a name="additional-guidance"></a>Aanvullende richtlijnen

Hier volgen enkele belangrijke tips voor het gebruik van Compliance Manager om u te helpen bij het verkrijgen van compliance van data privacy regulering:

- Elke bedrijfsvoor Schriften voor de privacy van gegevens bestaat uit een combinatie van technische besturingselementen, documentatie specificaties, en de vereisten voor operationeel, proces en rapporten. Allemaal worden weergegeven in de stappen voor verbetering.

- Als u de weergave van de uitzonderings stappen wilt benadrukken, kunt u filteren op Actietype op het tabblad **oplossingen** van de beheerder van de beheerder. Meer informatie over [het filteren van de dashboardweergave van uw Compliance Manager](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- De belangrijke belangrijke punten en prioriteit van verbeteringen in nalevings beheer moeten als onderdeel van een bredere risicobeoordeling worden beschouwd, samen met het gegevens privacy risico dat uw organisatie moet beheren.

- Ook als de beoordelings sjablonen van de regulering voor AVG, LGPD, CCPA en HIPAA-HITECH zijn geselecteerd, worden in Compliance Manager bijvoorbeeld bijna 400-verbeterings acties weergegeven. Als u deze lange lijst beter wilt gebruiken, kunt u het actie filter voor verbetering gebruiken om de resultatenset te reduceren naar een meer beheersbare lijst.

- Het filtercategorieën levert een gemiddelde manier voor het oplossen van verbeteringen op basis van logische groepering, waaronder de tracering, voorkomen, beveiligen, vasthouden en onderzoeken van artikelen in deze algemene oplossing.

- Sommige van de besturingselementen die in de verduidelijkings actie worden vermeld, kunnen worden beschouwd als direct rechtstreeks gebonden te zijn aan een specifiek regelgevend artikel, terwijl andere besturingselementen van de geest van een verordening en vele keren slechts voor de beste activiteiten kunnen worden gebruikt.