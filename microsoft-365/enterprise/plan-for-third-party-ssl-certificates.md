---
title: Abonnement voor externe SSL-certificaten voor Microsoft 365
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
description: 'Overzicht: hierin worden de SSL-certificaten beschreven die nodig zijn voor Exchange on-premises en hybride, SSO met AD FS, Exchange Online Services en Exchange-webservices.'
ms.openlocfilehash: 1738e4c316772d928138adc654372bd0b9efae65
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689198"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Abonnement voor externe SSL-certificaten voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u de communicatie tussen de clients en de Microsoft 365-omgeving wilt versleutelen, moet u de SSL-certificaten (Secure Socket Layer) van derden installeren op de infrastructuurservers.

Dit artikel maakt onderdeel uit van [netwerk planning en prestaties optimaliseren voor Microsoft 365](https://aka.ms/tune).
   
Certificaten zijn vereist voor de volgende Microsoft 365-onderdelen:
  
- Exchange on-premises
    
- Eenmalige aanmelding (SSO) (voor de AD FS-federatieservers (Active Directory Federation Services) en proxy's van de AD FS-federatie)
    
- Exchange Online-Services, zoals automatisch opsporen, Outlook Anywhere en Exchange-webservices
    
- Hybride Exchange-Server
    
## <a name="certificates-for-exchange-on-premises"></a>Certificaten voor Exchange on-premises

Voor een overzicht van het gebruik van digitale certificaten voor het maken van de communicatie tussen de on-premises Exchange-organisatie en Exchange Online veilig, raadpleegt u het TechNet-artikel [informatie over de certificaatvereisten](https://go.microsoft.com/fwlink/p/?LinkID=243657).
  
## <a name="certificates-for-single-sign-on"></a>Certificaten voor eenmalige aanmelding

Als u uw gebruikers wilt voorzien van eenvoudigere functionaliteit voor eenmalige aanmelding, inclusief krachtige beveiliging, zijn de certificaten in de volgende tabel nodig op de federatieservers of de federatieserver-proxy's. In de volgende tabel vindt u meer informatie over [het gebruik van id-providers van derden voor providers](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).
  
| Certificaat type | Beschrijving | Wat u moet weten voordat u de implementatie uitvoert |
|:-----|:-----|:-----|
|**SSL-certificaat (ook wel een serververificatiecertificaat genoemd)** <br/> |Dit is een standaard-SSL-certificaat dat wordt gebruikt voor het beveiligen van de communicatie tussen federatieservers, clients en federatieserverproxy servers.  <br/> |Voor AD FS is een SSL-certificaat vereist. AD FS maakt standaard gebruik van het SSL-certificaat dat is geconfigureerd voor de standaardwebsite in IIS (Internet Information Services).  <br/> De naam van het onderwerp van dit SSL-certificaat wordt gebruikt om de naam van de Federation service (FS) te bepalen voor elk exemplaar van AD FS dat u implementeert. Overweeg om een onderwerpnaam voor een nieuwe certificeringsinstantie (CA) te kiezen, die het beste de naam van uw bedrijf of organisatie voor Microsoft 365 vertegenwoordigt. Deze naam moet Internet routeerbaar zijn.  <br/>**Let op:** Voor AD FS moet dit SSL-certificaat de naam van het onderwerp van niet-wegnamen hebben.          <br/> **Aanbeveling:** Aangezien dit certificaat moet worden vertrouwd door clients van AD FS, wordt u aangeraden een SSL-certificaat te gebruiken dat is uitgegeven door een openbare (externe) certificeringsinstantie of door een certificeringsinstantie onder een openbaar vertrouwde basiscertificeringsinstantie. bijvoorbeeld VeriSign of Thawte.  <br/> |
|**Certificaat voor token-ondertekening** <br/> |Dit is een standaard X. 509-certificaat dat wordt gebruikt voor het veilig ondertekenen van alle tokens die door de federatieserver worden uitgegeven en die in Microsoft 365 worden geaccepteerd en gevalideerd.  <br/> |Het certificaat voor token-ondertekening moet een persoonlijke sleutel bevatten die kan worden gekoppeld aan een vertrouwd basisniveau in de FS. Standaard maakt AD FS een zelfondertekend certificaat. Afhankelijk van de behoeften van uw organisatie, kunt u dit certificaat echter wijzigen in een door de certificeringsinstantie verstrekt certificaat met de module AD FS-beheer.  <br/>**Let op:** Het certificaat voor token-ondertekening is essentieel voor de stabiliteit van de FS. Als het certificaat is gewijzigd, moet Microsoft 365 op de hoogte worden gesteld van de wijziging. Gebruikers kunnen zich niet aanmelden bij de Microsoft 365-serviceaanbiedingen als er geen melding wordt gegeven.<br/>**Aanbeveling:** U wordt aangeraden het zelfondertekend certificaat voor token-ondertekening te gebruiken dat is gegenereerd door AD FS. Op dit manier beheert dit certificaat standaard voor u. Wanneer dit certificaat binnenkort bijna verloopt, wordt er een nieuw, zelfondertekend certificaat voor AD FS gegenereerd.  <br/> |
   
Voor federatieserver proxy's is het certificaat vereist dat in de volgende tabel wordt beschreven.
  
| Certificaat type | Beschrijving | Wat u moet weten voordat u de implementatie uitvoert |
|:-----|:-----|:-----|
|SSL-certificaat  <br/> |Dit is een standaard-SSL-certificaat dat wordt gebruikt voor het beveiligen van de communicatie tussen een federatieserver, een federatieserverproxy en Internet clientcomputers.  <br/> |Dit SSL-certificaat moet zijn gekoppeld aan de standaardwebsite in IIS voordat u de wizard AD FS federatie server proxy configureren kunt uitvoeren.  <br/> Dit certificaat moet dezelfde onderwerpnaam hebben als het SSL-certificaat dat is geconfigureerd op de federatieserver in het bedrijfsnetwerk.  <br/> **Aanbeveling:** U wordt aangeraden het certificaat voor serververificatie te gebruiken dat is geconfigureerd op de federatieserver waarmee deze federatieserverproxy verbinding maakt.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificaten voor automatisch opsporen, Outlook Anywhere en Active Directory-synchronisatie

Voor externe Exchange 2013, Exchange 2010, Exchange 2007 en Exchange 2003 server voor client toegang (CASs) is een extern SSL-certificaat vereist voor beveiligde verbindingen voor automatisch opsporen, Outlook Anywhere en Active Directory-synchronisatie Services. U hebt mogelijk al dit certificaat in uw on-premises omgeving geïnstalleerd.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificaat voor een hybride Exchange-Server

Voor de extern gerichte Exchange-Server of-servers is een extern SSL-certificaat vereist voor een beveiligde verbinding met de Exchange Online-service. U moet dit certificaat aanvragen bij uw externe SSL-provider.
  
## <a name="microsoft-365-certificate-chains"></a>Certificaatketens van Microsoft 365

In dit artikel worden de certificaten beschreven die u mogelijk op de infrastructuur moet installeren. Zie [Microsoft 365 certificate chains](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)voor meer informatie over de certificaten die zijn geïnstalleerd op onze microsoft 365-servers.
  
## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
