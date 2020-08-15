---
title: Isolatie en toegangsbeheer in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 'Overzicht: een uitleg van de isolatie en toegangscontrole binnen de verschillende toepassingen van Microsoft 365.'
ms.openlocfilehash: 40a1f1d93fe34333366e456cc006ab2d1c700a83
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689278"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolatie en toegangsbeheer in Microsoft 365

Azure Active Directory (Azure AD) en Microsoft 365 gebruikmaken van een zeer complex gegevensmodel dat tientallen diensten, honderden entiteiten, duizenden relaties en tientallen kenmerken bevat. Op een hoog niveau, Azure AD en de service directory's, zijn de containers van de tenants en de geadresseerden gesynchroniseerd met behulp van op basis van de op basis van basis protocollen op basis van de status. Naast de directorygegevens die worden bijgehouden in azure AD, hebben alle service belastingen de eigen directory services-infrastructuur.
 
![Microsoft 365 Tenant Data Sync](../media/office-365-isolation-tenant-data-sync.png)

In dit model bevindt zich niet één bron van directorygegevens. Specifieke systemen hebben eigen afzonderlijke stukjes gegevens, maar er zijn geen enkele systemen. Microsoft 365-services werken via Azure AD in dit gegevensmodel. Azure AD is het ' systeem van waarheid ' voor gedeelde gegevens, meestal een kleine en statische gegevens die worden gebruikt door elke service. Het federatieve model dat wordt gebruikt in Microsoft 365 en Azure AD, biedt de gedeelde weergave van de gegevens.

Microsoft 365 maakt gebruik van fysieke opslag en Azure cloudopslag. Exchange Online (met inbegrip van Exchange Online Protection) en Skype voor bedrijven gebruiken hun eigen opslag voor klantgegevens. In SharePoint Online wordt zowel SQL Server Storage als Azure Storage gebruikt, en daarom is er meer isolatie van klantgegevens op het niveau van de opslag nodig.

## <a name="exchange-online"></a>Exchange Online

Exchange Online slaat klantgegevens op in postvakken. Postvakken zijn ondergebracht in ESE-databases (Extensible Storage Engine) genaamd postvak databases. Dit omvat gebruikerspostvakken, gekoppelde postvakken, gedeelde postvakken en postvakken in openbare mappen. Gebruikerspostvakken bevatten opgeslagen inhoud van Skype voor bedrijven, zoals de geschiedenis van gesprekken.

Inhoud van het gebruikerspostvak omvat:

- E-mails en e-mailbijlagen
- Agenda en beschikbaarheidsinfo
- Contactpersonen
- Taken
- Opmerkingen
- Groepen
- Gegevens voor devan beinterferentie

Elke postvakdatabase in Exchange Online bevat postvakken van meerdere tenants. Met een verificatiecode wordt elk postvak beveiligd, waaronder binnen een pacht. Standaard heeft alleen de toegewezen gebruiker toegang tot een postvak. De toegangsbeheerlijst (ACL) die een postvak beveiligt, bevat een id die wordt geverifieerd door Azure AD op tenantniveau. De postvakken voor een Tenant zijn beperkt tot identiteiten die zijn geverifieerd door de authenticatieprovider van de Tenant, die alleen gebruikers van die Tenant omvat. De inhoud in de Tenant A kan niet op een willekeurige manier worden verkregen door gebruikers in de Tenant B, tenzij dit expliciet is goedgekeurd door Tenant A.

## <a name="skype-for-business"></a>Skype voor Bedrijven

In Skype voor bedrijven worden gegevens op verschillende plaatsen opgeslagen:

