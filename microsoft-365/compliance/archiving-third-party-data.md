---
title: Gegevens van derden archiveren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het importeren van gegevens van derden van sociale mediaplatforms, chatplatforms en platformen voor documentsamenwerking om postvakken Microsoft 365 maken.
ms.openlocfilehash: 6c15da7c21382f6ef286ec493ea3d696c02761f4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227461"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>Gegevens van derden archiveren in Microsoft 365

Microsoft 365 kunnen beheerders gegevensconnectoren gebruiken om gegevens van derden van sociale mediaplatforms, chatplatforms en samenwerkingsplatformen voor documenten te importeren en te archiveren in postvakken in uw Microsoft 365 organisatie. Een van de belangrijkste voordelen van het gebruik van gegevensconnectoren voor het importeren en archiveren van gegevens van derden in Microsoft 365 is dat u verschillende Microsoft 365 complianceoplossingen kunt toepassen nadat deze zijn geïmporteerd. Op deze manier kunt u ervoor zorgen dat de niet-Microsoft-gegevens van uw organisatie voldoen aan de voorschriften en standaarden die van invloed zijn op uw organisatie.

## <a name="third-party-data-connectors"></a>Gegevensconnectors van derden

De Microsoft 365-compliancecentrum biedt inheems gegevensconnectors van Microsoft van derden om gegevens uit verschillende gegevensbronnen te importeren, zoals LinkedIn, Instant Bloomberg en Twitter en gegevensconnectoren die de Insider-oplossing voor risicobeheer ondersteunen. Naast deze gegevensconnectors werkt Microsoft samen met de volgende partners om veel meer gegevensconnectoren van het derde deel in de Microsoft 365-compliancecentrum. Uw organisatie werkt samen met deze partners om hun archiveringsservice in te stellen voordat u een bijbehorende gegevensconnector maakt in de Microsoft 365-compliancecentrum.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

De gegevens van derden die in de volgende secties worden vermeld (met uitzondering van HR-gegevens en fysieke foutgegevens die worden gebruikt voor de Microsoft 365 Insider-oplossing voor risicobeheer) worden geïmporteerd in gebruikerspostvakken. De Microsoft 365 complianceoplossingen die gegevens van derden ondersteunen, worden toegepast op het postvak van de gebruiker waarin de gegevens zijn opgeslagen.

### <a name="microsoft-data-connectors"></a>Microsoft-gegevensconnectors

