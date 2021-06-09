---
title: Isolatie en Toegangsbeheer in Microsoft 365
ms.author: robmazz
author: robmazz
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
description: 'Samenvatting: Een uitleg van isolatie en toegangsbeheer binnen de verschillende toepassingen van Microsoft 365.'
ms.openlocfilehash: 53f60c09b94bdcc2515bcc5ff70dfbcd47f42bb4
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332326"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolatie en Toegangsbeheer in Microsoft 365

Azure Active Directory (Azure AD) en Microsoft 365 gebruiken een zeer complex gegevensmodel dat tientallen services, honderden entiteiten, duizenden relaties en tienduizenden kenmerken bevat. Op hoog niveau zijn Azure AD en de service directories de containers van tenants en geadresseerden die worden gesynchroniseerd met behulp van op de staat gebaseerde replicatieprotocollen. Naast de adreslijstgegevens die in Azure AD worden gehouden, hebben alle servicewerkbelastingen een eigen infrastructuur voor adreslijstservices.
 
![Microsoft 365 tenantgegevenssynchronisatie](../media/office-365-isolation-tenant-data-sync.png)

In dit model is er geen enkele bron van adreslijstgegevens. Specifieke systemen bezitten afzonderlijke gegevens, maar geen enkel systeem bevat alle gegevens. Microsoft 365 services werken samen met Azure AD in dit gegevensmodel. Azure AD is het 'systeem van de waarheid' voor gedeelde gegevens, meestal kleine en statische gegevens die door elke service worden gebruikt. Het federatief model dat wordt gebruikt in Microsoft 365 Azure AD biedt de gedeelde weergave van de gegevens.

Microsoft 365 gebruikt zowel fysieke opslag als Azure Cloud Storage. Exchange Online (inclusief Exchange Online Protection) en Skype voor Bedrijven eigen opslag voor klantgegevens gebruiken. SharePoint Online gebruikt zowel SQL Server als Azure Storage, vandaar de noodzaak van extra isolatie van klantgegevens op opslagniveau.

## <a name="exchange-online"></a>Exchange Online

Exchange Online slaat klantgegevens op in postvakken. Postvakken worden gehost in Extensible Storage Engine (ESE) databases met de naam postvakdatabases. Dit omvat gebruikerspostvakken, gekoppelde postvakken, gedeelde postvakken en postvakken in openbare mappen. Gebruikerspostvakken bevatten opgeslagen Skype voor Bedrijven inhoud, zoals gespreksgeschiedenissen.

Inhoud van het gebruikerspostvak bevat:

- E-mailberichten en e-mailbijlagen
- Agenda's en informatie over gratis/bezet
- Contactpersonen
- Taken
- Opmerkingen
- Groepen
- Inference-gegevens

Elke postvakdatabase in Exchange Online bevat postvakken van meerdere tenants. Een autorisatiecode beveiligt elk postvak, ook binnen een huurperiode. Standaard heeft alleen de toegewezen gebruiker toegang tot een postvak. De access control list (ACL) die een postvak beveiligt, bevat een identiteit die is geverifieerd door Azure AD op tenantniveau. De postvakken voor elke tenant zijn beperkt tot identiteiten die zijn geverifieerd op basis van de verificatieprovider van de tenant, die alleen gebruikers van die tenant bevat. Inhoud in tenant A kan op geen enkele manier worden verkregen door gebruikers in tenant B, tenzij expliciet goedgekeurd door tenant A.

## <a name="skype-for-business"></a>Skype voor Bedrijven

Skype voor Bedrijven slaat gegevens op verschillende plaatsen op:

