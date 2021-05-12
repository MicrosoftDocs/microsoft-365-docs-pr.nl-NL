---
title: Controleoplossingen van Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Informatie over het controleren van de activiteiten van gebruikers en beheerders in uw Microsoft 365-organisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 214ea43348a4a33e6ce1b754cbaf9be6a43b2c70
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314286"
---
# <a name="auditing-solutions-in-microsoft-365"></a>Controleoplossingen in Microsoft 365

Controleoplossingen van Microsoft 365 bieden een geïntegreerde oplossing waarmee organisaties effectief kunnen reageren op beveiligingsgebeurtenissen, lopende onderzoeken, interne onderzoeken en nalevingsvereisten. Duizenden bewerkingen door gebruikers en beheerders die in tientallen Microsoft 365-services en -oplossingen worden uitgevoerd, worden vastgelegd, vastgelegd en bewaard in het geïntegreerde auditlogboek van uw organisatie. Auditrecords voor deze gebeurtenissen zijn doorzoekbaar door beveiligingsoperaties, IT-beheerders, insider-risicoteams en compliance- en juridische onderzoekers in uw organisatie. Deze mogelijkheid biedt inzicht in de activiteiten die in uw Microsoft 365-organisatie zijn uitgevoerd.

## <a name="microsoft-365-auditing-solutions"></a>Controleoplossingen van Microsoft 365

Microsoft 365 biedt twee controleoplossingen: Basiscontrole en Geavanceerde controle.

### <a name="basic-auditing"></a>Basiscontrole

Basiscontrole biedt u de mogelijkheid om te loggen en te zoeken naar gecontroleerde activiteiten en uw forensische, IT-, nalevings- en juridische onderzoeken te ondersteunen.

