---
title: Microsoft 365 Connectivity Optics
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Dit artikel bevat informatie over Microsoft 365 Connectivity Optics.
ms.openlocfilehash: 952990a63d4ad064b2027c6f2364e8082342fa34
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2021
ms.locfileid: "53455975"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365 Connectivity Optics

In dit document worden enkele van de connectiviteitsoptieken beschreven die Microsoft gewoonlijk verzamelt op apparaten van klanten en worden enkele manieren beschreven waarop Microsoft dergelijke gegevens gebruikt om servicelevering te analyseren en te optimaliseren en om de best mogelijke eindgebruikerservaring te beoordelen en te waarborgen.

Connectiviteitsoptiek wordt meestal verzameld uit Microsoft-toepassingen, die kunnen worden geïnstalleerd op apparaten van eindgebruikers of worden gebruikt vanuit browsers. In tegenstelling tot optionele gegevensverzameling binnen Microsoft 365 services, zijn veel van de hier beschreven connectiviteitsoptiek essentieel om ervoor te zorgen dat Microsoft voldoet aan onze beschikbaarheids- en prestatieverplichting voor klanten. Met deze optiek kan Microsoft problemen in het verbindingspad tussen eindgebruikers en Microsoft-service-eindpunten snel opsporen en oplossen. Sommige van deze optica worden ook gebruikt om functies in te stellen, zoals [Netwerkconnectiviteit in het Microsoft 365-beheer Center.](office-365-network-mac-perf-overview.md)

## <a name="optics-collected-from-microsoft-365-applications"></a>Optica verzameld uit Microsoft 365 toepassingen

Optica wordt momenteel verzameld met behulp van een niet-vaak gebruikte steekproef op alle apparaten. Over het algemeen worden de specifieke set optica en bestemmingen (service-eindpunten) die in een bepaalde iteratie moeten worden gemeten, geconfigureerd door Microsoft op basis van servicevereisten en gerandomiseerd voor steekproefdoeleinden.
Bij elk optiekverzamelingsinterval kunnen een of meer van de volgende metingen worden verzameld met behulp van het apparaat van de eindgebruiker als meetbron en een Microsoft 365 service-eindpunt als meetdoel:

| Meting | Omschrijving |
| --- | --- |
| Latentie | De tijd die nodig is om een klein bestand op te halen via HTTP |
| Doorvoer | Tijd die nodig is om een groter bestand op te halen via HTTP, zelden gemeten om overmatig bandbreedteverbruik te voorkomen |
| Round Trip Time (RTT) | ICMP-ping |
| Traceroute | ICMP-traceroute |

Elke meting wordt meestal gekoppeld aan aanvullende informatie, waaronder de volgende items:

| Item | Beschrijving |
| --- | --- |
| Tenant-id | Unieke id voor de klant Azure Active Directory tenant die is gekoppeld aan het apparaat van de eindgebruiker. |
| Monitor-id | Id voor de toepassing die de aanvraag genereert (zoals Outlook, OneDrive, enzovoort), die wordt geleverd door de clienttoepassing die de meting voert. |
| Aanvraag-id | Id voor het maatverzoek, opgegeven in de maatconfiguratie van Microsoft. |
| Extern IP-adres | Gemaskerde bron-IP die is gekoppeld aan de aanvraag van client naar service-eindpunt, geleverd door de server die het meetverzoek heeft ontvangen en berekend op basis van het IP-adres van de clientbron dat zichtbaar is voor Microsoft. IP-adressen worden gemaskeerd naar een /24-subnet voor IPv4-adressen of een /48-subnet voor IPv6-adressen om ervoor te zorgen dat Microsoft geen afzonderlijke apparaten of gebruikers kan identificeren. |
| Front-end | Microsoft 365 service front-end-id, geleverd door de server die het maatverzoek heeft ontvangen. |
| Eindpunt | Microsoft 365 service-eindpuntlocatie, geleverd door de server die het maatverzoek heeft ontvangen. |
| Certificaat uitgegeven door | De eigenschap 'certificaat afgegeven door' van het SSL-certificaat dat wordt gepresenteerd terwijl u verbinding maakt met het service-eindpunt, wat aangeeft dat de certificeringsinstantie het certificaat heeft uitgegeven aan het service-eindpunt. |
| Certificate Thumbprint | De eigenschap 'certificate thumbprint' van het SSL-certificaat dat wordt gepresenteerd tijdens het maken van verbinding met het service-eindpunt, een voor het publiek toegankelijke unieke id van het certificaat. |
| Breedtegraden/lengtelengte | De geabstraheerde breedte- en lengtegraad van het apparaat van de eindgebruiker. Dit wordt alleen verzameld voor tenants die Windows Locatieservice hebben ingeschakeld op apparaten van eindgebruikers en ook het verzamelen van deze gegevens hebben ingeschakeld in de [Microsoft 365-beheerportal.](office-365-network-mac-perf-overview.md#1-enable-windows-location-services) |

## <a name="measurement-process"></a>Meetproces

Elk apparaat van de eindgebruiker voert meestal een meting uit op een geplande basis (voor geïnstalleerde toepassingen) of op basis van de actie van het laden van browserpagina's (voor webtoepassingen). Meetactiviteiten worden uitgevoerd als achtergrondbewerkingen en hebben geen invloed op de toepassingservaring voor gebruikers. Aangezien de meettypen en bestemmingen die voor een bepaalde iteratie van dit proces worden gebruikt, gerandomiseerd zijn, kunnen klanten aanvragen voor Microsoft-service-eindpunten in hun regio zien die lijken op de gebruikelijke aanvragen van eindgebruikersapparaten voor normale toepassingsconnectiviteit. Daarnaast kunnen klanten aanvragen voor Microsoft-service-eindpunten zien die zich ver buiten hun lokale regio hebben. Deze metingen worden vaak gebruikt om een optimale routering van klantaanvragen naar het beste service-eindpunt te waarborgen, omdat voor wijzigingen in de klant- en isp-infrastructuur microsoft mogelijk het routeringsbeleid voor aanvragen voortdurend moet wijzigen. Meer informatie over hoe Microsoft verkeer naar het beste service-eindpunt routeert en hoe u de connectiviteit kunt optimaliseren voor Microsoft 365 services in het overzicht [Microsoft 365 netwerkconnectiviteit.](microsoft-365-networking-overview.md)

## <a name="service-endpoints"></a>Service-eindpunten

De Microsoft-service-eindpunten die worden gebruikt als bestemmingen voor deze metingen, zijn opgenomen in de gepubliceerde Office 365 URL's en [IP-adresbereiken.](urls-and-ip-address-ranges.md) Toegang tot extra service-eindpunten is niet nodig voor het verzamelen van deze connectiviteitsoptiek.
