---
title: Plan SSL-certificaten van derden voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 'Overzicht: Beschrijft de SSL-certificaten die nodig zijn voor Exchange on-premises en hybride, SSO met AD FS, Exchange Online services en Exchange Web Services.'
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927486"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Plan SSL-certificaten van derden voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u communicatie tussen uw clients en de Microsoft 365 omgeving wilt versleutelen, moeten SSL-certificaten (Secure Socket Layer) van derden op uw infrastructuurservers zijn geïnstalleerd.

Dit artikel maakt deel uit van [netwerkplanning en prestatieafstemming voor Microsoft 365.](./network-planning-and-performance.md)
   
Certificaten zijn vereist voor de volgende Microsoft 365 onderdelen:
  
- Exchange on-premises
    
- Single sign-on (SSO) (voor zowel de Active Directory Federation Services (AD FS) federatieservers als AD FS-federatieserverproxies)
    
- Exchange Online services, zoals Autodiscover, Outlook Anywhere en Exchange Web Services
    
- Exchange hybride server
    
## <a name="certificates-for-exchange-on-premises"></a>Certificaten voor Exchange on-premises

Zie het TechNet-artikel Certificaatvereisten begrijpen voor een overzicht van hoe u digitale certificaten gebruikt om de communicatie tussen de on-premises Exchange-organisatie en Exchange Online te [beveiligen.](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))
  
## <a name="certificates-for-single-sign-on"></a>Certificaten voor één Sign-On

Als u uw gebruikers een vereenvoudigde ervaring met één aanmelding wilt bieden die krachtige beveiliging bevat, zijn de certificaten die in de volgende tabel worden weergegeven, vereist op de federatieservers of de federatieserverproxies. De onderstaande tabel richt zich op Active Directory Federation Services (AD FS), we hebben ook meer informatie over het gebruik van externe [identiteitsproviders.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Certificaattype | Beschrijving | Wat u moet weten voordat u implementeert |
|:-----|:-----|:-----|
|**SSL-certificaat (ook wel een serververificatiecertificaat genoemd)** <br/> |Dit is een standaard SSL-certificaat dat wordt gebruikt om communicatie tussen federatieservers, clients en federatieserverproxycomputers veilig te maken.  <br/> |AD FS vereist een SSL-certificaat. Ad FS gebruikt standaard het SSL-certificaat dat is geconfigureerd voor de standaardwebsite in Internet Information Services (IIS).  <br/> De onderwerpnaam van dit SSL-certificaat wordt gebruikt om de FS-naam (Federation Service) te bepalen voor elk exemplaar van AD FS dat u implementeert. Overweeg een onderwerpnaam te kiezen voor nieuwe certificaten van certificeringsinstantie (CA) die het beste de naam van uw bedrijf of organisatie vertegenwoordigen om te Microsoft 365. Deze naam moet internet-routable zijn.  <br/>**Let op:** Ad FS vereist dat dit SSL-certificaat geen puntloze onderwerpnaam (korte naam) heeft.          <br/> **Aanbeveling:** Omdat dit certificaat moet worden vertrouwd door clients van AD FS, raden we u aan een SSL-certificaat te gebruiken dat is uitgegeven door een openbare (externe) ca of door een ca die ondergeschikt is aan een openbaar vertrouwde hoofdmap. bijvoorbeeld VeriSign of Thawte.  <br/> |
|**Certificaat voor token-ondertekening** <br/> |Dit is een standaard X.509-certificaat dat wordt gebruikt voor het veilig ondertekenen van alle tokens die door de federatieserver worden uitgevoerd en die Microsoft 365 accepteert en valideert.  <br/> |Het certificaat voor het ondertekenen van token moet een persoonlijke sleutel bevatten die is geketend naar een vertrouwde hoofdmap in de FS. Ad FS maakt standaard een zelf ondertekend certificaat. Afhankelijk van de behoeften van uw organisatie kunt u dit certificaat echter wijzigen in een certificaat dat door een certificeringsorganisatie is uitgegeven met behulp van de ad-FS-beheer-module.  <br/>**Let op:** Het certificaat voor het ondertekenen van tokens is essentieel voor de stabiliteit van de FS. Als het certificaat wordt gewijzigd, moet Microsoft 365 op de hoogte worden gesteld van de wijziging. Als er geen melding wordt gegeven, kunnen gebruikers zich niet aanmelden bij hun Microsoft 365 serviceaanbiedingen.<br/>**Aanbeveling:** U wordt aangeraden het zelf ondertekende certificaat voor het ondertekenen van tokens te gebruiken dat wordt gegenereerd door AD FS. Hierdoor wordt dit certificaat standaard voor u beheert. Als dit certificaat bijvoorbeeld bijna verloopt, wordt er een nieuw zelf ondertekend certificaat gegenereerd door AD FS.  <br/> |
   
Federatieserverproxies vereisen het certificaat dat in de volgende tabel wordt beschreven.
  
| Certificaattype | Beschrijving | Wat u moet weten voordat u implementeert |
|:-----|:-----|:-----|
|SSL-certificaat  <br/> |Dit is een standaard SSL-certificaat dat wordt gebruikt voor het beveiligen van communicatie tussen een federatieserver, een federatieserverproxy en internetclientcomputers.  <br/> |Dit SSL-certificaat moet zijn gebonden aan de standaardwebsite in IIS voordat u de wizard AD FS Federation Server Proxy Configuration kunt uitvoeren.  <br/> Dit certificaat moet dezelfde onderwerpnaam hebben als het SSL-certificaat dat is geconfigureerd op de federatieserver in het bedrijfsnetwerk.  <br/> **Aanbeveling:** U wordt aangeraden hetzelfde serververificatiecertificaat te gebruiken dat is geconfigureerd op de federatieserver waar deze federatieserverproxy verbinding mee maakt.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificaten voor Autodiscover, Outlook Anywhere en Active Directory-synchronisatie

Voor uw externe Exchange 2013, Exchange 2010, Exchange 2007 en Exchange 2003 Client Access-servers (CAS's) is een SSL-certificaat van derden vereist voor veilige verbindingen voor Autodiscover- Outlook Anywhere- en Active Directory-synchronisatieservices. Mogelijk hebt u dit certificaat al geïnstalleerd in uw on-premises omgeving.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificaat voor een Exchange hybride server

Voor uw externe Exchange hybride server of servers is een SSL-certificaat van derden vereist voor veilige connectiviteit met de Exchange Online service. U moet dit certificaat verkrijgen van uw externe SSL-provider.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 Certificaatketens

In dit artikel worden de certificaten beschreven die u mogelijk op uw infrastructuur moet installeren. Zie Voor meer informatie over de certificaten die zijn geïnstalleerd op onze Microsoft 365 servers, [Microsoft 365 Certificaatketens.](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)
  
## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise overzicht](microsoft-365-overview.md)