- **Standaard ingeschakeld**. Eenvoudige controle is standaard ingeschakeld voor alle organisaties met het juiste abonnement. Dat betekent dat records voor gecontroleerde activiteiten worden vastgelegd en doorzoekbaar zijn. De enige installatie die nodig is, is het toewijzen van de benodigde machtigingen voor toegang tot het hulpprogramma voor het zoeken naar auditlogboeken (en de bijbehorende cmdlet) en ervoor te zorgen dat gebruikers de juiste licentie krijgen voor Geavanceerde auditfuncties.
- **Duizenden doorzoekbare controlegebeurtenissen**. U kunt zoeken naar een breed scala aan gecontroleerde activiteiten die zich voordoen bij de meeste Microsoft 365-services in uw organisatie. Zie [Gecontroleerde activiteiten](search-the-audit-log-in-security-and-compliance.md#audited-activities) voor een gedeeltelijke lijst met activiteiten die u kunt zoeken. Zie [Het recordtype Auditlogboek](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype) voor een lijst met services en functies die gecontroleerde activiteiten ondersteunen.
- **Hulpprogramma voor controleren van zoekopdrachten in het Microsoft 365-compliancecentrum**. Gebruik het hulpprogramma Zoeken in auditlogboek in het Microsoft 365-compliancecentrum om te zoeken naar controlerecords. U kunt zoeken naar specifieke activiteiten, naar activiteiten die zijn uitgevoerd door specifieke gebruikers en activiteiten die hebben plaatsgevonden met een datumbereik. Hier is een schermafbeelding van het Hulpprogramma voor controleren in het compliancecentrum.

   ![Hulpprogramma Zoeken in auditlogboek in het Microsoft 365-compliancecentrum.](../media/AuditLogSearchToolMCC.png)

- **cmdlet Search-UnifiedAuditLog**. U kunt ook de cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell (de onderliggende cmdlet voor het zoekhulpmiddel) gebruiken om te zoeken naar controlegebeurtenissen of om in een script te gebruiken. Zie voor meer informatie:

  - [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)
  - [Een PowerShell-script gebruiken om in het auditlogboek te zoeken](audit-log-search-script.md)

- **Controlerecords exporteren naar een CSV-bestand**. Nadat u het zoekprogramma voor het auditlogboek in het compliancecentrum hebt uitgevoerd, kunt u de controlerecords die door de zoekopdracht worden geretourneerd, exporteren naar een CSV-bestand. Hiermee kunt u Microsoft Excel sorteren en filteren op verschillende eigenschappen van controlerecords. U kunt ook de transformatiefunctionaliteit van Excel Power Query gebruiken om elke eigenschap in het AuditData JSON-object in een eigen kolom te splitsen. Hierdoor kunt u vergelijkbare gegevens voor verschillende gebeurtenissen effectief bekijken en vergelijken. Zie voor meer informatie [Auditlogboekrecords exporteren, configureren en weergeven](export-view-audit-log-records.md).

- **Toegang tot auditlogboeken via de Office 365 Management Activity-API**. Een derde methode voor het openen en ophalen van controlerecords is het gebruik van de Office 365 Management Activity-API. Hierdoor kunnen organisaties controlegegevens gedurende langere perioden dan de standaardtijd van 90 dagen bewaren en kunnen ze de controlegegevens importeren in een SIEM-oplossing. Zie [Office 365 Management Activity-API-referentie](/office/office-365-management-api/office-365-management-activity-api-reference) voor meer informatie.

- **90 dagen bewaarbeleid voor auditlogboeken**. Wanneer een gecontroleerde activiteit wordt uitgevoerd door een gebruiker of beheerder, wordt een auditrecord gegenereerd en opgeslagen in het auditlogboek voor uw organisatie. In Eenvoudige controle worden records 90 dagen bewaard. Dit betekent dat u kunt zoeken naar activiteiten die in de afgelopen drie maanden hebben plaatsgevonden.

### <a name="advanced-audit"></a>Geavanceerde controle

Geavanceerde audit bouwt voort op de mogelijkheden van Basiccontrole door bewaarbeleid voor auditlogboeken, langere bewaring van auditrecords, cruciale gebeurtenissen van hoge waarde en toegang met een hogere bandbreedte tot de Office 365 Management Activity-API.

- **Bewaarbeleid voor auditlogboeken**. U kunt een aangepast bewaarbeleid voor auditlogboeken maken om controlerecords voor een langere periode tot een jaar te bewaren (en tot 10 jaar voor gebruikers met de vereiste invoeglicentie). U kunt een beleid maken om auditrecords te bewaren op basis van de service waar de gecontroleerde activiteiten plaatsvinden, specifieke gecontroleerde activiteiten of de gebruiker die een gecontroleerde activiteit uitvoert.

- **Langere bewaring van controlerecords**. Exchange-, SharePoint- en Azure Active Directory-auditrecords worden standaard één jaar bewaard. Controlerecords voor alle andere activiteiten worden standaard 90 dagen bewaard. U kunt het bewaarbeleid voor auditlogboeken gebruiken om langere bewaartermijnen te configureren.

- **Hoogwaardige, cruciale gebeurtenissen**. Controlerecords voor cruciale gebeurtenissen kunnen uw organisatie helpen forensische en nalevingsonderzoeken uit te voeren door inzicht te geven in gebeurtenissen zoals wanneer e-mailitems werden geopend of wanneer e-mailitems werden beantwoord en doorgestuurd, en wanneer en waarnaar een gebruiker zocht in Exchange Online en SharePoint Online. Aan de hand van deze belangrijke gebeurtenissen kunt u mogelijke schendingen onderzoeken en de omvang van de inbreuk bepalen.

- **Hogere bandbreedte voor de Office 365 Management Activity-API**. Geavanceerde controle biedt organisaties meer bandbreedte om toegang te krijgen tot controlelogboeken via de Office 365 Management Activity-API. Hoewel aan alle organisaties (die basiscontrole of geavanceerde controle hebben) in eerste instantie een basislijn van 2000 verzoeken per minuut wordt toegewezen, wordt deze limiet dynamisch verhoogd, afhankelijk van het aantal seats en het licentieabonnement van een organisatie. Dit resulteert erin dat organisaties met Geavanceerde controle ongeveer twee keer zoveel bandbreedte krijgen als organisaties met Basiscontrole.

Zie [Geavanceerde controle in Microsoft 365](advanced-audit.md) voor meer informatie over geavanceerde controlefuncties.

## <a name="comparison-of-key-capabilities"></a>Vergelijking van de belangrijkste mogelijkheden

In de volgende tabel worden de belangrijkste mogelijkheden vergeleken die beschikbaar zijn in Basiscontrole en Geavanceerde controle. Alle Basiscontrolefuncties zijn opgenomen in Geavanceerde controle.

|Functie|Basiscontrole|Geavanceerde controle|
|:------|:-------------|:-------------|
|Standaard ingeschakeld|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)|
|Duizenden doorzoekbare controlegebeurtenissen|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)|
|Hulpprogramma voor controleren van zoekopdrachten in het Microsoft 365-compliancecentrum|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)|
|**Search-UnifiedAuditLog**-cmdlet|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)|
|Controlerecords exporteren naar een CSV-bestand|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)|
|Toegang tot auditlogboeken via de Office 365 Management Activity-AP <sup>1</sup>|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)</sup>|
|90 dagen bewaarbeleid voor auditlogboeken|![Ondersteund](../media/check-mark.png)|![Ondersteund](../media/check-mark.png)|
|Bewaartermijn van 1 jaar van controlelogboeken||![Ondersteund](../media/check-mark.png)|
|Bewaartermijn van 10 jaar van controlelogboeken <sup>2</sup>||![Ondersteund](../media/check-mark.png)|
|Bewaarbeleid voor controlelogboeken||![Ondersteund](../media/check-mark.png)|
|Hoogwaardige, cruciale gebeurtenissen||![Ondersteund](../media/check-mark.png)|
||||
> [!NOTE]
> <sup>1</sup> Geavanceerde controle omvat hogere bandbreedtetoegang tot de Office 365 Management Activity-API, die snellere toegang biedt tot controlegegevens.<br/><sup>2</sup> Naast de vereiste licentie voor geavanceerde controle (zie de volgende sectie), moet aan een gebruiker een licentie voor het bewaren van het auditlogboek van tien jaar worden toegewezen om zijn of haar controlerecords tien jaar te kunnen behouden.

