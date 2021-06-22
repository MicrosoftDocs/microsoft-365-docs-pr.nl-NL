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
ms.openlocfilehash: 5e1eab67019184e337b7e5404bf96bdf26d0446d
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061732"
---
# <a name="archive-third-party-data"></a>Gegevens van derden archiveren

Microsoft 365 kunnen beheerders gegevensconnectoren gebruiken om gegevens van derden van sociale mediaplatforms, chatplatforms en samenwerkingsplatformen voor documenten te importeren en te archiveren in postvakken in uw Microsoft 365 organisatie. Een van de belangrijkste voordelen van het gebruik van gegevensconnectoren voor het importeren en archiveren van gegevens van derden in Microsoft 365 is dat u verschillende Microsoft 365 complianceoplossingen kunt toepassen nadat deze zijn geïmporteerd. Op deze manier kunt u ervoor zorgen dat de niet-Microsoft-gegevens van uw organisatie voldoen aan de voorschriften en standaarden die van invloed zijn op uw organisatie.

## <a name="third-party-data-connectors"></a>Gegevensconnectors van derden

De volgende tabel bevat de gegevensconnectors van derden die beschikbaar zijn in de Microsoft 365-compliancecentrum. De tabel bevat ook een overzicht van de complianceoplossingen die u kunt toepassen op gegevens van derden nadat u gegevens van derden hebt geïmporteerd en gearchiveerd in Microsoft 365. Zie de [volgende sectie voor](#overview-of-compliance-solutions-that-support-third-party-data) een gedetailleerde beschrijving van elke complianceoplossing en hoe deze voordelen kan hebben voor gegevens van derden.

> [!TIP]
> Klik op de koppeling in **de** gegevenskolom van derden om de stapsgewijs instructies te volgen voor het maken van een verbindingslijn voor dat gegevenstype.

|Gegevens van derden  |Proces in de wacht zetten|eDiscovery  |Bewaarinstellingen  |Records Management  |Communicatiecompliance  |Beheer van insider-risico's  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Bloomberg-bericht](archive-bloomberg-message-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber op MS SQL <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber op Oracle <sup>2</sup>](archive-ciscojabberonoracle-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Cisco Jabber op PostgreSQL <sup>2</sup>](archive-ciscojabberonpostgresql-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[<sup>Ondernemingsnummer 1</sup>](archive-enterprise-number-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[FX Verbinding maken <sup>2</sup>](archive-fxconnect-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Personeelszaken (HR)](import-hr-data.md) ||||||![Vinkje](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[O2 Network <sup>1</sup>](archive-o2-network-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Fysieke badging](import-physical-badging-data.md) ||||||![Vinkje](../media/checkmark.png)|
|[Draaipunt <sup>2</sup>](archive-pivot-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Signaal <sup>1</sup>](archive-signal-archiver-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Skype voor Bedrijven <sup>2</sup>](archive-skypeforbusiness-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Symfonie <sup>2</sup>](archive-symphony-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Telegram <sup>1</sup>](archive-telegram-archiver-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Tekst met <sup>scheidingstekens 2</sup>](archive-text-delimited-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[<sup>Webpagina's 2</sup>](archive-webpagecapture-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[WeChat <sup>1</sup>](archive-wechat-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[Workplace from Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|[<sup>Zoomvergaderingen 2</sup>](archive-zoommeetings-data.md)     |![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Gegevensconnector die door TeleMessage wordt geleverd. Voordat u gegevens kunt archiveren in Microsoft 365, moet u met TeleMessage werken om de archiveringsservice voor uw organisatie in te stellen. Zie de vereiste sectie in de stapsgewijs instructies voor dit gegevenstype voor meer informatie. TeleMessage-gegevensconnectoren zijn ook beschikbaar in GCC omgevingen in Microsoft 365 cloud van de Amerikaanse overheid. Zie de sectie Gegevensconnectoren in de cloud van de Amerikaanse overheid [in](#data-connectors-in-the-us-government-cloud) dit artikel voor meer informatie. <br/><br/><sup>2</sup> Gegevensconnector geleverd door Veritas. Voordat u gegevens kunt archiveren in Microsoft 365, moet u samenwerken met Veritas om de archiveringsservice voor uw organisatie in te stellen. Zie de vereiste sectie in de stapsgewijs instructies voor dit gegevenstype voor meer informatie.

De gegevens van derden in de vorige tabel (met uitzondering van HR-gegevens en fysieke foutgegevens) worden geïmporteerd in gebruikerspostvakken. De bijbehorende complianceoplossingen die gegevens van derden ondersteunen, worden toegepast op het postvak van de gebruiker waarin de gegevens zijn opgeslagen.

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
