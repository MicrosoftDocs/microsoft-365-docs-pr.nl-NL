---
title: Microsoft 365 compatibiliteits extensibility
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het Microsoft 365 complianceoplossingen met behulp van gegevensconnectoren van derden en MICROSOFT-Graph API's.
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651054"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 compatibiliteits extensibility

Microsoft 365 complianceoplossingen helpen organisaties hun compliancerisico's op intelligente wijze te beoordelen, gevoelige gegevens te besturen en te beschermen en effectief te reageren op wettelijke vereisten. Microsoft 365 compliance is rijk aan uitbreidbaarheidsscenario's en stelt organisaties in staat hun complianceoplossingen aan te passen, uit te breiden, te integreren, te versnellen en te ondersteunen.

Er zijn twee belangrijke bouwstenen voor de extensibiliteit van naleving:

- **Gegevensconnectoren.** Gebruik deze gegevens om niet-Microsoft-gegevens te importeren en te archiveren, zodat u Microsoft 365 en beheermogelijkheden kunt toepassen op gegevens van derden.

- **API's**. Hiermee kunt u programmatische toegang tot Microsoft 365 compliancemogelijkheden.

## <a name="data-connectors"></a>Gegevensconnectors

Microsoft biedt gegevensconnectoren van derden die kunnen worden geconfigureerd in het Microsoft 365 compliancecentrum. Zie de tabel Gegevensconnectors van [](archiving-third-party-data.md#third-party-data-connectors) derden voor een lijst met gegevensconnectoren van Microsoft. De tabel met gegevensconnectoren van derden bevat ook een overzicht van de complianceoplossingen die u kunt toepassen op gegevens van derden nadat u gegevens in Microsoft 365 hebt geïmporteerd en gearchiveerd, en koppelingen naar de stapsgewijs instructies voor elke connector.

Zie Gegevens van derden archiveren voor meer Microsoft 365 [gegevensconnectoren.](archiving-third-party-data.md) Als een gegevenstype van derden niet wordt ondersteund door de gegevensconnectors die beschikbaar zijn in het Microsoft 365 compliancecentrum, kunt u samenwerken met een partner die u een aangepaste verbindingslijn kan bieden. Zie Werken met een partner om gegevens van derden te archiveren voor een lijst met partners waarmee u kunt werken en het stapsgewijs proces voor deze [methode.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Vereisten voor gegevensconnectors

Voor veel gegevensconnectoren die beschikbaar zijn in het Microsoft 365 compliancecentrum voor het importeren en archiveren van gegevens van derden, moet u configuratietaken voorbereiden en uitvoeren in de gegevensbron van derden. Deze vereisten worden gedetailleerd gedocumenteerd voor elke gegevensconnector van derden.

Voor gegevensconnectoren in het Microsoft 365 compliancecentrum dat wordt geleverd door een van de partners van Microsoft, heeft uw organisatie een zakelijke relatie met de partner nodig voordat u een connector kunt implementeren.

U vindt licentievereisten voor gegevensconnectoren van derden in het document Microsoft 365 [compliancelicentievergelijking.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>API‘s

Microsoft 365 compliance-API's zijn beschikbaar in de Microsoft Information Protection SDK, Microsoft Graph API en de Office 365 Management Activity API. Sommige compliance-API's maken deel uit van een nieuwe set beveiligings- en compliance-API's waarmee ontwikkelaars voor Microsoft 365-klanten, onafhankelijke softwareleveranciers, systeemintegratoren en beheerde beveiligingsserviceproviders hoogwaardige beveiligings- en complianceoplossingen kunnen bouwen.

Zie Overzicht van Microsoft-Graph voor meer informatie over het openen van Graph [API's.](/graph/overview)

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

Met MIP SDK worden de labelings- en beveiligingsservices van Microsoft 365 beveiligings- en compliancecentra aan toepassingen en services van derden aangeboden. Ontwikkelaars kunnen de SDK gebruiken om native ondersteuning te bouwen voor het toepassen van etiketten en beveiliging op bestanden. Ontwikkelaars kunnen bepalen welke acties moeten worden ondernomen wanneer specifieke labels worden gedetecteerd en waarom MIP-versleutelde gegevens worden gebruikt.

MIP SDK-gebruiksgevallen op hoog niveau zijn:

- Een line-of-business-toepassing die classificatielabels op bestanden bij export van toepassing is.

- Een CAD/CAM-ontwerptoepassing die native ondersteuning biedt voor MIP-labeling.

- Een cloudtoegangsbeveiligingsagent of oplossing voor preventie van gegevensverlies die gegevens kan versleutelen met Azure Information Protection.

Zie MIP SDK Overview voor meer informatie over de [MIP SDK,](/information-protection/develop/overview)vereisten, extra scenario's en voorbeelden.

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph API voor Teams DLP

Mogelijkheden voor preventie van gegevensverlies [(DLP)](dlp-microsoft-teams.md) worden veel gebruikt in Microsoft Teams met name omdat organisaties zijn overge schakelen naar extern werk. Eerder dit jaar hebben we de openbare [preview](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) van de Microsoft-Graph Meldings-API wijzigen voor berichten in Teams. Met deze API kunnen ontwikkelaars apps maken die in Microsoft Teams realtime naar berichten kunnen luisteren en vervolgens DLP-scenario's implementeren voor zowel klanten als partners. Daarnaast kunt u met microsoft Graph Patch API DLP-acties toepassen op Teams berichten.

Deze twee API's vormen de Microsoft Graph API voor Teams DLP. U kunt aan de slag gaan door de [voorbeeld-app uit te proberen.](https://github.com/microsoftgraph/csharp-webhook-with-resource-data) Zie de documentatie voor Microsoft Teams webhooks voor [berichten.](/graph/api/subscription-post-subscriptions)

Zie voor de licentievereisten voor Teams DLP [Microsoft 365 richtlijnen](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)voor beveiligings- & naleving.

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API voor eDiscovery (preview)

Met [Advanced eDiscovery](overview-ediscovery-20.md)kunnen organisaties gegevens ontdekken waar deze zich in leven houden en meer end-to-end eDiscovery-werkstromen beheren met intelligente mogelijkheden voor machine learning en analyse om gegevens tot de relevante set te beperken, terwijl de gegevens binnen de Microsoft 365-beveiligings- en compliancegrens blijven.

Graph API's voor Advanced eDiscovery kunnen worden gebruikt om zaken te maken en te beheren, sets te controleren en query's in te stellen op een schaalbare en herhaalbare manier. Op deze manier kunnen klanten en partners apps en werkstromen maken om gangbare en terugkerende processen te automatiseren, zoals het maken van zaken en het beheren van bewaarders en wettelijke bewaarnemingen.

De eerste set Graph API's voor eDiscovery zijn beschikbaar in een openbare preview. We zijn van plan om tegen het einde van het kalenderjaar meer mogelijkheden toe te voegen. Zie deze blog voor meer informatie over deze API's en andere updates Advanced eDiscovery voor [meer informatie.](https://aka.ms/Ignite2020AeDAA)

Zie voor de licentievereisten voor Advanced eDiscovery en de API de sectie 'eDiscovery' in de [Microsoft 365-richtlijnen](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)voor beveiligings- & naleving.

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph API voor Teams exporteren (preview)

Enterprise Information Archiving (EIA) voor Microsoft Teams is een belangrijk scenario voor onze klanten, omdat ze hierdoor kunnen oplossen voor wettelijke vereisten. Naast onze ingebouwde mogelijkheden voor het archiveren van inhoud in Microsoft Teams, kunnen klanten en partners nu Teams EXPORT-API's gebruiken om op te lossen voor aangepaste toepassings- en integratiescenario's. De Teams EXPORT API's ondersteunen bulkexport (maximaal 200 aanvragen per seconde/per app/per tenant) van Teams berichten en berichtbijlagen. Verwijderde berichten zijn ook toegankelijk via de API tot 30 dagen nadat ze zijn verwijderd. Zie Inhoud exporteren met de Microsoft Teams API's exporteren voor meer informatie over deze Teams [api's](/microsoftteams/export-teams-content)exporteren en hoe u ze kunt gebruiken in uw toepassingen.

Zie voor de licentievereisten voor het gebruik van de Teams API's exporteren Microsoft 365 richtlijnen voor beveiligings- [& naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph Connector API's (preview)

Met [Microsoft Graph connectors](/microsoftsearch/connectors-overview)kunnen organisaties gegevens van derden indexeren, zodat deze worden weergegeven in de zoekresultaten van Microsoft. Met deze functie worden de typen inhoudsbronnen uitgebreid die kunnen worden gezocht in uw Microsoft 365 productiviteits-apps en het bredere Microsoft-ecosysteem. De gegevens van derden kunnen on-premises of in openbare of privéwolken worden gehost. Vanaf Advanced eDiscovery kunnen we ontwikkelaarsvoorbeelden van ingebouwde nalevingswaarde van Microsoft 365 verbonden apps inschakelen. Hierdoor kunnen apps worden geïntegreerd in het Microsoft 365 om gebruikers in staat te stellen naadloze nalevingservaringen te bieden. Zie Verbindingen maken, bijwerken en verwijderen in de Microsoft-Graph voor meer informatie over het opnemen van Microsoft Graph Connector-API's in de weergave [apps.](/graph/search-index-manage-connections)