## <a name="licensing-requirements"></a>Licentievereisten

In de volgende secties worden de licentievereisten voor Basiscontroles en Geavanceerde controles beschreven. Alle Basiscontrolefuncties zijn opgenomen in Geavanceerde controle.

### <a name="basic-auditing"></a>Basiscontrole

- Microsoft 365 Enterprise E3-abonnement
- Microsoft 365 Business Premium
- Microsoft 365 Education A3-abonnement
- Microsoft 365 Government G3-abonnement
- Microsoft 365 Government G1-abonnement
- Office 365 Enterprise E3-abonnement
- Office 365 Enterprise E1-abonnement
- Office 365 Education A1-abonnement
- Office 365 Education A3-abonnement

### <a name="advanced-audit"></a>Geavanceerde controle

- Microsoft 365 Enterprise E5-abonnement
- Microsoft 365 E3-abonnement + de invoegtoepassing Microsoft 365 E5 Compliance.
- Microsoft 365 Enterprise E3-abonnement + de invoegtoepassing Microsoft 365 E5 eDiscovery en Audit
- Microsoft 365 Education A5-abonnement
- Microsoft 365 A3-abonnement + de invoegtoepassing Microsoft 365 A5 Compliance.
- Microsoft 365 Enterprise A3-abonnement + de invoegtoepassing Microsoft 365 A5 eDiscovery en Audit
- Microsoft 365 Government G5-abonnement
- Microsoft 365 Government G5-abonnement + de invoegtoepassing Microsoft 365 G5 Compliance.
- Microsoft 365 Government G5-abonnement + de invoegtoepassing Microsoft 365 G5 eDiscovery en Audit
- Office 365 Enterprise E5-abonnement
- Office 365 Education A5-abonnement
- Office 365 Enterprise E3-abonnement + de invoegtoepassing Office 365 Advanced Compliance (niet meer beschikbaar voor nieuwe abonnementen)