- Gebruikers-en accountgegevens, waaronder verbindings eindpunten, Tenant-Id's, kies plannen, zwervende instellingen, aanwezigheidsstatus, lijsten met contactpersonen, enzovoort, worden opgeslagen in de Active Directory-servers van Skype voor bedrijven en in verschillende Skype voor bedrijven-databaseservers. Lijsten met contact personen worden opgeslagen in het Exchange Online-postvak van de gebruiker als de gebruiker is ingeschakeld voor beide producten of op Skype voor bedrijven-servers als de gebruiker dat niet doet. Database servers van Skype voor bedrijven zijn niet gepartitioneerd per Tenant, maar de isolatie van multitenancy van gegevens wordt afgedwongen via toegangsbeheer op basis van rollen (RBAC).
- Inhoud van de vergadering en geüploade gegevens zijn opgeslagen in de DFS-share (Distributed File System). Deze inhoud kan ook worden gearchiveerd in Exchange Online indien ingeschakeld. De DFS-shares zijn niet gepartitioneerd per Tenant. de inhoud is beveiligd met Acl's en multitenancy wordt afgedwongen via RBAC.
- Oproep detailrecords, welke de activiteitengeschiedenis zijn, zoals Oproepgeschiedenis, chatsessies, delen van toepassingen, chatgeschiedenis, etc., kunnen ook worden opgeslagen in Exchange Online, maar de meeste detailrecords voor oproep detailrecord (CDR)-servers zijn tijdelijk opgeslagen. Inhoud is niet gepartitioneerd per Tenant, maar multitenancy wordt afgedwongen via RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online bevat diverse onafhankelijke mechanismen waarmee gegevens kunnen worden geïsoleerd. Het bevat objecten als een abstracte code in toepassingsdatabases. Wanneer een gebruiker een bestand uploadt naar SharePoint Online, wordt het bestand bijvoorbeeld ontleed, vertaald in Application code en opgeslagen in meerdere tabellen in meerdere tabellen.

Als een gebruiker rechtstreeks toegang kan krijgen tot de opslag met de gegevens, kan de inhoud niet worden geïnterpreteerd voor personen of andere systemen dan SharePoint Online. Dit zijn de mechanismen voor toegangsbeheer en eigenschappen voor beveiliging. Alle SharePoint Online-bronnen worden beveiligd door de autorisatiecode en de RBAC-beleidsregels, waaronder binnen een pacht. De toegangsbeheerlijst (ACL) die een resource beveiligt, heeft een id die op tenantniveau is geverifieerd. SharePoint Online-gegevens voor een Tenant zijn beperkt tot identiteiten die zijn geverifieerd door de authenticatieprovider voor de Tenant.

Naast de Acl's wordt in de eigenschap tenantniveau opgegeven dat de authenticatieprovider (die de Tenant specifiek Azure AD) bevat, eenmaal vastgelegd en kan deze niet meer worden gewijzigd. Wanneer de Tenant eigenschap van de verificatieprovider is ingesteld voor een Tenant, kan deze niet worden gewijzigd met Api's die aan een Tenant zijn blootgesteld.

Voor elke Tenant wordt een unieke *SubscriptionId* gebruikt. Alle klanten sites zijn eigendom van een Tenant en krijgen een naam van een *SubscriptionId* toegewezen aan de Tenant. De eigenschap *SubscriptionId* op een site wordt eenmaal weggeschreven en is permanent. Wanneer een site is toegewezen aan een Tenant, kan een site niet worden verplaatst naar een andere Tenant. De *SubscriptionId* is de sleutel die wordt gebruikt om het beveiligingsbereik voor de authenticatieprovider te maken en is gekoppeld aan de Tenant.

SharePoint Online gebruikt SQL Server en Azure Storage voor metagegevens opslag voor inhoud. De partitiesleutel voor de inhouds opslag is een *site* -naam in SQL. Wanneer u een SQL-query uitvoert, wordt in SharePoint Online een gevolgde gebruikgemaakt van een gevolgde *site* *-controle op* tenantniveau.

In SharePoint Online worden versleutelde bestandsinhoud opgeslagen in Microsoft Azure-blob's. Elke SharePoint Online-Farm heeft een eigen Microsoft Azure-account en alle blob's die in azure zijn opgeslagen, worden afzonderlijk versleuteld met een sleutel die is opgeslagen in de SQL-inhouds opslag. De versleutelingssleutel is beveiligd met de code van de autorisatie slaag en wordt niet rechtstreeks aan de eindgebruiker blootgesteld. SharePoint Online biedt realtime monitoring om te detecteren wanneer een HTTP-aanvraaggegevens voor meer dan één Tenant leest of schrijft. De aanvraag id *subscriptionid* wordt bijgehouden op de *subscriptionid* van de toegankelijke resource. Aanvragen om toegang te krijgen tot bronnen van meer dan één Tenant, mag nooit door eindgebruikers plaatsvinden. Service aanvragen in een omgeving met meerdere tenants zijn de enige uitzondering. Wanneer de zoek crawler inhoud bijvoorbeeld voor een hele database tegelijk wijzigt. Dit geldt meestal voor het uitvoeren van een query naar sites van meer dan één Tenant in één serviceaanvraag, die voor efficiëntie redenen wordt uitgevoerd.

