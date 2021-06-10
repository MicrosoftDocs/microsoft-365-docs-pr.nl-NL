---
title: Compliancebeheer gebruiken om verbeteracties te beheren
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
description: Lees hoe u compliancescore en compliancebeheer gebruikt om uw beschermingsniveau voor persoonlijke gegevens te verbeteren.
ms.openlocfilehash: 87131ea65661e8285fd7c3b36a87c79b618348d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918568"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Compliancebeheer gebruiken om verbeteracties te beheren

Microsoft Compliance Manager kan u helpen bij het beheren van verbeteringen met betrekking tot privacyregels voor gegevens, zoals de Algemene Verordening gegevensbescherming van de Europese Unie [(AVG),](/compliance/regulatory/gdpr) [California Consumer Protection Act CTPA),](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (Amerikaanse privacywet voor de gezondheidszorg) en de Brazil Data Protection Act (LGPD).

Dit artikel bevat richtlijnen voor het gebruik van dit hulpprogramma voor privacydoeleinden voor gegevens.

>[!Note]
>Aanbevelingen van Compliancebeheer mogen niet worden geïnterpreteerd als een garantie voor naleving. Het is aan u om de effectiviteit van klantbesturingselementen per regelgevingsomgeving te evalueren en te valideren. Deze services zijn onderworpen aan de voorwaarden in de [Voorwaarden voor onlineservices.](https://go.microsoft.com/fwlink/?linkid=2108910) Zie ook [Microsoft 365 richtlijnen voor licenties voor beveiliging en naleving](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Aan de slag met Compliance Manager

#### <a name="what-is-compliance-manager"></a>Wat is Compliance Manager

[Compliance Manager](../compliance/compliance-manager.md) is een op werkstroom gebaseerd hulpprogramma voor risicoanalyse in het Microsoft 365 compliancecentrum voor het beheren van complianceactiviteiten voor regelgeving met betrekking tot Microsoft-cloudservices. Als onderdeel van uw Microsoft 365 of Azure Active Directory (Azure AD)-abonnement, helpt Compliance Manager u bij het beheren van naleving van regelgeving binnen het gedeelde verantwoordelijkheidsmodel voor Microsoft-cloudservices.

**Klaar om evaluaties te gebruiken**

Compliance Manager biedt voorafgebouwde sjablonen voor het maken van [beoordelingen](../compliance/compliance-manager-assessments.md) die zijn afgestemd op privacygerelateerde voorschriften voor gegevens, zoals AVG en HIPAA/HITECH. De sjablonen hebben ingebouwde besturingstoewijzing om u te helpen verbeteracties uit te voeren om aan de vereisten van de verordening te voldoen. Elke beoordeling bevat informatie over de besturingselementen die door elke verordening specifiek worden gebruikt voor de doelservice, uitgesplits naar besturingselementen die u beheert en besturingselementen die Microsoft beheert. 

Met behulp van een vooraf gebouwde sjabloon kunt u snel aan de slag met risicobeoordelingen. Naarmate u meer ervaring hebt met het gebruik van Compliance Manager, kunt u een vooraf gebouwde sjabloon aanpassen door uw eigen besturingselementen en verbeteracties toe te voegen, of u kunt uw eigen aangepaste beoordelingen maken die aan de behoeften van uw organisatie voldoen.

Bekijk de [volledige lijst met beoordelingssjablonen van](../compliance/compliance-manager-templates-list.md) Compliance Manager.

**Realtime compliancescore**

Compliance manager biedt u ook een compliancescore die uw voortgang meet bij het voltooien van aanbevolen verbeteracties binnen besturingselementen. U kunt deze score gebruiken om uw voortgang te controleren en acties te prioriteren op basis van hun potentieel om risico's te beperken.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>De handleiding Snelstart van Compliance manager gebruiken

De [handleiding Aan de slag met Compliance Manager](../compliance/compliance-manager-quickstart.md) bevat de volgende stappen en koppelingen naar belangrijke bronnen om u te helpen met Compliance Manager te werken:

- [Eerste bezoek: vertrouwd raken met Compliance Manager](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Werken met uw Compliance Manager-dashboard
    - Inzicht krijgen in de nalevingsscore
    - Informatie over verbeteracties
    - Evaluaties en sjablonen begrijpen
- [Up-to-top: Compliance Manager configureren om uw complianceactiviteiten te beheren](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Uw eerste beoordeling opbouwen en beheren
    - Uitvoeren van implementatie- en testwerk voor verbeteracties om besturingselementen in uw beoordelingen te voltooien
    - Inzicht in de invloed van verschillende acties op de nalevingsscore
- [Schaalvergroting: gebruik geavanceerde functionaliteit om aan uw aangepaste behoeften te voldoen](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Aangepaste beoordelingen maken om niet-Microsoft 365 bijhouden
    - Bestaande sjablonen wijzigen om besturingselementen toe te voegen of te verwijderen
    - Het automatisch testen van verbeteracties instellen

## <a name="how-your-compliance-score-is-calculated"></a>Hoe uw compliancescore wordt berekend

Uw compliancescore wordt berekend op basis van een combinatie van microsoft- en door de klant beheerde beheer-implementaties. Zie [berekening van compliancescores](../compliance/compliance-score-calculation.md) voor een gedetailleerde uitleg.

Aan besturingselementen wordt een scorewaarde toegewezen op basis van of ze verplicht of discretionair zijn en of ze preventief, foutief of corrigerend zijn. Deze vormen gezamenlijk het risico dat het niet wordt geïmplementeerd ten opzichte van andere besturingselementen.

Zoals wordt weergegeven in het artikel compliancescoreberekening, krijgen preventieve besturingselementen een hogere score dan foutieve en corrigerende besturingselementen en krijgen verplichte besturingselementen een hogere score dan discretionaire besturingselementen.

De gebruikersinterface van compliancescorebeheerder bevat deze parameters niet en biedt evenmin de mogelijkheid om door deze parameters te filteren. Als u echter de bijbehorende sjabloon downloadt van Compliance Manager, bevat de resulterende gegevensset deze parameters voor de meeste regelgeving.

Voor technische besturingselementen wordt de actiescore voor de verbetering automatisch bijgewerkt nadat de actie is geïmplementeerd en getest. Andere, niet-technische beheeracties, zoals acties die operationeel zijn of gerelateerd zijn aan documentatie, moeten handmatig worden vastgelegd zoals geïmplementeerd voordat punten meetellen &mdash; &mdash; voor uw score.

U kunt ook bepaalde verbeteringsacties implementeren voor andere doeleinden, bijvoorbeeld het gebruik van bewaarlabels om andere redenen dan naleving van de privacyregels voor gegevens, zodat u krediet krijgt voor het gebruik van een dergelijke functie, zelfs als deze voor andere doeleinden wordt gebruikt en geen deel uitmaakt van een opzettelijke &mdash; &mdash; nalevingsactie.

Uw nalevingsscore moet worden beschouwd als een relatieve meting om de verbetering op grote schaal bij te houden. U moet niet naar een perfecte score streven.

## <a name="additional-guidance"></a>Aanvullende richtlijnen

Hier vindt u enkele belangrijke tips voor het gebruik van Compliance Manager om u te helpen naleving van de privacyregels voor gegevens te bereiken:

- Elke privacyregel voor gegevens heeft een combinatie van technische besturingselementen, documentatiespecificaties en operationele, proces- en rapportagevereisten. Al deze acties worden in de verbeteracties op de voor- en afd.

- Als u de weergave van verbeteracties wilt richten op uw  interessegebied, kunt u filteren op actietype op het tabblad Oplossingen in de compliancebeheerbeheerder. Meer informatie over het [filteren van de dashboardweergave van Compliance Manager.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- Het relatieve belang en de prioriteit van verbeteracties die zijn geïdentificeerd in Compliance Manager, moeten worden beschouwd als onderdeel van een bredere risicoanalyse, samen met het privacyrisico voor gegevens dat uw organisatie moet beheren.

- Zelfs met aggregatie van actieacties voor verbeteringen voor meerdere wettelijke vereisten, worden bijvoorbeeld bijna 400 verbeteracties weergegeven in Compliance Manager als de sjablonen voor de beoordeling van de regelgeving voor AVG, LGPD, CTPA en HIPAA-HITECH zijn geselecteerd. Als u deze lange lijst beter wilt aanpakken, gebruikt u het filter voor de verbeteringsactie om de resultatenset te beperken tot een beter beheerbare lijst.

- Het filter Categorieën biedt een manier om verbeteringsacties te filteren door logische groeperingen, waarop de artikelen in deze algehele oplossing worden uitgelijnd door artikelen in deze algemene oplossing bijhouden, voorkomen, beveiligen, behouden en onderzoeken.

- Sommige besturingselementen in de verbeteracties kunnen worden beschouwd als meer rechtstreeks gekoppeld aan een specifiek regelgevingsartikel, terwijl andere besturingselementen indirecter zijn gekoppeld aan de geest van een verordening en vaak alleen aanbevolen activiteiten of aanbevolen procedures zijn.