- Gebruikers- en accountgegevens, waaronder verbindings-eindpunten, tenant-1D's, kiesplannen, roaming-instellingen, aanwezigheidstoestand, lijsten met contactpersonen, enzovoort, worden opgeslagen in de Skype voor Bedrijven Active Directory-servers en in verschillende Skype voor Bedrijven-databaseservers. Lijsten met contactpersonen worden opgeslagen in het postvak van de gebruiker Exchange Online als de gebruiker is ingeschakeld voor beide producten of op Skype voor Bedrijven servers als de gebruiker dat niet is. Skype voor Bedrijven databaseservers worden niet per tenant gepartitiefd, maar meervoudige isolatie van gegevens wordt afgedwongen via RBAC (Role-Based Access Control).
- Inhoud van vergadering en geüploade gegevens worden opgeslagen in DFS-aandelen (Distributed File System). Deze inhoud kan ook worden gearchiveerd in Exchange Online indien ingeschakeld. De DFS-aandelen worden niet per tenant verdeeld. de inhoud is beveiligd met ACL's en multi-tenancy wordt afgedwongen via RBAC.
- Oproepdetailrecords, zoals de activiteitengeschiedenis, zoals gespreksgeschiedenis, chatsessies, delen van toepassingen, chatgeschiedenis, enzovoort, kunnen ook worden opgeslagen in Exchange Online, maar de meeste records voor gespreksdetails worden tijdelijk opgeslagen op cdr-servers (Call Detail Record). Inhoud wordt niet verdeeld per tenant, maar multi-tenancy wordt afgedwongen via RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online heeft verschillende onafhankelijke mechanismen die gegevensisolatie bieden. Objecten worden opgeslagen als geabstraheerde code in toepassingsdatabases. Wanneer een gebruiker bijvoorbeeld een bestand uploadt naar SharePoint Online, wordt het bestand gedemonteerd, vertaald in toepassingscode en opgeslagen in meerdere tabellen in meerdere databases.

Als een gebruiker rechtstreeks toegang kan krijgen tot de opslag die de gegevens bevat, is de inhoud niet te interpreteren voor een mens of een ander systeem dan SharePoint Online. Deze mechanismen omvatten beveiligingstoegangsbeheer en -eigenschappen. Alle SharePoint onlinebronnen worden beveiligd met de autorisatiecode en het RBAC-beleid, ook binnen een huurperiode. De access control list (ACL) die een resource beveiligt, bevat een identiteit die is geverifieerd op tenantniveau. SharePoint Onlinegegevens voor een tenant zijn beperkt tot identiteiten die zijn geverifieerd door de verificatieprovider voor de tenant.

Naast de ACL's wordt een eigenschap op tenantniveau die de verificatieprovider aangeeft (de tenantspecifieke Azure AD), eenmaal geschreven en kan niet worden gewijzigd nadat deze is ingesteld. Wanneer de tenant-eigenschap van de verificatieprovider is ingesteld voor een tenant, kan deze niet worden gewijzigd met behulp van API's die aan een tenant zijn blootgesteld.

Voor elke tenant wordt een unieke *SubscriptionId* gebruikt. Alle klantsites zijn eigendom van een tenant en hebben een *SubscriptionId* toegewezen die uniek is voor de tenant. De *eigenschap SubscriptionId* op een site wordt eenmaal geschreven en is permanent. Wanneer een site is toegewezen aan een tenant, kan een site niet worden verplaatst naar een andere tenant. De *SubscriptionId* is de sleutel die wordt gebruikt om het beveiligingsbereik voor de verificatieprovider te maken en is gekoppeld aan de tenant.

SharePoint Online gebruikt SQL Server en Azure Storage voor opslag van inhoudsgegevens. De partitiesleutel voor het inhoudsopslag is *SiteId* in SQL. Wanneer u een SQL uitvoert, gebruikt SharePoint Online een *SiteId* die is geverifieerd als onderdeel van een *tenant-level SubscriptionId-controle.*

SharePoint Online worden versleutelde bestandsinhoud opgeslagen in Microsoft Azure blobs. Elke SharePoint Online farm heeft een eigen Microsoft Azure-account en alle blobs die in Azure zijn opgeslagen, worden afzonderlijk versleuteld met een sleutel die is opgeslagen in de SQL inhoudsopslag. De versleutelingssleutel die in code is beveiligd door de autorisatielaag en niet rechtstreeks aan de eindgebruiker wordt blootgesteld. SharePoint Online heeft realtime monitoring om te detecteren wanneer een HTTP-aanvraag gegevens voor meer dan één tenant leest of schrijft. De aanvraagidentiteit *SubscriptionId* wordt bijgespoord op *de SubscriptionId* van de accessed resource. Aanvragen voor toegang tot resources van meer dan één tenant mogen nooit worden ingediend door eindgebruikers. Serviceaanvragen in een omgeving met meerdere tenants zijn de enige uitzondering. De zoekcrawler haalt bijvoorbeeld inhoudswijzigingen voor een hele database in één keer op. Dit gaat meestal om het opvragen van sites van meer dan één tenant in één serviceaanvraag, die om efficiëntieredenen wordt uitgevoerd.