In de volgende tabel vindt u de native gegevensconnectors van derden die beschikbaar zijn in de Microsoft 365-compliancecentrum. De tabel bevat ook een overzicht van de complianceoplossingen die u kunt toepassen nadat u gegevens van derden hebt geïmporteerd en gearchiveerd in Microsoft 365. Zie het [overzicht van complianceoplossingen](#overview-of-compliance-solutions-that-support-third-party-data) die gegevens van derden ondersteunen voor een gedetailleerde beschrijving van elke complianceoplossing en hoe deze gegevens van derden ondersteunt.

Klik op de koppeling in **de** gegevenskolom van derden om de stapsgewijs instructies te volgen voor het maken van een verbindingslijn voor dat gegevenstype.

|Gegevens van derden  |Proces in de wacht zetten|eDiscovery  |Bewaarinstellingen  |Records Management  |Communicatiecompliance  |Beheer van insider-risico's  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg-bericht](archive-bloomberg-message-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Personeelszaken (HR)](import-hr-data.md) ||||||![Vinkje](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Fysieke badging](import-physical-badging-data.md) ||||||![Vinkje](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Gegevensconnectors van Veritas

De tabel in deze sectie bevat de gegevensconnectors van derden die beschikbaar zijn in samenwerking met Veritas. De tabel bevat ook een overzicht van de complianceoplossingen die u kunt toepassen op gegevens van derden nadat u deze hebt geïmporteerd en gearchiveerd in Microsoft 365. Zie het [overzicht van complianceoplossingen](#overview-of-compliance-solutions-that-support-third-party-data) die gegevens van derden ondersteunen voor een gedetailleerde beschrijving van elke complianceoplossing en hoe deze gegevens van derden ondersteunt.

Voordat u gegevens van derden kunt archiveren in Microsoft 365, moet u samenwerken met Veritas om de archiveringsservice *(merge1* genoemd) voor uw organisatie in te stellen. Klik voor meer informatie op  de koppeling in de gegevenskolom van derden om de stapsgewijs instructies te volgen voor het maken van een verbindingslijn voor dat gegevenstype.

|Gegevens van derden  |Proces in de wacht zetten|eDiscovery  |Bewaarinstellingen  |Records Management  |Communicatiecompliance  |Beheer van insider-risico's  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber op MS SQL](archive-ciscojabberonmssql-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber op Oracle](archive-ciscojabberonoracle-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber op PostgreSQL](archive-ciscojabberonpostgresql-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[FX Connect](archive-fxconnect-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[MS SQL-database](archive-mssqldatabaseimporter-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Pivot](archive-pivot-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Slack eDiscovery](archive-slack-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Tekst met scheidingstekens](archive-text-delimited-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[WebEx Teams](archive-webexteams-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Webpagina's](archive-webpagecapture-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Workplace van Facebook](archive-workplacefromfacebook-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Zoom Meetings](archive-zoommeetings-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage-gegevensconnectors

De tabel in deze sectie bevat de gegevensconnectors van derden die beschikbaar zijn in samenwerking met TeleMessage. De tabel bevat ook een overzicht van de complianceoplossingen die u kunt toepassen op gegevens van derden nadat u deze hebt geïmporteerd en gearchiveerd in Microsoft 365. Zie het [overzicht van complianceoplossingen](#overview-of-compliance-solutions-that-support-third-party-data) die gegevens van derden ondersteunen voor een gedetailleerde beschrijving van elke complianceoplossing en hoe deze gegevens van derden ondersteunt.

Voordat u gegevens van derden kunt archiveren in Microsoft 365, moet u met TeleMessage werken om de archiveringsservice voor uw organisatie in te stellen. Klik voor meer informatie op  de koppeling in de gegevenskolom van derden om de stapsgewijs instructies te volgen voor het maken van een verbindingslijn voor dat gegevenstype.

TeleMessage-gegevensconnectoren zijn ook beschikbaar in GCC omgevingen in Microsoft 365 cloud van de Amerikaanse overheid. Zie de sectie Gegevensconnectoren in de cloud van de Amerikaanse overheid in dit artikel voor meer informatie.

|Gegevens van derden  |Proces in de wacht zetten|eDiscovery  |Bewaarinstellingen  |Records Management  |Communicatiecompliance  |Beheer van insider-risico's  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[AT&T-netwerk](archive-att-network-archiver-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Bell-netwerk](archive-bell-network-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Ondernemingsnummer](archive-enterprise-number-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[O2-netwerk](archive-o2-network-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[TELUS-netwerk](archive-telus-network-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Verizon-netwerk](archive-verizon-network-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4-gegevensconnectors

De tabel in deze sectie bevat de gegevensconnectors van derden die beschikbaar zijn in samenwerking met 17a-4 LLC. De tabel bevat ook een overzicht van de complianceoplossingen die u kunt toepassen op gegevens van derden nadat u deze hebt geïmporteerd en gearchiveerd in Microsoft 365. Zie het [overzicht van complianceoplossingen](#overview-of-compliance-solutions-that-support-third-party-data) die gegevens van derden ondersteunen voor een gedetailleerde beschrijving van elke complianceoplossing en hoe deze gegevens van derden ondersteunt.

Voordat u gegevens van derden in Microsoft 365 kunt archiveren, moet u samenwerken met Veritas om de archiveringsservice *(dataparser)* voor uw organisatie in te stellen. Klik voor meer informatie op  de koppeling in de gegevenskolom van derden om de stapsgewijs instructies te volgen voor het maken van een verbindingslijn voor dat gegevenstype.

|Gegevens van derden  |Proces in de wacht zetten|eDiscovery  |Bewaarinstellingen  |Records Management  |Communicatiecompliance  |Beheer van insider-risico's  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Bloomberg](archive-17a-4-bloomberg-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Fuze](archive-17a-4-fuze-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[FX Connect](archive-17a-4-fxconnect-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[ICE Chat](archive-17a-4-ice-im-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[LivePerson Conversational Cloud](archive-17a-4-liveperson-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Slack](archive-17a-4-slack-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Inzoomen](archive-17a-4-zoom-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust-gegevensconnectoren

De tabel in deze sectie bevat de gegevensconnector van derden die beschikbaar is in samenwerking met CellTrust. De tabel bevat ook een overzicht van de complianceoplossingen die u kunt toepassen op gegevens van derden nadat u deze hebt geïmporteerd en gearchiveerd in Microsoft 365. Zie het [overzicht van complianceoplossingen](#overview-of-compliance-solutions-that-support-third-party-data) die gegevens van derden ondersteunen voor een gedetailleerde beschrijving van elke complianceoplossing en hoe deze gegevens van derden ondersteunt.

Voordat u gegevens van derden kunt archiveren in Microsoft 365, moet u samenwerken met CellTrust om de archiveringsservice *(cellTrust SL2)* voor uw organisatie in te stellen. Klik voor meer informatie op  de koppeling in de gegevenskolom van derden om de stapsgewijs instructies te volgen voor het maken van een CellTrust SL2-connector.

|Gegevens van derden  |Proces in de wacht zetten|eDiscovery  |Bewaarinstellingen  |Records Management  |Communicatiecompliance  |Beheer van insider-risico's  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
||||||||

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Overzicht van complianceoplossingen die gegevens van derden ondersteunen

In de volgende secties worden enkele dingen beschreven die Microsoft 365 complianceoplossingen u kunnen helpen bij het beheren van de gegevens van derden die in de vorige tabel worden vermeld.

### <a name="litigation-hold"></a>Proces in de wacht zetten

U houdt een [procedure in de wacht](create-a-litigation-hold.md) op een gebruikerspostvak om gegevens van derden te bewaren. Wanneer u een wachtperiode maakt, kunt u een duur opgeven (ook wel een tijdsinstelling *genoemd)* zodat verwijderde en gewijzigde gegevens van derden gedurende een bepaalde periode worden bewaard en vervolgens definitief uit het postvak worden verwijderd. Of u kunt inhoud voor onbepaalde tijd behouden (een oneindige greep *genoemd)* of totdat de procesvoering is verwijderd.

### <a name="ediscovery"></a>eDiscovery

De drie primaire eDiscovery-hulpprogramma's in Microsoft 365 zijn Inhoud zoeken, Core eDiscovery en Advanced eDiscovery.

- **[Zoeken naar inhoud](content-search.md).** U kunt het zoekprogramma voor inhoud gebruiken om in postvakken te zoeken naar gegevens van derden die u hebt geïmporteerd. U kunt zoekquery's en voorwaarden gebruiken om de zoekresultaten te beperken en de zoekresultaten te exporteren.

- **[Core eDiscovery](get-started-core-ediscovery.md).** Dit hulpprogramma bouwt voort op de basisfunctie voor zoeken en exporteren doordat u zaken kunt maken waarmee u kunt bepalen wie toegang heeft tot hoofdzaken, gebruikerspostvakken of postvakinhoud in de wacht houdt die overeenkomt met zoekcriteria. Dat betekent dat u een eDiscovery-hold kunt plaatsen op de gegevens van derden die zijn geïmporteerd in gebruikerspostvakken.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Met dit krachtige hulpprogramma wordt de casefunctionaliteit van Core eDiscovery uitgebreid door u beheerders toe te voegen aan een zaak, de gegevens van de bewaarder in de wacht te zetten en vervolgens de gegevens van een bewaarder te laden in een revisie voor verdere analyse, zoals thema's en dubbele detectie. Nadat u gegevens van derden hebt geladen in een revisieset, kunt u deze query's uitvoeren en filteren op een smalle resultatenset.

   Met Core eDiscovery en Advanced eDiscovery kunt u gegevens van derden beheren die relevant kunnen zijn voor het juridische of interne onderzoek van uw organisatie.

### <a name="retention-settings"></a>Bewaarinstellingen

U kunt een bewaarbeleid [toepassen](retention.md) op postvakken van gebruikers om gegevens van derden (en andere postvakinhoud) te behouden en vervolgens te verwijderen nadat de bewaarperiode is verlopen. U kunt bewaarbeleid ook gebruiken om gegevens van derden van een bepaalde leeftijd te verwijderen of bewaarlabels te gebruiken om een [dispositiebeoordeling](disposition.md) te activeren wanneer de bewaarperiode voor gegevens van derden verloopt.

### <a name="records-management"></a>Records Management

Met [de functie recordbeheer](records-management.md) in Microsoft 365 kunt u gegevens van derden declareeren als record. Dit kan handmatig worden gedaan door gebruikers die een bewaarlabel toepassen dat gegevens van derden in hun postvak markeert als record. U kunt ook bewaarlabels automatisch toepassen door gevoelige informatie, trefwoorden of inhoudstypen in gegevens van derden te identificeren.

### <a name="communication-compliance"></a>Communicatiecompliance

U kunt communicatie [compliance gebruiken](communication-compliance.md) om gegevens van derden te onderzoeken om te controleren of deze voldoen aan de gegevensstandaarden van uw organisatie. U kunt dit doen door ongepaste berichten in uw organisatie te detecteren, vast te leggen en herstelacties uit te voeren. U kunt bijvoorbeeld de gegevens van derden controleren die u importeert voor aanstootgevende taal, gevoelige informatie en naleving van regelgeving.

### <a name="insider-risk-management"></a>Intern risicobeheer

Signalen van gegevens van derden, zoals selectieve HR-gegevens, kunnen worden gebruikt door de [Insider-oplossing](insider-risk-management.md) voor risicobeheer om interne risico's te minimaliseren door u te laten detecteren, onderzoeken en handelen op risicovolle activiteiten in uw organisatie. Gegevens die door de HR-gegevensconnector worden geïmporteerd, worden bijvoorbeeld gebruikt als risicoindicatoren om te helpen bij het opsporen van diefstal van vertrekkende werknemersgegevens.

## <a name="data-connectors-in-the-us-government-cloud"></a>Gegevensconnectoren in de Cloud van de Amerikaanse overheid

Zoals eerder vermeld, zijn gegevensconnectoren die door TeleMessage worden geleverd, beschikbaar in de cloud van de Amerikaanse overheid. In de volgende tabel worden de specifieke overheidsomgevingen aangegeven die elke TeleMessage-gegevensconnector ondersteunen. Zie voor meer informatie over amerikaanse overheidswolken [Microsoft 365 Amerikaanse overheid.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)

|TeleMessage-gegevensconnector  |GCC  |GCC Hoog  |DoD  |
|:---------|:---------|:---------|:---------|
|Android Archiver | Ja | Nee | Nee |
|AT&T SMS/MMS Network Archiver | Ja | Nee | Nee |
|Bell SMS/MMS Network Archiver | Ja | Nee | Nee |
|Enterprise Number Archiver | Ja | Nee | Nee |
|O2 Sms- en Voice Network Archiver | Ja         | Nee | Nee |
|TELUS SMS Network Archiver | Ja | Nee | Nee |
|Verizon SMS/MMS Network Archiver | Ja | Nee | Nee |
|WhatsApp Archiver | Ja | Nee | Nee |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Werken met een Microsoft-partner om gegevens van derden te archiveren

Een andere optie voor het importeren en archiveren van gegevens van derden is dat uw organisatie met een Microsoft-partner werkt. Als een gegevenstype van derden niet wordt ondersteund door de gegevensconnectoren die beschikbaar zijn in het Microsoft-compliancecentrum, kunt u samenwerken met een partner die een aangepaste connector kan leveren die wordt geconfigureerd om regelmatig items uit de gegevensbron van derden op te halen en vervolgens verbinding te maken met de Microsoft-cloud via een API van derden en deze items te importeren in Microsoft 365. De partnerconnector converteert ook de inhoud van een item uit de gegevensbron van derden naar een e-mailbericht en importeert het vervolgens in een postvak in Microsoft 365.

Zie Werken met een partner om gegevens van derden te archiveren in Microsoft 365 voor een lijst met partners waarmee u kunt werken en het stapsgewijs proces [voor deze methode.](work-with-partner-to-archive-third-party-data.md)