## <a name="set-up-microsoft-365-auditing-solutions"></a>Controleoplossingen van Microsoft 365 instellen

Zie de volgende installatie-instructies om aan de slag te gaan met de controleoplossingen in Microsoft 365.

### <a name="set-up-basic-auditing"></a>Basiscontrole instellen

De eerste stap bestaat uit het instellen van Basiscontrole en het uitvoeren van zoekopdrachten in het auditlogboek.

![Werkstroom voor het instellen van Basiscontrole](../media/BasicAuditingWorkflow.png)

1. Controleer of uw organisatie een abonnement heeft dat ondersteuning biedt voor Eenvoudige controle en, indien van toepassing, een abonnement dat ondersteuning biedt voor Geavanceerd controleren.

2. Wijs machtigingen in Exchange Online toe aan personen in uw organisatie die het zoekprogramma voor het auditlogboek in het Microsoft 365-compliancecentrum of de cmdlet **Search-UnifiedAuditLog** gebruiken. Specifiek moet aan het gebruik de rol Auditlogboeken of Auditlogboeken in Exchange Online worden toegewezen.

3. Zoeken in het auditlogboek. Na het voltooien van stap 1 en 2 kunnen gebruikers in uw organisatie het zoekprogramma voor het auditlogboek (of de bijbehorende cmdlet) gebruiken om te zoeken naar gecontroleerde activiteiten.

### <a name="set-up-advanced-audit"></a>Geavanceerde controle instellen

Als uw organisatie een abonnement heeft dat ondersteuning biedt voor Geavanceerd controleren, voert u de volgende stappen uit om de aanvullende mogelijkheden van Geavanceerd controleren in te stellen en te gebruiken.

![Werkstroom voor het instellen van geavanceerde controle](../media/AdvancedAuditWorkflow.png)

1. Geavanceerde audit voor gebruikers instellen. Deze stap bestaat uit de volgende taken:

   - Controleren of aan gebruikers de juiste licentie of licentie voor de invoegtoepassing voor Geavanceerde controle is toegewezen.
  
   - Het inschakelen van de app Geavanceerde controle/serviceplan moet voor die gebruikers zijn.
  
   - Controle van cruciale gebeurtenissen mogelijk maken en vervolgens de app/serviceplan voor Geavanceerde controle inschakelen voor die gebruikers.

2. Schakel belangrijke gebeurtenissen in die moeten worden geregistreerd wanneer gebruikers zoekopdrachten uitvoeren in Exchange Online en SharePoint Online.

3. Bewaarbeleid voor auditlogboek instellen. Naast het standaardbeleid dat Exchange-, SharePoint- en Azure AD-auditrecords gedurende één jaar bewaart, kunt u aanvullend bewaarbeleid voor auditlogboeken maken om te voldoen aan de vereisten van de beveiligingsactiviteiten, IT- en complianceteams van uw organisatie.

4. Zoeken naar belangrijke gebeurtenissen en andere activiteiten bij het uitvoeren van onderzoek. Na het voltooien van stap 1 en 2 kunt u in het auditlogboek zoeken naar belangrijke gebeurtenissen en andere activiteiten tijdens onderzoek naar gehackte accounts en andere typen beveiligings- of nalevingsonderzoeken.

## <a name="training"></a>Training

Door uw team voor beveiligingsactiviteiten, IT-beheerders en nalevingsonderzoekers te trainen in basiscontroles en geavanceerde controles, kan uw organisatie sneller aan de slag gaan met auditing om u te helpen bij uw onderzoeken. Microsoft 365 biedt de volgende informatiebron om deze gebruikers in uw organisatie te helpen aan de slag te gaan met auditing: [Beschrijf de auditmogelijkheden in Microsoft 365](/learn/modules/describe-audit-capabilities-microsoft-365).