## <a name="teams"></a>Teams

Uw Teams gegevens worden anders opgeslagen, afhankelijk van het inhoudstype. 

Bekijk de [Ignite-brainstormsessie over Microsoft Teams architectuur](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) voor een uitgebreide discussie.

### <a name="core-teams-customer-data"></a>Kerngegevens Teams klantgegevens

Als uw tenant is ingericht in Australië, Canada, de Europese Unie, Frankrijk, Duitsland, India, Japan, Zuid-Afrika, Zuid-Korea, Zwitserland (inclusief Liechtenstein), de Verenigde Arabische Emiraten, het Verenigd Koninkrijk of de Verenigde Staten, slaat Microsoft de volgende klantgegevens alleen op op die locatie:

- Teams chats, team- en kanaalgesprekken, afbeeldingen, voicemailberichten en contactpersonen.
- SharePoint Onlinesite-inhoud en de bestanden die op die site zijn opgeslagen.
- Bestanden die zijn geüpload OneDrive voor werk of school.

#### <a name="chat-channel-messages-team-structure"></a>Chatten, kanaalberichten, teamstructuur

Elk team in Teams team wordt gebacked door een Microsoft 365 groep en de SharePoint site en Exchange postvak. Privéchats (inclusief groepschats), berichten die als onderdeel van een gesprek in een kanaal worden verzonden en de structuur van teams en kanalen worden opgeslagen in een chatservice die wordt uitgevoerd in Azure. De gegevens worden ook opgeslagen in een verborgen map in de postvakken van de gebruiker en de groep om informatiebeveiligingsfuncties in te stellen.

#### <a name="voicemail-and-contacts"></a>Voicemail en contactpersonen

Voicemails worden opgeslagen in Exchange. Contactpersonen worden opgeslagen in Exchange cloudgegevensopslag. Exchange en de Exchange cloudstore bieden al gegevensopslag in elk van de wereldwijde datacenter-geo's. Voor alle teams worden voicemail en contactpersonen opgeslagen in het land voor Australië, Canada, Frankrijk, Duitsland, India, Japan, de Verenigde Arabische Emiraten, het Verenigd Koninkrijk, Zuid-Afrika, Zuid-Korea, Zwitserland (inclusief Liechtenstein) en de Verenigde Staten. Voor alle andere landen worden bestanden opgeslagen in de VS, Europa of Asia-Pacific locatie op basis van tenant-affiniteit.

#### <a name="images-and-media"></a>Afbeeldingen en media

Media die worden gebruikt in chats (met uitzondering van Giphy GIF's die niet worden opgeslagen, maar een verwijzingskoppeling zijn naar de oorspronkelijke Giphy-service-URL, Giphy is een niet-Microsoft-service) worden opgeslagen in een op Azure gebaseerde mediaservice die wordt geïmplementeerd op dezelfde locaties als de chatservice.

#### <a name="files"></a>Bestanden

Bestanden (inclusief OneNote en Wiki) die iemand in een kanaal deelt, worden opgeslagen op de teamsite SharePoint team. Bestanden die worden gedeeld in een privéchat of een chat tijdens een vergadering of gesprek, worden geüpload en opgeslagen in de OneDrive voor werk- of schoolaccount van de gebruiker die het bestand deelt. Exchange, SharePoint en OneDrive bieden al gegevenslocatie in elk van de wereldwijde datacenter-geo's. Voor bestaande klanten zijn alle bestanden, OneNote-notitieblokken, Teams wiki-inhoud en postvakken die deel uitmaken van de Teams-ervaring al opgeslagen op de locatie op basis van uw tenant-affiniteit. Bestanden worden in het land opgeslagen voor Australië, Canada, Frankrijk, Duitsland, India, Japan, de Verenigde Arabische Emiraten, het Verenigd Koninkrijk, Zuid-Afrika, Zuid-Korea en Zwitserland (inclusief Liechtenstein). Voor alle andere landen worden bestanden opgeslagen in de amerikaanse, Europese of Aziatische Stille Oceaan op basis van tenant-affiniteit.