## <a name="teams"></a>Teams

Afhankelijk van het inhoudstype worden de gegevens van uw teams verschillend opgeslagen. 

Bekijk de [Ignite-spreek-sessie in Microsoft teams Architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) voor een uitgebreide discussie.

### <a name="core-teams-customer-data"></a>Belangrijkste teams-klantgegevens

Als uw Tenant is ingericht in Australië, Canada, de Europese Unie, Frankrijk, Frankrijk, Duitsland, India, Japan, Zuid-Afrika, Zuid-Korea, Zwitserland (inclusief Liechtenstein), de Verenigde Arabische Emiraten, het Verenigd Koninkrijk of de Verenigde Staten, Microsoft Microsoft storeeert de volgende klantgegevens op hun plaats op de plaats:

- Teams-chats, gesprekken van team en kanaal, afbeeldingen, voicemailberichten en contactpersonen.
- Site-inhoud van SharePoint Online en de bestanden die zijn opgeslagen op deze site.
- Bestanden die zijn geüpload naar OneDrive voor werk of school.

#### <a name="chat-channel-messages-team-structure"></a>Chatten, kanaalberichten, team structuur

Elk team in teams wordt ondersteund door een Microsoft 365-groep en de bijbehorende SharePoint-site en het Exchange-postvak. Persoonlijke chats (waaronder chat gesprekken), berichten die als onderdeel van een gesprek in een kanaal zijn verzonden en de structuur van teams en kanalen, worden opgeslagen in een chatservice die wordt uitgevoerd in Azure. De gegevens worden ook opgeslagen in een verborgen map van de gebruikers-en groeps postvakken om functies voor gegevensbeveiliging in te schakelen.

#### <a name="voicemail-and-contacts"></a>Voicemail en contactpersonen

Voicemailberichten worden opgeslagen in Exchange. Contactpersonen worden opgeslagen in de op Exchange gebaseerde cloudgegevens opslag. Voor Exchange en het Exchange-Cloud archief bevindt zich al gegevens woonplaats in alle wereldwijde datacenter-GEOS. Voor alle teams, voicemail en contactpersonen zijn opgeslagen in het land voor Australië, Canada, Frankrijk, Duitsland, India, Japan, Japan, de Verenigde Arabische Emiraten, Zuid-Korea, Zuid-Korea, Zuid-Korea, Zuid-Korea, Zuid-Korea en de Verenigde Staten. Voor alle andere landen worden bestanden opgeslagen op de Amerikaanse, Europe of Azië-Pacific locatie op basis van Tenant affiniteit.

#### <a name="images-and-media"></a>Afbeeldingen en media

Media die worden gebruikt in chats (met uitzondering van Giphy-Gif's die niet zijn opgeslagen, maar wel een verwijzingskoppeling naar de oorspronkelijke URL van de Giphy-service zijn, Giphy is een niet-Microsoft-service), wordt opgeslagen in een Azure-media service die wordt geïmplementeerd op dezelfde locaties als de chatservice.

#### <a name="files"></a>Bestanden

Bestanden (waaronder OneNote en wiki) die iemand deelt in een kanaal, wordt opgeslagen op de SharePoint-site van het team. Bestanden die in een privégesprek of chat worden gedeeld tijdens een vergadering of gesprek, worden geüpload en opgeslagen in het OneDrive voor werk-of schoolaccount van de gebruiker die het bestand deelt. Voor Exchange, SharePoint en OneDrive is al gegevens woonplaats beschikbaar in de wereldwijde datacenter-GEOS. Voor bestaande klanten worden alle bestanden, OneNote-notitieblokken, wiki-notitieblokken en postvakken die deel uitmaken van de teams-ervaring al op de locatie opgeslagen op basis van de Tenant affiniteit. Bestanden zijn opgeslagen in het land voor Australië, Canada, Frankrijk, Duitsland, India, Japan, de Verenigde Arabische Emiraten, het Verenigd Koninkrijk, Zuid-Afrika, Zuid-Korea en Zwitserland (inclusief Liechtenstein). Voor alle andere landen worden bestanden opgeslagen op de Amerikaanse, Europe of Azië/Pacific-locatie op basis van Tenant affiniteit.
